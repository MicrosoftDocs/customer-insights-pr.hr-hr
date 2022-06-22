---
title: Pregled objedinjavanja podataka
description: Pregledajte korake objedinjavanja podataka, stvorite jedinstvene profile kupaca i pregledajte rezultate
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844077"
---
# <a name="review-data-unification"></a>Pregled objedinjavanja podataka

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Ovaj posljednji korak u procesu ujedinjenja prikazuje sažetak koraka u procesu i pruža priliku za promjene prije stvaranja jedinstvenog profila.

:::image type="content" source="media/m3_review.png" alt-text="Snimka zaslona pregleda i stvaranja korisničkih profila.":::

## <a name="review-the-data-unification-steps"></a>Pregled koraka objedinjavanja podataka

1. Odaberite **Uredi** u bilo kojem koraku objedinjavanja podataka da biste pregledali i unijeli bilo kakve promjene.

1. Ako ste zadovoljni odabirom, odaberite **Stvori profile kupaca**. Stranica **Objedinjavanje prikazat** će se tijekom stvaranja jedinstvenog korisničkog profila. Sve pločice osim **izvornih polja** prikazuju **stanje u redu čekanja** ili **osvježavanje**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Snimka zaslona stranice Objedinjavanje s pločicama na kojima se vidi u redu čekanja ili osvježavanje.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Dovršetak algoritma ujedinjenja potrebno je neko vrijeme i ne možete promijeniti konfiguraciju dok se ne dovrši. Kada se proces ujedinjenja dovrši, jedinstveni entitet profila klijenta, nazvan *Kupac*, naveden je na **stranici Entiteti** u **odjeljku Profili**. Prvi uspješan niz ujedinjenja stvara jedinstveni *entitet Klijenta*. Sva sljedeća izvođenja proširuju taj entitet.

## <a name="review-the-results-of-data-unification"></a>Pregled rezultata objedinjavanja podataka

Nakon ujedinjenja, stranica **Objedinjavanje** > **podataka** prikazuje broj jedinstvenih profila kupaca. Rezultati svakog koraka u procesu ujedinjenja prikazuju se na svakoj pločici. Na primjer, **polja** Izvor prikazuje broj mapiranih atributa (polja), a **Duplicirani zapisi** prikazuju broj pronađenih duplikata zapisa.

:::image type="content" source="media/m3_unified.png" alt-text="Snimka zaslona stranice Objedinjavanje podataka nakon ujedinjenja podataka.":::

> [!TIP]
> Pločica Odgovarajući uvjeti **prikazuje se samo ako je** odabrano više entiteta.

Preporučujemo da pregledate rezultate, posebno kvalitetu pravila [podudaranja i po potrebi ih doradite](data-unification-update.md#manage-match-rules).

Kada je potrebno, [promijenite postavke](data-unification-update.md) ujedinjenja i ponovno pokrenite jedinstveni profil.

## <a name="next-step"></a>Sljedeći korak

Konfigurirajte [aktivnosti](activities.md), [obogaćivanje](enrichment-hub.md), [Odnosi](relationships.md) ili [mjere](measures.md) da biste stekli više uvida o svojim klijentima.

[!INCLUDE[footer-include](includes/footer-banner.md)]
