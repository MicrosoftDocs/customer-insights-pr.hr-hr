---
title: Obogaćivanje za izvore podataka (pretpregled)
description: Obogatite izvore podataka prije nego što prođete kroz postupak objedinjavanja podataka.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: fb97b721cc82ccd23cfd1df74a0712b8fc277b8a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082109"
---
# <a name="enrichment-for-data-sources-preview"></a>Obogaćivanje za izvore podataka (pretpregled)

Koristite podatke iz izvora kao što su Microsoft i drugi partneri da biste obogatili svoje korisničke podatke prije ujedinjenja podataka. Izvor podataka obogaćivanja pomažu u stvaranju veće cjelovitosti i kvalitete podataka koji mogu pomoći u postizanju boljih rezultata nakon što objedinite svoje podatke. Na primjer, korištenje normaliziranog i standardiziranog formata za adrese povećava kvalitetu rezultata podudaranja. Popis podržanih obogaćivanja potražite u podržanim [mogućnostima obogaćivanja izvor podataka](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Obogatite izvor podataka

Za stvaranje ili uređivanje obogaćenja morate imati suradnik ili administratorske dozvole. Za dodatne informacije pogledajte [Dozvole](permissions.md).  

1. Otvorite Objedinjavanje **podataka** > **·**. Odaberite entitet koji želite obogatiti i odaberite jedan atribut kao primarni ključ entiteta. Dodatne informacije potražite u odjeljku [Odabir primarnog ključa](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Idite na **Podaci** > **Izvor podataka**.

1. Odaberite okomitu trotočje (&vellip;) pokraj izvor podataka želite obogatiti i odaberite **Obogaćivanje**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Stranica izvori podataka s istaknutim obogaćenim":::

   Na **kartici Discover** prikazuju se podržane [mogućnosti](#supported-data-source-enrichments) obogaćivanja izvor podataka.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Stranica za obogaćivanje izvora podataka.":::

1. Odaberite **Obogati moje podatke** da biste konfigurirali izvor podataka obogaćivanje. Naziv izlaznog entiteta automatski se popunjava.

## <a name="supported-data-source-enrichments"></a>Podržana izvor podataka obogaćivanja

Sljedeća obogaćivanja trenutno su dostupna za izvore podataka. Pregledajte detaljne korake za obogaćivanje da biste saznali kako ga konfigurirati.

- [Poboljšane adrese](enrichment-enhanced-addresses.md)
- [Poboljšani podaci tvrtke](enrichment-enhanced-company-data.md)
- [Podaci o identitetu s LiveRampa](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Upravljanje postojećim izvor podataka obogaćenjima

Idite na karticu **Moja obogaćivanja** da biste vidjeli sva konfigurirana obogaćivanja.

Odaberite obogaćivanje da biste vidjeli dostupne mogućnosti. Također možete odabrati okomitu trotočje (&vellip;) na stavci popisa da biste vidjeli mogućnosti. Ako ste konfigurirali nekoliko obogaćivanja, možete ih brzo pronaći pomoću okvira za pretraživanje.

Možete pregledavati, uređivati, izvoditi ili brisati izvor podataka obogaćivanja. Dodatne informacije potražite u članku [Upravljanje postojećim obogaćivanjima](enrichment-hub.md).
