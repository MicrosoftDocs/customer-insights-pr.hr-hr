---
title: Unos podataka putem Power Query poveznika (sadrži videozapis)
description: Poveznici za izvore podataka koji se temelje na Power Query.
ms.date: 05/09/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: b99c3b446e580f455f9678d54d9db414aea9b331
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011648"
---
# <a name="connect-to-a-power-query-data-source"></a>Povezivanje s Power Query izvor podataka

Power Query nudi širok skup konektora za unos podataka. Većinu ovih poveznika podržava aplikacija Dynamics 365 Customer Insights.

Dodavanje izvora podataka na Power Query temelju poveznika općenito slijedi korake navedene u ovom odjeljku. Međutim, ovisno o povezniku koji upotrebljavate, potrebni su različiti podaci. Dodatne informacije potražite u dokumentaciji o pojedinačnim poveznicima u referenci [Power Query poveznika](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Izrada novog izvora podataka

1. Idite na **Podaci** > **Izvor podataka**.

1. Odaberite **Dodaj izvor podataka**.

1. Odaberite **Microsoft Power Query**.

1. Navedite naziv **i** neobavezni **opis** za izvor podataka, a zatim odaberite **Dalje**.

1. Odaberite jedan od [dostupnih poveznika](#available-power-query-data-sources). U ovom primjeru odabiremo **poveznik Tekst/CSV**.

1. Unesite potrebne pojedinosti u **Postavke veze** za odabrani poveznike i odaberite **Dalje** kako biste vidjeli pregled podataka.

1. Odaberite **Pretvori podatke**. U ovom ćete koraku dodati entitete u izvor podataka. Entiteti su skupovi podataka. Ako imate bazu podataka koja sadrži više skupova podataka, svaki je skup podataka vlastiti entitet.

1. Dijaloški **Power Query okvir - uređivanje upita** omogućuje pregled i sužavanje podataka. Entiteti koje su sustavi identificirali u vašem odabranom izvoru podataka prikazuju se u lijevom oknu.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Dijaloški okvir uređivanja upita":::

1. Podatke možete i pretvoriti. Odaberite entitet koji želite urediti ili pretvoriti. Za primjenu transformacija koristite mogućnosti u Power Query prozoru. Svaka transformacija navedena je u odjeljku **Primijenjeni koraci**. Power Query pruža brojne unaprijed izgrađene mogućnosti transformacije. Dodatne informacije potražite u odjeljku [Power Query Transformacije](/power-query/power-query-what-is-power-query#transformations).

   Preporučujemo da koristite sljedeće transformacije:

   - Ako unosite podatke iz CSV datoteke, prvi redak često sadrži zaglavlja. Idite na **Pretvorba** i odaberite **Koristi prvi redak kao zaglavlja**.
   - Provjerite je li vrsta podataka postavljena na odgovarajući način. Na primjer, za polja datuma odaberite vrstu datuma.

1. Da biste dodali dodatne entitete u izvor podataka u **dijaloškom okviru Uređivanje upita**, idite na **Polazno** i odaberite **Dohvati podatke**. Ponavljajte korake od 6 do 10 dok ne dodate sve entitete za ovu izvor podataka.

1. Odaberite **Spremi**. Otvorit **će se stranica Izvori** podataka koja prikazuje novi izvor podataka u **statusu Osvježavanje**.

### <a name="available-power-query-data-sources"></a>Dostupni Power Query izvori podataka

Pogledajte referencu [Power Query](/power-query/connectors/) poveznika za popis poveznika koje možete koristiti za uvoz podataka u Customer Insights.

Poveznici s kvačicom u stupcu **Customer Insights (Dataflows)** dostupni su za stvaranje novih izvora podataka na Power Query temelju. Pregledajte dokumentaciju određenog poveznika da biste saznali više o njegovim preduvjetima, [ograničenjima](/power-query/power-query-online-limits) upita i drugim detaljima.

## <a name="add-data-from-on-premises-data-sources"></a>Dodavanje podataka iz lokalnih izvora podataka

Unos podataka iz lokalno izvora podataka podržan je na Microsoft Power Platform temelju tokova podataka (PPDF-ova). Protok podataka u uvidima kupaca možete omogućiti pružanjem [URL-a Microsoft Dataverse](create-environment.md) okruženja prilikom postavljanja okruženja.

Izvori podataka stvoreni nakon povezivanja Dataverse okruženja s Customer Insights prema zadanim postavkama koriste [Power Platform tijekove](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) podataka. Tijekovi podataka podržavaju lokalnu povezivost pomoću pristupnika za podatke. Pomoću pristupnika podataka možete ukloniti i ponovno stvoriti izvore podataka koji su postojali prije Dataverse povezivanja [okruženja pomoću pristupnika](/data-integration/gateway/service-gateway-app) podataka lokalno.

Pristupnici za podatke iz postojećeg okruženja Power BI ili Power Apps bit će vidljivi i možete ih ponovno koristiti u Customer Insights. Stranica izvora podataka prikazuje veze do okruženja platforme Microsoft Power Platform u kojem možete pregledavati i konfigurirati lokalne pristupnike za podatke.

> [!IMPORTANT]
> Provjerite jesu li pristupnici ažurirani na najnoviju verziju. Možete instalirati ažuriranje i ponovno konfigurirati pristupnik iz upita prikazanog na zaslonu pristupnika izravno ili [preuzeti najnoviju verziju](https://powerapps.microsoft.com/downloads/). Ako ne koristite najnoviju verziju pristupnika, osvježavanje tijeka podataka ne uspijeva s porukama o pogreškama kao što **je Ključna riječ nije podržana: svojstva konfiguracije. Naziv parametra: ključna riječ**.

## <a name="edit-power-query-data-sources"></a>Uređivanje Power Query izvora podataka

> [!NOTE]
> Možda nećete moći izmijeniti izvore podataka koji se trenutačno koriste u jednom od postupaka aplikacije (npr. *segmentacija*, *podudaranje* ili *spajanje*).
>
> **Na stranici Postavke** možete pratiti napredak svakog od aktivnih procesa. Kada se postupak dovrši, možete se vratiti na stranicu **Izvori podataka** i unijeti promjene.

1. Idite na **Podaci** > **Izvor podataka**.

1. Uz izvor podataka koje želite ažurirati odaberite **Uredi**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. Primijenite promjene i transformacije u **Power Query dijaloškom okviru Uređivanje upita** kako je opisano u sekciji [Stvaranje novog izvor podataka](#create-a-new-data-source).

1. Nakon dovršetka uređivanja odaberite **Spremi** unutra Power Query da biste spremili promjene.
