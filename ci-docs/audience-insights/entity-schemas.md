---
title: Sheme entiteta usluge Customer Insights u formatu Common Data Model
description: Rad s entitetima u formatu Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6667e411a1b56e13105a6b59b7b5d249bc8141ea
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596352"
---
# <a name="entity-schemas-in-common-data-model"></a>Sheme entiteta u modelu zajedničkih podatakal

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Model zajedničkih podataka](/common-data-model/) je deklarativna specifikacija i definicija standardnih entiteta koji predstavljaju uobičajene koncepte i aktivnosti u poslovnim i produktivnim aplikacijama. Ovaj model se proširuje i na opažajne i na analitičke podatke. Model zajedničkih podataka pruža dobro definirane, modularne i proširive poslovne entitete, kao što su Račun, Poslovna jedinica, Slučaj, Kontakt, Potencijalni klijent i Proizvod te interakcije s dobavljačima, suradnicima i klijentima, kao što su aktivnosti i ugovori o razini usluge. Svatko može nadograditi i proširiti definicije modela zajedničkih podataka kako bi zabilježio dodatne ideje vezane uz poslovanje.

Ovaj model zajedničkih podataka omogućuje aplikacijama i integratorima podataka jednostavniju suradnju pružajući jedinstvenu definiciju podataka. Model zajedničkih podataka uključuje bogati sustav metapodataka sa standardnim entitetima, odnosima, hijerarhijom, osobinama i još mnogo toga. Potječe iz aplikacija Dynamics 365 i otvorenog je izvora na usluzi GitHub s više od 260 standardnih entiteta. Veliki sustav unutarnjih i vanjskih partnera pridonosi konceptima koji se odnose na industriju modelu zajedničkih podataka.

Više sustava i platformi danas implementiraju model zajedničkih podataka, uključujući protoke podataka Power BI i podatkovne usluge Azure. Već je podržana u uslugama Common Data Service, Dynamics 365, Power Apps, Power BI i nadolazeće Azure podatkovne usluge, koje izravno prikupljaju vrijednost prema modelu [Open Data Initiative](https://www.microsoft.com/open-data-initiative),

## <a name="customer-insights-entity-schemas"></a>Sheme entiteta usluge Customer Insights

Da bismo dobili sveobuhvatan pregled klijenta i učinili modele aplikacije Customer Insights dostupnima u modelu zajedničkih podataka radi proširivosti, objavili smo sljedeće sheme entiteta:

| Entitet | Opis |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Aktivnost koju izvršava korisnik koji ima promatračku vrijednost za poslovanje. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Osoba ili tvrtka ili ustanova koja je obavljala poslovnu aktivnost ili ima potencijal da se bavi poslovnom aktivnošću. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definicija KPI-ija podijeljenih s nula ili više dimenzija (npr. Mjesečni aktivni korisnici, Ukupna potrošnja prema klijentu, Prosječni troškovi kupnje klijenta) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definira grupu članova sa zajedničkim osobinama. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Članovi koji sudjeluju u određenom segmentu. |

Više informacija potražite u dokumentaciji u odjeljku [Sheme entieta usluge Customer Insights u modelu zajedničkih podataka](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Pregled entiteta pomoću navigatora entiteta modela zajedničkih podataka

Entitete možete pregledati u [Navigatoru entiteta formata Common Data Model](https://microsoft.github.io/CDM/). Odaberite gumb **Učitaj iz GitHub-a!** i pomaknite se do **foundationCommon** > **crmCommon** > **rješenja** > **customerInsights** gdje ćete pronaći popis entiteta usluge Customer Insights i njihove definicije.
> [!div class="mx-imgBorder"]
> ![CDM navigator eniteta koji prikazuje entitet CustomerActivity](media/CDM-entity-navigator.png "CDM navigator eniteta koji prikazuje entitet CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]