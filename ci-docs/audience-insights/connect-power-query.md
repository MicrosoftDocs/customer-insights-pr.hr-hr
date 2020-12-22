---
title: Unos podataka putem konektora Power Query
description: Poveznici za izvore podataka koji se temelje na platformi Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405318"
---
# <a name="connect-to-a-power-query-data-source"></a>Povezivanje s izvorom podataka platforme Power Query

Power Query nudi širok skup poveznika za unos podataka. Većinu ovih poveznika podržava aplikacija Dynamics 365 Customer Insights. Dodavanje izvora podataka koji se temelje na poveznicima platforme Power Query obično slijedi korake navedene u sljedećem odjeljku. Međutim, ovisno o povezniku koji upotrebljavate, potrebni su različiti podaci. Dodatne informacije potražite u dokumentaciji o pojedinim poveznicima u odjeljku [Reference poveznika platforme Power Query](https://docs.microsoft.com/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Izrada novog izvora podataka

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

1. Odaberite **Dodaj izvor podataka**.

1. Odaberite način **Uvoz podataka** i zatim **Dalje**.

1. Navedite **Naziv** izvora podataka i odaberite **Dalje** kako biste stvorili izvor podataka.

1. Odaberite jedan od [dostupnih poveznika](#available-power-query-data-sources). Za ovaj primjer odabiremo poveznik **Tekst/CSV**.

1. Unesite potrebne pojedinosti u **Postavke veze** za odabrani poveznike i odaberite **Dalje** kako biste vidjeli pregled podataka.

1. Odaberite **Pretvori podatke**. U ovom ćete koraku dodati entitete u izvor podataka. Entiteti su skupovi podataka. Ako imate bazu podataka koja sadrži više skupova podataka, svaki je skup podataka vlastiti entitet.

1. Dijaloški okvir **Power Query – Uređivanje upita** omogućuje pregled i pročišćavanje podataka. Entiteti koje su sustavi identificirali u vašem odabranom izvoru podataka prikazuju se u lijevom oknu.

   > [!div class="mx-imgBorder"]
   > ![Dijaloški okvir uređivanja upita](media/data-manager-configure-edit-queries.png "Dijaloški okvir uređivanja upita")

1. Podatke možete i pretvoriti. Odaberite entitet koji želite urediti ili pretvoriti. Upotrijebite mogućnosti u prozoru platforme Power Query za primjenu pretvorbi. Svaka se pretvorba navodi pod stavkom **Primijenjeni koraci**. Power Query pruža brojne unaprijed izgrađene mogućnosti pretvorbe. Dodatne informacije potražite u odjeljku [Pretvorbe platforme Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).

1. U izvor podataka možete dodati dodatne entitete tako da odaberete **Dohvati podatke** u dijalogu **Uređivanje upita**.

   Preporučene su sljedeće pretvorbe:

   - Ako unosite podatke iz CSV datoteke, prvi redak često sadrži zaglavlja. Idite na stavku **Tablica pretvorbe** i odaberite mogućnost **Uporaba zaglavlja kao prvog reda**.
   - Provjerite je li vrsta podataka postavljena na odgovarajući način.

1. Pri dnu prozora platforme Power Query odaberite **Spremi** kako biste spremili pretvorbe. Nakon spremanja pronaći ćete svoj izvor podataka u stavci **Podaci** > **Izvori podataka**.

1. Na stranici **Izvori podataka** primijetit ćete da je novi izvor podataka u statusu **Osvježavanje**.

## <a name="available-power-query-data-sources"></a>Dostupni izvori podataka platforme Power Query

Pogledajte članak [Referenca poveznika platforme Power Query](https://docs.microsoft.com/power-query/connectors/) za ažurirani popis poveznika koje možete odabrati za uvoz podataka u aplikaciju Customer Insights. 

Poveznici s kvačicom u stupcu **Customer Insights (tijekovi podataka)** dostupni su za stvaranje novih izvora podataka koji se temelje na platformi Power Query. Pregledajte dokumentaciju određenog poveznika kako biste saznali više o njegovim preduvjetima, ograničenjima i ostalim pojedinostima.

## <a name="edit-power-query-data-sources"></a>Uređivanje izvora podataka platforme Power Query

> [!NOTE]
> Možda nećete moći izmijeniti izvore podataka koji se trenutačno koriste u jednom od postupaka aplikacije (npr. *segmentacija*, *podudaranje* ili *spajanje*). 
>
> Pomoću stranice **Postavke** možete pratiti napredak pojedinih aktivnih postupaka. Kada se postupak dovrši, možete se vratiti na stranicu **Izvori podataka** i unijeti promjene.

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Odaberite okomitu trotočku pored izvora podataka koju želite promijeniti i odaberite **Uredi** iz padajućeg izbornika.

   > [!div class="mx-imgBorder"]
   > ![Uređivanje mogućnosti](media/edit-option-data-sources.png "Uređivanje mogućnosti")

3. Primijenite svoje promjene i pretvorbe u dijaloškom okviru **Power Query – Uređivanje upita** onako kao je opisano u odjeljku [Stvaranje novog izvora podataka](#create-a-new-data-source).

4. Kako biste nakon dovršetka uređivanja spremili promjene na platformu Power Query, odaberite **Spremi**.
