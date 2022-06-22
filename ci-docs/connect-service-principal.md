---
title: Spajanje na Azure Data Lake Storage račun upotrebom upravitelja usluge
description: Upotrijebite upravitelja usluge Azure da biste se spojili na vlastito jezero podataka.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 36ad957f59b23df6ee83d9d90898ef03ddfd320a
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011832"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Spajanje na Azure Data Lake Storage račun upotrebom upravitelja usluge Azure

U ovom se članku opisuje kako se povezati Dynamics 365 Customer Insights s računom Azure Data Lake Storage pomoću glavnog programa servisa Azure umjesto ključeva računa za pohranu.

Automatizirani alati koji koriste servise Azure uvijek bi trebali imati ograničene dozvole. Umjesto da se aplikacije prijavljuju kao potpuno privilegirani korisnik, Azure nudi upravitelje servisa. Upravitelje usluga možete koristiti za sigurno [dodavanje ili uređivanje mape Uobičajeni podatkovni model kao izvor podataka](connect-common-data-model.md) ili [stvaranje ili ažuriranje okruženja](create-environment.md).

> [!IMPORTANT]
>
> - Račun za pohranu na servisu Data Lake koji će koristiti glavnicu usluge mora biti Gen2 i mora imati [omogućen hijerarhijski prostora za naziv](/azure/storage/blobs/data-lake-storage-namespace). Računi za pohranu servisa Azure Data Lake Gen1 nisu podržani.
> - Potrebne su vam administratorske dozvole za klijent platforme Azure da biste stvorili upravitelja usluge.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Izrada upravitelja usluge Azure za uslugu Customer Insights

Prije stvaranja novog upravitelja usluge za Customer Insights provjerite postoji li već u vašoj tvrtki ili ustanovi.

### <a name="look-for-an-existing-service-principal"></a>Traženje postojećeg upravitelja servisa

1. Idite na [administracijski portal za Azure](https://portal.azure.com) i prijavite se u svoju organizaciju.

2. Pod **Usluge Azure** odaberite **Azure Active Directory**.

3. U odjeljku **Upravljanje** odaberite **Microsoftova aplikacija**.

4. Dodajte filtar za **ID aplikacije, započnite s**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` nazivom `Dynamics 365 AI for Customer Insights` ili ga potražite u njemu.

5. Ako pronađete zapis koji se podudara, to znači da upravitelj usluge već postoji.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snimka zaslona na kojoj je prikazan postojeći upravitelj usluge.":::

6. Ako se ne vrate rezultati, možete [kreirati novu glavnu ulogu](#create-a-new-service-principal) servisa. U većini slučajeva već postoji i samo trebate dati dozvole za ravnatelja usluge za pristup računu za pohranu.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Dodjela dozvola za pristup računu za pohranu upravitelju usluge

Idite na portal servisa Azure da biste upravitelju servisa dodijelili dozvole za račun za pohranu koji želite koristiti u odjeljku Customer Insights. Računu za pohranu ili spremniku mora se dodijeliti jedna od sljedećih uloga:

|Vjerodajnica|Preduvjeti|
|----------|------------|
|Trenutno prijavljeni u korisniku|**Uloga**: pohrana blob data Čitatelj, Storage Blob suradnik ili Storage Blob Owner.<br>**Razina**: Dozvole se mogu dodijeliti na računu za pohranu ili spremniku.</br>|
|Voditelj usluge uvida u kupce -<br>Korištenje Azure Data Lake Storage kao izvor podataka</br>|Mogućnost 1<ul><li>**Uloga**: pohrana Blob Data Čitatelj, Storage Blob Data suradnik ili Storage Blob Data Owner.</li><li>**Razina**: dozvole treba izdavati na računu za pohranu.</li></ul>Opcija 2 *(bez dijeljenja pristupa servisnog nalogodavca računu za pohranu)*<ul><li>**Uloga 1**: Pohrana Blob Data Čitatelj, Storage Blob Data suradnik ili Storage Blob Data Owner.</li><li>**Razina**: Dozvole se trebaju izdavati na spremniku.</li><li>**Uloga 2**: Delegator podataka o blobu pohrani.</li><li>**Razina**: dozvole treba izdavati na računu za pohranu.</li></ul>|
|Voditelj usluge uvida u kupce - <br>Korištenje Azure Data Lake Storage kao izlaza ili odredišta</br>|Mogućnost 1<ul><li>**Uloga**: Pohrana Blob Data suradnik ili Storage Blob Owner.</li><li>**Razina**: dozvole treba izdavati na računu za pohranu.</li></ul>Opcija 2 *(bez dijeljenja pristupa servisnog nalogodavca računu za pohranu)*<ul><li>**Uloga**: Pohrana Blob Data suradnik ili Storage Blob Owner.</li><li>**Razina**: Dozvole se trebaju izdavati na spremniku.</li><li>**Uloga 2**: Delegator bloba za pohranu.</li><li>**Razina**: dozvole treba izdavati na računu za pohranu.</li></ul>|

1. Idite na [administracijski portal za Azure](https://portal.azure.com) i prijavite se u svoju organizaciju.

1. Otvorite račun za pohranu kojem želite da upravitelj usluge za Customer Insights ima pristup.

1. U lijevom oknu odaberite **Kontrola pristupa (IAM)**, a zatim **Dodaj** > **Dodaj dodjelu uloge**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snimka zaslona na kojoj je prikazan Azure portal u trenutku dodavanja dodjele uloge.":::

1. U oknu **Dodaj dodjelu uloge** postavite sljedeća svojstva:
   - Uloga: pohrana Blob Data Čitatelj, Storage Blob suradnik ili Storage Blob Owner na temelju gore navedenih vjerodajnica.
   - Dodijelite pristup: **Korisnik, grupa ili upravitelj servisa**
   - Odabir članova: **Dynamics 365 AI for Customer Insights** (upravitelj [servisa kojeg](#create-a-new-service-principal) ste potražili ranije u ovom postupku)

1. Odaberite **Pregled + dodjela**.

Provedba izmjena može potrajati i do 15 minuta.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Unesite ID resursa servisa Azure ili podatke o pretplati na Azure u privitak računa za pohranu u Customer Insights

Račun za pohranu na servisu Data Lake možete priložiti u customer insightsu da biste pohranili [izlazne podatke](manage-environments.md) ili [ih koristili kao izvor podataka](connect-dataverse-managed-lake.md). Ta vam opcija omogućuje odabir između pristupa koji se temelji na resursu ili na temelju pretplate. Ovisno o pristupu koji odaberete, slijedite postupak u jednom od sljedećih odjeljaka.

### <a name="resource-based-storage-account-connection"></a>Veza računa pohrane temeljena na resursima

1. Idite na [Azure administrativni portal](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite račun za pohranu.

1. U lijevom oknu otvorite **Krajnje točke postavki** > **·**.

1. Kopirajte vrijednost ID-a resursa računa za pohranu.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopirajte ID resursa računa za pohranu.":::

1. U odjeljku Customer Insights umetnite ID resursa u polje resursa prikazano na zaslonu za povezivanje računa za pohranu.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Unesite podatke ID-a resursa računa za pohranu.":::   

1. Nastavite s preostalim koracima u odjeljku Customer Insights da biste priložili račun za pohranu.

### <a name="subscription-based-storage-account-connection"></a>Veza računa utemeljena na pretplati

1. Idite na [Azure administrativni portal](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite račun za pohranu.

1. U lijevom oknu idite na **Postavke** > **Svojstva**.

1. Pregledajte pretplatu, grupu **resursa** i naziv **računa za pohranu da biste bili sigurni da odaberete prave vrijednosti u odjeljku Customer Insights.** **·**

1. U odjeljku Customer Insights odaberite vrijednosti za odgovarajuća polja prilikom prilaganja računa za pohranu.

1. Nastavite s preostalim koracima u odjeljku Customer Insights da biste priložili račun za pohranu.

### <a name="create-a-new-service-principal"></a>Stvaranje novog upravitelja servisa

1. Instalirajte najnoviju verziju modula PowerShell for Graph za Azure Active Directory. Više informacija potražite u članku [Instaliranje modula PowerShell for Graph za Azure Active Directory](/powershell/azure/active-directory/install-adv2).

   1. Na PC-ju pritisnite tipku Windows na tipkovnici i potražite **Windows PowerShell**, a zatim odaberite **Pokreni kao administrator**.

   1. U prozoru PowerShell koji se otvori unesite `Install-Module AzureAD`.

2. Izradite upravitelja usluge za Customer Insights pomoću modula Azure AD PowerShell.

   1. U prozoru PowerShell unesite `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Zamijenite *[svoj ID direktorija]* stvarnim ID-om direktorija pretplate na Azure gdje želite stvoriti glavnicu usluge. Parametar naziva okruženja `AzureEnvironmentName` nije obavezan.
  
   1. Unesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ova naredba stvara glavni servisni program za Customer Insights na odabranoj pretplati na Azure.

[!INCLUDE [footer-include](includes/footer-banner.md)]
