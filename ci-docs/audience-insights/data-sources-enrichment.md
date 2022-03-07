---
title: Izvor podataka obogaćivanje
description: Obogatite izvore podataka prije nego što prođete kroz postupak ujedinjenja podataka.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: eebaaf18795e80dd1ba16a15a23844d685c94c6e
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373057"
---
# <a name="enrichment-for-data-sources-preview"></a>Obogaćivanje izvora podataka (pretpregled)

Koristite podatke iz izvora kao što su Microsoft i drugi partneri da biste obogatili svoje korisničke podatke prije ujedinjenja podataka. Izvor podataka obogaćivanja pomažu u stvaranju veće cjelovitosti i kvalitete podataka koji mogu pomoći u postizanju boljih rezultata nakon što ujedinite svoje podatke. Na primjer, korištenje normaliziranog i standardiziranog formata za adrese povećava kvalitetu rezultata podudaranja. Popis podržanih obogaćenja potražite u [odjeljku Podržane mogućnosti obogaćivanja izvor podataka](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Obogatite izvor podataka

Da biste stvorili ili uredili obogaćivanja, morate imati suradnik ili administratorske dozvole. Za dodatne informacije pogledajte [Dozvole](permissions.md).  

1. Idite na **DataUnify** > **·**. Odaberite entitet koji želite obogatiti i odaberite jedan atribut kao primarni ključ za entitet. Dodatne informacije potražite u članku [Odabir primarnog ključa](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Idite na **Podaci** > **Izvor podataka**.
 
1. Odaberite okomitu trotočje pokraj izvor podataka želite obogatiti, a zatim odaberite **Obogati**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Stranica za obogaćivanje izvora podataka.":::

   Kartica **Discover** prikazuje podržane mogućnosti [obogaćivanja](#supported-data-source-enrichments) izvor podataka.

1. Odaberite **Obogati moje podatke** da biste konfigurirali izvor podataka obogaćivanje. Naziv izlaznog entiteta automatski se popunjava.

## <a name="supported-data-source-enrichments"></a>Podržana izvor podataka obogaćivanja

Za izvore podataka trenutno su dostupna sljedeća obogaćivanja. Pregledajte detaljne korake za obogaćivanje da biste saznali kako ga konfigurirati.

- [Poboljšane adrese](enrichment-enhanced-addresses.md)
- [Podaci o identitetu iz LiveRampa](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Upravljanje postojećim izvor podataka obogaćivanjima

Idite na karticu **Moja obogaćivanja** da biste vidjeli sva konfigurirana obogaćivanja.

Odaberite obogaćivanje da biste vidjeli dostupne mogućnosti. Možete odabrati i elipsu (...) na stavci popisa da biste vidjeli mogućnosti. Ako ste konfigurirali nekoliko obogaćivanja, možete ih brzo pronaći pomoću okvira za pretraživanje.

Možete pregledavati, uređivati, izvoditi ili brisati izvor podataka obogaćivanje. Dodatne informacije potražite u članku [Upravljanje postojećim obogaćenjima](enrichment-hub.md).
