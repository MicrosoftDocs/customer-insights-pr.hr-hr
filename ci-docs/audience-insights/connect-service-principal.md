---
title: Spajanje na Azure Data Lake Storage račun upotrebom upravitelja usluge
description: Upotrijebite upravitelja usluge Azure da biste se spojili na vlastito jezero podataka.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1af01e5579f85d7c8bc8976a003f53ef2dd280d1
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088109"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Spajanje na Azure Data Lake Storage račun upotrebom upravitelja usluge Azure

U ovom se članku objašnjava kako se povezati Dynamics 365 Customer Insights s računom Azure Data Lake Storage pomoću upravitelja servisa Azure umjesto ključeva računa za pohranu. 

Automatizirani alati koji koriste servise Azure uvijek bi trebali imati ograničene dozvole. Umjesto da se aplikacije prijavljuju kao potpuno privilegirani korisnik, Azure nudi upravitelje servisa. Pomoću upravitelja servisa možete sigurno [dodati ili urediti mapu Zajednički podatkovni model kao izvor podataka](connect-common-data-model.md) ili [stvoriti ili ažurirati okruženje](create-environment.md).

> [!IMPORTANT]
> - Račun za pohranu jezera podataka koji će koristiti glavni servis mora biti Gen2 i imati [omogućen hijerarhijski prostor naziva](/azure/storage/blobs/data-lake-storage-namespace). Računi za pohranu na Azure Data Lake Gen1 nisu podržani.
> - Da biste stvorili glavnog servisa, potrebne su vam administratorske dozvole za pretplatu na Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Izrada upravitelja usluge Azure za uslugu Customer Insights

Prije stvaranja novog direktora servisa za Uvide u klijente provjerite postoji li već u vašoj tvrtki ili ustanovi.

### <a name="look-for-an-existing-service-principal"></a>Traženje postojećeg upravitelja servisa

1. Idite na [administracijski portal za Azure](https://portal.azure.com) i prijavite se u svoju organizaciju.

2. Pod **Usluge Azure** odaberite **Azure Active Directory**.

3. Pod stavkom **Upravljanje** odaberite **Enterprise Applications**.

4. Potražite ID Microsoftove aplikacije:
   - uvidi u ciljnu skupinu: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` s nazivom `Dynamics 365 AI for Customer Insights`
   - uvidi u angažman: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` s nazivom `Dynamics 365 AI for Customer Insights engagement insights`

5. Ako pronađete zapis koji se podudara, to znači da upravitelj usluge već postoji. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snimka zaslona na kojoj je prikazan postojeći upravitelj usluge.":::
   
6. Ako se ne dobiju rezultati, stvorite novog upravitelja servisa.

>[!NOTE]
>Kako biste u potpunosti iskoristili uslugu Dynamics 365 Customer Insights, predlažemo da obje aplikacije dodate upravitelju usluge.

### <a name="create-a-new-service-principal"></a>Stvaranje novog upravitelja servisa

1. Instalirajte najnoviju verziju modula PowerShell for Graph za Azure Active Directory. Više informacija potražite u članku [Instaliranje modula PowerShell for Graph za Azure Active Directory](/powershell/azure/active-directory/install-adv2).

   1. Na računalu pritisnite tipku Windows na tipkovnici, potražite **Windows PowerShell** i odaberite **Pokreni kao administrator**.
   
   1. U prozoru PowerShell koji se otvori unesite `Install-Module AzureAD`.

2. Izradite upravitelja usluge za Customer Insights pomoću modula Azure AD PowerShell.

   1. U prozoru PowerShell unesite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Zamijenite *[ID svojeg klijenta]* stvarnim ID-jem svojeg klijenta na kojem želite stvoriti upravitelja usluge. Parametar naziva okruženja `AzureEnvironmentName` nije obavezan.
  
   1. Unesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ova naredba stvara upravitelja usluge za uvide ciljne skupne na odabranom klijentu. 

   1. Unesite `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Ovu naredbu stvara upravitelj usluge za uvide u angažman na odabranom klijentu.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Dodjela dozvola za pristup računu za pohranu upravitelju usluge

Idite na Azure portal kako biste dodijelili dozvole upravitelju serviss za račun pohrane koji želite koristiti u uvidima ciljne skupine.

1. Idite na [administracijski portal za Azure](https://portal.azure.com) i prijavite se u svoju organizaciju.

1. Otvorite račun za pohranu kojem želite da ima pristup upravitelj servisa za uvide ciljne skupine.

1. U lijevom oknu odaberite **Kontrola pristupa (IAM)**, a zatim **Dodaj** > **Dodaj dodjelu uloge**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snimka zaslona na kojoj je prikazan Azure portal u trenutku dodavanja dodjele uloge.":::

1. U oknu **Dodaj dodjelu uloge** postavite sljedeća svojstva:
   - Uloga: **Suradnik spremišta podataka za blob**
   - Dodijelite pristup: **Korisnik, grupa ili upravitelj servisa**
   - Odaberite: **Dynamics 365 AI for Customer Insights** i **Uvidi u angažman usluge Dynamics 365 AI za Customer Insights** (dva [upravitelja usluge](#create-a-new-service-principal) koja ste izradili ranije u ovom postupku)

1.  Odaberite **Spremi**.

Provedba izmjena može potrajati i do 15 minuta.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Unesite ID Azure resursa ili pojedinosti pretplate na Azure u prilogu računa za pohranu za uvide u ciljnu skupinu

Možete priložiti račun za pohranu Data Lake u uvide u ciljnu skupinu da biste [pohranili izlazne podatke](manage-environments.md) ili ga možete [koristiti kao izvor podataka](connect-common-data-service-lake.md). Ta vam opcija omogućuje odabir između pristupa koji se temelji na resursu ili na temelju pretplate. Ovisno o pristupu koji odaberete, slijedite postupak u jednom od sljedećih odjeljaka.

### <a name="resource-based-storage-account-connection"></a>Veza računa pohrane temeljena na resursima

1. Idite na [Azure administrativni portal](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite račun za pohranu.

1. U lijevom oknu idite na **Postavke** > **Svojstva**.

1. Kopirajte vrijednost ID-a resursa računa za pohranu.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopirajte ID resursa računa za pohranu.":::

1. U uvidima u ciljnu skupinu umetnite ID resursa u polje resursa prikazano na zaslonu za povezivanje računa za pohranu.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Unesite podatke ID-a resursa računa za pohranu.":::   

1. Nastavite s preostalim koracima u uvidima ciljne skupine da biste priložili račun za pohranu.

### <a name="subscription-based-storage-account-connection"></a>Veza računa utemeljena na pretplati

1. Idite na [Azure administrativni portal](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite račun za pohranu.

1. U lijevom oknu idite na **Postavke** > **Svojstva**.

1. Pregledajte **Pretplatu**, **Grupu resursa** i **Naziv** računa za pohranu kako biste bili sigurni da ste odabrali prave vrijednosti u uvidima ciljne skupine.

1. U uvidima u ciljnu skupinu odaberite vrijednosti za odgovarajuća polja prilikom prilaganja računa za pohranu.

1. Nastavite s preostalim koracima u uvidima ciljne skupine da biste priložili račun za pohranu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
