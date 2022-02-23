---
title: Podaci Customer Insights u Microsoft Dataverse
description: Pomoću entiteta Uvidi u klijente koristite tablice u Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866925"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Rad s podacima customer insights u Microsoft Dataverse

Customer Insights pruža mogućnost da izlazne entitete učinite dostupnima u [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Ova integracija omogućuje jednostavnu razmjenu podataka i prilagođeni razvoj putem pristupa s malo kodiranja / bez kodiranja. Izlazni entiteti bit će dostupni kao tablice u Dataverse. Te tablice omogućuju scenarije kao što su [automatizirani tijekovi rada putem Power Automate](/power-automate/getting-started) aplikacija [utemeljenih na modelu](/powerapps/maker/model-driven-apps/) i aplikacija na [platnu](/powerapps/maker/canvas-apps/) putem Power Apps. Podatke možete koristiti za bilo koju drugu aplikaciju koja se temelji na Dataverse tablicama. Trenutna implementacija uglavnom podržava pretraživanja gdje se podaci iz dostupnih entiteta uvida u ciljne skupine mogu dohvatiti za zadani ID klijenta.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Prilaganje Dataverse okruženja uvidima u klijente

**Organizacije s postojećim Dataverse okruženjima**

Organizacije koje već koriste Dataverse mogu [koristiti jedno od svojih postojećih okruženja Dataverse](create-environment.md) kada administrator postavi publika uvide. Pružanjem URL-a Dataverse okruženju prilaže se njihovom novom okruženju publika uvida. Da bi se osigurale najbolje moguće performanse, Customer Insights i Dataverse okruženja moraju biti smješteni u istoj regiji.

**Nova tvrtka ili ustanova**

Ako prilikom postavljanja uvida u klijenta stvorite novu organizaciju, automatski ćete dobiti novi Dataverse okruženju.

> [!NOTE]
> Ako vaša tvrtka ili ustanova već koristi Dataverse u klijentu, važno je zapamtiti da [stvaranje Dataverse okruženja kontrolira administrator](/power-platform/admin/control-environment-creation.md) . Na primjer, ako postavljate novi publika okruženje uvida s računom tvrtke ili ustanove, a administrator je onemogućio stvaranje probnih okruženja za Dataverse za sve osim za administratore, ne možete stvoriti novo probno okruženje.
> 
> Probna okruženja Dataverse stvorena u Customer Insights imaju 3 GB prostora za pohranu koji se neće računati s ukupnim kapacitetom koji ima pravo na klijenta. Plaćene pretplate dobivaju Dataverse pravo od 15 GB za bazu podataka i 20 GB za pohranu datoteka.

## <a name="output-entities"></a>Izlazni entiteti

Neki izlazni entiteti iz publika uvida dostupni su kao tablice u Dataverse. Odjeljci u nastavku opisuju očekivanu shemu ovih tablica.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obogaćivanje](#enrichment)
- [Predviđanje](#prediction)
- [Članstvo u segmentu](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Ova tablica sadrži objedinjeni profil klijenta iz rješenja Customer Insights. Shema za objedinjeni profil klijenta ovisi o entitetima i atributima koji se koriste u procesu spajanja. Shema profila klijenta obično sadrži podskup atributa iz [definicije Common Data Model tablice CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tablica AlternateKey sadrži ključeve entiteta koji su sudjelovali u procesu objedinjavanja.

|Column  |Tip  |Opis  |
|---------|---------|---------|
|DataSourceName    |String         | Naziv izvora podataka. Na primjer: `datasource5`.        |
|EntityName        | String        | Naziv entiteta u uvidima u ciljne skupine. Na primjer: `contact1`.        |
|AlternateValue    |String         |Alternativni ID koji se preslikava na ID klijenta. Primjer: `cntid_1078`         |
|KeyRing           | Tekst s više redaka        | Vrijednost JSON  </br> Uzorak: [{"dataSourceName":" izvor podataka5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"ključevi":[" cntid_1078"]}]       |
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

Ova tablica sadrži informacije o članstvu u segmentu profila kupaca.

| Column        | Tip | Opis                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ID profila klijenta        |
| SegmentProvider      | String       | Aplikacija koja objavljuje segmente. Zadano: uvidi u publika         |
| SegmentMembershipType | String       | Vrsta klijenta za ovaj zapis članstva u segmentu. Podržava više vrsta kao što su Klijent, Kontakt ili Poslovni subjekt. Zadano: Kupac  |
| Segmenti       | Niz JSON  | Popis jedinstvenih segmenata u koje je profil kupca      |
| msdynci_identifier  | String   | Jedinstveni identifikator zapisa članstva u segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministički GUID generiran iz`msdynci_identifier`          |
