---
title: Upotreba izvora podataka za unos podataka
description: Saznajte način uvoza podataka iz različitih izvora.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 9cf97c3e30d7501ba1f188a0e25a1a103299aa7f
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464040"
---
# <a name="data-sources-overview"></a>Pregled izvora podataka



Mogućnost uvida u ciljnu skupinu na platformi Dynamics 365 Customer Insights povezuje se s podacima iz širokog skupa izvora. Povezivanje s izvorom podataka često se naziva postupkom *gutanja podataka*. Nakon unosa podataka, možete ih [ujediniti](data-unification.md) i na njima raditi.

## <a name="add-a-data-source"></a>Dodaj izvor podataka

Pogledajte detaljne članke kako dodati izvor podataka, ovisno o opciji koju odaberete.

Možete dodati sljedeće izvore podataka:

- [Kroz desetke konektora Power Query](connect-power-query.md)
- [Iz mape Common Data Model](connect-common-data-model.md)
- [Iz svog vlastitog jezera aplikacije Microsoft Dataverse](connect-dataverse-managed-lake.md)
- [Azure Synapse Analytics Iz baze podataka](connect-synapse.md)

> [!NOTE]
> Ako koristite probnu verziju, odjeljak Načini uvoza sadrži **mogućnost biblioteke** podataka Customer Insights. Odaberite ovu mogućnost za odabir oglednog skupa podataka dostupnog za različite industrije. Dodatne informacije potražite na [Dynamics 365 Customer Insights suđenju](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Dodavanje podataka iz lokalnih izvora podataka

Unošenje podataka iz lokalnih izvora podataka u uvidima publike podržano je na temelju tijekova podataka platforme Microsoft Power Platform. Protok podataka u uvidima kupaca možete omogućiti pružanjem [URL-a Microsoft Dataverse](create-environment.md) okruženja prilikom postavljanja okruženja.

Izvori podataka stvoreni nakon povezivanja Dataverse okruženja s Customer Insights prema zadanim postavkama koriste [Power Platform tijekove](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) podataka. Tijekovi podataka podržavaju lokalnu povezivost pomoću pristupnika za podatke. Pomoću pristupnika podataka možete ukloniti i ponovno stvoriti izvore podataka koji su postojali prije Dataverse povezivanja [okruženja pomoću pristupnika](/data-integration/gateway/service-gateway-app) podataka lokalno.

Pristupnici za podatke iz postojećeg okruženja Power BI ili Power Apps bit će vidljivi i možete ih ponovno koristiti u Customer Insights. Stranica izvora podataka prikazuje veze do okruženja platforme Microsoft Power Platform u kojem možete pregledavati i konfigurirati lokalne pristupnike za podatke.

> [!IMPORTANT]
> Provjerite jesu li pristupnici ažurirani na najnoviju verziju. Možete instalirati ažuriranje i ponovno konfigurirati pristupnik iz upita prikazanog na zaslonu pristupnika izravno ili [preuzeti najnoviju verziju](https://powerapps.microsoft.com/downloads/). Ako ne koristite najnoviju verziju pristupnika, osvježavanje tijeka podataka ne uspijeva s porukama o pogreškama kao što **je Ključna riječ nije podržana: svojstva konfiguracije. Naziv parametra: ključna riječ**.

## <a name="review-ingested-data"></a>Pregled unijetih podataka
Ako vaše okruženje sadrži Power Platform tijekove podataka, stranica **Izvori** podataka navodi tri odjeljka: 
- **Zajedničko**: izvori podataka kojima mogu upravljati svi administratori customer insightsa. Power BI tokovi podataka, vlastiti račun za pohranu i prilaganje na upravljano Dataverse jezero podataka primjeri su zajedničkih izvora podataka.
- **Upravljam ja**: Power Platform tokovi podataka stvoreni i njima možete upravljati samo vi. Drugi administratori customer insightsa mogu samo pregledavati te tijekove podataka, ali ih ne mogu uređivati, osvježavati ili brisati.
- **Njima upravljaju drugi** korisnici: Power Platform tijekovi podataka koje su stvorili drugi administratori. Možete ih samo vidjeti. Navodi vlasnika toka podataka za kontakt za bilo kakvu pomoć.
> [!NOTE]
> Sve entitete mogu pregledavati i koristiti drugi korisnici. Kontekstualnost korisnika primjenjuje se samo na izvore podataka, a ne na entitete koji proizlaze iz tih tokova podataka.

Ako se ne Power Platform koriste tijekovi podataka, nećete vidjeti nijednu grupu ili sekciju. Stranica **Izvori** podataka sadrži samo popis svih izvora podataka.

Vidjet ćete naziv svakog unijetog izvor podataka, njegov status i zadnji put kada su podaci iz tog izvora osvježavani. Popis izvora podataka možete sortirati prema svakom stupcu.

> [!div class="mx-imgBorder"]
> ![Dodan je izvor podataka.](media/configure-data-datasource-added.png "Dodan je izvor podataka")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Učitavanje podataka može potrajati. Nakon uspješnog osvježavanja umetnuti podaci mogu se pregledati na stranici **Entiteti**. Dodatne informacije potražite u odjeljku [Entiteti](entities.md).

## <a name="refresh-a-data-source"></a>Osvježavanje izvora podataka

Izvori podataka mogu se osvježiti prema automatskom rasporedu ili ručno na zahtjev. 

Idite u odjeljak **Administrator** > **Sustav** > [**Raspored**](system.md#schedule-tab) za konfiguriranje zakazanih osvježavanja svih unesenih izvora podataka.

Da biste osvježili izvor podataka na zahtjev, slijedite korake u nastavku:

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Odaberite okomito trotočje pored izvora podataka koji želite osvježiti i odaberite **Osvježi** s padajućeg popisa.

3. Izvor podataka sada se pokreće za ručno osvježavanje. Osvježavanje izvora podataka ažurirat će i shemu entiteta i podatke za sve entitete navedene u izvoru podataka.

4. Odaberite **Zaustavljanje osvježavanja** ako želite otkazati postojeće osvježavanje i izvor podataka će se vratiti na posljednji status osvježavanja.

## <a name="delete-a-data-source"></a>Brisanje izvora podataka

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Odaberite okomito trotočje pored izvora podataka koji želite ukloniti i odaberite **Izbriši** s padajućeg izbornika.

3. Potvrdite brisanje.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
