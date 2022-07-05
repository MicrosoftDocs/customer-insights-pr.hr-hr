---
title: Pregled izvora podataka
description: Saznajte kako uvesti ili unijeti podatke iz različitih izvora.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: fbe44f655bdbc20ef7f0956022395e2dcb570adf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051444"
---
# <a name="data-sources-overview"></a>Pregled izvora podataka

Dynamics 365 Customer Insights pruža veze za dovođenje podataka iz širokog skupa izvora. Povezivanje s izvorom podataka često se naziva postupkom *gutanja podataka*. Nakon unosa podataka možete [objediniti, generirati](data-unification.md) uvide i aktivirati podatke za izgradnju personaliziranih iskustava.

## <a name="add-data-sources"></a>Dodavanje izvora podataka

Možete priložiti ili uvesti izvore podataka u Customer Insights. Veze u nastavku pružaju upute za dodavanje izvora podataka.

**Prilaganje izvor podataka**

Ako imate pripremljene podatke u jednom od Microsoftovih podatkovnih servisa Azure, Customer Insights se može jednostavno povezati s izvor podataka bez potrebe za ponovnim unosom podataka. Odaberite jednu od sljedećih mogućnosti:
- [Azure Data Lake Storage(csv ili parketne datoteke u mapi Uobičajeni podatkovni model)](connect-common-data-model.md)
- [Azure Synapse Analytics(Baze podataka na jezeru)](connect-synapse.md)
- [Microsoft Dataverse podatkovno jezero](connect-dataverse-managed-lake.md)

**Uvoz i pretvorba**

Ako koristite lokalne izvore podataka, Microsoftove podatke ili podatke drugih proizvođača, uvezite i transformirajte podatke pomoću Power Query poveznika.
- [Power Query Priključci](connect-power-query.md)

## <a name="review-data-sources"></a>Pregled izvora podataka

Ako je vaše okruženje konfigurirano za korištenje pohrane customer insights i koristite lokalne izvore podataka, koristite Power Platform protok podataka. Pomoću Power Platform tijekova podataka možete pregledavati zajedničke izvore podataka i izvore podataka kojima upravljaju drugi. Stranica **Izvori** podataka navodi izvore podataka u tri odjeljka:
- **Zajedničko**: izvori podataka kojima mogu upravljati svi administratori customer insightsa. Power Platform tokovi podataka, vlastiti račun za pohranu i prilaganje na upravljano Dataverse jezero podataka primjeri su zajedničkih izvora podataka.
- **Upravljam ja**: Power Platform tokovi podataka koje ste stvorili i kojima upravljate samo vi. Drugi administratori customer insightsa mogu samo pregledavati te tijekove podataka, ali ih ne mogu uređivati, osvježavati ili brisati.
- **Njima upravljaju drugi** korisnici: Power Platform tijekovi podataka koje su stvorili drugi administratori. Možete ih samo vidjeti. Navodi vlasnika toka podataka za kontakt za bilo kakvu pomoć.
> [!NOTE]
> Sve entitete mogu pregledavati i koristiti drugi korisnici. Iako su izvori podataka u vlasništvu korisnika koji ih je stvorio, dobivene entitete iz unosa podataka može koristiti svaki korisnik Customer Insightsa.

Ako vaše okruženje ne koristi Power Platform tijekove podataka, **stranica Izvori** podataka sadrži samo popis svih izvora podataka. Nema prikaza sekcija.

Idite na **izvore** > **podataka** da biste vidjeli naziv svakog unesenog izvor podataka, njegov status i posljednji put kada su podaci osvježeni za taj izvor. Popis izvora podataka možete sortirati prema svakom stupcu.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Dodan je izvor podataka.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Učitavanje podataka može potrajati. Nakon uspješnog osvježavanja umetnuti podaci mogu se pregledati na stranici **Entiteti**. Dodatne informacije potražite u odjeljku [Entiteti](entities.md).

## <a name="refresh-data-sources"></a>Osvježivanje izvora podataka

Izvori podataka mogu se osvježiti prema automatskom rasporedu ili ručno na zahtjev. [Lokalni izvori](connect-power-query.md#add-data-from-on-premises-data-sources) podataka osvježavaju se prema vlastitim rasporedima koji su postavljeni tijekom gutanja podataka. Za priložene izvore podataka unos podataka troši najnovije podatke dostupne iz tog izvor podataka.

Idite na **Raspored** > **administratorskih** > [**sustava**](system.md#schedule-tab) da biste konfigurirali sistemski zakazana osvježavanja unesenih izvora podataka.

Da biste osvježili izvor podataka na zahtjev, slijedite korake u nastavku:

1. Idite na **Podaci** > **Izvor podataka**.

1. Odaberite okomitu trotočje (&vellip;) pokraj izvor podataka želite osvježiti, a zatim na padajućem popisu odaberite **Osvježi**. Izvor podataka sada se pokreće za ručno osvježavanje. Osvježavanje izvora podataka ažurirat će i shemu entiteta i podatke za sve entitete navedene u izvoru podataka.

1. Odaberite **Zaustavljanje osvježavanja** ako želite otkazati postojeće osvježavanje i izvor podataka će se vratiti na posljednji status osvježavanja.

## <a name="delete-a-data-source"></a>Brisanje izvora podataka

Izvor podataka se može izbrisati samo ako se podaci ne koriste u bilo kojoj obradi kao što su ujedinjenje, uvidi, aktivacije ili izvoz.

1. Idite na **Podaci** > **Izvor podataka**.

2. Odaberite okomitu trotočje (&vellip;) pokraj izvor podataka želite ukloniti, a zatim na padajućem izborniku odaberite **Izbriši**.

3. Potvrdite brisanje.


[!INCLUDE [footer-include](includes/footer-banner.md)]
