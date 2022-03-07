---
title: Spajanje entiteta u objedinjavanju podataka
description: Spojite entitete da biste stvorili objedinjene profile klijenata.
ms.date: 01/28/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: c7743104bf89d9a2a741f1b358a89ed0240be024
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355836"
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

1.  Možete dodati još polja za sudjelovanje u procesu spajanja.

1.  Spojeno polje možete preimenovati.

1. Odaberite **Gotovo** za primjenu izmjena.

1. Odaberite **Spremi** i **Pokreni** za obradu promjena. 

## <a name="combine-fields-manually"></a>Ručno kombiniranje polja

Ručno navedite spojeni atribut.

1. Na stranici **Spajanje** odaberite **Kombiniraj**.

1. **Odaberite mogućnost Polja**.

1. Navedite pravila pobjednika spajanja u padajućem izborniku **Kombiniraj polja prema**.

1. Odaberite polje za dodavanje. Odaberite **Dodaj polja** za kombiniranje više polja.

1. Navedite **Naziv** i **Naziv polja rezultata**.

1. Odaberite **Gotovo** za primjenu izmjena.

1. Odaberite **Spremi** i **Pokreni** za obradu promjena. 

## <a name="combine-a-group-of-fields"></a>Kombiniranje grupe polja

Tretirajte grupu polja kao jednu jedinicu. Na primjer, kada naši zapisi sadrže polja Adresa1, Adresa2, Grad, Država i Zip. Vjerojatno se ne želimo spojiti u adresu2 drugog zapisa, misleći da će to učiniti naše podatke potpunijima

1. Na stranici **Spajanje** odaberite **Kombiniraj**.

1. **Odaberite mogućnost Grupiraj polja**.

1. Odredite pravilo pobjednika spajanja **u grupama ranga prema padajućem** izborniku.

1. Odaberite **Dodaj** i odaberite želite li poljima dodati još polja ili dodatnih grupa.

1. **Navedite naziv** i izlazni **naziv** za svako kombinirano polje.

1. **Navedite naziv** grupe polja. 

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

CustomerId u entitetu Klijent temelji se na raspršivanju prve vrijednosti pobjedničkih primarnih ključeva koji nisu null. Ovi ključevi dolaze od entiteta koji se koriste u fazi podudaranja i spajanja, a na njih utječe redoslijed podudaranja.Tako da se generirani CustomerID može promijeniti kada se promijeni vrijednost primarnog ključa u primarnom entitetu redoslijeda podudaranja. Dakle, vrijednost primarnog ključa ne mora uvijek predstavljati istog klijenta.

Konfiguriranje stabilnog ID-ja klijenta omogućuje vam da izbjegnete takvo ponašanje.

**Konfiguracija jedinstvenog ID-ja klijenta**

1. Idite na **Objedini** > **Spoji**.

1. Odaberite karticu **Ključevi**. 

1. Zadržite pokazivač miša na retku **CustomerId** i odaberite mogućnost **Konfiguriraj**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontrola za prilagodbu generiranja ID-ja.":::

1. Odaberite do pet polja koja će sadržavati jedinstveni ID klijenta i koja su stabilnija. Zapisi koji ne odgovaraju vašoj konfiguraciji umjesto toga koriste ID koji je konfigurirao sustav.  

1. Odaberite **Gotovo** i pokrenite postupak spajanja kako biste primijenili svoje promjene.

## <a name="group-profiles-into-households-or-clusters"></a>Grupirajte profile u kućanstva ili klastere

Kao dio procesa konfiguracije generiranja profila korisnika, možete definirati pravila za grupiranje povezanih profila u klaster. Trenutačno postoje dvije vrste klastera – klasteri za kućanstva i prilagođeni klasteri. Sustav automatski odabire kućanstvo s unaprijed definiranim pravilima ako entitet *Klijent* sadrži semantička polja *Person.LastName* i *Location.Address*. Također možete stvoriti klaster sa svojim vlastitim pravilima i uvjetima, slično [pravilima podudaranja](match-entities.md#define-rules-for-match-pairs).

**Definiranje kućanstva ili klastera**

1. Idite na **Objedini** > **Spoji**.

1. Na kartici **Spoji** odaberite **Napredno** > **Stvori klaster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Kontrola za stvaranje novog klastera.":::

1. Birajte između klastera **Kućanstvo** ili **Prilagođen**. Ako semantička polja *Person.LastName* i *Location.Address* postoje u entitetu *Klijent*, automatski se odabire kućanstvo.

1. Navedite naziv klastera i odaberite **Gotovo**.

1. Odaberite karticu **Klasteri** kako biste pronašli klaster koji ste stvorili.

1. Navedite pravila i uvjete za definiranje klastera.

1. Odaberite **Pokreni** za pokretanje procesa spajanja i stvaranje klastera.

Nakon pokretanja procesa spajanja, identifikatori klastera dodaju se kao nova polja u entitet *Klijent*.

## <a name="run-your-merge"></a>Pokretanje spajanja

Bilo da ručno spajate atribute ili da ih spaja sustav, uvijek možete pokrenuti spajanje. Odaberite **Pokreni** na stranici **Spoji** da biste pokrenuli proces.

> [!div class="mx-imgBorder"]
> ![Spremi i Pokreni spajanje podataka.](media/configure-data-merge-save-run.png "Spremi i pokreni spajanje podataka")

Odaberite **Pokreni samo spajanje** ako želite vidjeti samo rezultat koji se odražava u objedinjenom entitetu klijenta. Nizvodni procesi bit će osvježeni kako je [definirano u rasporedu osvježavanja](system.md#schedule-tab).

Odaberite **Pokreni spajanje i nizvodne procese** kako biste sustav osvježili svojim promjenama. Svi procesi, uključujući obogaćivanje, segmente i mjere automatski će se ponovno pokrenuti. Nakon završetka svih nizvodnih procesa, profili klijenata odražavaju sve promjene koje ste napravili.

Da biste izvršili više promjena i ponovno pokrenuli korak, možete otkazati spajanje u tijeku. Odaberite **Osvježavanje...** i odaberite **Otkaži posao**  na bočnom oknu koje se pojavljuje.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Detaljna putanja za pristup pojedinostima obrade s veze statusa zadatka.":::

## <a name="next-step"></a>Sljedeći korak

Konfigurirajte [aktivnosti](activities.md), [obogaćivanje](enrichment-hub.md) ili [odnose](relationships.md) za više uvida u svoje klijente.

Ako ste već konfigurirali aktivnosti, obogaćivanje ili segmente, obrađivat će se automatski kako bi se upotrijebili najnoviji podaci o klijentu.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
