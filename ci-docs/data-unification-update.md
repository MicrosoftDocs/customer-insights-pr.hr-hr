---
title: Ažuriranje postavki objedinjavanja klijenta, poslovnog subjekta ili kontakta
description: Ažurirajte dvostruka pravila, pravila podudaranja ili jedinstvena polja u postavkama ujedinjenja klijenta ili računa.
ms.date: 08/26/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392462"
---
# <a name="update-unification-settings"></a>Ažuriraj postavke objedinjavanja

Da biste pregledali ili promijenili postavke objedinjavanja nakon stvaranja jedinstvenog profila, poduzmite sljedeće korake.

1. Otvorite Objedinjavanje **podataka** > **·**.

   Za pojedinačne kupce (B-do-C) **stranica Objedinjavanje** prikazuje broj jedinstvenih profila i pločica kupaca za svaki od koraka ujedinjenja.

   :::image type="content" source="media/m3_unified.png" alt-text="Snimka zaslona stranice Objedinjavanje podataka nakon ujedinjenja podataka." lightbox="media/m3_unified.png":::

   Za poslovne račune (B-do-B) **stranica Objedinjavanje** prikazuje broj jedinstvenih profila računa i pločica za svaki od koraka objedinjavanja računa. Ako su kontakti ujedinjeni, prikazat će se broj jedinstvenih profila kontakata i pločica za svaki od koraka objedinjavanja kontakata. Odaberite odgovarajuću pločicu u odjeljku **Objedinjavanje poslovnih subjekata** ili **Objedinjavanje kontakata (pretpregled),** ovisno o tome što želite ažurirati.

   :::image type="content" source="media/b2b_unified.png" alt-text="Snimka zaslona stranice Objedinjavanje podataka nakon objedinjavanja podataka o računu i kontaktima." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > Pločica Odgovarajući uvjeti **prikazuje se samo ako je** odabrano više entiteta.

1. Odaberite što želite ažurirati:
   - [Izvorišna polja](#edit-source-fields) za dodavanje atributa ili entiteta ili promjenu vrsta atributa. Upute za uklanjanje atributa potražite u članku [Uklanjanje jedinstvenog polja](#remove-a-unified-field). Upute za uklanjanje entiteta potražite u članku [Uklanjanje jedinstvenog entiteta](#remove-a-unified-entity).
   - [Duplicirani zapisi](#manage-deduplication-rules) za upravljanje pravilima deduplikacije ili preference spajanja.
   - [Odgovarajući uvjeti](#manage-match-rules) za ažuriranje odgovarajućih pravila u dva ili više entiteta.
   - [Objedinjena polja kupca](#manage-unified-fields) za kombiniranje ili isključivanje polja. Povezane profile možete grupirati i u klastere.
   - [Semantička polja](#manage-semantic-fields-for-unified-contacts) za upravljanje semantičkim tipovima za jedinstvena polja kontakata.
   - [Odnosi](#manage-contact-and-account-relationships) da biste upravljali odnosom kontakta s poslovnim subjektom.

1. Nakon što unesete promjene, odaberite sljedeću opciju:

   - [Pokrenite odgovarajuće uvjete](#run-matching-conditions) da biste brzo procijenili kvalitetu odgovarajućih uvjeta (pravila deduplikacije i podudaranja) bez ažuriranja jedinstvenog profila. Mogućnost **Pokreni samo** odgovarajuće uvjete ne prikazuje se za jedan entitet.
   - [Objedinite](#run-updates-to-the-unified-profile) profile kako biste pokrenuli odgovarajuće uvjete i ažurirali jedinstveni entitet profila bez utjecaja na ovisnosti (kao što su obogaćivanja, segmenti ili mjere). Zavisni procesi se ne izvode, već će se osvježiti kako [je definirano u rasporedu](schedule-refresh.md) osvježavanja.
   - [Objedinite profile i ovisnosti](#run-updates-to-the-unified-profile) za pokretanje odgovarajućih uvjeta, ažurirajte jedinstveni entitet profila i ažurirajte sve ovisnosti (kao što su obogaćivanja, segmenti ili mjere). Svi se procesi automatski ponavljaju. U B-do-B ujedinjenje se provodi i na subjektima za poslovni subjekt i na subjektima za kontakt koji ažuriraju jedinstvene profile.

## <a name="edit-source-fields"></a>Uređivanje izvorišnih polja

1. Na pločici Izvorna **polja** odaberite **Uređivanje**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Snimka zaslona stranice Izvorna polja na kojoj se vidi broj primarnih ključeva, mapiranih i nepreslikanih polja":::

   Prikazuje se broj preslikanih i nepreslikanih polja.

1. Da biste dodali druge atribute ili entitete, odaberite **Odaberi entitete i polja**.

1. Po želji možete promijeniti primarni ključ za entitet, vrste atributa i uključiti **ili isključiti inteligentno mapiranje**. Dodatne informacije potražite u odjeljku [Odabir izvorišnih polja](map-entities.md).

1. Odaberite **Dalje** da biste promijenili pravila deduplikacije ili Spremi **i zatvorite** te se vratite na [Ažuriraj postavke](#update-unification-settings) objedinjavanja.

### <a name="remove-a-unified-field"></a>Uklanjanje jedinstvenog polja

Da biste uklonili jedinstveno polje, polje se mora ukloniti iz svih ovisnosti kao što su segmenti, mjere, obogaćivanja ili Odnosi.

1. Nakon uklanjanja svih zavisnosti za polje idite na **Objedinjavanje** > **podataka**.

1. Na **pločici Sjedinjena polja** klijenta odaberite **Uredi**.

1. Odaberite sva pojavljivanja polja, a zatim **izostavi**.

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="Snimka zaslona stranice s objedinjenim poljima na kojoj su prikazana odabrana polja i gumb Isključi":::

1. Odaberite **Gotovo** da biste potvrdili, a zatim Spremi **i zatvori**.

   > [!TIP]
   > Ako se prikaže poruka "Nije moguće spremiti objedinite. Navedeni resurs ne može se mijenjati ili brisati zbog silaznih ovisnosti", a polje se i dalje koristi u silaznoj ovisnosti.

1. Ako se polje koristi u pravilu za duplicirane zapise ili odgovarajuće uvjete, poduzmite sljedeće korake. Inače prijeđite na sljedeći korak.
   1. Na **pločici Dupliciraj zapise** odaberite **Uređivanje**.
   1. Uklonite polje iz svih pravila u kojima se koristi, ako postoji, a zatim odaberite **Dalje**.
   1. **Na stranici Odgovarajući uvjeti** uklonite polje iz svih pravila u kojima se koristi, ako postoje, a zatim odaberite **Spremi i zatvori**.
   1. Odaberite **Objedini objedinjavanje** > **profila i ovisnosti** klijenata. Pričekajte da se ujedinjenje dovrši prije nego što prijeđete na sljedeći korak.

1. Na pločici Izvorna **polja** odaberite **Uređivanje**.

1. Odaberite **Odaberite entitete i polja** i poništite potvrdni okvir pokraj svakog pojavljivanja polja.

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="Snimka zaslona dijaloškog okvira Odabir entiteta i polja s prikazanim očišćenim potvrdnim okvirima":::

1. Odaberite **Primijeni**.

1. Odaberite **Spremi i zatvori**.

1. Odaberite **Objedini objedinjavanje** > **profila i ovisnosti** klijenata da biste ažurirali jedinstveni profil.

### <a name="remove-a-unified-entity"></a>Uklanjanje jedinstvenog entiteta

Da bi se uklonio entitet koji je ujedinjen, entitet mora biti uklonjen iz svih ovisnosti kao što su segmenti, mjere, obogaćivanja ili Odnosi.

1. Nakon uklanjanja svih ovisnosti za entitet, idite na **Objedinjavanje** > **podataka**.

1. Na **pločici Sjedinjena polja** klijenta odaberite **Uredi**.

1. Odaberite sva polja za entitet, a zatim **izostavi**.

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="Snimka zaslona s objedinjenim poljima sa svim poljima za odabrani entitet i gumb Isključi":::

1. Odaberite **Gotovo** da biste potvrdili, a zatim Spremi **i zatvori**.

   > [!TIP]
   > Ako se prikaže poruka "Nije moguće spremiti objedinite. Navedeni resurs nije moguće izmijeniti ili izbrisati zbog silaznih ovisnosti", tada se entitet i dalje koristi u silaznoj ovisnosti.

1. Na **pločici Dupliciraj zapise** odaberite **Uređivanje**.

1. Uklonite sva pravila iz entiteta, ako postoje, a zatim odaberite **Dalje**.

1. **Na stranici Odgovarajući uvjeti** odaberite entitet, a zatim **Izbriši**.

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="Snimka zaslona s odgovarajućim uvjetima s odabranim entitetom i gumbom Izbriši":::

1. Odaberite **Spremi i zatvori**.

1. Na pločici Izvorna **polja** odaberite **Uređivanje**.

1. Odaberite **Odaberite entitete i polja** i poništite potvrdni okvir pokraj entiteta.

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="Snimka zaslona dijaloškog okvira Odabir entiteta i polja s poništenim potvrdnim okvirom entiteta":::

1. Odaberite **Primijeni**.

1. Odaberite **Spremi i zatvori**.

1. Odaberite **Objedini objedinjavanje** > **profila i ovisnosti** klijenata da biste ažurirali jedinstveni profil.

## <a name="manage-deduplication-rules"></a>Upravljanje pravilima deduplikacije

1. Na **pločici Dupliciraj zapise** odaberite **Uređivanje**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Snimka zaslona stranice Duplicirani zapisi na kojoj se prikazuje broj dupliciranih zapisa" lightbox="media/m3_duplicates_edit.png":::

   Broj pronađenih duplikata zapisa prikazuje se u odjeljku **Duplikati**. Stupac Zapisi **koji se dodjeljuju** prikazuje koji entiteti imaju duplicirane zapise i postotak dupliciranih zapisa.

1. Da biste koristili obogaćeni entitet, odaberite **Koristi obogaćene entitete**. Dodatne informacije potražite u odjeljku [Obogaćivanje izvora](data-sources-enrichment.md) podataka.

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

   1. Odaberite **Gotovo**.

1. Odaberite **Dalje** da biste promijenili odgovarajuće uvjete ili odaberite **Spremi i zatvori** te se vratite na [Ažuriraj postavke](#update-unification-settings) objedinjavanja.

## <a name="manage-match-rules"></a>Upravljanje pravilima uparivanja

Većinu parametara uparivanja možete ponovno konfigurirati i fino podesiti. Ne možete dodavati ni brisati entitete. Pravila podudaranja ne primjenjuju se na jedan entitet.

1. Na **pločici** Odgovarajući uvjeti **odaberite Uređivanje**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Snimka zaslona stranice Podudaranje s pravilima i uvjetima sa statistikom." lightbox="media/m3_match_edit.png":::

   Stranica prikazuje redoslijed podudaranja i definirana pravila te sljedeće statistike:
   - **Jedinstveni izvorišni zapisi** prikazuju broj pojedinačnih izvornih zapisa obrađenih u posljednjem izvođenju podudaranja.
   - **Podudarni i neusporedivi zapisi** ističu koliko jedinstvenih zapisa ostaje nakon obrade pravila podudaranja.
   - **Podudarni zapisi prikazuju samo** broj podudaranja u svim parovima vaših podudaranja.

1. Da biste vidjeli rezultate svih pravila i njihovih rezultata, odaberite **Prikaz zadnjeg izvođenja**. Prikazuju se rezultati, uključujući alternativne ID-ove kontakata. Rezultate možete preuzeti.

1. Da biste vidjeli rezultate i rezultate određenog pravila, odaberite pravilo, a zatim **Pretpregled**. Rezultati se prikazuju. Rezultate možete preuzeti.

1. Da biste vidjeli rezultate određenog uvjeta na pravilu, odaberite pravilo, a zatim **Uredite**. U oknu Uređivanje pod uvjetom odaberite **Pretpregled**. Rezultate možete preuzeti.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafički prikaz neusporedivih i podudarnih zapisa, uključujući popis podataka.":::

1. Ako ste dodali obogaćeni entitet, odaberite **Koristi obogaćene entitete**. Dodatne informacije potražite u odjeljku [Obogaćivanje izvora](data-sources-enrichment.md) podataka.

1. Da biste upravljali pravilima, odaberite neku od sljedećih mogućnosti:
   - **Stvaranje novog pravila**: Odaberite Dodaj **pravilo** u odgovarajućem entitetu. Dodatne informacije potražite u članku [Definiranje pravila za parove podudaranja](match-entities.md#define-rules-for-match-pairs).
   - **Promijenite redoslijed pravila** ako ste definirali više pravila: Povucite i ispustite pravila u željeni redoslijed. Dodatne informacije potražite u odjeljku [Određivanje redoslijeda](match-entities.md#specify-the-match-order) podudaranja.
   - **Promjena uvjeta** pravila: Odaberite pravilo, a zatim **Uredite**. Promijenite polja, dodajte ili uklonite uvjete ili dodajte ili uklonite iznimke.
   - **Deaktiviraj pravilo**: Odaberite pravilo, a zatim **Deaktivirajte da biste zadržali** pravilo podudaranja, a zatim ga isključite iz postupka podudaranja.
   - **Dupliciranje pravila**: Odaberite pravilo, a zatim **Dupliciraj** da biste stvorili slično pravilo s izmjenama.
   - **Brisanje pravila**: Odaberite pravilo, a zatim **izbrišite**.

1. Odaberite **Dalje** da biste unijeli promjene u jedinstvena polja ili odaberite **Spremi i zatvori** te se vratite na [Ažuriraj postavke](#update-unification-settings) objedinjavanja.

## <a name="manage-unified-fields"></a>Upravljanje jedinstvenim poljima

1. Na **pločici Sjedinjena polja** klijenta odaberite **Uredi**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Snimka zaslona s objedinjenim poljima klijenta":::

1. Pregledajte kombinirana i isključena polja i po potrebi napravite sve promjene. Dodajte ili uredite IDD-a klijenta ili profile grupa u klastere. Dodatne informacije potražite u članku [Objedinjavanje polja](merge-entities.md) kupaca.

1. Za klijente ili račune odaberite **Dalje** da biste pregledali i [ažurirali jedinstveni profil i ovisnosti](#run-updates-to-the-unified-profile). Ili odaberite **Spremi i zatvorite** i vratite se na [Ažuriraj postavke](#update-unification-settings) ujedinjenja da biste unijeli dodatne promjene.

   Za kontakte odaberite **Dalje** da biste upravljali semantičkim poljima. Ili odaberite **Spremi i zatvorite** i vratite se na [Ažuriraj postavke](#update-unification-settings) ujedinjenja da biste unijeli dodatne promjene.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Upravljanje semantičkim poljima za objedinjene kontakte

1. Na pločici **Semantička polja** odaberite **Uredi**.

1. Da biste promijenili semantičku vrstu za objedinjeno polje, odaberite novu vrstu. Dodatne informacije potražite u odjeljku [Definiranje semantičkih polja za objedinjene kontakte](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Odaberite **Dalje** da biste upravljali odnosom računa i kontakta ili Odaberite **Spremi i zatvori** te se vratite na [Ažuriraj postavke](#update-unification-settings) objedinjavanja da biste unijeli dodatne promjene.

## <a name="manage-contact-and-account-relationships"></a>Upravljanje Odnosi kontakta i računa

1. Na **pločici** Odnosi **odaberite Uređivanje**.

1. Da biste promijenili odnos kontakta i poslovnog subjekta, promijenite bilo koju od sljedećih informacija:

   - **Vanjski ključ iz entiteta** kontakta: Odaberite atribut koji povezuje vaš kontaktni entitet s poslovnim subjektom.
   - **Entitet za poslovni kontakt**: Odaberite entitet poslovnog subjekta pridružen kontaktu.

1. Odaberite **Dalje** da biste pregledali postavke ujedinjenja i [ažurirali jedinstveni profil i ovisnosti ili odaberite](#run-updates-to-the-unified-profile) Spremi i zatvori **i vratite** se na [Ažuriraj postavke](#update-unification-settings) ujedinjenja da biste unijeli dodatne promjene.

## <a name="run-matching-conditions"></a>Pokreni odgovarajuće uvjete

Pokretanje odgovarajućih uvjeta pokreće samo pravila deduplikacije i podudaranja te ažurira *entitete Deduplication_* i *ConflationMatchPair*.

1. **Na stranici Objedinjavanje** > **podataka** odaberite **Pokreni samo** odgovarajuće uvjete.

   Pločice **Duplicirani zapisi** i **odgovarajući uvjeti** prikazuju **status u redu čekanja** ili **osvježavanje**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Kada se postupak podudaranja dovrši, na **pločici Odgovarajući uvjeti** odaberite **Uredi**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Obrezana snimka zaslona ključnih mjernih podataka na stranici Uparivanje s brojevima i pojedinostima.":::

1. Upute za unos promjena potražite u člancima [Upravljanje pravilima](#manage-deduplication-rules) deduplikacije ili [Upravljanje pravilima](#manage-match-rules) podudaranja.

1. Ponovno pokrenite postupak podudaranja ili [pokrenite ažuriranja profila](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Pokretanje ažuriranja za objedinjeni profil

- Da biste pokrenuli odgovarajuće uvjete i ažurirali jedinstveni entitet *profila bez* utjecaja na ovisnosti (kao što su kartice kupaca, obogaćenja, segmenti ili mjere), odaberite **Objedini profile** kupaca. Za račune odaberite **Objedinjavanje računa** > **Objedinjavanje profila**. Za kontakte odaberite **Objedinjavanje kontakata (pretpregled)** > **Objedinjavanje profila**. Zavisni procesi se ne izvode, već će se osvježiti kako [je definirano u rasporedu](schedule-refresh.md) osvježavanja.
- Da biste pokrenuli odgovarajuće uvjete, ažurirajte objedinjeni profil i pokrenite sve zavisnosti, odaberite **Objediniraj profile i ovisnosti** klijenata. Svi se procesi automatski ponavljaju. Za poslovne subjekte i kontakte odaberite **Objedinjavanje računa** > **Objedinjavanje profila i ovisnosti**. Odgovarajući uvjeti pokreću se i za poslovne subjekte i za kontakte koji ažuriraju objedinjene profile i sve ostale zavisnosti.

Sve pločice osim **izvornih polja** prikazuju **red čekanja** ili **osvježavanje**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Rezultati uspješnog izvođenja prikazuju se **na stranici Objedinjavanje** koja prikazuje broj jedinstvenih profila.
