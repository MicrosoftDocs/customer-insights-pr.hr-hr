---
title: Rad s podacima rješenja Customer Insights u servisu Microsoft Dataverse
description: Saznajte kako povezati Customer Insights i Microsoft Dataverse razumjeti izlazne entitete koji se izvoze u Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833667"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Rad s podacima rješenja Customer Insights u servisu Microsoft Dataverse

Customer Insights pruža mogućnost da izlazne entitete učinite dostupnima kao [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ova integracija omogućuje jednostavnu razmjenu podataka i prilagođeni razvoj kroz pristup koda niskog koda / bez koda. Izlazni [entiteti](#output-entities) dostupni su kao tablice u Dataverse okruženju. Podatke možete koristiti za bilo koju drugu aplikaciju na Dataverse temelju tablica. Ove tablice omogućavaju scenarije kao što su automatizirani tijekovi rada kroz Power Automate ili izrada aplikacija pomoću programa Power Apps.

Povezivanje s okolinom Dataverse također vam omogućuje unos [podataka iz lokalno izvora podataka pomoću Power Platform tokova podataka i pristupnika](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Preduvjeti

- Uvidi u kupce i Dataverse okruženja moraju biti smješteni u istoj regiji.
- Morate imati globalnu administratorsku ulogu u Dataverse okruženju. Provjerite je li ovo [Dataverse okruženje povezano](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) s određenim sigurnosnim grupama i provjerite jeste li dodani u te sigurnosne grupe.
- Nijedno drugo okruženje Customer Insights već nije povezano s okruženjem Dataverse koje želite povezati. Saznajte kako [ukloniti postojeću vezu s okruženjem Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Okruženje Microsoft Dataverse se može povezati samo s jednim računom za pohranu. Primjenjuje se samo ako konfigurirate okruženje za [korištenje sustava Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Povezivanje okruženja s Dataverse uvidima kupaca

Korak **Microsoft Dataverse** vam omogućuje povezivanje uvida u korisnike s okolinom Dataverse tijekom [stvaranja okruženja](create-environment.md) Customer Insights.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="zajedničko korištenje podataka s omogućenim Microsoft Dataverse automatskim omogućivanjem za nova mrežna okruženja.":::

Administratori mogu konfigurirati Customer Insights za povezivanje postojećeg Dataverse okruženja. Pružanjem URL-a okolišu Dataverse pridaje se njihovom novom okruženju Customer Insights.

Ako ne želite koristiti postojeće Dataverse okruženje, sustav stvara novo okruženje za podatke Customer Insights u vašem klijentu. [Power Platform administratori mogu kontrolirati tko može stvarati okruženja](/power-platform/admin/control-environment-creation). Kada postavljate novo okruženje customer insights, a administrator onemogući stvaranje okruženja Dataverse za sve osim za administratore, možda nećete moći stvoriti novo okruženje.

**Omogućite zajedničko korištenje** podataka pomoću Dataverse pomoću potvrdnog okvira za zajedničko korištenje podataka.

Ako koristite vlastiti račun za pohranu na jezeru podataka, potreban vam je **i identifikator** Dozvole. Dodatne informacije o dobivanju identifikatora dozvole potražite u sljedećem odjeljku.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Omogućivanje zajedničkog korištenja podataka s Dataverse vlastitim Azure Data Lake Storage (pretpregled)

Omogućavanje dijeljenja podataka kada Microsoft Dataverse vaše okruženje [koristi vlastiti Azure Data Lake Storage račun](own-data-lake-storage.md) treba dodatnu konfiguraciju. Korisnik koji postavlja okruženje Customer Insights mora imati barem **dozvole za pohranu Blob Data Čitatelj** u *spremniku* CustomerInsights Azure Data Lake Storage na računu.

1. Stvorite dvije sigurnosne grupe na pretplati na Azure – jednu **Čitatelj** sigurnosnu grupu i jednu **suradnik** sigurnosnu grupu Microsoft Dataverse te postavite uslugu kao vlasnika za obje sigurnosne grupe.
2. Upravljajte popisom kontrole pristupa (ACL) u spremniku CustomerInsights na računu za pohranu putem tih sigurnosnih grupa. Microsoft Dataverse Dodajte servis i sve Dataverse poslovne aplikacije temeljene na sustavu Dynamics 365 Marketing u sigurnosnu grupu **Čitatelj** s **dozvolama samo** za čitanje. Dodajte *samo* aplikaciju Customer Insights u sigurnosnu grupu **suradnik** da biste dodijelili **dozvole za čitanje i pisanje** profila i uvida.

### <a name="limitations"></a>Ograničenja

Postoje dva ograničenja pri korištenju Dataverse s vlastitim Azure Data Lake Storage računom:

- Postoji mapiranje jedan-na-jedan između Dataverse organizacije i Azure Data Lake Storage računa. Dataverse Nakon što se tvrtka ili ustanova poveže s računom za pohranu, ne može se povezati s drugim računom za pohranu. Ovo ograničenje onemogućuje da ne popunjava Dataverse više računa za pohranu.
- Zajedničko korištenje podataka neće funkcionirati ako je za pristup računu za pohranu servisa Azure Data Lake potreban instalacijski program servisa Azure Private Link jer se nalazi iza vatrozida. Dataverse trenutno ne podržava vezu s privatnim krajnjim točkama putem Private Linka.

### <a name="set-up-powershell"></a>Postavljanje ljuske PowerShell

Da biste izvršili skripte komponente PowerShell, najprije morate postaviti PowerShell u skladu s tim.

1. Instalirajte najnoviju verziju ljuske [Azure Active Directory PowerShell za grafikon](/powershell/azure/active-directory/install-adv2).
   1. Na računalu pritisnite tipku Windows na tipkovnici, potražite **Windows PowerShell** i odaberite **Pokreni kao administrator**.
   1. U prozoru PowerShell koji se otvori unesite `Install-Module AzureAD`.
2. Uvezite tri modula.
    1. U prozoru ljuske PowerShell unesite `Install-Module -Name Az.Accounts` korake i slijedite ih.
    1. Ponovite za `Install-Module -Name Az.Resources` i `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Koraci konfiguriranja

1. Preuzmite dvije PowerShell skripte koje su vam potrebne za pokretanje iz GitHub repo našeg [inženjera](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Za pokretanje ove skripte komponente PowerShell potrebne su vam *administratorske* dozvole klijenta.
       - Ova skripta komponente PowerShell stvara dvije sigurnosne grupe u pretplati na Azure. Jedan za Čitatelj grupu, a drugi za suradnik grupu i pružit Microsoft Dataverse će uslugu kao vlasnik za obje ove sigurnosne grupe.
       - Izvršite ovu powershell skriptu u komponenti Windows PowerShell pružanjem ID-ja pretplate na Azure koji sadrži vaš Azure Data Lake Storage. Otvorite skriptu komponente PowerShell u uređivaču da biste pregledali dodatne informacije i implementiranu logiku.
       - Spremite obje vrijednosti ID-a sigurnosne grupe generirane ovom skriptom jer ćemo ih koristiti u skripti `ByolSetup.ps1`.

        > [!NOTE]
        > Stvaranje sigurnosne grupe može se onemogućiti na klijentu. U tom bi slučaju bilo potrebno ručno postavljanje i vaš Azure AD bi administrator morao [omogućiti stvaranje](/azure/active-directory/enterprise-users/groups-self-service-management) sigurnosne grupe.

    2. `ByolSetup.ps1`
        - Za pokretanje ove skripte potrebne su vam *dozvole vlasnika* blob podataka za pohranu na razini računa/spremnika za pohranu ili će vam je ova skripta stvoriti. Dodjela uloge može se ukloniti ručno nakon uspješnog pokretanja skripte.
        - Ova skripta ljuske PowerShell dodaje potrebnu kontrolu pristupa temeljenu na toleu (RBAC) za uslugu Microsoft Dataverse i sve Dataverse poslovne aplikacije koje se temelje na njima. Također ažurira Popis kontrole pristupa (ACL) u spremniku CustomerInsights za sigurnosne grupe stvorene skriptom `CreateSecurityGroups.ps1`. Grupa suradnik imat *će rwx* dozvolu, a grupa Readers imat *će samo r-x* dozvolu.
        - Izvršite ovu skriptu komponente PowerShell u komponenti Windows PowerShell tako da navedete ID pretplate na Azure koji sadrži naziv računa Azure Data Lake Storage za pohranu, naziv grupe resursa te vrijednosti ID-a sigurnosne grupe Čitatelj i suradnik. Otvorite skriptu komponente PowerShell u uređivaču da biste pregledali dodatne informacije i implementiranu logiku.
        - Kopirajte izlazni niz nakon uspješnog pokretanja skripte. Izlazni niz izgleda ovako: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Unesite izlazni niz kopiran odozgo u **polje identifikatora** dozvola koraka konfiguracije okruženja za Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Mogućnosti konfiguracije za omogućavanje zajedničkog korištenja podataka s vlastitog Azure Data Lake Storage pomoću programa Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Uklanjanje postojeće veze s okruženjem Dataverse

Kada se povezujete s okruženjem Dataverse, poruka **o pogrešci Ova cds organizacija već je priložena drugoj instanci** Customer Insights znači da Dataverse se okruženje već koristi u okruženju Customer Insights. Postojeću vezu možete ukloniti kao globalni administrator u Dataverse okruženju. Može potrajati nekoliko sati da se popune promjene.

1. Idite na [Power Apps](https://make.powerapps.com).
1. Odaberite okruženje iz birača okruženja.
1. Idi na **rješenja**
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
| SegmentMembershipType | String       | Upišite zapis članstva u ovom segmentu kupca. Podržava više vrsta kao što su Klijent, Kontakt ili Poslovni subjekt. Zadano: kupac  |
| Segmenti       | Niz JSON  | Popis jedinstvenih segmenata čiji je profil kupca član      |
| msdynci_identifier  | String   | Jedinstveni identifikator zapisa članstva u segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministički GUID generiran iz`msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
