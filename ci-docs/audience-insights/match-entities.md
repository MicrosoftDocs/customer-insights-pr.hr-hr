---
title: Podudaranje entiteta za objedinjavanje podataka
description: Prilagodite entitete da biste stvorili objedinjene profile klijenata.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2eb84c44aa530346a73ba720106734d705a45f23
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595555"
---
# <a name="match-entities"></a>Slaganje entiteta

Faza uparivanja određuje kako kombinirati skupove podataka u objedinjeni skup podataka profila klijenta. Nakon dovršetka [koraka mapiranja](map-entities.md) u postupku objedinjavanja podataka spremni ste za uparivanje vaših entiteta. Faza uparivanja zahtijeva najmanje dva mapirana entiteta.

Stranica uparivanja sastoji se od tri odjeljka: 
- Ključni mjerni podaci koji sažimaju broj uparenih zapisa
- Redoslijed uparivanja i pravila za međuentitetsko uparivanje
- Pravila za uklanjanje duplikata entiteta uparivanja

## <a name="specify-the-match-order"></a>Zadavanje redoslijeda uparivanja

Idite na **Podaci** > **Objedini** > **Upari** i odaberite **Postavi redoslijed** za početak faze podudaranja.

Svako uparivanje ujedinjuje dva ili više entiteta u jedan objedinjeni entitet. Istodobno vodi jedinstvenu evidenciju klijenata. Na primjer, odabrali smo dva entiteta: **eCommerce:eCommerceContacts** kao primarni entitet i **LoyaltyScheme:loyCustomers** kao drugi entitet. Redoslijed entiteta određuje kojim će redoslijedom sustav pokušati upariti zapise.

:::image type="content" source="media/match-page.png" alt-text="Snimka zaslona stranice Uparivanje u području Objedinjavanje za postupak objedinjavanja podataka.":::
  
Primarni entitet *eCommerce:eCommerceContacts* uparuje se sa sljedećim entitetom *LoyaltyScheme:loyCustomers*. Skup podataka koji je rezultat prvog koraka uparivanja uparuje se sa sljedećim entitetom ako imate više od dva entiteta.

> [!IMPORTANT]
> Entitet koji odaberete kao primarni entitet poslužit će kao osnova za vaš objedinjeni skup podataka profila. Ovom entitetu dodat će se dodatni entiteti koji su odabrani tijekom faze uparivanja. To ne znači da će objedinjeni entitet uključivati *sve* podatke uključene u ovaj entitet.
>
> Postoje dva razmatranja koja vam mogu pomoći da odaberete hijerarhiju entiteta:
>
> - Kao primarni entitet odaberite entitet s najpotpunijim i najpouzdanijim podacima profila o svojim klijentima.
> - Kao primarni entitet odaberite entitet koji ima nekoliko zajedničkih atributa s drugim entitetima (npr. ime, telefonski broj ili adresa e-pošte).

Nakon što odredite redoslijed uparivanja, vidjet ćete definirane parove uparivanja u odjeljku **Pojedinosti o uparenim zapisima** u **Podaci** > **Objedinjavanje** > **Uparivanje**. Ključni mjerni podaci bit će prazni dok se ne dovrši postupak uparivanja.

## <a name="define-rules-for-match-pairs"></a>Definiranje pravila za parove uparivanja

Pravila uparivanja određuju logiku kojom će se uparivati određeni par entiteta.

Upozorenje **Potrebna pravila** pored naziva entiteta sugerira da za par uparivanja nije definirano pravilo uparivanja. 

:::image type="content" source="media/match-rule-add.png" alt-text="Snimka zaslona odjeljka s pojedinostima o zapisu Upareno s istaknutom kontrolom za dodavanje pravila.":::

1. Odaberite **Dodavanje pravila** ispod entiteta u odjeljku **Pojedinosti o uparenim zapisima** za definiranje pravila uparivanja.

1. U oknu **Stvaranje pravila** konfigurirajte uvjete za pravilo.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Snimka zaslona otvorenog pravila uparivanja s dodanim uvjetima.":::

   - **Entitet/Polje (prvi redak)**: Odaberite povezani entitet i atribut da biste odredili svojstvo zapisa koje je vjerojatno jedinstveno za klijenta. Na primjer, telefonski broj ili adresu e-pošte. Izbjegavajte uparivanje prema atributima vrste aktivnosti. Na primjer, ID kupnje vjerojatno neće pronaći uparivanje u drugim vrstama zapisa.

   - **Entitet/Polje (drugi redak)**: Odaberite atribut koji se odnosi na atribut entiteta navedenog u prvom retku.

   - **Normalizacija**: Odaberite jednu od sljedećih mogućnosti normalizacije za odabrane atribute. 
     - Praznina: uklanja sve razmake. *Pozdrav,   svijete* postaje *Pozdrav,svijete*.
     - Simboli: uklanja sve simbole i posebne znakove. *Head&Shoulder* postaje *HeadShoulder*.
     - Tekst u mala slova: pretvara sve znakove u mala slova. *SVE VELIKA SLOVA i Velika početna slova* postaje *sve velika slova i velika početna slova*.
     - Unicode u ASCII: pretvara unicode notaciju u ASCII znakove. */u00B2* postaje *2*.
     - Brojevi: pretvara ostale brojevne sustave, poput rimskih brojeva, u arapske brojeve. *VIII* postaje *8*.
     - Semantičke vrste: standardizira imena, titule, telefonske brojeve, adrese itd. 

   - **Preciznost**: postavite razinu preciznosti koja će se primjenjivati za ovaj uvjet. 
     - **Osnovno**: odaberite između *Nisko*, *Srednje*, *Visoko* i *Točno*. Odaberite **Točno** da biste uparili samo zapise s podudaranjem od 100 posto. Odaberite jednu od ostalih razina za uparivanje zapisa koji nisu 100 posto identični.
     - **Prilagođeno**: postavite postotak kojem zapisi moraju odgovarati. Sustav će upariti samo zapise koji prelaze ovaj prag.

1. Navedite **Naziv** za pravilo.

1. [Dodajte još uvjeta](#add-conditions-to-a-rule) ili odaberite **Gotovo** za dovršetak pravila.

1. Ako želite, [dodajte još pravila](#add-rules-to-a-match-pair).

1. Odaberite **Spremi** za primjenu izmjena.

### <a name="add-conditions-to-a-rule"></a>Dodavanje uvjeta pravilu

Da biste uparili entitete samo ako atributi ispunjavaju više uvjeta, dodajte još uvjeta pravilu uparivanja. Uvjeti su povezani logičkim operatorom AND i stoga se izvršavaju samo ako su ispunjeni svi uvjeti.

1. Idite u odjeljak **Podaci** > **Objedinjavanje** > **Uparivanje** i odaberite **Uređivanje** na pravilu kojem želite dodati uvjete.

1. U oknu **Uredi pravilo**, odaberite **Dodaj uvjet**.

1. Odaberite **Gotovo** da biste spremili pravilo.

### <a name="add-rules-to-a-match-pair"></a>Dodavanje pravila paru uparivanja

Pravila uparivanja predstavljaju skupove uvjeta. Za uparivanje entiteta prema uvjetima na temelju više atributa, dodajte još pravila

1.  Idite u odjeljak **Podaci** > **Objedinjavanje** > **Uparivanje** i odaberite **Dodavanje pravila** na entitetu kojem želite dodati pravila.

2. Slijedite korake u odjeljku [Definiranje pravila za parove uparivanja](#define-rules-for-match-pairs).

> [!NOTE]
> Bitan je redoslijed pravila. Algoritam uparivanja pokušava uparivati na temelju vašeg prvog pravila i prelazi na drugo pravilo samo ako s prvim pravilom nisu identificirana uparivanja.

## <a name="define-deduplication-on-a-match-entity"></a>Definiranje uklanjanja duplikata na entitetu podudaranja

Pored [pravila međuentitetskih uparivanja](#define-rules-for-match-pairs), također možete odrediti pravila o uklanjanju duplikata. *Uklanjanje duplikata* je još jedan postupak prilikom uparivanja zapisa. On identificira duplikate zapisa i spaja ih u jedan zapis. Izvorni zapisi povezuju se s objedinjenim zapisom sa zamjenskim ID-ovima.

Zapisi kojima su uklonjeni duplikati upotrijebit će se u postupku međuentitetskih uparivanja. Uklanjanje duplikata se događa na pojedinačnim entitetima i može se konfigurirati za svaki entitet koji se koristi u parovima uparivanja.

Navođenje pravila za uklanjanje duplikata nije obavezno. Ako takva pravila nisu konfigurirana, primjenjuju se pravila koja je definirao sustav. Ona kombiniraju sve zapise u jedan zapis prije prosljeđivanja podataka entiteta međuentitetskom uparivanju radi poboljšane izvedbe.

### <a name="add-deduplication-rules"></a>Dodavanje pravila uklanjanja duplikata

1. Idite u odjeljak **Podaci** > **Objedinjavanje** > **Uparivanje**.

1. U odjeljku **Spojeni duplikati** odaberite **Postavi entitete**. Ako su pravila za uklanjanje duplikata već stvorena, odaberite **Uređivanje**.

1. U oknu **Spajanje preferenci** odaberite entitete na kojima želite izvesti uklanjanje duplikata.

1. Navedite kako kombinirati duplikate zapisa i odaberite jednu od tri mogućnosti:
   - **Najispunjeniji**: identificira zapis s najviše ispunjenih polja atributa kao pobjednički zapis. To je zadana mogućnost spajanja.
   - **Najnoviji**: Identificira pobjednički zapis na temelju nedavnosti. Zahtijeva datum ili numeričko polje za definiranje nedavnosti.
   - **Najstariji**: Identificira pobjednički zapis na temelju starosti. Zahtijeva datum ili numeričko polje za definiranje nedavnosti.
 
   > [!div class="mx-imgBorder"]
   > ![Korak 1 pravila uklanjanja duplikata](media/match-selfconflation.png "Korak 1 pravila uklanjanja duplikata")
 
1. Nakon što se odaberu entiteti i postave njihove preference spajanja, odaberite **Dodavanje pravila** kako bi se definirala pravila uklanjanja duplikata na razini entiteta.
   - **Odabir polja** navodi sva dostupna polja iz tog entiteta. Odaberite polje u kojem želite provjeriti duplikate. Odaberite polja koja su vjerojatno jedinstvena za svakog pojedinog klijenta. Na primjer, adresa e-pošte ili kombinacija imena, grada i telefonskog broja.
   - Navedite postavke normalizacije i preciznosti.
   - Definirajte više uvjeta odabirom mogućnosti **Dodavanje uvjeta**.
 
   > [!div class="mx-imgBorder"]
   > ![Korak 2 pravila uklanjanja duplikata](media/match-selfconflation-rules.png "Korak 2 pravila uklanjanja duplikata")

  Možete stvoriti više pravila za uklanjanje duplikata za entitet. 

1. Pokretanje procesa podudaranja sada grupira zapise na temelju uvjeta definiranih u pravilima za uklanjanje duplikata. Nakon grupiranja zapisa primjenjuje se politika spajanja za identificiranje pobjedničkog zapisa.

1. Taj se pobjednički zapis zatim prenosi na međusobno podudaranje entiteta, zajedno sa zapisima koji nisu pobjednički (na primjer, zamjenski ID-jevi) da bi se poboljšala kvaliteta podudaranja.

1. Sva definirana prilagođena pravila uparivanja zamjenjuju pravila uklanjanja duplikata. Ako pravilo o uklanjanju duplikata identificira podudarne zapise, a prilagođeno pravilo podudaranja postavi se tako da se nikada ne podudara s tim zapisima, tada se ova dva zapisa neće podudarati.

1. Nakon [pokretanja postupka uparivanja](#run-the-match-process) vidjet ćete statistiku uklanjanja duplikata na pločicama ključnih mjernih podataka.

### <a name="deduplication-output-as-an-entity"></a>Izlazna vrijednost uklanjanja duplikata kao entitet

Postupak uklanjanja duplikata stvara novi entitet za svaki entitet iz parova uparivanja kako bi se identificirali zapisi kojima su uklonjeni duplikati. Ti se entiteti mogu pronaći zajedno s **ConflationMatchPairs:CustomerInsights** u odjeljku **Sustav** na stranici **Entiteti** s nazivom **Deduplication_DataSource_Entity**.

Entitet izlazne vrijednosti uklanjanja duplikata sadrži sljedeće informacije:
- ID-jevi/ključevi
  - Polje primarnog ključa i njegovo zamjensko polje ID-ja. Polje zamjenskih ID-jeva sastoji se od svih zamjenskih ID-jeva identificiranih za zapis.
  - Polje Deduplication_GroupId prikazuje grupu ili klaster identificiran unutar entiteta koji grupira sve slične zapise na temelju navedenih polja uklanjanja duplikata. To se koristi u svrhu obrade sustava. Ako nisu navedena ručna pravila za uklanjanje duplikata i ako se primjenjuju pravila za uklanjanje duplikata koja je definirao sustav, ovo polje možda nećete pronaći u entitetu izlazne vrijednosti uklanjanja duplikata.
  - Deduplication_WinnerId: Ovo polje sadrži ID pobjednika iz identificiranih grupa ili klastera. Ako je Deduplication_WinnerId jednak vrijednosti primarnog ključa za zapis, to znači da je zapis pobjednički zapis.
- Polja koja se koriste za definiranje pravila za uklanjanje duplikata.
- Polja Pravilo i Ocjena označavaju koja su pravila za uklanjanja duplikata primijenjena i ocjenu koju vraća algoritam podudaranja.
   
## <a name="run-the-match-process"></a>Pokretanje postupka uparivanja

Nakon konfiguriranja pravila uparivanja, uključujući pravila za međuentitetsko uparivanje i uklanjanje duplikata, možete pokrenuti postupak uparivanja. 

Idite u odjeljak **Podaci** > **Objedinjavanje** > **Uparivanje** i odaberite **Pokretanje** za pokretanje postupka. Algoritmu za uparivanje potrebno je određeno vrijeme za završetak i ne možete promijeniti konfiguraciju dok ne završi. Da biste izvršili promjene, možete otkazati izvođenje. Odaberite status posla pa odaberite **Otkaži posao** u oknu **Pojedinosti o napretku**.

Rezultat uspješnog pokretanja, jedinstveni entitet profila klijenta, pronaći ćete na stranici **Entiteti**. Vaš objedinjeni entitet klijenta naziva se **Klijenti** u odjeljku **Profili**. Prvo uspješno pokretanje uparivanja stvara objedinjeni entitet *Klijent*. Sva sljedeća pokretanja uparivanja proširuju taj entitet.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies). Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla. Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.

## <a name="review-and-validate-your-matches"></a>Pregled i provjera valjanosti vaših uparivanja

Idite u odjeljak **Podaci** > **Objedinjavanje** > **Uparivanje** kako biste procijenili kvalitetu vaših parova uparivanja i po potrebi ih pročistili.

Pločice na vrhu stranice prikazuju ključne mjerne podatke sažimajući broj uparenih zapisa i duplikata.

:::image type="content" source="media/match-KPIs.png" alt-text="Obrezana snimka zaslona ključnih mjernih podataka na stranici Uparivanje s brojevima i pojedinostima.":::

- **Jedinstveni izvorni zapisi** pokazuje broj pojedinačnih izvornih zapisa koji su obrađeni u zadnjem izvođenju uparivanja.
- **Upareni i neupareni zapisi** ističe koliko jedinstvenih zapisa ostaje nakon obrade pravila uparivanja.
- **Samo upareni zapisi** prikazuje broj uparivanja u svim vašim parovima uparivanja.

Rezultate svakog para uparivanja i njegova pravila možete procijeniti u tablici **Pojedinosti o uparenim zapisima**. Usporedite broj zapisa koji proizilaze iz para uparivanja s postotkom uspješno uparenih zapisa.

Pregledajte pravila para uparivanja kako biste vidjeli postotak uspješno uparenih zapisa na razini pravila. Odaberite elipsu (...), a zatim odaberite **Pretpregled uparivanja** da biste pregledali sve ove zapise na razini pravila. Preporučujemo da pogledate neke zapise kako biste potvrdili da su se pravilno uparili.

Isprobajte različite pragove preciznosti u uvjetima kako biste pronašli optimalnu vrijednost.

  1. Odaberite elipsu (...) za pravilo s kojim želite eksperimentirati pa odaberite **Uređivanje**.

  2. Promijenite vrijednosti preciznosti u uvjetima koje želite revidirati.

  3. Odaberite **Pretpregled** pa pogledajte broj uparenih i neuparenih zapisa za odabrani uvjet.

## <a name="manage-match-rules"></a>Upravljanje pravilima uparivanja

Većinu parametara uparivanja možete ponovno konfigurirati i fino podesiti.

:::image type="content" source="media/match-rules-management.png" alt-text="Snimka zaslona padajućeg izbornika s mogućnostima pravila uparivanja.":::

- **Promijenite redoslijed pravila** ako ste definirali više pravila. Redoslijed pravila uparivanja možete izmijeniti odabirom mogućnosti **Pomakni prema gore** i **Pomakni prema dolje** ili povlačenjem i ispuštanjem.

- **Promijenite uvjete pravila** odabirom mogućnosti **Uređivanje** i odaberite različita polja.

- **Deaktiviraj pravilo** zadržava pravilo podudaranja dok ga isključuje iz postupka podudaranja.

- **Duplicirajte svoja pravila** ako ste definirali pravilo uparivanja i želite stvoriti slično pravilo s izmjenama, odaberite **Dupliciranje**.

- **Izbrišite pravilo** odabirom simbola **Brisanje**.

## <a name="specify-custom-match-conditions"></a>Određivanje prilagođenih uvjeta uparivanja

Možete odrediti uvjete s kojima bi se određeni zapisi trebali uvijek ili nikada uparivati. Ta se pravila mogu prenijeti kako bi zamijenila standardni postupak uparivanja. Na primjer, ako u našim zapisima postoje John Doe I i John Doe II, sustav bi ih mogao upariti kao jednu osobu. Prilagođena pravila uparivanja omogućuju vam da odredite da se njihovi profili odnose na različite osobe. 

1. Idite u odjeljak **Podaci** > **Objedinjavanje** > **Uparivanje** i odaberite **Prilagođeno uparivanje** u odjeljku **Pojedinosti o uparenim zapisima**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Snimka zaslona odjeljka s pravilima uparivanja s istaknutom kontrolom prilagođenog uparivanja.":::

1. Ako niste postavili pravila za prilagođeno uparivanje, vidjet ćete novo okno **Prilagođeno uparivanje** s više pojedinosti.

1. Odaberite **Ispuni predložak** da biste dobili datoteku predloška koja može odrediti koji se zapisi iz kojih entiteta trebaju uvijek ili nikada uparivati. Morat ćete zasebno ispuniti zapise "uvijek uparuj" i "nikada ne uparuj" u dvije različite datoteke.

1. Predložak sadrži polja za određivanje entiteta i vrijednosti primarnog ključa entiteta koji će se koristiti u prilagođenom uparivanju. Na primjer, ako želite da se primarni ključ *12345* iz entiteta *Prodaja* uvijek upari s primarnim ključem *34567* iz entiteta *Kontakt*, ispunite predložak:
    - Entitet1: Prodaja
    - Ključ entiteta1: 12345
    - Entitet2: Kontakt
    - Ključ entiteta2: 34567

   Ista datoteka predloška može odrediti zapise prilagođenog uparivanja iz više entiteta.
   
   Ako želite navesti prilagođeno podudaranje za uklanjanje duplikata na entitetu, navedite isti entitet kao Entitet1 i Entitet2 i postavite različite vrijednosti primarnog ključa.

1. Nakon dodavanja svih poništavanja koje želite primijeniti, spremite datoteku predloška.

1. Idite na **Podaci** > **Izvori podataka** i unesite datoteke predloška kao nove entitete. Nakon uvođenja, možete ih koristiti za određivanje konfiguracije uparivanja.

1. Nakon što ste prenijeli datoteke i ako su entiteti dostupni, ponovno odaberite mogućnost **Prilagođeno uparivanje**. Vidjet ćete mogućnosti za određivanje entiteta koje želite uključiti. Odaberite tražene entitete s padajućeg izbornika.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Snimka zaslona dijaloga za odabir nadjačavanja za scenarij prilagođenog uprivanja.":::

1. Odaberite entitete koje želite koristiti za **Uvijek uparuj** i **Nikada ne uparuj** i odaberite **Gotovo**.

1. Odaberite **Spremanje** na stranici **Uparivanje** za primjenu konfiguracije prilagođenog uparivanja.

1. Odaberite **Pokretanje** na stranici **Uparivanje** za pokretanje postupka uparivanja. Ostala navedena pravila uparivanja se zamjenjuju konfiguracijom prilagođenog uparivanja.

> [!TIP]
> Idite u odjeljak **Podaci** > **Entiteti** i pregledajte entitet **ConflationMatchPair** za potvrdu primjene nadjačavanja.

## <a name="next-step"></a>Sljedeći korak

Nakon dovršetka procesa uparivanja za barem jedan par uparivanja, moguće proturječnosti u podacima možete riješiti temom [**Spajanje**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
