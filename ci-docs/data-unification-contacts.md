---
title: Stvaranje jedinstvenog profila kontakta (pretpregled)
description: Prođite kroz postupak objedinjavanja podataka da biste stvorili jedan skup glavnih podataka kontakata.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305065"
---
# <a name="create-a-unified-contact-profile-preview"></a>Stvaranje jedinstvenog profila kontakta (pretpregled)

Nakon [objedinjavanja poslovnih računa](map-entities.md) po želji možete objediniti kontakte za te poslovne subjekte i povezati objedinjene kontakte s objedinjenim poslovnim subjektima. Proces objedinjavanja kontakata mapira podatke o kontaktima iz više izvora podataka, uklanja duplikate, podudara podatke među entitetima, postavlja semantičko mapiranje, stvara Odnosi između kontakata i poslovnih subjekata, a zatim stvara jedinstveni profil kontakta.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Prvih nekoliko koraka identično je koracima za objedinjavanje računa.

## <a name="prerequisites"></a>Preduvjeti

Zapisi o poslovnim subjektima i kontaktima moraju imati jedinstveni ključ (koji se naziva strani ključ) koji ih povezuje. Na primer, ID poslovnog subjekta koji postoji u zapisu o poslovnom kontaktu i zapisu kontakta koji povezuje poslovni subjekt i kontakt.

## <a name="preview-limitations"></a>Ograničenja pretpregleda

- Kontakti bez veze na račun se ispuštaju.
- Ako je račun dodijeljen, zapis pobjednika identificira se na temelju preferenci spajanja. Gubitnički zapisi nisu odabrani i stoga se ispuštaju. Kontakti povezani s gubitničkim zapisima se ispuštaju.
- Poslovni subjekt može imati više kontakata, ali kontakt je povezan s jednim računom.
- Atributi kontakta mapirani u koraku semantičkog mapiranja jedini su atributi koji se mogu prikazati na kartici Kupca. Međutim, dostupno je 17 atributa.

## <a name="select-source-fields"></a>Odabir izvorišnih polja

1. U odjeljku **Objedinjavanje kontakata (pretpregled)** odaberite **Prvi koraci**.

1. [Odaberite entitete i polja](map-entities.md) za izvore podataka kontakta, uključujući primarne ključeve i vrste atributa.

1. Odaberite **Dalje**.

## <a name="remove-duplicate-records"></a>Uklanjanje dupliciranih zapisa

1. Po želji [definirajte pravila](remove-duplicates.md) deduplikacije za odabrane entitete.

1. Odaberite **Dalje**.

## <a name="match-conditions"></a>Uskladi uvjete

1. [Definirajte redoslijed podudaranja i pravila](match-entities.md) za podudaranje među entitetima.

1. Odaberite **Dalje**.

## <a name="unify-contact-fields"></a>Objedinjavanje polja kontakata

1. [Kombinirajte i izuzimajte polja](merge-entities.md) kontakata.

1. Odaberite **Dalje**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Definirajte semantička polja za objedinjene kontakte

Ovaj korak u procesu ujedinjenja mapira vaša jedinstvena polja kontakta na semantičke vrste. U B-to-B kartice kupaca prikazuju račune. Kada je kartica odabrana, prikazuju se svi kontakti povezani s računom. Polja koja mapirate u ovom koraku su polja koja će se prikazati na karticama.

1. Odaberite semantičku vrstu koja se mapira na svako objedinjeno polje. Odaberite **Ništa** ako semantička vrsta nije dostupna.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Snimka zaslona stranice Semantičkih polja za definiranje semantičkih vrsta." lightbox="media/semantic_mapping.png":::

1. Nakon mapiranja svih objedinjenih polja odaberite **Dalje**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Postavljanje odnosa između kontakata i poslovnih subjekata

Ovaj korak u procesu ujedinjenja povezuje vaše podatke za kontakt s odgovarajućim podacima računa.

1. Za svaki entitet unesite sljedeće podatke:

   - **Vanjski ključ iz entiteta** kontakta: Odaberite atribut koji povezuje vaš kontaktni entitet s poslovnim subjektom.
   - **Entitet za poslovni kontakt**: Odaberite entitet poslovnog subjekta pridružen kontaktu.

   :::image type="content" source="media/contact_relationship.png" alt-text="Snimka zaslona stranice Odnos radi povezivanja entiteta kontakta i poslovnog subjekta.":::

1. Odaberite **Dalje**.

## <a name="review-contact-unification"></a>Pregled ujedinjenja kontakta

Pregledajte sažetak promjena, stvorite jedinstveni profil i pregledajte rezultate.

### <a name="review-and-create-contact-profiles"></a>Pregledajte i izradite profile kontakata

Ovaj posljednji korak u procesu ujedinjenja prikazuje sažetak koraka u procesu i pruža priliku za promjene prije stvaranja jedinstvenog profila kontakta.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Snimka zaslona pregleda i stvaranja profila kontakata.":::

1. Odaberite **Uredi** na bilo kojem koraku objedinjavanja kontakata da biste pregledali i unijeli bilo kakve promjene.

1. Ako ste zadovoljni odabirom, odaberite **Stvori profile** kontakata. Stranica **Objedinjavanje** prikazuje se tijekom stvaranja jedinstvenog profila kontakta.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Snimka zaslona stranice Objedinjavanje kontakata s pločicama na kojima se vidi u redu čekanja ili osvježavanje.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Dovršetak algoritma ujedinjenja potrebno je neko vrijeme i ne možete promijeniti konfiguraciju dok se ne dovrši.

### <a name="view-the-results-of-contact-unification"></a>Prikaz rezultata ujedinjenja kontakata

Nakon dovršetka objedinjavanja, stranica **Objedinjavanje** > **podataka** prikazuje broj jedinstvenih profila kontakata. Rezultati svakog koraka u procesu ujedinjenja prikazuju se na svakoj pločici. Na primjer, **polja** Izvor prikazuje broj mapiranih atributa (polja), a **Duplicirani zapisi** prikazuju broj pronađenih duplikata zapisa.

:::image type="content" source="media/unified_contacts.png" alt-text="Snimka zaslona stranice Objedinjavanje podataka nakon ujedinjenja kontakata.":::

> [!TIP]
> Pločica Odgovarajući uvjeti **prikazuje se samo ako je** odabrano više entiteta.

Preporučujemo da pregledate rezultate, posebno kvalitetu pravila [podudaranja i po potrebi ih doradite](data-unification-update.md#manage-match-rules).

Po potrebi [promijenite postavke](data-unification-update.md) objedinjavanja kontakata i ponovno pokrenite jedinstveni profil.

### <a name="verify-output-entities-from-data-unification"></a>Provjera izlaznih entiteta iz objedinjavanja podataka

Idite na **Podatkovni** > **entiteti** da biste provjerili izlazne entitete.

Jedinstveni entitet profila kontakta, nazvan *ContactProfile*, prikazuje se u **sekciji Semantički entiteti**. Prvim uspješnim izvođenjem ujedinjenja stvara se jedinstveni *entitet ContactProfile*. Sva sljedeća izvođenja proširuju taj entitet.

Entitet *ContactsCustomer* (pretpregled) stvara se i prikazuje u sekciji **Profili**. Ovaj entitet sadrži podatke o kontaktima bez veza na poslovne subjekte. Ovaj entitet se koristi kao ulaz u semantičko mapiranje i korake odnosa ujedinjenja kontakata.

Entiteti deduplikacije i konfakcije stvaraju se i prikazuju u **odjeljku Sustav**. Za svaki od izvornih entiteta stvara se deduplicirani entitet s nazivom **Deduplication_DataSource_Entity**. Entitet **ContactsConflationMatchPairs** sadrži informacije o međuentitetskim podudaranjima.

Entitet izlazne vrijednosti uklanjanja duplikata sadrži sljedeće informacije:
- ID-jevi/ključevi
  - Polja primarnog ključa i alternativnog ID-a. Zamjensko polje ID-a sastoji se od svih alternativnih ID-ova identificiranih za zapis.
  - Polje Deduplication_GroupId prikazuje grupu ili klaster identificiran unutar entiteta koji grupira sve slične zapise na temelju navedenih polja uklanjanja duplikata. To se koristi u svrhu obrade sustava. Ako nisu navedena ručna pravila za uklanjanje duplikata i ako se primjenjuju pravila za uklanjanje duplikata koja je definirao sustav, ovo polje možda nećete pronaći u entitetu izlazne vrijednosti uklanjanja duplikata.
  - Deduplication_WinnerId: Ovo polje sadrži ID pobjednika iz identificiranih grupa ili klastera. Ako je Deduplication_WinnerId jednak vrijednosti primarnog ključa za zapis, to znači da je zapis pobjednički zapis.
- Polja koja se koriste za definiranje pravila za uklanjanje duplikata.
- Polja Pravilo i Ocjena označavaju koja su pravila za uklanjanja duplikata primijenjena i ocjenu koju vraća algoritam podudaranja.

## <a name="next-step"></a>Sljedeći korak

Konfigurirajte [aktivnosti](activities.md), [obogaćivanje](enrichment-hub.md) ili [Odnosi](relationships.md) da biste stekli više uvida u svoje kontakte.
