---
title: Rad s podacima rješenja Customer Insights u servisu Microsoft Dataverse
description: Saznajte kako povezati Customer Insights i Microsoft Dataverse razumjeti izlazne entitete koji se izvoze u Dataverse.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303820"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Rad s podacima rješenja Customer Insights u servisu Microsoft Dataverse

Customer Insights pruža mogućnost omogućivanja izlaznih entiteta u servisu [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ova integracija omogućuje jednostavnu razmjenu podataka i prilagođeni razvoj kroz pristup koda niskog koda / bez koda. Izlazni [entiteti](#output-entities) dostupni su kao tablice u Dataverse okruženju. Podatke možete koristiti za bilo koju drugu aplikaciju na Dataverse temelju tablica. Ove tablice omogućavaju scenarije kao što su automatizirani tijekovi rada kroz Power Automate ili izrada aplikacija pomoću programa Power Apps.

Povezivanje s okolinom Dataverse također vam omogućuje unos [podataka iz lokalno izvora podataka pomoću Power Platform tokova podataka i pristupnika](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Preduvjeti

- Uvidi u kupce i Dataverse okruženja moraju biti smješteni u istoj regiji.
- Uloga globalnog administratora postavljena Dataverse u okruženju. Provjerite je li ovo [Dataverse okruženje povezano](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) s određenim sigurnosnim grupama i provjerite jeste li dodani u te sigurnosne grupe.
- Nijedno drugo okruženje Customer Insights već nije povezano s okruženjem Dataverse koje želite povezati. Saznajte kako [ukloniti postojeću vezu s okruženjem Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Okruženje Microsoft Dataverse povezano s jednim računom za pohranu ako konfigurirate okruženje za [korištenje sustava Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse pravo na kapacitet pohrane

Pretplata na Customer Insights daje vam pravo na dodatni kapacitet za postojeći [Dataverse kapacitet](/power-platform/admin/capacity-storage) pohrane vaše tvrtke ili ustanove. Dodani kapacitet ovisi o broju profila koje vaša pretplata koristi.

**Primjer:**

Pod pretpostavkom da ćete dobiti pohranu baze podataka od 15 GB i pohranu datoteka od 20 GB na 100.000 korisničkih profila. Ako vaša pretplata uključuje 300 000 korisničkih profila, vaš ukupni kapacitet pohrane je 45 GB (3 x 15 GB) za pohranu baze podataka i 60 GB prostora za pohranu datoteka (3 x 20 GB). Slično tome, ako imate pretplatu od B do B s 30K računima, vaš ukupni kapacitet pohrane je 45 GB (3 x 15 GB) pohrane baze podataka i pohrana datoteka od 60 GB (3 x 20 GB).

Kapacitet zapisnika nije inkrementalan i fiksiran za vašu tvrtku ili ustanovu.

Dodatne informacije o detaljnim pravima na kapacitet potražite u članku [Vodič za](https://go.microsoft.com/fwlink/?LinkId=866544) licenciranje sustava Dynamics 365.

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Povezivanje okruženja s Dataverse uvidima kupaca

Korak **Microsoft Dataverse** vam omogućuje povezivanje uvida u korisnike s okolinom Dataverse tijekom [stvaranja okruženja](create-environment.md) Customer Insights.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="zajedničko korištenje podataka s automatski omogućenim Microsoft Dataverse za nova okruženja.":::

1. Navedite URL svom Dataverse okruženju ili ostavite prazno da biste ga stvorili.

   > [!NOTE]
   > Nakon uspostavljanja veze između customer insights i Dataverse, nemojte mijenjati naziv tvrtke ili ustanove za Dataverse okoliš. Naziv organizacije koristi se u URL-u Dataverse, a promijenjeni naziv prekida vezu s Customer Insights.

   [Power Platform administratori mogu kontrolirati tko može stvoriti nova Dataverse okruženja](/power-platform/admin/control-environment-creation). Ako pokušavate postaviti novo okruženje customer insights, a ne možete, administrator je možda onemogućio stvaranje okruženja Dataverse za sve osim za administratore.

1. Ako koristite vlastiti račun za pohranu podataka na jezeru:
   1. Izaberite stavku **Omogući zajedničko korištenje** podataka pomoću programa Dataverse.
   1. **Unesite identifikator Dozvola**. Da biste dobili identifikator dozvole, [omogućite zajedničko korištenje podataka s Dataverse vlastitim Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Omogućivanje zajedničkog korištenja podataka s Dataverse vlastitim Azure Data Lake Storage (pretpregled)

Na [vlastitom Azure Data Lake Storage računu](own-data-lake-storage.md) provjerite ima li korisnik koji postavlja okruženje Customer Insights barem **storage Blob Data Čitatelj** dozvole za spremnik na `customerinsights` računu za pohranu.

### <a name="limitations"></a>Ograničenja

- Samo jedan-na-jedan mapiranje Dataverse između organizacije i Azure Data Lake Storage računa. Dataverse Nakon što se tvrtka ili ustanova poveže s računom za pohranu, ne može se povezati s drugim računom za pohranu. Ovo ograničenje onemogućuje popunjavanje Dataverse više računa za pohranu.
- Zajedničko korištenje podataka neće funkcionirati ako je za pristup računu Azure Data Lake Storage potrebna postava servisa Azure Private Link jer se nalazi iza vatrozida. Dataverse trenutno ne podržava vezu s privatnim krajnjim točkama putem Private Linka.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Samostalno postavljanje sigurnosnih grupa Azure Data Lake Storage

1. Stvorite dvije sigurnosne grupe na pretplati na Azure – jednu **Čitatelj** sigurnosnu grupu i jednu **suradnik** sigurnosnu grupu Microsoft Dataverse te postavite uslugu kao vlasnika za obje sigurnosne grupe.

1. Upravljajte popisom kontrole pristupa (ACL) u spremniku `customerinsights` na računu za pohranu putem tih sigurnosnih grupa.
   1. Microsoft Dataverse Dodajte servis i sve Dataverse poslovne aplikacije temeljene na sustavu Dynamics 365 Marketing u sigurnosnu grupu **Čitatelj** s **dozvolama samo** za čitanje.
   1. Dodajte *samo* aplikaciju Customer Insights u sigurnosnu grupu **suradnik** da biste dodijelili **dozvole za čitanje i pisanje** profila i uvida.

### <a name="set-up-powershell"></a>Postavljanje ljuske PowerShell

Postavite PowerShell za izvršavanje skripti komponente PowerShell.

1. Instalirajte najnoviju verziju ljuske [Azure Active Directory PowerShell za grafikon](/powershell/azure/active-directory/install-adv2).
   1. Na računalu pritisnite tipku Windows na tipkovnici, potražite **Windows PowerShell** i odaberite **Pokreni kao administrator**.
   1. U prozoru PowerShell koji se otvori unesite `Install-Module AzureAD`.

1. Uvezite tri modula.
   1. U prozoru ljuske PowerShell unesite `Install-Module -Name Az.Accounts` korake i slijedite ih.
   1. Ponovite za `Install-Module -Name Az.Resources` i `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Izvršavanje skripti komponente PowerShell i dobivanje identifikatora dozvole

1. Preuzmite dvije PowerShell skripte koje su vam potrebne za pokretanje iz GitHub repo našeg [inženjera](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: potrebne su administratorske dozvole klijenta.
   - `ByolSetup.ps1`: zahtijeva dozvole vlasnika podataka o blobu pohrani na razini računa/spremnika za pohranu. Ova skripta će stvoriti dozvolu za vas. Dodjela uloge može se ukloniti ručno nakon uspješnog pokretanja skripte.

1. Izvršite u komponenti Windows PowerShell tako da navedete ID pretplate `CreateSecurityGroups.ps1` na Azure koji sadrži vaš Azure Data Lake Storage. Otvorite skriptu komponente PowerShell u uređivaču da biste pregledali dodatne informacije i implementiranu logiku.

   Ova skripta stvara dvije sigurnosne grupe na pretplati na Azure: jednu za grupu Čitatelj i drugu za grupu suradnik. Microsoft Dataverse usluga je vlasnik obje ove sigurnosne grupe.

1. Spremite obje vrijednosti ID-a sigurnosne grupe generirane ovom skriptom za korištenje u skripti `ByolSetup.ps1`.

   > [!NOTE]
   > Stvaranje sigurnosne grupe može se onemogućiti na klijentu. U tom bi slučaju bilo potrebno ručno postavljanje i vaš Azure AD bi administrator morao [omogućiti stvaranje](/azure/active-directory/enterprise-users/groups-self-service-management) sigurnosne grupe.

1. Izvršite u komponenti Windows PowerShell tako da navedete ID pretplate `ByolSetup.ps1` na Azure koji sadrži naziv računa Azure Data Lake Storage za pohranu, naziv grupe resursa te vrijednosti ID-a Čitatelj i suradnik sigurnosne grupe. Otvorite skriptu komponente PowerShell u uređivaču da biste pregledali dodatne informacije i implementiranu logiku.

   Ova skripta dodaje potrebnu kontrolu pristupa temeljenu na ulogama za uslugu Microsoft Dataverse i sve Dataverse poslovne aplikacije koje se temelje na ulozima. Također ažurira popis kontrole pristupa (ACL) u spremniku `customerinsights` za sigurnosne grupe stvorene skriptom `CreateSecurityGroups.ps1`. Grupa suradnik dobila *je dozvolu za rwx*, a grupi Readers dodijeljena *je samo r-x* dozvola.

1. Kopirajte izlazni niz koji izgleda kao: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Unesite kopirani izlazni niz u **polje identifikatora** dozvola koraka konfiguracije okruženja za Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Mogućnosti konfiguracije za omogućavanje zajedničkog korištenja podataka s vlastitog Azure Data Lake Storage pomoću programa Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Uklanjanje postojeće veze s okruženjem Dataverse

Kada se povezujete s okruženjem Dataverse, poruka **o pogrešci Ova cds organizacija već je priložena drugoj instanci** Customer Insights znači da Dataverse se okruženje već koristi u okruženju Customer Insights. Postojeću vezu možete ukloniti kao globalni administrator u Dataverse okruženju. Može potrajati nekoliko sati da se popune promjene.

1. Idite na [Power Apps](https://make.powerapps.com).
1. Odaberite okruženje iz birača okruženja.
1. Idite na **Rješenja**.
1. Deinstalirajte ili izbrišite rješenje pod nazivom **Dynamics 365 Customer Insights Dodatak za karticu kupca (pretpregled)**.

ILI

1. Otvorite okolinu Dataverse.
1. Otvorite Rješenja **za dodatne postavke** > **·**.
1. **Deinstalirajte rješenje CustomerInsightsCustomerCard**.

Ako uklanjanje veze ne uspije zbog ovisnosti, morate ukloniti i ovisnosti. Dodatne informacije potražite u članku [Uklanjanje ovisnosti](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Izlazni entiteti

Neki izlazni entiteti iz customer insightsa dostupni su kao tablice u programu Dataverse. Odjeljci u nastavku opisuju očekivanu shemu ovih tablica.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obogaćivanje](#enrichment)
- [Predviđanje](#prediction)
- [Članstvo u segmentu](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Ova tablica sadrži objedinjeni profil klijenta iz rješenja Customer Insights. Shema za jedinstveni profil klijenta ovisi o entitetima i atributima koji se koriste u procesu objedinjavanja podataka. Shema profila klijenta obično sadrži podskup atributa iz [definicije Common Data Model tablice CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tablica AlternateKey sadrži ključeve entiteta koji su sudjelovali u procesu objedinjavanja.

|Column  |Tip  |Opis  |
|---------|---------|---------|
|DataSourceName    |String         | Naziv izvora podataka. Na primjer: `datasource5`.        |
|EntityName        | String        | Naziv entiteta u odjeljku Uvidi kupaca. Na primjer: `contact1`.        |
|AlternateValue    |String         |Alternativni ID koji se preslikava na ID klijenta. Primjer: `cntid_1078`         |
|KeyRing           | Tekst s više redaka        | Vrijednost JSON  </br> Uzorak: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | ID objedinjenog profila klijenta.         |
|AlternateKeyId     | GUID         |  AlternateKey određuje GUID na temelju msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Uzorak: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Ova tablica sadrži aktivnosti korisnika koje su dostupne u rješenju Customer Insights.

| Column            | Tip        | Opis                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | ID profila klijenta                                                                      |
| ActivityId        | String      | Interni ID aktivnosti klijenta (primarni ključ)                                       |
| SourceEntityName  | String      | Naziv izvornog entiteta                                                                |
| SourceActivityId  | String      | Primarni ključ iz izvornog entiteta                                                       |
| ActivityType      | String      | Vrsta semantičke aktivnosti ili naziv prilagođene aktivnosti                                        |
| ActivityTimeStamp | DATETIME    | Vremenska oznaka aktivnosti                                                                      |
| Naziv             | String      | Naslov ili naziv aktivnosti                                                               |
| Opis       | String      | Opis aktivnosti                                                                     |
| URL               | String      | Veza do vanjskog URL-a specifičnog za aktivnost                                         |
| SemanticData      | Niz JSON | Uključuje popis parova vrijednosti ključeva za polja semantičkog mapiranja specifična za vrstu aktivnosti |
| RangeIndex        | String      | Unix vremenska oznaka koja se koristi za sortiranje vremenske trake aktivnosti i učinkovite upite raspona |
| mydynci_unifiedactivityid   | GUID | Interni ID aktivnosti klijenta (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Ova tablica sadrži izlazne podatke mjera na temelju atributa klijenata.

| Column             | Tip             | Opis                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | ID profila klijenta        |
| Mjerila           | Niz JSON      | Uključuje popis parova vrijednosti ključeva za naziv mjere i vrijednosti za datog klijenta | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID profila klijenta |


### <a name="enrichment"></a>Obogaćivanje

Ova tablica sadrži rezultate postupka obogaćivanja.

| Column               | Tip             |  Opis                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | ID profila klijenta                                 |
| EnrichmentProvider   | String           | Naziv davatelja za obogaćivanje                                  |
| EnrichmentType       | String           | Vrsta obogaćivanja                                      |
| Vrijednosti               | Niz JSON      | Popis atributa dobivenih postupkom obogaćivanja |
| msdynci_enrichmentid | GUID             | Deterministički GUID generiran iz msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predviđanje

Ova tablica sadrži rezultate predviđanja modela.

| Column               | Tip        | Opis                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | ID profila klijenta                                  |
| ModelProvider        | String      | Naziv davatelja modela                                      |
| Model                | String      | Naziv modela                                                |
| Vrijednosti               | Niz JSON | Popis atributa koje stvara model |
| msdynci_predictionid | GUID        | Deterministički GUID generiran iz msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Članstvo u segmentu

Ova tablica sadrži podatke o članstvu u segmentima profila kupaca.

| Column        | Tip | Opis                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ID profila klijenta        |
| SegmentProvider      | String       | Aplikacija koja objavljuje segmente.      |
| SegmentMembershipType | String       | Vrsta klijenta za ovaj zapis članstva u segmentu. Podržava više vrsta kao što su Klijent, Kontakt ili Poslovni subjekt. Zadano: kupac  |
| Segmenti       | Niz JSON  | Popis jedinstvenih segmenata čiji je profil kupca član      |
| msdynci_identifier  | String   | Jedinstveni identifikator zapisa članstva u segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministički GUID generiran iz`msdynci_identifier`          |


[!INCLUDE [footer-include](includes/footer-banner.md)]
