---
title: Povezivanje se s računom za Azure Data Lake Storage Gen2 s upraviteljem servisa
description: Koristite upravitelja servisa Azure za uvide u ciljnu skupinu da biste se povezali s vlastitim data lake kada ga priključite uvidima u ciljnu skupinu.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596490"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Povezivanje na račun servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure za uvide ciljne skupine

Automatizirani alati koji koriste servise Azure uvijek bi trebali imati ograničene dozvole. Umjesto da se aplikacije prijavljuju kao potpuno privilegirani korisnik, Azure nudi upravitelje servisa. Pročitajte kako biste saznali kako povezati uvide ciljne skupine s računom za Azure Data Lake Storage Gen2 koji koristi upravitelja servisa Azure umjesto ključeva računa za pohranu. 

Upravitelja servisa možete koristiti za sigurno [dodavanje ili uređivanje mape Common Data Model kao izvor podataka](connect-common-data-model.md) ili [stvaranje novog ili ažuriranje postojećeg okruženja](manage-environments.md#create-an-environment-in-an-existing-organization).

> [!IMPORTANT]
> - Račun za pohranu Azure Data Lake druge generacije koji namjerava koristiti upravitelja servisa mora imati [Hijerarhijski prostor naziva (HNS) omogućen](/azure/storage/blobs/data-lake-storage-namespace).
> - Za izradu upravitelja servisa trebaju vam administratorske dozvole za vašu pretplatu na Azure.

## <a name="create-azure-service-principal-for-audience-insights"></a>Stvaranje upravitelja servisa Azure za uvide ciljne skupine

Prije stvaranja novog upravitelja usluge za uvide ciljne skupine provjerite postoji li već u vašoj organizaciji.

### <a name="look-for-an-existing-service-principal"></a>Traženje postojećeg upravitelja servisa

1. Idite na [administracijski portal za Azure](https://portal.azure.com) i prijavite se u svoju organizaciju.

2. Među servisima Azure odaberite **Azure Active Directory**.

3. Pod stavkom **Upravljanje** odaberite **Enterprise Applications**.

4. Potražite ID aplikacije prve strane `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` za uvide ciljne skupine ili naziv `Dynamics 365 AI for Customer Insights`.

5. Ako pronađete odgovarajući zapis, to znači da postoji upravitelj servisa za uvide ciljne skupine. Ne morate ga ponovno stvoriti.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snimka zaslona na kojoj se prikazuje postojeći upravitelj servisa.":::
   
6. Ako se ne dobiju rezultati, stvorite novog upravitelja servisa.

### <a name="create-a-new-service-principal"></a>Stvaranje novog upravitelja servisa

1. Instalirajte najnoviju verziju **Azure Active Directory PowerShell za graf**. Za više informacija pogledajte [Instalacija Azure Active Directory PowerShell za graf](/powershell/azure/active-directory/install-adv2).
   - Na računalu na tipkovnici odaberite tipku Windows pa potražite **Windows PowerShell** i **Pokreni kao administrator**.
   
   - U prozoru PowerShell koji se otvori unesite `Install-Module AzureAD`.

2. Stvorite upravitelja servisa za uvide ciljne skupine s Azure AD PowerShell modulom.
   - U prozoru PowerShell unesite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Zamijenite "your tenant ID" stvarnim ID-om svog klijenta na kojem želite stvoriti upravitelja servisa. Parametar naziva okruženja `AzureEnvironmentName` nije obvezan.
  
   - Unesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ova naredba stvara upravitelja usluge za uvide ciljne skupne na odabranom klijentu.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Dodjela dozvola za pristup računu za pohranu upravitelju usluge

Idite na Azure portal kako biste dodijelili dozvole upravitelju serviss za račun pohrane koji želite koristiti u uvidima ciljne skupine.

1. Idite na [administracijski portal za Azure](https://portal.azure.com) i prijavite se u svoju organizaciju.

1. Otvorite račun za pohranu kojem želite da ima pristup upravitelj servisa za uvide ciljne skupine.

1. Odaberite **Kontrola pristupa (IAM)** u navigacijskom oknu pa odaberite **Dodaj** > **Dodaj dodjelu uloge**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snimka zaslona na kojoj se prikazuje Azure portal tijekom dodavanja dodjele uloge.":::
   
1. U oknu **Dodavanje dodjele uloge** postavite sljedeća svojstva:
   - Uloga: *Suradnik spremišta podataka za blob*
   - Dodijelite pristup: *Korisnik, grupa ili upravitelj servisa*
   - Odaberite: *Dynamics 365 AI za Customer Insights* ([upravitelja servisa kojeg ste stvorili](#create-a-new-service-principal))

1.  Odaberite **Spremi**.

Provedba izmjena može potrajati i do 15 minuta.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Unesite ID Azure resursa ili pojedinosti o pretplati na Azure u prilogu računa za pohranu servisa Audience Insights.

Priložite račun za Azure Data Lake Storage u uvide ciljne skupine radi [pohrane izlaznih podataka](manage-environments.md) ili [za upotrebu kao izvora podataka](connect-common-data-service-lake.md). Odabirom opcije Azure Data Lake omogućuje vam se odabir između pristupa temeljenog na resursima ili na pretplati.

Slijedite korake u nastavku kako biste pružili potrebne informacije o odabranom pristupu.

### <a name="resource-based-storage-account-connection"></a>Veza računa pohrane temeljena na resursima

1. Idite na [Azure administrativni portal](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite račun za pohranu.

1. Idite na **Postavke** > **Svojstva** na navigacijskom oknu.

1. Kopirajte vrijednost ID-a resursa računa za pohranu.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopirajte ID resursa računa za pohranu.":::

1. U uvidima ciljne skupine umetnite ID resursa u polje resursa prikazano na zaslonu veze računa za pohranu.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Unesite podatke ID-a resursa računa za pohranu.":::   
   
1. Nastavite s preostalim koracima u uvidima ciljne skupine da biste priložili račun za pohranu.

### <a name="subscription-based-storage-account-connection"></a>Veza računa utemeljena na pretplati

1. Idite na [Azure administrativni portal](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite račun za pohranu.

1. Idite na **Postavke** > **Svojstva** na navigacijskom oknu.

1. Pregledajte **Pretplatu**, **Grupu resursa** i **Naziv** računa za pohranu kako biste bili sigurni da ste odabrali prave vrijednosti u uvidima ciljne skupine.

1. U uvidima ciljne skupine odaberite vrijednosti ili za odgovarajuća polja prilikom prilaganja računa za pohranu.
   
1. Nastavite s preostalim koracima u uvidima ciljne skupine da biste priložili račun za pohranu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]