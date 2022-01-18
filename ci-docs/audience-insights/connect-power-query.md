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
ms.openlocfilehash: aae49be4364676ecc7a307e60eeca13859f1662a
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934969"
---
# <a name="connect-to-a-power-query-data-source"></a>Povezivanje s Power Query izvor podataka

Power Query nudi širok skup konektora za unos podataka. Većinu ovih poveznika podržava aplikacija Dynamics 365 Customer Insights. 

Dodavanje izvora podataka na temelju Power Query poveznika obično slijedi korake navedene u ovom odjeljku. Međutim, ovisno o povezniku koji upotrebljavate, potrebni su različiti podaci. Dodatne informacije potražite u dokumentaciji o pojedinačnim poveznicima u [Power Query referenci poveznika](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Izrada novog izvora podataka

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

1. Odaberite **Dodaj izvor podataka**.

1. Odaberite **Microsoft Power Query**, a zatim **Dalje**.

1. Navedite **Naziv** izvora podataka i odaberite **Dalje** kako biste stvorili izvor podataka.

1. Odaberite jedan od [dostupnih poveznika](#available-power-query-data-sources). U ovom primjeru odabiremo **poveznik** Tekst/CSV.

1. Unesite potrebne pojedinosti u **Postavke veze** za odabrani poveznike i odaberite **Dalje** kako biste vidjeli pregled podataka.

1. Odaberite **Pretvori podatke**. U ovom ćete koraku dodati entitete u izvor podataka. Entiteti su skupovi podataka. Ako imate bazu podataka koja sadrži više skupova podataka, svaki je skup podataka vlastiti entitet.

1. **Power Query Dijaloški okvir - uređivanje upita** omogućuje pregled i sužavanje podataka. Entiteti koje su sustavi identificirali u vašem odabranom izvoru podataka prikazuju se u lijevom oknu.

   > [!div class="mx-imgBorder"]
   > ![Dijaloški okvir za uređivanje upita.](media/data-manager-configure-edit-queries.png "Dijaloški okvir uređivanja upita")

1. Podatke možete i pretvoriti. Odaberite entitet koji želite urediti ili pretvoriti. Pomoću mogućnosti u Power Query prozoru primijenite transformacije. Svaka se pretvorba navodi pod stavkom **Primijenjeni koraci**. Power Query pruža brojne unaprijed izgrađene mogućnosti transformacije. Dodatne informacije potražite u [Power Query odjeljku Transformacije](/power-query/power-query-what-is-power-query#transformations).

1. U izvor podataka možete dodati dodatne entitete tako da odaberete **Dohvati podatke** u dijalogu **Uređivanje upita**.

   Preporučujemo da koristite sljedeće transformacije:

   - Ako unosite podatke iz CSV datoteke, prvi redak često sadrži zaglavlja. Idite na stavku **Tablica pretvorbe** i odaberite mogućnost **Uporaba zaglavlja kao prvog reda**.
   - Provjerite je li vrsta podataka postavljena na odgovarajući način.

1. Pri **dnu** prozora odaberite Spremi Power Query da biste spremili transformacije. Nakon spremanja pronaći ćete svoj izvor podataka u stavci **Podaci** > **Izvori podataka**.

1. Na stranici **Izvori podataka** primijetit ćete da je novi izvor podataka u statusu **Osvježavanje**.

## <a name="available-power-query-data-sources"></a>Dostupni Power Query izvori podataka

Pogledajte [Power Query referencu poveznika](/power-query/connectors/) za popis poveznika pomoću kojih možete uvoziti podatke u Customer Insights. 

Poveznici s kvačionom u **stupcu Uvidi u klijenta (Dataflows)** dostupni su za stvaranje novih izvora podataka na temelju Power Query. Pregledajte dokumentaciju određenog poveznika kako biste saznali više o njegovim preduvjetima, ograničenjima i ostalim pojedinostima.

## <a name="edit-power-query-data-sources"></a>Uređivanje Power Query izvora podataka

> [!NOTE]
> Možda nećete moći izmijeniti izvore podataka koji se trenutačno koriste u jednom od postupaka aplikacije (npr. *segmentacija*, *podudaranje* ili *spajanje*). 
>
> Na **stranici Postavke** možete pratiti napredak svakog aktivnog procesa. Kada se postupak dovrši, možete se vratiti na stranicu **Izvori podataka** i unijeti promjene.

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Odaberite okomito trotočje pored izvora podataka koji želite promijeniti i odaberite **Uredi** s padajućeg izbornika.

   > [!div class="mx-imgBorder"]
   > ![Mogućnost uređivanja.](media/edit-option-data-sources.png "Uređivanje mogućnosti")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Primijenite promjene i transformacije u **Power Query dijaloškom okviru - Uređivanje upita** kao što je opisano u [odjeljku Stvaranje novog](#create-a-new-data-source) izvor podataka.

4. Nakon **dovršetka uređivanja odaberite Spremi u da** Power Query biste spremili promjene.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
