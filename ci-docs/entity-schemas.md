---
title: Sheme entiteta u modelu zajedničkih podatakal
description: Rad s entitetima u formatu Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: cc65314f1b083694b60ac0a2625bea906be7272b
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183484"
---
# <a name="entity-schemas-in-common-data-model"></a>Sheme entiteta u modelu zajedničkih podatakal

[Model zajedničkih podataka](/common-data-model/) je deklarativna specifikacija i definicija standardnih entiteta koji predstavljaju uobičajene koncepte i aktivnosti u poslovnim i produktivnim aplikacijama. Ovaj model se proširuje i na opažajne i na analitičke podatke. Model zajedničkih podataka pruža dobro definirane, modularne i proširive poslovne entitete, kao što su Račun, Poslovna jedinica, Slučaj, Kontakt, Potencijalni klijent i Proizvod te interakcije s dobavljačima, suradnicima i klijentima, kao što su aktivnosti i ugovori o razini usluge. Svatko može nadograditi i proširiti definicije modela zajedničkih podataka kako bi zabilježio dodatne ideje vezane uz poslovanje.

Ovaj model zajedničkih podataka omogućuje aplikacijama i integratorima podataka jednostavniju suradnju pružajući jedinstvenu definiciju podataka. Model zajedničkih podataka uključuje bogati sustav metapodataka sa standardnim entitetima, odnosima, hijerarhijom, osobinama i još mnogo toga. Potječe iz aplikacija Dynamics 365 i otvorenog je izvora na usluzi GitHub s više od 260 standardnih entiteta. Veliki sustav unutarnjih i vanjskih partnera pridonosi konceptima koji se odnose na industriju modelu zajedničkih podataka.

Više sustava i platformi danas implementiraju zajednički model podataka, uključujući Power BI tijekove podataka i Azure podatkovne usluge. Već je podržano u Microsoft Dataverse, Dynamics 365, Power Apps, Power BI i nadolazećim podatkovnim uslugama servisa Azure koje izravno ostvaruju vrijednost prema [Inicijativi za otvorene podatke](https://dynamics.microsoft.com/en-us/open-data-initiative/).

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

Prikažite entitete u navigatoru entiteta uobičajenog [podatkovnog modela](https://microsoft.github.io/CDM/). Odaberite entitet iz odjeljka aplikacije Insights da biste dobili popis entiteta usluge Customer Insights i njihove definicije.

:::image type="content" source="media/CDM-entity-navigator.png" alt-text="CDM navigator eniteta koji prikazuje entitet CustomerActivity.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
