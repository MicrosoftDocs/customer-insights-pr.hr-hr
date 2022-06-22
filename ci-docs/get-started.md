---
title: Uvod u Dynamics 365 Customer Insights
description: Pregled uvida u kupce pomaže resursima da brzo započnu.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1c925110f40319df77940d1c32f24a99504d6ec6
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011970"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Uvod u Dynamics 365 Customer Insights

Uvidi u kupce mogu vam pomoći da izgradite dublje razumijevanje svojih kupaca. Povežite podatke iz različitih izvora transakcija, ponašanja i promatranja kako biste stvorili sveobuhvatan prikaz klijenta. Iskoristite te uvide da biste potaknuli doživljaje i postupke usmjerene na klijenta. Objedinite i razumijte podatke o klijentima te ih iskoristite za inteligentne uvide i radnje.

## <a name="step-1-create-an-environment"></a>Korak 1: Stvaranje okruženja

Prvo stvorite okruženje u kojem ćete raditi. Ako je vaša tvrtka ili ustanova već kupila licencu, pogledajte [Stvaranje okruženja](create-environment.md). Upute za započinjanje probnog razdoblja za uvide u korisnike potražite u članku [Postavljanje probnog okruženja](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Korak 2: Istražite uvide kupaca

Kada se prvi put prijavite u Customer Insights, konfigurirajte postavke i istražite proizvod.

1. [prijavite se u Customer Insights](https://home.ci.ai.dynamics.com) pomoću Microsoftova Azure Active Directory (AAD) korisničkog računa.

1. Promijenite okruženje da biste vidjeli demo podatke i [istražite uvide u kupce](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Korak 3: Unesite, objedinite i postavite odnose za svoje podatke

Objedinjeni profili temelj su za stjecanje uvida i poduzimanje radnji u vezi s podacima. Unesite podatke iz različitih izvora i pokrenite proces objedinjavanja podataka kako biste kombinirali objedinjene profile. Navedite Odnosi između unesenih entiteta i koristite značajke obogaćivanja za dodavanje informacija profilima.

1. Unesite podatke stvaranjem izvora podataka iz više mogućnosti. Izaberite između [Azure Data Lake Storage, uključujući Uobičajeni podatkovni model](connect-common-data-model.md), [Azure Synapse Analytics](connect-synapse.md), ili [Microsoft Dataverse](connect-dataverse-managed-lake.md)[Power Query poveznika](connect-power-query.md).

1. Pokrenite postupak objedinjavanja [podataka identificiranjem izvorišnih](data-unification.md) polja [, uklanjanjem](map-entities.md) duplikata, [odgovarajućih](remove-duplicates.md) uvjeta [i](match-entities.md) ujedinjavanjem polja [.](merge-entities.md)

1. Upoznajte se s [entitetima koje stvara sustav](entities.md) i stvorite [odnose među unesenim entitetima](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Korak 4: Poboljšajte objedinjene profile predviđanjima, aktivnostima i mjerama

Uz postavljanje jedinstvenih profila poboljšajte svoje podatke i dodatno povećajte informacije koje pružaju.

1. Birajte iz sve veće knjižnice pružatelja usluga obogaćivanja da biste [obogatili svoje podatke o klijentima](enrichment-hub.md).

1. Koristite [gotove modele](predictions-overview.md) za predviđanje vjerojatnosti gubitka ili očekivanih prihoda.

1. [Konfigurirajte aktivnosti](activities.md) na temelju unesenih podataka i vizualizirajte interakcije sa svojim klijentima na kronološkoj vremenskoj traci.

1. [Izgradite mjere](measures.md) za mjerenje vaših poslovnih ciljeva i KPI-jeva.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Korak 5: Stvorite segmente i aktivirajte podatke kroz različite mogućnosti izvoza

Sada kada su vaši podaci potpuni i sadrže širok raspon informacija o vašim klijentima, potražite načine za poduzimanje radnji na tim podacima.

1. [Stvorite segmente](segments.md), podskupove vaše baze klijenata kako biste bili sigurni da su vaše radnje relevantne za ciljane klijente.

1. Pregledajte proširujući katalog za [mogućnosti izvoza](export-destinations.md) gdje možete koristiti podatke o klijentima. Na primjer, možete koristiti podatke za upravljanje promocijama i kontakt s digitalnim marketingom.

1. Pregledajte mogućnosti integracije, na primjer u druge aplikacije sustava Dynamics 365 pomoću dodatka [Kartica kupca](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
