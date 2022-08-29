---
title: Pregled objedinjavanja podataka
description: Pregledajte korake objedinjavanja podataka, stvorite jedinstvene profile kupaca i pregledajte rezultate
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303958"
---
# <a name="review-data-unification"></a>Pregled objedinjavanja podataka

Pregledajte sažetak promjena, stvorite jedinstveni profil i pregledajte rezultate.

## <a name="review-and-create-customer-profiles"></a>Pregledajte i stvorite profile klijenata

Ovaj posljednji korak u procesu ujedinjenja prikazuje sažetak koraka u procesu i pruža priliku za promjene prije stvaranja jedinstvenog profila.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Snimka zaslona pregleda i stvaranja korisničkih profila.":::

1. Odaberite **Uredi** u bilo kojem koraku objedinjavanja podataka da biste pregledali i unijeli bilo kakve promjene.

1. Ako ste zadovoljni odabirom, odaberite **Stvori profile** kupaca (ili **Stvori profile** računa za B-do-B). Stranica **Objedinjavanje prikazat** će se tijekom stvaranja jedinstvenog korisničkog profila.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Snimka zaslona stranice Objedinjavanje s pločicama na kojima se vidi u redu čekanja ili osvježavanje.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Dovršetak algoritma ujedinjenja potrebno je neko vrijeme i ne možete promijeniti konfiguraciju dok se ne dovrši.

## <a name="view-the-results-of-data-unification"></a>Prikaz rezultata objedinjavanja podataka

Nakon ujedinjenja, **stranica Objedinjavanje** > **podataka** prikazuje broj jedinstvenih profila kupaca (ili profila računa za B-do-B). Rezultati svakog koraka u procesu ujedinjenja prikazuju se na svakoj pločici. Na primjer, **polja** Izvor prikazuje broj mapiranih atributa (polja), a **Duplicirani zapisi** prikazuju broj pronađenih duplikata zapisa.

:::image type="content" source="media/m3_unified.png" alt-text="Snimka zaslona stranice Objedinjavanje podataka nakon ujedinjenja podataka.":::

> [!TIP]
> Pločica Odgovarajući uvjeti **prikazuje se samo ako je** odabrano više entiteta.

Preporučujemo da pregledate rezultate, posebno kvalitetu pravila [podudaranja i po potrebi ih doradite](data-unification-update.md#manage-match-rules).

Kada je potrebno, [promijenite postavke](data-unification-update.md) ujedinjenja i ponovno pokrenite jedinstveni profil.

### <a name="verify-output-entities-from-data-unification"></a>Provjera izlaznih entiteta iz objedinjavanja podataka

Idite na **Podatkovni** > **entiteti** da biste provjerili izlazne entitete.

Jedinstveni entitet korisničkog profila, nazvan *Kupac*, prikazuje se **u odjeljku Profili**. Prvi uspješan niz ujedinjenja stvara jedinstveni *entitet Klijenta*. Sva sljedeća izvođenja proširuju taj entitet.

Entiteti deduplikacije i konfakcije stvaraju se i prikazuju u **odjeljku Sustav**. Za svaki od izvornih entiteta stvara se deduplicirani entitet s nazivom **Deduplication_DataSource_Entity**. Entitet **ConflationMatchPairs** sadrži informacije o međuentitetskim podudaranjima.

Entitet izlazne vrijednosti uklanjanja duplikata sadrži sljedeće informacije:
- ID-jevi/ključevi
  - Polja primarnog ključa i alternativnog ID-a. Zamjensko polje ID-a sastoji se od svih alternativnih ID-ova identificiranih za zapis.
  - Polje Deduplication_GroupId prikazuje grupu ili klaster identificiran unutar entiteta koji grupira sve slične zapise na temelju navedenih polja uklanjanja duplikata. To se koristi u svrhu obrade sustava. Ako nisu navedena ručna pravila za uklanjanje duplikata i ako se primjenjuju pravila za uklanjanje duplikata koja je definirao sustav, ovo polje možda nećete pronaći u entitetu izlazne vrijednosti uklanjanja duplikata.
  - Deduplication_WinnerId: Ovo polje sadrži ID pobjednika iz identificiranih grupa ili klastera. Ako je Deduplication_WinnerId jednak vrijednosti primarnog ključa za zapis, to znači da je zapis pobjednički zapis.
- Polja koja se koriste za definiranje pravila za uklanjanje duplikata.
- Polja Pravilo i Ocjena označavaju koja su pravila za uklanjanja duplikata primijenjena i ocjenu koju vraća algoritam podudaranja.

## <a name="next-step"></a>Sljedeći korak

- Za B-do-B po želji izvršite [ujedinjenje](data-unification-contacts.md) kontakata.

- Za B-to-C konfigurirajte [aktivnosti](activities.md), [obogaćivanja](enrichment-hub.md), [Odnosi](relationships.md) ili [mjere](measures.md) kako biste stekli više uvida o svojim kupcima.

[!INCLUDE[footer-include](includes/footer-banner.md)]
