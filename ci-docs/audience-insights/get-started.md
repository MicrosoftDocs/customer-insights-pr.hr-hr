---
title: Započnite sa sposobnošću uvida u ciljnu skupinu u Dynamics 365 Customer Insights
description: Pregled uvida u ciljnu skupinu pomaže resursima da brzo započnu.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5e8545bc9bf0d953150248fa859c6ca71a12f9cf
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645255"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Započnite sa sposobnošću uvida u ciljnu skupinu u Dynamics 365 Customer Insights

Uvidi u ciljnu skupinu mogu vam pomoći u stjecanju boljeg razumijevanja vaših klijenata. Povežite podatke iz različitih izvora transakcija, ponašanja i promatranja kako biste stvorili sveobuhvatan prikaz klijenta. Iskoristite te uvide da biste potaknuli doživljaje i postupke usmjerene na klijenta. Objedinite i razumijte podatke o klijentima te ih iskoristite za inteligentne uvide i radnje.

## <a name="step-1-create-an-environment"></a>Korak 1: Stvaranje okruženja

Za početak najprije morate stvoriti okruženje za rad. Ako je vaša tvrtka ili ustanova već kupila licencu, pogledajte [Stvaranje okruženja](create-environment.md). Za početak probnog razdoblja za uvide u ciljnu skupinu pogledajte [Postavljanje probnog okruženja](../trial-signup.md). 

## <a name="step-2-explore-audience-insights"></a>Korak 2: Istraživanje uvida u ciljnu skupinu

Prilikom prve prijave u uvide u ciljnu skupinu, možete konfigurirati postavke i istražiti proizvod.

1. [Prijavite se u uvide u ciljnu skupinun](https://home.ci.ai.dynamics.com) koristeći svoj korisnički račun Microsoft Azure Active Directory (AAD).

1. [Promijenite okruženje](manage-environments.md#switch-environments) da biste vidjeli demo podatke i [istražili uvide u ciljnu skupinu](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Korak 3: Unesite, objedinite i postavite odnose za svoje podatke

Objedinjeni profili temelj su za stjecanje uvida i poduzimanje radnji u vezi s podacima. Unesite podatke iz različitih izvora i pokrenite proces objedinjavanja podataka kako biste kombinirali objedinjene profile. Navedite odnose između unesenih entiteta i koristite značajke obogaćivanja za dodavanje informacija profilima. 

1. Unesite podatke stvaranjem izvora podataka iz više mogućnosti. Odaberite između [Poveznici Power Query](connect-power-query.md), [Mapa Common Data Model](connect-common-data-model.md) ili [Microsoft Dataverse](connect-common-data-service-lake.md). 

1. Pokrenite [proces objedinjavanja podataka](data-unification.md) prolaskom kroz faze [mapiranja](map-entities.md), [podudaranja](match-entities.md) i [spajanja](merge-entities.md).

1. Upoznajte se s [entitetima koje stvara sustav](entities.md) i stvorite [odnose među unesenim entitetima](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Korak 4: Poboljšajte objedinjene profile predviđanjima, aktivnostima i mjerama

S postavljenim objedinjenim profilima možete poboljšati svoje podatke i dodatno povećati podatke koje oni pružaju.

1. Birajte iz sve veće knjižnice pružatelja usluga obogaćivanja da biste [obogatili svoje podatke o klijentima](enrichment-hub.md).

1. Koristite [gotove modele](predictions-overview.md) za predviđanje vjerojatnosti gubitka ili očekivanih prihoda.

1. [Konfigurirajte aktivnosti](activities.md) na temelju unesenih podataka i vizualizirajte interakcije sa svojim klijentima na kronološkoj vremenskoj traci. 

1. [Izgradite mjere](measures.md) za mjerenje vaših poslovnih ciljeva i KPI-jeva.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Korak 5: Stvorite segmente i aktivirajte podatke kroz različite mogućnosti izvoza

Sada kada su vaši podaci potpuni i sadrže širok raspon informacija o vašim klijentima, vrijeme je da potražite načine za poduzimanje radnji na tim podacima. 

1. [Stvorite segmente](segments.md), podskupove vaše baze klijenata kako biste bili sigurni da su vaše radnje relevantne za ciljane klijente.

1. Pregledajte proširujući katalog za [mogućnosti izvoza](export-destinations.md) gdje možete koristiti podatke o klijentima. Na primjer, možete koristiti podatke za upravljanje promocijama i kontakt s digitalnim marketingom.

1. Pregledajte mogućnosti integracije, na primjer pomoću [izravne veze s uvidima u angažman](../engagement-insights/integrate-audience-insights-engagement-insights.md) ili drugih aplikacija sustava Dynamics 365 s [dodatkom za karticu klijenta](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
