---
title: Rad s podacima rješenja Customer Insights u servisu Microsoft Dataverse
description: Saznajte kako povezati Customer Insights i Microsoft Dataverse razumjeti izlazne entitete koji se izvoze u Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9433c411a2c7eb0db137c6392578993d47be82a2
ms.sourcegitcommit: 8559ca47a22d1d7cd9be13531c2eaf0c1083942b
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/12/2022
ms.locfileid: "9671242"
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

> [!NOTE]
> Dijeljenje podataka primjenjivo je samo ako koristite vlastiti Azure Data Lake Storage račun. Ova postavka nije dostupna ako okruženje Customer Insights koristi zadanu Dataverse pohranu.

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
   > Stvaranje sigurnosne grupe može se onemogućiti na klijentu. U tom bi slučaju bilo potrebno ručno postavljanje i vaš Azure AD bi administrator morao [omogućiti stvaranje sigurnosne grupe](/azure/active-directory/enterprise-users/groups-self-service-management).

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
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obogaćivanje](#enrichment)
- [Predviđanje](#prediction)
- [Članstvo u segmentu](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Ova tablica sadrži objedinjeni profil klijenta iz rješenja Customer Insights. Shema za jedinstveni profil klijenta ovisi o entitetima i atributima koji se koriste u procesu objedinjavanja podataka. Shema profila klijenta obično sadrži podskup atributa iz [definicije Common Data Model tablice CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Za scenarij od B do B profil kupca sadrži jedinstvene račune, a shema obično sadrži podskup atributa iz [definicije zajedničkog podatkovnog modela računa](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

ContactProfile sadrži jedinstvene informacije o kontaktu. Kontakti su [pojedinci koji su mapirani na račun](data-unification-contacts.md) u scenariju B-do-B.

| Column                       | Tip                | Opis     |
| ---------------------------- | ------------------- | --------------- |
|  Datum Rođenja            | DatumVrijeme       |  Datum rođenja kontakta               |
|  Grad                 | SMS |  Grad kontakt adrese               |
|  ID kontakta            | SMS |  ID profila kontakta               |
|  ContactProfileId     | Jedinstveni identifikator   |  GUID kontakta               |
|  CountryOrRegion      | SMS |  Država/regija adrese kontakta               |
|  CustomerId           | SMS |  ID poslovnog subjekta na koji je kontakt mapiran               |
|  EntityName           | SMS |  Entitet iz kojeg dolaze podaci                |
|  FirstName            | SMS |  Ime kontakta               |
|  Rod               | SMS |  Spol kontakta               |
|  Id                   | SMS |  Deterministički GUID temeljen na`Identifier`               |
|  Identifier           | SMS |  Interni ID profila kontakta: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | SMS |  Naziv radnog mjesta kontakta               |
|  LastName             | SMS |  Prezime kontakta               |
|  PostalCode           | SMS |  Poštanski broj adrese kontakta               |
|  PrimaryEmail         | SMS |  Adresa e-pošte kontakta               |
|  Primarni telefon         | SMS |  Telefonski broj kontakta               |
|  Savezna država ili pokrajina      | SMS |  Država ili pokrajina adrese kontakta               |
|  StreetAddress        | SMS |  Ulica kontakt adrese               |

### <a name="alternatekey"></a>AlternateKey

Tablica AlternateKey sadrži ključeve entiteta koji su sudjelovali u procesu objedinjavanja.

|Column  |Tip  |Opis  |
|---------|---------|---------|
|DataSourceName    |SMS         | Naziv izvora podataka. Na primjer: `datasource5`.        |
|EntityName        | SMS        | Naziv entiteta u odjeljku Uvidi kupaca. Na primjer: `contact1`.        |
|AlternateValue    |SMS         |Alternativni ID koji se preslikava na ID klijenta. Primjer: `cntid_1078`         |
|KeyRing           | SMS        | Vrijednost JSON  </br> Uzorak: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | SMS        | ID objedinjenog profila klijenta.         |
|AlternateKeyId     | Jedinstveni identifikator        |  AlternateKey deterministički GUID temeljen na`Identifier`      |
|Identifier |   SMS      |   `DataSourceName|EntityName|AlternateValue`  </br> Uzorak: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Ova tablica sadrži aktivnosti korisnika koje su dostupne u rješenju Customer Insights.

| Column            | Tip        | Opis                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | SMS      | ID profila klijenta                                                                      |
| ActivityId        | SMS      | Interni ID aktivnosti klijenta (primarni ključ)                                       |
| SourceEntityName  | SMS      | Naziv izvornog entiteta                                                                |
| SourceActivityId  | SMS      | Primarni ključ iz izvornog entiteta                                                       |
| ActivityType      | SMS      | Vrsta semantičke aktivnosti ili naziv prilagođene aktivnosti                                        |
| ActivityTimeStamp | DatumVrijeme    | Vremenska oznaka aktivnosti                                                                      |
| Naziv             | SMS      | Naslov ili naziv aktivnosti                                                               |
| Opis       | SMS      | Opis aktivnosti                                                                     |
| URL               | SMS      | Veza do vanjskog URL-a specifičnog za aktivnost                                         |
| SemanticData      | SMS | Uključuje popis parova vrijednosti ključeva za polja semantičkog mapiranja specifična za vrstu aktivnosti |
| RangeIndex        | SMS      | Unix vremenska oznaka koja se koristi za sortiranje vremenske trake aktivnosti i učinkovite upite raspona |
| UnifiedActivityId   | Jedinstveni identifikator | Interni ID aktivnosti klijenta (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Ova tablica sadrži izlazne podatke mjera na temelju atributa klijenata.

| Column             | Tip             | Opis                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | SMS           | ID profila klijenta        |
| Mjerila           | SMS      | Uključuje popis parova vrijednosti ključeva za naziv mjere i vrijednosti za datog klijenta |
| Identifier | SMS           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Jedinstveni identifikator     | ID profila klijenta |

### <a name="enrichment"></a>Obogaćivanje

Ova tablica sadrži rezultate postupka obogaćivanja.

| Column               | Tip             |  Opis                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | SMS           | ID profila klijenta                                 |
| EnrichmentProvider   | SMS           | Naziv davatelja za obogaćivanje                                  |
| EnrichmentType       | SMS           | Vrsta obogaćivanja                                      |
| Vrijednosti               | SMS      | Popis atributa dobivenih postupkom obogaćivanja |
| ID obogaćivanja | Jedinstveni identifikator            | Deterministički GUID generiran iz`Identifier` |
| Identifier   | SMS           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predviđanje

Ova tablica sadrži rezultate predviđanja modela.

| Column               | Tip        | Opis                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | SMS      | ID profila klijenta                                  |
| ModelProvider        | SMS      | Naziv davatelja modela                                      |
| Model                | SMS      | Naziv modela                                                |
| Vrijednosti               | SMS | Popis atributa koje stvara model |
| ID predviđanja | Jedinstveni identifikator       | Deterministički GUID generiran iz`Identifier` |
| Identifier   | SMS      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Članstvo u segmentu

Ova tablica sadrži podatke o članstvu u segmentima profila kupaca.

| Column        | Tip | Opis                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | SMS       | ID profila klijenta        |
| SegmentProvider      | SMS       | Aplikacija koja objavljuje segmente.      |
| SegmentMembershipType | SMS       | Vrsta klijenta za ovaj zapis članstva u segmentu. Podržava više vrsta kao što su Klijent, Kontakt ili Poslovni subjekt. Zadano: kupac  |
| Segmenti       | SMS  | Popis jedinstvenih segmenata čiji je profil kupca član      |
| Identifier  | SMS   | Jedinstveni identifikator zapisa članstva u segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Jedinstveni identifikator      | Deterministički GUID generiran iz`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
