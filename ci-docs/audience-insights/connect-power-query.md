---
title: Unos podataka putem Power Query poveznika (video)
description: Poveznici za izvore podataka koji se temelje na platformi Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 38c447d80a25feca087ca9f110278b8401423018
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903831"
---
# <a name="connect-to-a-power-query-data-source"></a>Povezivanje s izvorom podataka platforme Power Query

Power Query nudi širok skup poveznika za unos podataka. Većinu ovih poveznika podržava aplikacija Dynamics 365 Customer Insights. 

Dodavanje izvora podataka na temelju Power Query poveznika obično slijedi korake navedene u ovom odjeljku. Međutim, ovisno o povezniku koji upotrebljavate, potrebni su različiti podaci. Dodatne informacije potražite u dokumentaciji o pojedinačnim poveznicima u [referenci Power Query poveznika](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Izrada novog izvora podataka

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

1. Odaberite **Dodaj izvor podataka**.

1. Odaberite **Microsoft Power Query, a** zatim **Dalje**.

1. Navedite **Naziv** izvora podataka i odaberite **Dalje** kako biste stvorili izvor podataka.

1. Odaberite jedan od [dostupnih poveznika](#available-power-query-data-sources). U ovom primjeru odabiremo **poveznik** Tekst/CSV.

1. Unesite potrebne pojedinosti u **Postavke veze** za odabrani poveznike i odaberite **Dalje** kako biste vidjeli pregled podataka.

1. Odaberite **Pretvori podatke**. U ovom ćete koraku dodati entitete u izvor podataka. Entiteti su skupovi podataka. Ako imate bazu podataka koja sadrži više skupova podataka, svaki je skup podataka vlastiti entitet.

1. Dijaloški okvir **Power Query – Uređivanje upita** omogućuje pregled i pročišćavanje podataka. Entiteti koje su sustavi identificirali u vašem odabranom izvoru podataka prikazuju se u lijevom oknu.

   > [!div class="mx-imgBorder"]
   > ![Dijaloški okvir za uređivanje upita.](media/data-manager-configure-edit-queries.png "Dijaloški okvir uređivanja upita")

1. Podatke možete i pretvoriti. Odaberite entitet koji želite urediti ili pretvoriti. Upotrijebite mogućnosti u prozoru platforme Power Query za primjenu pretvorbi. Svaka se pretvorba navodi pod stavkom **Primijenjeni koraci**. Power Query pruža brojne unaprijed izgrađene mogućnosti pretvorbe. Dodatne informacije potražite u odjeljku [Pretvorbe platforme Power Query](/power-query/power-query-what-is-power-query#transformations).

1. U izvor podataka možete dodati dodatne entitete tako da odaberete **Dohvati podatke** u dijalogu **Uređivanje upita**.

   Preporučujemo da koristite sljedeće transformacije:

   - Ako unosite podatke iz CSV datoteke, prvi redak često sadrži zaglavlja. Idite na stavku **Tablica pretvorbe** i odaberite mogućnost **Uporaba zaglavlja kao prvog reda**.
   - Provjerite je li vrsta podataka postavljena na odgovarajući način.

1. Pri dnu prozora platforme Power Query odaberite **Spremi** kako biste spremili pretvorbe. Nakon spremanja pronaći ćete svoj izvor podataka u stavci **Podaci** > **Izvori podataka**.

1. Na stranici **Izvori podataka** primijetit ćete da je novi izvor podataka u statusu **Osvježavanje**.

## <a name="available-power-query-data-sources"></a>Dostupni izvori podataka platforme Power Query

Pogledajte [referencu Power Query poveznika](/power-query/connectors/) za popis poveznika pomoću kojih možete uvoziti podatke u Customer Insights. 

Poveznici s kvačicom u stupcu **Customer Insights (tijekovi podataka)** dostupni su za stvaranje novih izvora podataka koji se temelje na platformi Power Query. Pregledajte dokumentaciju određenog poveznika kako biste saznali više o njegovim preduvjetima, ograničenjima i ostalim pojedinostima.

## <a name="edit-power-query-data-sources"></a>Uređivanje izvora podataka platforme Power Query

> [!NOTE]
> Možda nećete moći izmijeniti izvore podataka koji se trenutačno koriste u jednom od postupaka aplikacije (npr. *segmentacija*, *podudaranje* ili *spajanje*). 
>
> Na **stranici Postavke** možete pratiti napredak svakog aktivnog procesa. Kada se postupak dovrši, možete se vratiti na stranicu **Izvori podataka** i unijeti promjene.

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Odaberite okomito trotočje pored izvora podataka koji želite promijeniti i odaberite **Uredi** s padajućeg izbornika.

   > [!div class="mx-imgBorder"]
   > ![Mogućnost uređivanja.](media/edit-option-data-sources.png "Uređivanje mogućnosti")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Primijenite svoje promjene i pretvorbe u dijaloškom okviru **Power Query – Uređivanje upita** onako kao je opisano u odjeljku [Stvaranje novog izvora podataka](#create-a-new-data-source).

4. Kako biste nakon dovršetka uređivanja spremili promjene na platformu Power Query, odaberite **Spremi**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
