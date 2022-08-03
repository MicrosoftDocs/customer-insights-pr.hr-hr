---
title: Povezivanje s Power Query izvor podataka (sadrži videozapis)
description: Unos podataka putem Power Query poveznika (sadrži videozapis).
ms.date: 07/26/2022
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
ms.openlocfilehash: 7af51ed04fbd28149ea501c58e6fe71b5fa6d4b6
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207036"
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

1. Odaberite **Pretvori podatke**.

1. Dijaloški **Power Query okvir - uređivanje upita** omogućuje pregled i sužavanje podataka. Entiteti koje su sustavi identificirali u vašem odabranom izvoru podataka prikazuju se u lijevom oknu.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Dijaloški okvir uređivanja upita":::

1. Podatke možete i pretvoriti. Odaberite entitet koji želite urediti ili pretvoriti. Za primjenu transformacija koristite mogućnosti u Power Query prozoru. Svaka transformacija navedena je u odjeljku **Primijenjeni koraci**. Power Query pruža brojne [unaprijed izgrađene mogućnosti transformacije](/power-query/power-query-what-is-power-query#transformations).

   Preporučujemo da koristite sljedeće transformacije:

   - Ako unosite podatke iz CSV datoteke, prvi redak često sadrži zaglavlja. Idite na **Pretvorba** i odaberite **Koristi prvi redak kao zaglavlja**.
   - Provjerite je li vrsta podataka postavljena na odgovarajući način. Na primjer, za polja datuma odaberite vrstu datuma.

1. Da biste dodali dodatne entitete u izvor podataka u **dijaloškom okviru Uređivanje upita**, idite na **Polazno** i odaberite **Dohvati podatke**. Ponavljajte korake od 5 do 10 dok ne dodate sve entitete za ovu izvor podataka. Ako imate bazu podataka koja sadrži više skupova podataka, svaki je skup podataka vlastiti entitet.

1. Odaberite **Spremi**. Otvorit **će se stranica Izvori** podataka koja prikazuje novi izvor podataka u **statusu Osvježavanje**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Učitavanje podataka može potrajati. Nakon uspješnog osvježavanja uneseni podaci mogu se pregledati sa [**stranice Entiteti**](entities.md).

> [!CAUTION]
> Izvor podataka na Power Query kojem se temelji kreira tijek [podataka u programu Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Nemojte mijenjati naziv tijeka podataka u centru za administratore Power Platform koji se koristi u odjeljku Customer Insights. Preimenovanje tijeka podataka uzrokuje probleme s referencama između izvor podataka Customer Insights i tijeka Dataverse podataka.

### <a name="available-power-query-data-sources"></a>Dostupni Power Query izvori podataka

Pogledajte referencu [Power Query](/power-query/connectors/) poveznika za popis poveznika koje možete koristiti za uvoz podataka u Customer Insights.

Poveznici s kvačicom u stupcu **Customer Insights (Dataflows)** dostupni su za stvaranje novih izvora podataka na Power Query temelju. Pregledajte dokumentaciju određenog poveznika da biste saznali više o njegovim preduvjetima, [ograničenjima](/power-query/power-query-online-limits) upita i drugim detaljima.

## <a name="add-data-from-on-premises-data-sources"></a>Dodavanje podataka iz lokalnih izvora podataka

Unos podataka iz lokalno izvora podataka podržan je na Microsoft Power Platform temelju tokova podataka (PPDF-ova). Protok podataka u uvidima kupaca možete omogućiti pružanjem [URL-a Microsoft Dataverse](create-environment.md) okruženja prilikom postavljanja okruženja.

Izvori podataka stvoreni nakon povezivanja Dataverse okruženja s Customer Insights prema zadanim postavkama koriste [Power Platform tijekove](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) podataka. Tijekovi podataka podržavaju lokalnu povezivost pomoću pristupnika za podatke. Pomoću pristupnika podataka možete ukloniti i ponovno stvoriti izvore podataka koji su postojali prije Dataverse povezivanja [okruženja pomoću pristupnika](/data-integration/gateway/service-gateway-app) podataka lokalno.

Pristupnici podataka iz postojećeg Power BI ili Power Apps okruženja bit će vidljivi i možete ih ponovno koristiti u customer insights. Stranica izvora podataka prikazuje veze do okruženja platforme Microsoft Power Platform u kojem možete pregledavati i konfigurirati lokalne pristupnike za podatke.

> [!IMPORTANT]
> Provjerite jesu li pristupnici ažurirani na najnoviju verziju. Možete instalirati ažuriranje i ponovno konfigurirati pristupnik iz upita prikazanog na zaslonu pristupnika izravno ili [preuzeti najnoviju verziju](https://powerapps.microsoft.com/downloads/). Ako ne koristite najnoviju verziju pristupnika, osvježavanje tijeka podataka ne uspijeva s porukama o pogreškama kao što **je Ključna riječ nije podržana: svojstva konfiguracije. Naziv parametra: ključna riječ**.
>
> Pogreške s lokalno pristupnicima podataka u customer insights često su uzrokovane problemima s konfiguracijom. Dodatne informacije o otklanjanju poteškoća s pristupnicima podataka potražite u članku [Otklanjanje poteškoća s lokalno pristupnikom podataka](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Uređivanje Power Query izvora podataka

> [!NOTE]
> Možda neće biti moguće izmijeniti izvore podataka koji se trenutno koriste u jednom od procesa aplikacije (na primjer segmentacija ili objedinjavanje podataka).
>
> **Na stranici Postavke** možete pratiti napredak svakog od aktivnih procesa. Kada se postupak dovrši, možete se vratiti na stranicu **Izvori podataka** i unijeti promjene.

1. Idite na **Podaci** > **Izvor podataka**.

1. Uz izvor podataka koje želite ažurirati odaberite **Uredi**.

1. Primijenite promjene i transformacije u **Power Query dijaloškom okviru Uređivanje upita** kako je opisano u sekciji [Stvaranje novog izvor podataka](#create-a-new-data-source).

1. Odaberite **Spremi** da biste primijenili promjene i vratili se na **stranicu Izvori** podataka.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
