---
title: Primjeri OData za API-jeve Dynamics 365 Customer Insights
description: Uobičajeni primjeri protokola otvorenih podataka (OData) za pretraživanje API-ja Customer Insights za pregled podataka.
ms.date: 05/10/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 007278e1330e1a8e64d524ded8496acaf83b874c
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740063"
---
# <a name="odata-query-examples"></a>Primjeri OData upita

Protokol otvorenih podataka (OData) protokol je pristupa podacima izgrađen na osnovnim protokolima kao što je HTTP. Koristi općeprihvaćene metodologije poput REST za web. Postoje razne vrste knjižnica i alata koji se mogu koristiti za konzumiranje OData usluga.

U ovom se članku navode neki često traženi primjeri upita koji će vam pomoći u izgradnji vlastitih implementacija na [temelju API-ja customer insights](apis.md).

Morate izmijeniti uzorke upita da bi radili na ciljnim okruženjima: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` gdje {instanceId} se nalazi GUID okruženja Customer Insights koje želite postaviti na upit. Operacija [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) omogućuje vam da pronađete {InstanceId} pristup kojem imate pristup.
- {CID}: GUID jedinstvenog zapisa o klijentu. Primjer: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identifikator primarnog ključa zapisa o klijentu u izvor podataka. Primjer: `CNTID_1002`
- {DSname}: Niz s nazivom entiteta izvor podataka koji se unosi u Customer Insights. Primjer: `Website_contacts`.
- {SegmentName}: Niz s nazivom izlaznog entiteta segmenta u customer insights. Primjer: `Male_under_40`.

## <a name="customer"></a>klijente

Sljedeća tablica sadrži skup oglednih upita za *entitet Kupac*.


|Vrsta upita |Primjer  | Napomena  |
|---------|---------|---------|
|ID jednog kupca     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Zamjenski ključ    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}' `         |  Zamjenski ključevi i dalje postoje u jedinstvenom entitetu klijenta       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Za    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Zamjenski ključ + u   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Traži  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Vraća prvih 10 rezultata za niz za pretraživanje      |
|Članstvo u segmentu  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10  `     | Vraća unaprijed postavljeni broj redaka iz entiteta segmentacije.      |

## <a name="unified-activity"></a>Objedinjena aktivnost

Sljedeća tablica sadrži skup oglednih upita za *entitet Objedinjenost*.

|Vrsta upita |Primjer  | Napomena  |
|---------|---------|---------|
|Aktivnost CID-a     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Navodi aktivnosti određenog profila klijenta |
|Vremenski okvir aktivnosti    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktivnosti korisničkog profila u vremenski okvir       |
|Vrsta aktivnosti    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktivnost po zaslonsko ime     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’ `        | |
|Sortiranje aktivnosti    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Sortiranje aktivnosti uzlazno ili silazno       |
|Aktivnost proširena iz članstva u segmentu  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Drugi primjeri

Sljedeća tablica sadrži skup oglednih upita za druge entitete.

|Vrsta upita |Primjer  | Napomena  |
|---------|---------|---------|
|Mjere CID-a    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Obogaćene marke CID-a    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Obogaćeni interesi CID-a    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|U-odredbi + proširi     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |
