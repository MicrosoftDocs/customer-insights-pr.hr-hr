---
title: Spajanje entiteta u objedinjavanju podataka
description: Spojite entitete da biste stvorili objedinjene profile klijenata.
ms.date: 09/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b038cd3f5b433fedf918d34bbfaf2261e11c5c17
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494310"
---
# <a name="merge-entities"></a>Spajanje entiteta

Faza spajanja zadnja je faza u procesu objedinjavanja podataka. Njezina je svrha usklađivanje zbunjujućih podataka. Primjeri sukobljenih podataka mogu uključivati ime klijenta koje se nalazi u dvama skupovima podataka, ali se malo drugačije prikazuje u svakome od njih („Grant Marshall” u odnosu na „Grant Marshal”) ili telefonski broj koji se razlikuje u obliku (617-803-091X u odnosu na 617803091X). Spajanje tih zbunjujućih podatkovnih točaka vrši se na osnovi atribut prema atributu.

:::image type="content" source="media/merge-fields-page.png" alt-text="Stranica spajanja u postupku objedinjavanja podataka koja prikazuje tablicu sa spojenim poljima koja definiraju objedinjeni profil klijenta.":::

Nakon dovršetka [faze uparivanja](match-entities.md) fazu spajanja možete započeti odabirom pločice **Spajanje** na stranici **Objedinjavanje**.

## <a name="review-system-recommendations"></a>Pregled preporuka sustava

U odjeljku **Podaci** > **Objedini** > **Spoji** odabirete i isključujete atribute za spajanje unutar vašeg entiteta objedinjenog profila klijenta. Objedinjeni profil klijenta rezultat je postupka objedinjavanja podataka. Sustav automatski spaja neke atribute.

Da biste pregledali atribute koji su uključeni u jedan od vaših automatski spojenih atributa, odaberite taj spojeni atribut na kartici **Polja klijenata** za tablicu. Atributi koji čine taj spojeni atribut prikazuju se u dva nova retka ispod spojenog atributa.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Razdvajanje, preimenovanje, isključivanje i uređivanje spojenih polja

Možete promijeniti način na koji sustav obrađuje spojene atribute kako bi stvorio objedinjeni profil klijenta. Odaberite **Prikaži više** i odaberite što želite promijeniti.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opcije u padajućem izborniku Prikaži više za upravljanje spojenim atributima.":::

Dodatne informacije potražite u sljedećim odjeljcima.

## <a name="separate-merged-fields"></a>Razdvajanje spojenih polja

Da biste razdvojili spojena polja, pronađite atribut u tablici. Razdvojena polja prikazuju se kao pojedinačne podatkovne točke na objedinjenom profilu klijenta. 

1. Odaberite spojeno polje.
  
1. Odaberite **Prikaži više** pa odaberite **Razdvoji polja**.
 
1. Potvrdite razdvajanje.

1. Odaberite **Spremi** i **Pokreni** za obradu promjena.

## <a name="rename-merged-fields"></a>Preimenovanje spojenih polja

Promijenite zaslonski naziv spojenih atributa. Ne možete promijeniti naziv izlaznog entiteta.

1. Odaberite spojeno polje.
  
1. Odaberite **Prikaži više** pa odaberite **Preimenuj**.

1. Potvrdite promijenjeni zaslonski naziv. 

1. Odaberite **Spremi** i **Pokreni** za obradu promjena.

## <a name="exclude-merged-fields"></a>Isključivanje spojenih polja

Isključite atribut iz objedinjenog profila klijenta. Ako se polje koristi u drugim postupcima, npr. u segmentu, uklonite ga iz tih postupaka prije nego što ga isključite iz profila klijenta. 

1. Odaberite spojeno polje.
  
1. Odaberite **Prikaži više** pa odaberite **Isključi**.

1. Potvrdite isključivanje.

1. Odaberite **Spremi** i **Pokreni** za obradu promjena. 

Na stranici **Spajanje** odaberite **Isključena polja** da biste vidjeli popis svih isključenih polja. Ovo okno omogućuje vraćanje isključenih polja.

## <a name="edit-a-merged-field"></a>Uređivanje spojenog polja

1.  Odaberite spojeno polje.

1.  Odaberite **Prikaži više** pa odaberite **Uredi**.

1.  Navedite kako kombinirati ili spojiti polja iz jedne od tri mogućnosti:
    - **Važnost**: Identificira pobjedničku vrijednost na temelju razine važnosti navedene za polja koja sudjeluju. To je zadana mogućnost spajanja. Odaberite **Pomakni se prema gore/dolje** za postavljanje razine važnosti.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Mogućnost važnosti u dijalogu za spajanje polja."::: 
    - **Nedavno**: Identificira pobjedničku vrijednost na temelju nedavnosti. Zahtijeva datum ili numeričko polje za svaki entitet koji sudjeluje u djelokrugu polja za spajanje kako bi se definirala nedavnost.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Mogućnost nedavnosti u dijalogu za spajanje polja.":::
    - **Najstarije**: Identificira pobjedničku vrijednost na temelju starosti. Zahtijeva datum ili numeričko polje za svaki entitet koji sudjeluje u djelokrugu polja za spajanje kako bi se definirala nedavnost.

1.  Možete dodati dodatna polja za sudjelovanje u procesu spajanja.

1.  Spojeno polje možete preimenovati.

1. Odaberite **Gotovo** za primjenu izmjena.

1. Odaberite **Spremi** i **Pokreni** za obradu promjena. 

## <a name="manually-combine-fields"></a>Ručno kombiniranje polja

Ručno navedite spojeni atribut. 

1. Na stranici **Spajanje** odaberite **Kombiniraj polja**.

1. Navedite pravila pobjednika spajanja u padajućem izborniku **Kombiniraj polja prema**.

1. Odaberite polje za dodavanje. Odaberite **Dodaj polja** za kombiniranje više polja.

1. Navedite **Naziv** i **Naziv polja rezultata**.

1. Odaberite **Gotovo** za primjenu izmjena.

1. Odaberite **Spremi** i **Pokreni** za obradu promjena. 

## <a name="change-the-order-of-fields"></a>Promjena redoslijeda polja

Neki entiteti sadrže više pojedinosti od drugih. Ako entitet uključuje najnovije podatke o polju, možete mu dati prednost nad drugim entitetima pri spajanju vrijednosti.

1. Odaberite spojeno polje.
  
1. Odaberite **Prikaži više** pa odaberite **Uredi**.

1. U oknu **Kombiniraj polja** odaberite **Pomakni gore/dolje** za postavljanje redoslijeda ili ih povucite i ispustite u željeni položaj.

1. Potvrdite promjenu.

1. Odaberite **Spremi** i **Pokreni** za obradu promjena.

## <a name="configure-customer-id-generation"></a>Konfiguracija generiranja ID-ja klijenta 

Nakon konfiguriranja spajanja polja možete definirati kako generirati vrijednosti CustomerId, jedinstvene identifikatore profila klijenta. Korak spajanja u procesu objedinjavanja podataka generira jedinstveni identifikator profila klijenta. Identifikator je CustomerId u entitetu *Klijent* koji je rezultat procesa objedinjavanja podataka. 

CustomerId u entitetu Klijent temelji se na raspršivanju prve vrijednosti pobjedničkih primarnih ključeva koji nisu null. Ovi ključevi dolaze od entiteta koji se koriste u fazi podudaranja i spajanja, a na njih utječe redoslijed podudaranja.Tako da se generirani CustomerID može promijeniti kada se promijeni vrijednost primarnog ključa u primarnom entitetu redoslijeda podudaranja. Slijedom toga, vrijednost primarnog ključa ne mora uvijek predstavljati istog klijenta.

Konfiguriranje stabilnog ID-ja klijenta omogućuje vam da izbjegnete takvo ponašanje.

**Konfiguracija jedinstvenog ID-ja klijenta**

1. Idite na **Objedini** > **Spoji**.

1. Na stranici **Spoji** odaberite karticu **Ključevi**. 

1. Zadržite pokazivač miša na retku **CustomerId** i odaberite mogućnost **Konfiguriraj**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontrola za prilagodbu generiranja ID-ja.":::

1. Odaberite do pet polja koja će sadržavati jedinstveni ID klijenta i koja su stabilnija. Zapisi koji ne odgovaraju vašoj konfiguraciji umjesto toga koriste ID koji je konfigurirao sustav.  

1. Odaberite **Gotovo** i pokrenite postupak spajanja kako biste primijenili svoje promjene.

## <a name="run-your-merge"></a>Pokretanje spajanja

Bilo da ručno spajate atribute ili da ih spaja sustav, uvijek možete pokrenuti spajanje. Odaberite **Pokreni** na stranici **Spoji** da biste pokrenuli proces.

> [!div class="mx-imgBorder"]
> ![Spremi i Pokreni spajanje podataka.](media/configure-data-merge-save-run.png "Spremi i pokreni spajanje podataka")

Odaberite **Pokreni samo spajanje** ako želite vidjeti samo rezultat koji se odražava u objedinjenom entitetu klijenta. Nizvodni procesi bit će osvježeni kako je [definirano u rasporedu osvježavanja](system.md#schedule-tab).

Odaberite **Pokreni spajanje i nizvodne procese** kako biste sustav osvježili svojim promjenama. Svi procesi, uključujući obogaćivanje, segmente i mjere automatski će se ponovno pokrenuti. Nakon završetka svih nizvodnih procesa, profili klijenata odražavaju sve promjene koje ste napravili.

Da biste izvršili više promjena i ponovno pokrenuli korak, možete otkazati spajanje u tijeku. Odaberite **Osvježavanje...** i odaberite **Otkaži posao**  na bočnom oknu koje se pojavljuje.

> [!TIP]
> Nakon pokretanja procesa spajanja odaberite status procesa da biste otvorili okno **Pojedinosti o zadatku** . On daje pregled o vremenu obrade, posljednjem datumu obrade i svim pogreškama i upozorenjima povezanima sa zadatkom. Odaberite **Pogledaj pojedinosti** da biste vidjeli koji su entiteti sudjelovali u procesu podudaranja, je li uspjelo razrješavanje sukoba i jesu li ažuriranja uspješno objavljena.  
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Detaljna putanja za pristup pojedinostima obrade s veze statusa zadatka.":::

## <a name="next-step"></a>Sljedeći korak

Konfigurirajte [aktivnosti](activities.md), [obogaćivanje](enrichment-hub.md) ili [odnose](relationships.md) za više uvida u svoje klijente.

Ako ste već konfigurirali aktivnosti, obogaćivanje ili segmente, obrađivat će se automatski kako bi se upotrijebili najnoviji podaci o klijentu.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
