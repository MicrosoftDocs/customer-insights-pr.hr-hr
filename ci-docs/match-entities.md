---
title: Podudaranje entiteta za objedinjavanje podataka
description: Prilagodite entitete da biste stvorili objedinjene profile klijenata.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: bc470dd932c2c981adc5840bb52d60f8dfe0de61
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740940"
---
# <a name="match-conditions"></a>Uskladi uvjete

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Ovaj korak u ujedinjenju definira redoslijed podudaranja i pravila za međusobno podudaranje. Za ovaj korak potrebna su najmanje dva entiteta.

> [!NOTE]
> Nakon što stvorite uvjete podudaranja i odaberete **Dalje**, ne možete ukloniti odabrani entitet ili atribut. Ako je potrebno, odaberite **Natrag** da biste pregledali odabrane entitete i atribute prije nastavka.

## <a name="include-enriched-entities-preview"></a>Uključi obogaćene entitete (pretpregled)

Ako ste obogatili entitete na razini izvor podataka kako biste poboljšali rezultate ujedinjenja, odaberite ih. Dodatne informacije potražite u odjeljku [Obogaćivanje izvora podataka](data-sources-enrichment.md). Ako ste na stranici Duplicirani zapisi odabrali **obogaćene entitete**, ne morate ih ponovno odabrati.

1. **Na stranici Odgovarajući uvjeti** pri vrhu stranice odaberite **Koristi obogaćene entitete**.

1. U oknu **Koristi obogaćene entitete** odaberite jedan ili više obogaćenih entiteta.

1. Odaberite **Gotovo**.

## <a name="specify-the-match-order"></a>Zadavanje redoslijeda uparivanja

Svako uparivanje ujedinjuje dva ili više entiteta u jedan objedinjeni entitet. Istodobno vodi jedinstvenu evidenciju klijenata. Redoslijed podudaranja označava redoslijed kojim sustav pokušava uskladiti zapise.

> [!IMPORTANT]
> Prvi entitet na listi naziva se primarni entitet. Primarni entitet služi kao osnova za skup podataka o objedinjenim profilima. U ovaj entitet bit će dodani dodatni odabrani entiteti.
>
> Važna razmatranja:
>
> - Odaberite entitet s najcjelovitijim i najpouzdanijim profilnim podacima o vašim klijentima kao primarnom entitetu.
> - Odaberite entitet koji ima nekoliko zajedničkih atributa s drugim entitetima (na primjer, ime, telefonski broj ili adresu e-pošte) kao primarni entitet.

1. **Na stranici Odgovarajući uvjeti** koristite strelice za pomicanje gore i dolje da biste premjestili entitete željenim redoslijedom ili ih povucite i ispustite. Na primjer, odaberite **Kontakti:e-trgovina** kao primarni entitet i **CustomerLoyalty:Loyalty** kao drugi entitet.

1. Da bi svaki zapis u entitetu bio jedinstveni klijent bez obzira na to je li pronađeno podudaranje, odaberite **Uključi sve zapise**. Svi zapisi u ovom entitetu koji se ne podudaraju sa zapisima ni u jednom drugom entitetu uključeni su u objedinjeni profil. Zapisi koji nemaju podudaranje nazivaju se singletoni.
  
Kontakti:e-trgovina primarnog entiteta *podudara se sa sljedećim entitetom* CustomerLoyalty:Loyalty *.* Skup podataka koji proizlazi iz prvog koraka podudaranja podudara se sa sljedećim entitetom ako imate više od dva entiteta.

:::image type="content" source="media/m3_match.png" alt-text="Snimka zaslona odabranog redoslijeda podudaranja za entitete." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definiranje pravila za parove uparivanja

Pravila uparivanja određuju logiku kojom će se uparivati određeni par entiteta. Pravilo se sastoji od jednog ili više uvjeta.

Upozorenje pored naziva entiteta znači da za par podudaranja nije definirano pravilo podudaranja.

1. Odaberite **Dodaj pravilo** za par entiteta da biste definirali pravila podudaranja.

1. **U oknu Dodavanje pravila** konfigurirajte uvjete za pravilo.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Snimka zaslona s prikazom mogućnosti Dodavanje okna pravila.":::

   - **Odabir entiteta/polja (prvi redak)**: Odaberite povezani entitet i atribut da biste naveli svojstvo zapisa koje je vjerojatno jedinstveno za klijenta. Na primjer, telefonski broj ili adresu e-pošte. Izbjegavajte uparivanje prema atributima vrste aktivnosti. Na primjer, ID kupnje vjerojatno neće pronaći uparivanje u drugim vrstama zapisa.

   - **Odabir entiteta/polja (drugog retka)**: Odaberite atribut koji se odnosi na atribut entiteta navedenog u prvom retku.

   - **Normalizacija**: Odaberite jednu od sljedećih mogućnosti normalizacije za odabrane atribute.
     - **Brojevi**: Pretvara druge numeričke sustave, kao što su rimski brojevi, u arapske brojeve. *VIII* postaje *8*.
     - **Simboli**: uklanja sve simbole i posebne znakove. *Head&Shoulder* postaje *HeadShoulder*.
     - **Tekst u mala slova**: pretvara sav znak u mala slova. *SVE VELIKA SLOVA i Velika početna slova* postaje *sve velika slova i velika početna slova*.
     - **Vrsta (telefon, ime, adresa, organizacija)**: Standardizira imena, naslove, telefonske brojeve, adrese i organizacije.
     - **Unicode u ASCII**: Pretvara unicode notaciju u ASCII znakove. */u00B2* postaje *2*.
     - **Whitespace**: Uklanja sve razmake. *Pozdrav,   svijete* postaje *Pozdrav,svijete*.

   - **Preciznost**: postavite razinu preciznosti koja će se primjenjivati za ovaj uvjet.
     - **Osnovno**: Odaberite nisko *(30%)*, *srednje (60%)*, *visoko (80%)* i *točno (100%)*. Odaberite **Točno** da bi odgovarali samo zapisima koji odgovaraju 100 posto.
     - **Prilagođeno**: postavite postotak kojem zapisi moraju odgovarati. Sustav će upariti samo zapise koji prelaze ovaj prag.

   - **Naziv**: naziv pravila.

1. Da biste odgovarali entitetima samo ako atributi zadovoljavaju više uvjeta, odaberite **Dodaj** > **uvjet** da biste pravilu podudaranja dodali još uvjeta. Uvjeti su povezani logičkim operatorom AND i stoga se izvršavaju samo ako su ispunjeni svi uvjeti.

1. Po želji razmotrite napredne opcije kao [što su iznimke ili](#add-exceptions-to-a-rule) prilagođeni [uvjeti](#specify-custom-match-conditions) podudaranja.

1. Odaberite **Gotovo** da biste dovršili pravilo.

1. Ako želite, [dodajte još pravila](#add-rules-to-a-match-pair).

1. Kliknite **Sljedeće**.

> [!div class="nextstepaction"]
> [Sljedeći korak: Objedinjavanje polja](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Dodavanje pravila paru uparivanja

Pravila uparivanja predstavljaju skupove uvjeta. Da biste entitete uskladili s uvjetima koji se temelje na više atributa, dodajte još pravila.

1. Odaberite **Dodaj pravilo** za entitet kojem želite dodati pravila.

1. Slijedite korake u odjeljku [Definiranje pravila za parove uparivanja](#define-rules-for-match-pairs).

> [!NOTE]
> Bitan je redoslijed pravila. Odgovarajući algoritam pokušava uskladiti određeni zapis o kupcu na temelju vašeg prvog pravila i nastavlja se na drugo pravilo samo ako nisu identificirana podudaranja s prvim pravilom.

## <a name="advanced-options"></a>Dodatne mogućnosti

### <a name="add-exceptions-to-a-rule"></a>Dodavanje iznimaka pravilu

U većini slučajeva podudaranje entiteta dovodi do jedinstvenih profila klijenata s konsolidiranim podacima. Da biste dinamički riješili rijetke slučajeve lažno pozitivnih rezultata i lažno negativnih rezultata, možete definirati iznimke za pravilo podudaranja. Iznimke se primjenjuju nakon obrade pravila podudaranja i izbjegavaju podudaranje svih zapisa koji ispunjavaju kriterije iznimke.

Na primjer, ako vaše pravilo podudaranja kombinira prezime, grad i datum rođenja, sustav bi identificirao blizance s istim prezime koji žive u istom gradu kao i isti profil. Možete odrediti iznimku koja se ne podudara s profilima ako ime u entitetima koje kombinirate nisu iste.

1. **U oknu pravila** Uređivanje odaberite **Dodaj** > **iznimku**.

1. Navedite kriterije iznimke.

1. Odaberite **Gotovo** da biste spremili pravilo.

### <a name="specify-custom-match-conditions"></a>Određivanje prilagođenih uvjeta uparivanja

Možete odrediti uvjete koji nadjačavaju zadanu logiku podudaranja. Dostupne su četiri mogućnosti:

|Mogućnost  |Opis |Primjer  |
|---------|---------|---------|
|Uvijek se podudara     | Definira vrijednosti koje se uvijek podudaraju.         |  Uvijek se podudaraj s *Mikeom* i *Mikerom*.       |
|Nikad se ne podudara     | Definira vrijednosti koje se nikada ne podudaraju.        | Nikad ne odgovaraj Johnu *i* *Jonathanu*.        |
|Prilagođeno zaobilaženje     | Definira vrijednosti koje sustav uvijek treba zanemariti u fazi podudaranja. |  Zanemarite vrijednosti *111111* i *Nepoznato* tijekom podudaranja.        |
|Mapiranje pseudonima    | Definiranje vrijednosti koje bi sustav trebao smatrati istom vrijednošću.         | Smatraj *Joea* jednakim *Josephu*.        |

1. Odaberite **Prilagođeni**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Prilagođeni gumb":::

1. Odaberite prilagođenu **vrstu**, a zatim Preuzmi **predložak**. Potreban vam je zaseban predložak za svaku opciju podudaranja.

1. Otvorite preuzetu datoteku predloška i ispunite detalje. Predložak sadrži polja za određivanje entiteta i vrijednosti primarnog ključa entiteta koji će se koristiti u prilagođenom uparivanju. Na primjer, ako želite da se primarni ključ *12345* iz entiteta *Prodaja* uvijek upari s primarnim ključem *34567* iz entiteta *Kontakt*, ispunite predložak:
    - Entitet1: Prodaja
    - Ključ entiteta1: 12345
    - Entitet2: Kontakt
    - Ključ entiteta2: 34567

   Ista datoteka predloška može odrediti zapise prilagođenog uparivanja iz više entiteta.

   Ako želite navesti prilagođeno podudaranje za uklanjanje duplikata na entitetu, navedite isti entitet kao Entitet1 i Entitet2 i postavite različite vrijednosti primarnog ključa.

1. Nakon dodavanja svih poništenja spremite datoteku predloška.

1. Idite na **Podaci** > **Izvori podataka** i unesite datoteke predloška kao nove entitete.

1. Nakon prijenosa datoteka ponovno odaberite **mogućnost Prilagođeno**. Na padajućem izborniku odaberite potrebne entitete i odaberite **Gotovo**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Snimka zaslona dijaloga za odabir nadjačavanja za scenarij prilagođenog uprivanja.":::

1. Primjena prilagođenog podudaranja ovisi o mogućnosti podudaranja koju želite koristiti.

   - Za **podudaranje Uvijek se podudaraj** ili **Nikad**, prijeđite na sljedeći korak.
   - Za **mapiranje** premosnice **ili** pseudonima odaberite **Uredi** na postojećem pravilu podudaranja ili stvorite novo pravilo. Na padajućem izborniku Normalizacije odaberite **mogućnost Prilagođena premosnica** ili **Mapiranje** pseudonima i odaberite **Gotovo**.

1. U **oknu Prilagođeno** **odaberite Gotovo** da biste primijenili prilagođenu konfiguraciju podudaranja.

> [!div class="nextstepaction"]
> [Sljedeći korak: Objedinjavanje polja](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
