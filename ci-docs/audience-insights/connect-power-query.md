---
title: Unos podataka putem Power Query poveznika (sadrži videozapis)
description: Poveznici za izvore podataka koji se temelje na sustavu Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 727cb9a4d754b6dbd74d6ecab1b183d41f713d8f
ms.sourcegitcommit: aadee829eff111c95eb30c0a97a68dcc87994acf
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092063"
---
# <a name="connect-to-a-power-query-data-source"></a>Power Query Povezivanje s izvor podataka

Power Query nudi širok skup konektora za unos podataka. Većinu ovih poveznika podržava aplikacija Dynamics 365 Customer Insights. 

Dodavanje izvora podataka na temelju Power Query poveznika obično slijedi korake navedene u ovom odjeljku. Međutim, ovisno o povezniku koji upotrebljavate, potrebni su različiti podaci. Dodatne informacije potražite u dokumentaciji o pojedinačnim poveznicima u referenci [Power Query poveznika](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Izrada novog izvora podataka

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

1. Odaberite **Dodaj izvor podataka**.

1. Odaberite **Microsoft Power Query**.

1. Navedite **Naziv** izvora podataka i odaberite **Dalje** kako biste stvorili izvor podataka.

1. Odaberite jedan od [dostupnih poveznika](#available-power-query-data-sources). U ovom primjeru odabiremo **poveznik Tekst/CSV**.

1. Unesite potrebne pojedinosti u **Postavke veze** za odabrani poveznike i odaberite **Dalje** kako biste vidjeli pregled podataka.

1. Odaberite **Pretvori podatke**. U ovom ćete koraku dodati entitete u izvor podataka. Entiteti su skupovi podataka. Ako imate bazu podataka koja sadrži više skupova podataka, svaki je skup podataka vlastiti entitet.

1. Dijaloški **Power Query okvir - uređivanje upita** omogućuje pregled i sužavanje podataka. Entiteti koje su sustavi identificirali u vašem odabranom izvoru podataka prikazuju se u lijevom oknu.

   > [!div class="mx-imgBorder"]
   > ![Dijaloški okvir za uređivanje upita.](media/data-manager-configure-edit-queries.png "Dijaloški okvir uređivanja upita")

1. Podatke možete i pretvoriti. Odaberite entitet koji želite urediti ili pretvoriti. Pomoću mogućnosti u prozoru primijenite Power Query transformacije. Svaka se pretvorba navodi pod stavkom **Primijenjeni koraci**. Power Query pruža brojne unaprijed izgrađene mogućnosti transformacije. Dodatne informacije potražite u članku [Power Query Transformacije](/power-query/power-query-what-is-power-query#transformations).

   Preporučujemo da koristite sljedeće transformacije:

   - Ako unosite podatke iz CSV datoteke, prvi redak često sadrži zaglavlja. Idite na Pretvorba **i** odaberite **Koristi prvi redak kao zaglavlja**.
   - Provjerite je li vrsta podataka postavljena na odgovarajući način. Na primjer, za polja datuma odaberite vrstu datuma.

1. Da biste dodali dodatne entitete u izvor podataka u dijaloškom okviru **Uređivanje upita otvorite** Polazno **i** odaberite **Dohvaćanje podataka**.

1. Pri dnu prozora odaberite **Spremi** Power Query da biste spremili transformacije. Nakon spremanja pronaći ćete svoj izvor podataka u stavci **Podaci** > **Izvori podataka**.

1. Na stranici **Izvori podataka** primijetit ćete da je novi izvor podataka u statusu **Osvježavanje**.

## <a name="available-power-query-data-sources"></a>Dostupni Power Query izvori podataka

Pogledajte referencu [Power Query](/power-query/connectors/) poveznika za popis poveznika pomoću kojih možete uvoziti podatke u Customer Insights. 

Poveznici s kvačionom u stupcu **Uvidi u klijenta (Dataflows)** dostupni su za stvaranje novih izvora podataka na temelju Power Query. Pregledajte dokumentaciju određenog poveznika kako biste saznali više o njegovim preduvjetima, ograničenjima i ostalim pojedinostima.

## <a name="edit-power-query-data-sources"></a>Uređivanje Power Query izvora podataka

> [!NOTE]
> Možda nećete moći izmijeniti izvore podataka koji se trenutačno koriste u jednom od postupaka aplikacije (npr. *segmentacija*, *podudaranje* ili *spajanje*). 
>
> Na stranici **Postavke** možete pratiti napredak svakog aktivnog procesa. Kada se postupak dovrši, možete se vratiti na stranicu **Izvori podataka** i unijeti promjene.

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Odaberite okomito trotočje pored izvora podataka koji želite promijeniti i odaberite **Uredi** s padajućeg izbornika.

   > [!div class="mx-imgBorder"]
   > ![Mogućnost uređivanja.](media/edit-option-data-sources.png "Uređivanje mogućnosti")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Primijenite promjene i transformacije u dijaloškom okviru **Power Query - Uređivanje upita** kao što je opisano u [odjeljku Stvaranje novog izvor podataka](#create-a-new-data-source).

4. Nakon dovršetka uređivanja odaberite **Spremi** u Power Query da biste spremili promjene.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
