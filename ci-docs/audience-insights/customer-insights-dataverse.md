---
title: Podaci rješenja Customer Insights u servisu Microsoft Dataverse
description: Koristite entitete Customer Insights kao tablice u servisu Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 45535a7368b89e19a91f08fcd825bda9d57a8709653104bf4043c29ffa14d0b8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032887"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Rad s podacima rješenja Customer Insights u servisu Microsoft Dataverse

Customer Insights pruža mogućnost omogućivanja izlaznih entiteta u servisu [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Ova integracija omogućuje jednostavnu razmjenu podataka i prilagođeni razvoj putem pristupa s malo kodiranja / bez kodiranja. Izlazni entiteti bit će dostupni kao tablice u servisu Dataverse. Ove tablice omogućuju scenarije kao što su [automatizirani tijekovi rada putem servisa Power Automate](/power-automate/getting-started), [aplikacije stvorene prema modelu](/powerapps/maker/model-driven-apps/) i [aplikacije od gotovih gradivnih elemenata](/powerapps/maker/canvas-apps/) putem servisa Power Apps. Podatke možete koristiti za bilo koju drugu aplikaciju koja se temelji na tablicama servisa Dataverse. Trenutna implementacija uglavnom podržava pretraživanja gdje se podaci iz dostupnih entiteta uvida u ciljne skupine mogu dohvatiti za zadani ID klijenta.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Povezivanje okruženja servisa Dataverse s rješenjem Customer Insights

**Tvrtke ili ustanove s postojećim okruženjima Dataverse**

Tvrtke ili ustanove koje već koriste Dataverse mogu [koristiti jedno od svojih postojećih okruženja Dataverse](get-started-paid.md) kada administrator postavi uvide u ciljne skupine. Pružanjem URL-a okruženju Dataverse, povezuje se s njihovim novim okruženjem uvida u ciljne skupine. Kako bi se osigurale najbolje moguće performanse, Customer Insights i okruženja Dataverse moraju biti udomaćena u istoj regiji.

Za povezivanje okruženja Dataverse proširite **Napredne postavke** prilikom stvaranja okruženja uvida u ciljne skupine. Navedite **URL okruženja Microsoft Dataverse** i potvrdite okvir za **Omogućivanje dijeljenja podataka**.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt.":::

**Nova tvrtka ili ustanova**

Ako prilikom postavljanja rješenja Customer Insights stvorite novu tvrtku ili ustanovu, automatski ćete dobiti novo okruženje Dataverse.

> [!NOTE]
> Ako vaša tvrtka ili ustanova već koristi Dataverse u svom klijentu, važno je upamtiti da [stvaranje okruženja Dataverse kontrolira administrator](/power-platform/admin/control-environment-creation.md). Na primjer, ako postavljate novo okruženje uvida u ciljne skupine s računom svoje tvrtke ili ustanove, a administrator je onemogućio stvaranje probnih okruženja Dataverse za sve osim za administratore, ne možete stvoriti novo probno okruženje.
> 
> Probna okruženja Dataverse stvorena u rješenju Customer Insights imaju 3 GB prostora za pohranu koji se neće računati u ukupni kapacitet na koji klijent ima pravo. Plaćene pretplate dobivaju pravo servisa Dataverse na 15 GB za bazu podataka i 20 GB za pohranu datoteka.

## <a name="output-entities"></a>Izlazni entiteti

Neki izlazni entiteti iz uvida u ciljne skupine dostupni su kao tablice u servisu Dataverse. Odjeljci u nastavku opisuju očekivanu shemu ovih tablica.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obogaćivanje](#enrichment)
- [Predviđanje](#prediction)


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
