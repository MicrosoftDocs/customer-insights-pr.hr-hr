---
title: Ažuriranje postavki objedinjavanja
description: Ažurirajte duplicirana pravila, pravila podudaranja ili jedinstvena polja u postavkama ujedinjenja.
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: be399da9b98d8803d7d1a90f44a40e0d638a8d47
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755581"
---
# <a name="update-the-unification-settings"></a>Ažuriranje postavki objedinjavanja

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Da biste pregledali ili promijenili postavke objedinjavanja nakon stvaranja jedinstvenog profila, poduzmite sljedeće korake.

1. Otvorite Objedinjavanje **podataka** > **·**.

   :::image type="content" source="media/m3_unified.png" alt-text="Snimka zaslona stranice Objedinjavanje podataka nakon ujedinjenja podataka.":::

   > [!TIP]
   > Pločica Odgovarajući uvjeti **prikazuje se samo ako je** odabrano više entiteta.

1. Odaberite što želite ažurirati:
   - [Izvorišna polja](#edit-source-fields) za dodavanje entiteta ili atributa ili promjenu vrsta atributa.
   - [Duplicirani zapisi](#manage-deduplication-rules) za upravljanje pravilima deduplikacije ili preference spajanja.
   - [Odgovarajući uvjeti](#manage-match-rules) za ažuriranje odgovarajućih pravila u dva ili više entiteta.
   - [Objedinjena polja kupca](#manage-unified-fields) za kombiniranje ili isključivanje polja. Povezane profile možete grupirati i u klastere.

1. Nakon što unesete promjene, odaberite sljedeću opciju:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Snimka zaslona stranice Objedinjavanje podataka s istaknutim mogućnostima objedinjavanja.":::

   - Upute za ažuriranje jedinstvenog korisničkog profila (sa ili bez zavisnosti) potražite u članku [Pokretanje ažuriranja korisničkog profila](#run-updates-to-the-unified-customer-profile).
   - Da biste procijenili kvalitetu odgovarajućih uvjeta bez ažuriranja jedinstvenog profila, pročitajte članak [Pokretanje odgovarajućih uvjeta](#run-matching-conditions). Mogućnost **Pokreni samo** odgovarajuće uvjete ne prikazuje se za jedan entitet.

## <a name="edit-source-fields"></a>Uređivanje izvorišnih polja

Atribut ili entitet ne možete ukloniti ako su već ujedinjeni.

1. Na pločici Izvorna **polja** odaberite **Uređivanje**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Snimka zaslona stranice Izvorna polja na kojoj se vidi broj primarnih ključeva, mapiranih i nepreslikanih polja":::

   Prikazuje se broj preslikanih i nepreslikanih polja.

1. Odaberite **Odaberite entitete i polja** da biste dodali druge atribute ili entitete. S pomoću pretraživanja ili pomicanja pronađite i odaberite svoje atribute i entitete od interesa. Odaberite **Primijeni**.

1. Po želji možete promijeniti primarni ključ za entitet, vrste atributa i uključiti **ili isključiti inteligentno mapiranje**. Dodatne informacije potražite u odjeljku [Odabir primarnog ključa i semantičke vrste za atribute](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Odaberite **Dalje** da biste promijenili pravila deduplikacije ili Odaberite **Spremi i zatvorite** i vratite se da biste [ažurirali postavke](#update-the-unification-settings) objedinjavanja.

## <a name="manage-deduplication-rules"></a>Upravljanje pravilima deduplikacije

1. Na **pločici Dupliciraj zapise** odaberite **Uređivanje**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Snimka zaslona stranice Duplicirani zapisi na kojoj se prikazuje broj dupliciranih zapisa" lightbox="media/m3_duplicates_edit.png":::

   Broj pronađenih duplikata zapisa prikazuje se u odjeljku **Duplikati**. Stupac Zapisi **koji se dodjeljuju** prikazuje koji entiteti imaju duplicirane zapise i postotak dupliciranih zapisa.

1. Ako ste dodali obogaćeni entitet, odaberite **Koristi obogaćene entitete**. Dodatne informacije potražite u odjeljku [Obogaćivanje izvora podataka](data-sources-enrichment.md).

1. Da biste upravljali pravilima deduplikacije, odaberite neku od sljedećih mogućnosti:
   - **Stvaranje novog pravila**: Odaberite Dodaj **pravilo** u odgovarajućem entitetu. Dodatne informacije potražite u članku [Definiranje pravila](remove-duplicates.md#define-deduplication-rules) deduplikacije.
   - **Promjena uvjeta** pravila: Odaberite pravilo, a zatim **Uredite**. Promijenite polja, dodajte ili uklonite uvjete ili dodajte ili uklonite iznimke.
   - **Pretpregled**: Odaberite pravilo, a zatim **Pretpregled** da biste vidjeli rezultate posljednjeg izvođenja za ovo pravilo.
   - **Deaktiviraj pravilo**: Odaberite pravilo, a zatim **Deaktivirajte** da biste zadržali pravilo deduplikacije, a istovremeno ga isključili iz postupka podudaranja.
   - **Dupliciranje pravila**: Odaberite pravilo, a zatim **Dupliciraj** da biste stvorili slično pravilo s izmjenama.
   - **Brisanje pravila**: Odaberite pravilo, a zatim **izbrišite**.

1. Da biste promijenili preference spajanja, odaberite entitet. Preference možete promijeniti samo ako je stvoreno pravilo.
   1. Odaberite **Uređivanje preferenci spajanja** i promijenite **mogućnost Zapis da biste zadržali**.
   1. Da biste promijenili preference spajanja na pojedinačnim atributima entiteta, odaberite **Dodatno** i unesite potrebne promjene.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Snimka zaslona s naprednim preferencama spajanja koje prikazuju najnoviju e-poštu i najcjelovitiju adresu":::

   1. Odaberite **Gotovo**.

1. Odaberite **Dalje** da biste promijenili odgovarajuće uvjete ili Odaberite **Spremi i zatvori** te se vratite da biste [ažurirali postavke](#update-the-unification-settings) objedinjavanja.

## <a name="manage-match-rules"></a>Upravljanje pravilima uparivanja

Većinu parametara uparivanja možete ponovno konfigurirati i fino podesiti. Ne možete dodavati ni brisati entitete. Pravila podudaranja ne primjenjuju se na jedan entitet.

1. Na **pločici** Odgovarajući uvjeti **odaberite Uređivanje**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Snimka zaslona stranice Podudaranje s pravilima i uvjetima sa statistikom." lightbox="media/m3_match_edit.png":::

   Stranica prikazuje redoslijed podudaranja i definirana pravila te sljedeće statistike:
   - **Jedinstveni izvorni zapisi** pokazuje broj pojedinačnih izvornih zapisa koji su obrađeni u zadnjem izvođenju uparivanja.
   - **Upareni i neupareni zapisi** ističe koliko jedinstvenih zapisa ostaje nakon obrade pravila uparivanja.
   - **Samo upareni zapisi** prikazuje broj uparivanja u svim vašim parovima uparivanja.

1. Da biste vidjeli rezultate svih pravila i njihovih rezultata, odaberite **Prikaz zadnjeg izvođenja**. Prikazuju se rezultati, uključujući alternativne ID-ove kontakata. Rezultate možete preuzeti.

1. Da biste vidjeli rezultate i rezultate određenog pravila, odaberite pravilo, a zatim **Pretpregled**. Rezultati se prikazuju. Rezultate možete preuzeti.

1. Da biste vidjeli rezultate određenog uvjeta na pravilu, odaberite pravilo, a zatim **Uredite**. U oknu Uređivanje pod uvjetom odaberite **Pretpregled**. Rezultate možete preuzeti.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafički prikaz neusporedivih i podudarnih zapisa, uključujući popis podataka.":::

1. Ako ste dodali obogaćeni entitet, odaberite **Koristi obogaćene entitete**. Dodatne informacije potražite u odjeljku [Obogaćivanje izvora podataka](data-sources-enrichment.md).

1. Da biste upravljali pravilima, odaberite neku od sljedećih mogućnosti:
   - **Stvaranje novog pravila**: Odaberite Dodaj **pravilo** u odgovarajućem entitetu. Dodatne informacije potražite u članku [Definiranje pravila za parove podudaranja](match-entities.md#define-rules-for-match-pairs).
   - **Promijenite redoslijed pravila** ako ste definirali više pravila: Povucite i ispustite pravila u željeni redoslijed. Dodatne informacije potražite u odjeljku [Određivanje redoslijeda](match-entities.md#specify-the-match-order) podudaranja.
   - **Promjena uvjeta** pravila: Odaberite pravilo, a zatim **Uredite**. Promijenite polja, dodajte ili uklonite uvjete ili dodajte ili uklonite iznimke.
   - **Deaktiviraj pravilo**: Odaberite pravilo, a zatim **Deaktivirajte da biste zadržali** pravilo podudaranja, a zatim ga isključite iz postupka podudaranja.
   - **Dupliciranje pravila**: Odaberite pravilo, a zatim **Dupliciraj** da biste stvorili slično pravilo s izmjenama.
   - **Brisanje pravila**: Odaberite pravilo, a zatim **izbrišite**.

1. Odaberite **Dalje** da biste unijeli promjene u objedinjena polja ili odaberite **Spremi i zatvori** te se vratite da biste [ažurirali postavke](#update-the-unification-settings) objedinjavanja.

## <a name="manage-unified-fields"></a>Upravljanje jedinstvenim poljima

1. Na **pločici Sjedinjena polja** klijenta odaberite **Uredi**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Snimka zaslona s objedinjenim poljima klijenta":::

1. Pregledajte kombinirana i isključena polja i po potrebi napravite sve promjene. Dodajte ili uredite IDD-a klijenta ili profile grupa u klastere. Dodatne informacije potražite u članku [Objedinjavanje polja](merge-entities.md) kupaca.

1. Odaberite **Dalje** da biste pregledali postavke ujedinjenja i [ažurirali jedinstveni profil i ovisnosti ili odaberite](#run-updates-to-the-unified-customer-profile) Spremi i zatvori **i vratite** se na [Ažuriranje postavki](#update-the-unification-settings) ujedinjenja da biste unijeli dodatne promjene.

## <a name="run-matching-conditions"></a>Pokreni odgovarajuće uvjete

1. **Na stranici Objedinjavanje** > **podataka** odaberite **Pokreni samo** odgovarajuće uvjete.

   **Pločice Duplicirani zapisi** i **odgovarajući uvjeti** prikazuju **pločice u redu čekanja** ili **osvježavanje**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

1. Kada se postupak podudaranja dovrši, na **pločici Odgovarajući uvjeti** odaberite **Uredi**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Obrezana snimka zaslona ključnih mjernih podataka na stranici Uparivanje s brojevima i pojedinostima.":::

1. Upute za unos promjena potražite u člancima [Upravljanje pravilima](#manage-deduplication-rules) deduplikacije ili [Upravljanje pravilima](#manage-match-rules) podudaranja.

1. Ponovno pokrenite postupak podudaranja ili [pokrenite ažuriranja korisničkog profila](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Pokretanje ažuriranja za jedinstveni profil klijenta

1. **Na stranici Objedinjavanje** > **podataka** odaberite:

   - **Objedinjavanje korisničkih** profila: ažurira jedinstveni entitet korisničkog profila bez utjecaja na ovisnosti (kao što su obogaćivanja, segmenti ili mjere). Zavisni procesi se ne izvode, već će se osvježiti kako [je definirano u rasporedu](system.md#schedule-tab) osvježavanja.

   - **Objedinite profile i ovisnosti** klijenata: ažurira jedinstveni profil i sve ovisnosti. Svi se procesi automatski ponavljaju. Nakon završetka svih nizvodnih procesa, profil kupca odražava ažurirane podatke.

   Pločice **Duplicirani zapisi**, **Odgovarajući uvjeti** i **Objedinjeni klijenti** prikazuju **se u redu čekanja** ili **osvježavanje**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]
