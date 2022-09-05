---
title: Primjeri OData upita za API-je za uvide kupaca
description: Uobičajeni primjeri protokola otvorenih podataka (OData) za pretraživanje API-ja Customer Insights za pregled podataka.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387193"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Primjeri OData upita za API-je za uvide kupaca

Protokol otvorenih podataka (OData) protokol je pristupa podacima izgrađen na osnovnim protokolima kao što je HTTP. Koristi općeprihvaćene metodologije poput REST za web. Postoje razne vrste knjižnica i alata koji se mogu koristiti za konzumiranje OData usluga.

Da biste lakše izgradili vlastite implementacije na [temelju API-ja](apis.md) customer insights, pregledajte neke često tražene primjere upita.

Izmijenite uzorke upita da bi funkcionirali na ciljnim okruženjima:

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` gdje {instanceId} se nalazi GUID okruženja Customer Insights koje želite postaviti na upit. Operacija [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) omogućuje vam da pronađete {InstanceId} pristup kojem imate pristup.
- {CID}: GUID jedinstvenog zapisa o klijentu. Primjer: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identifikator primarnog ključa zapisa o klijentu u izvor podataka. Primjer: `CNTID_1002`
- {DSname}: Niz s nazivom entiteta izvor podataka koji se unosi u Customer Insights. Primjer: `Website_contacts`.
- {SegmentName}: Niz s nazivom izlaznog entiteta segmenta u customer insights. Primjer: `Male_under_40`.

## <a name="customer"></a>klijente

Ogledni upiti za *entitet Klijent*.

|Vrsta upita |Primjer  | Napomena  |
|---------|---------|---------|
|ID jednog kupca     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Zamjenski ključ    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Zamjenski ključevi i dalje postoje u jedinstvenom entitetu klijenta       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Za    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Zamjenski ključ + u   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Traži  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Vraća prvih 10 rezultata za niz za pretraživanje      |
|Članstvo u segmentu  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Vraća unaprijed postavljeni broj redaka iz entiteta segmentacije.      |
|Članstvo u segmentu za klijenta | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Vraća profil kupca ako je član određenog segmenta.     |

## <a name="unified-activity"></a>Objedinjena aktivnost

Ogledni upiti za *entitet Jedinstvena aktivnost*.

|Vrsta upita |Primjer  | Napomena  |
|---------|---------|---------|
|Aktivnost CID-a     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Navodi aktivnosti određenog profila klijenta |
|Vremenski okvir aktivnosti    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktivnosti korisničkog profila u vremenski okvir       |
|Vrsta aktivnosti    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktivnost po zaslonsko ime     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Sortiranje aktivnosti    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Sortiranje aktivnosti uzlazno ili silazno       |
|Aktivnost proširena iz članstva u segmentu  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Drugi primjeri

Ogledni upiti za druge entitete.

|Vrsta upita |Primjer  | Napomena  |
|---------|---------|---------|
|Mjere CID-a    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Obogaćene marke CID-a    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Obogaćeni interesi CID-a    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|U-odredbi + proširi     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Nisu podržani OData upiti

Uvidi kupaca ne podržavaju sljedeće upite:

- `$filter` o unesenim izvornim entitetima. Upite $filter možete izvoditi samo na sistemskim entitetima koje kreira Customer Insights.
- `$expand``$search` iz upita. Primjer: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` iz `$select` ako je odabran samo podskup atributa. Primjer: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` obogaćena robna marka ili afiniteti interesa za određenog kupca. Primjer: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Upit predviđanje izlaznih entiteta modela kroz zamjenski ključ. Primjer: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
