---
title: Objedinjavanje polja klijenata radi ujedinjenja podataka
description: Spojite entitete da biste stvorili objedinjene profile klijenata.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: a6f29c4985ee274207d122fb1bd76d97b98613b6
ms.sourcegitcommit: 10dcfc32eaf8ec0903be96136dca7bb4e250276a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/01/2022
ms.locfileid: "9213573"
---
# <a name="unify-customer-fields-for-data-unification"></a>Objedinjavanje polja klijenata radi ujedinjenja podataka

U ovom koraku postupka ujedinjenja odaberite i izuzmite atribute za spajanje unutar jedinstvenog entiteta profila. Na primjer, ako su tri entiteta imala podatke e-pošte, možda ćete htjeti zadržati sva tri odvojena polja e-pošte ili ih spojiti u jedno polje e-pošte za jedinstveni profil. Sustav automatski kombinira neke atribute. Stabilne i jedinstvene ID-ove klijenata možete stvoriti i grupirati povezane profile u klaster.

:::image type="content" source="media/m3_unify.png" alt-text="Stranica spajanja u postupku objedinjavanja podataka koja prikazuje tablicu sa spojenim poljima koja definiraju objedinjeni profil klijenta.":::

## <a name="review-and-update-the-customer-fields"></a>Pregled i ažuriranje polja kupaca

1. Pregledajte popis polja koja će biti ujedinjena na **kartici Polja** kupca tablice. Ako je primjenjivo, napravite bilo kakve promjene.

   1. Za sva kombinirana polja možete:
      - [Uređivanje](#edit-a-merged-field)
      - [Preimenuj](#rename-fields)
      - [Odvoji](#separate-merged-fields)
      - [Isključi](#exclude-fields)
      - [Pomicanje gore ili dolje](#change-the-order-of-fields)

   1. Za sva pojedinačna polja možete:
      - [Kombinirajte polja](#combine-fields-manually)
      - [Kombiniranje grupe polja](#combine-a-group-of-fields)
      - [Preimenuj](#rename-fields)
      - [Isključi](#exclude-fields)
      - [Pomicanje gore ili dolje](#change-the-order-of-fields)

1. Po želji [generirajte konfiguraciju ID-a kupca](#configure-customer-id-generation).

1. Po želji grupirajte [profile u kućanstva ili klastere](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Sljedeći korak: Pregled ujedinjenja](review-unification.md)

### <a name="edit-a-merged-field"></a>Uređivanje spojenog polja

1. Odaberite spojeno polje, a zatim **Uređivanje**. Prikazuje se okno Kombiniraj polja.

1. Navedite kako kombinirati ili spojiti polja iz jedne od tri mogućnosti:
    - **Važnost**: Identificira pobjedničku vrijednost na temelju razine važnosti navedene za polja koja sudjeluju. To je zadana mogućnost spajanja. Odaberite **Pomakni se prema gore/dolje** za postavljanje razine važnosti.

      > [!NOTE]
      > Customer Insights koristi prvu vrijednost koja nije null. Na primjer, s obzirom na entitete A, B i C rangirane tim redoslijedom, ako su A.Name i B.Name null, tada se koristi vrijednost iz C.Name.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Mogućnost važnosti u dijalogu za spajanje polja.":::

    - **Nedavno**: Identificira pobjedničku vrijednost na temelju nedavnosti. Zahtijeva datum ili numeričko polje za svaki entitet koji sudjeluje u djelokrugu polja za spajanje kako bi se definirala nedavnost.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Mogućnost nedavnosti u dijalogu za spajanje polja.":::

    - **Najstarije**: Identificira pobjedničku vrijednost na temelju starosti. Zahtijeva datum ili numeričko polje za svaki entitet koji sudjeluje u djelokrugu polja za spajanje kako bi se definirala nedavnost.

1. Možete dodati još polja za sudjelovanje u procesu spajanja.

1. Spojeno polje možete preimenovati.

1. Odaberite **Gotovo** za primjenu izmjena.

### <a name="rename-fields"></a>Preimenovanje polja

Promijenite zaslonsko ime spojenih ili zasebnih polja. Ne možete promijeniti naziv izlaznog entiteta.

1. Odaberite polje, a zatim **Preimenuj**.

1. Unesite novi zaslonsko ime.

1. Odaberite **Gotovo**.

### <a name="separate-merged-fields"></a>Razdvajanje spojenih polja

Da biste razdvojili spojena polja, pronađite atribut u tablici. Razdvojena polja prikazuju se kao pojedinačne podatkovne točke na objedinjenom profilu klijenta.

1. Odaberite spojeno polje i odaberite **Odvoji polja**.

1. Potvrdite razdvajanje.

### <a name="exclude-fields"></a>Izostavi polja

Izuzimanje spojenog ili zasebnog polja iz jedinstvenog profila kupca. Ako se polje koristi u drugim postupcima, npr. u segmentu, uklonite ga iz tih postupaka prije nego što ga isključite iz profila klijenta.

1. Odaberite polje, a zatim **Izostavi**.

1. Potvrdite isključivanje.

Da biste vidjeli popis svih isključenih polja, odaberite **Isključena polja**. Ako je potrebno, možete pročitati isključeno polje.

### <a name="change-the-order-of-fields"></a>Promjena redoslijeda polja

Neki entiteti sadrže više pojedinosti od drugih. Ako entitet uključuje najnovije podatke o polju, možete mu dati prednost nad drugim entitetima pri spajanju vrijednosti.

1. Odaberite polje.
  
1. Odaberite **Premjesti gore/dolje** da biste postavili redoslijed ili povucite i ispustite ih na željeni položaj.

### <a name="combine-fields-manually"></a>Ručno kombiniranje polja

Kombinirajte odvojena polja da biste stvorili spojeni atribut.

1. Odaberite **Kombiniraj** > **polja**. Prikazuje se okno Kombiniraj polja.

1. Navedite pravila pobjednika spajanja u padajućem izborniku **Kombiniraj polja prema**.

1. Odaberite **Dodaj polje** da biste kombinirali više polja.

1. Navedite **Naziv** i **Naziv polja rezultata**.

1. Odaberite **Gotovo** za primjenu izmjena.

### <a name="combine-a-group-of-fields"></a>Kombiniranje grupe polja

Tretirajte grupu polja kao jednu jedinicu. Na primjer, ako naši zapisi sadrže polja Adresa1, Adresa2, Grad, Država i Zip, ne želimo se spojiti u adresu drugog zapisa2, misleći da bi to naše podatke učinilo potpunijima.

1. Odaberite **Kombiniraj** > **grupu polja**.

1. Navedite pravilo pobjednika spajanja **u grupama Rang prema** padajućem izborniku.

1. Odaberite **Dodaj** i odaberite želite li u polja dodati još polja ili grupa.

1. Navedite naziv **i** izlazni **naziv** za svako kombinirano polje.

1. Navedite naziv **za** grupu polja.

1. Odaberite **Gotovo** za primjenu izmjena.

## <a name="configure-customer-id-generation"></a>Konfiguriranje generiranja korisničkog ID-a

Definirajte kako generirati vrijednosti ID-a klijenta, jedinstvene identifikatore profila klijenta. Korak objedinjavanja polja u procesu objedinjavanja podataka generira jedinstveni identifikator korisničkog profila. Identifikator je *CustomerId* u entitetu *Klijent* koji proizlazi iz postupka objedinjavanja podataka.

*CustomerId* se temelji na raspršivanju prve vrijednosti primarnih ključeva koji nisu null. Ti ključevi dolaze od entiteta koji se koriste u objedinjavanju podataka i na njih utječe redoslijed podudaranja.Tako se generirani ID klijenta može promijeniti kada se vrijednost primarnog ključa promijeni u primarnom entitetu redoslijeda podudaranja. Vrijednost primarnog ključa možda neće uvijek predstavljati istog kupca.

Konfiguriranje stabilnog ID-ja klijenta omogućuje vam da izbjegnete takvo ponašanje.

1. Odaberite karticu **Ključevi**.

1. Zadržite pokazivač miša u **retku CustomerId** i odaberite **Konfiguriraj**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontrola za prilagodbu generiranja ID-ja.":::

1. Odaberite do pet polja koja će sadržavati jedinstveni ID klijenta i koja su stabilnija. Zapisi koji ne odgovaraju vašoj konfiguraciji umjesto toga koriste ID koji je konfigurirao sustav.  

1. Odaberite **Gotovo**.

## <a name="group-profiles-into-households-or-clusters"></a>Grupirajte profile u kućanstva ili klastere

Možete definirati pravila za grupiranje povezanih profila u klaster. Trenutačno postoje dvije vrste klastera – klasteri za kućanstva i prilagođeni klasteri. Sustav automatski odabire kućanstvo s unaprijed definiranim pravilima ako entitet *Klijent* sadrži semantička polja *Person.LastName* i *Location.Address*. Također možete stvoriti klaster sa svojim vlastitim pravilima i uvjetima, slično [pravilima podudaranja](match-entities.md#define-rules-for-match-pairs).

1. Odaberite **Klaster** > **naprednog** stvaranja.

   :::image type="content" source="media/create-cluster.png" alt-text="Kontrola za stvaranje novog klastera.":::

1. Birajte između klastera **Kućanstvo** ili **Prilagođen**. Ako semantička polja *Person.LastName* i *Location.Address* postoje u entitetu *Klijent*, automatski se odabire kućanstvo.

1. Navedite naziv klastera i odaberite **Gotovo**.

1. Odaberite karticu **Klasteri** kako biste pronašli klaster koji ste stvorili.

1. Navedite pravila i uvjete za definiranje klastera.

1. Odaberite **Gotovo**. Klaster se stvara po dovršetku postupka ujedinjenja. Identifikatori klastera dodaju se kao nova polja entitetu *Klijent*.

> [!div class="nextstepaction"]
> [Sljedeći korak: Pregled ujedinjenja](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
