---
title: Podaci rješenja Customer Insights u servisu Microsoft Dataverse
description: Koristite entitete Customer Insights kao tablice u servisu Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: bbbbf2a7f5edb81ee75f6e33988cd4721134b6e7
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547617"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Rad s podacima rješenja Customer Insights u servisu Microsoft Dataverse

Customer Insights pruža mogućnost omogućivanja izlaznih entiteta u servisu [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ova integracija omogućuje jednostavnu razmjenu podataka i prilagođeni razvoj kroz pristup koda niskog koda / bez koda. Izlazni [entiteti](#output-entities) dostupni su kao tablice u Dataverse okruženju. Podatke možete koristiti za bilo koju drugu aplikaciju na Dataverse temelju tablica. Ove tablice omogućavaju scenarije kao što su automatizirani tijekovi rada kroz Power Automate ili izrada aplikacija pomoću programa Power Apps. Trenutna implementacija uglavnom podržava pretraživanja u kojima se podaci iz dostupnih entiteta Customer Insights mogu dohvatiti za određeni ID klijenta.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Povezivanje okruženja servisa Dataverse s rješenjem Customer Insights

**Postojeća organizacija**

Administratori mogu konfigurirati Customer Insights za [korištenje postojećeg Dataverse okruženja](create-environment.md) prilikom stvaranja okruženja Customer Insights. Pružanjem URL-a okruženju Dataverse, povezuje se s njihovim novim okruženjem uvida u ciljne skupine. Uvidi u kupce i Dataverse okruženja moraju biti smješteni u istoj regiji. 

Ako ne želite koristiti postojeće Dataverse okruženje, sustav stvara novo okruženje za podatke Customer Insights u vašem klijentu. 

> [!NOTE]
> Ako vaša tvrtka ili ustanova već koristi Dataverse u svom klijentu, važno je upamtiti da [stvaranje okruženja Dataverse kontrolira administrator](/power-platform/admin/control-environment-creation). Na primjer, ako postavljate novo okruženje uvida u ciljne skupine s računom svoje tvrtke ili ustanove, a administrator je onemogućio stvaranje probnih okruženja Dataverse za sve osim za administratore, ne možete stvoriti novo probno okruženje.
> 
> Probna okruženja Dataverse stvorena u rješenju Customer Insights imaju 3 GB prostora za pohranu koji se neće računati u ukupni kapacitet na koji klijent ima pravo. Plaćene pretplate dobivaju pravo servisa Dataverse na 15 GB za bazu podataka i 20 GB za pohranu datoteka.

**Nova tvrtka ili ustanova**

Ako prilikom postavljanja customer insightsa stvorite novu organizaciju, sustav automatski stvara novo Dataverse okruženje u vašoj tvrtki ili ustanovi.

## <a name="output-entities"></a>Izlazni entiteti

Neki izlazni entiteti iz uvida u ciljne skupine dostupni su kao tablice u servisu Dataverse. Odjeljci u nastavku opisuju očekivanu shemu ovih tablica.

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

| Column        | Tip | Opis                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ID profila klijenta        |
| SegmentProvider      | String       | Aplikacija koja objavljuje segmente. Zadano: publika uvidi         |
| SegmentMembershipType | String       | Upišite zapis članstva u ovom segmentu kupca. Podržava više vrsta kao što su Klijent, Kontakt ili Poslovni subjekt. Zadano: kupac  |
| Segmenti       | Niz JSON  | Popis jedinstvenih segmenata čiji je profil kupca član      |
| msdynci_identifier  | String   | Jedinstveni identifikator zapisa članstva u segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministički GUID generiran iz`msdynci_identifier`          |
