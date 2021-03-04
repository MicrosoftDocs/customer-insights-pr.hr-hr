---
title: Podudaranje entiteta za objedinjavanje podataka
description: Prilagodite entitete da biste stvorili objedinjene profile klijenata.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267469"
---
# <a name="match-entities"></a>Slaganje entiteta

Nakon završetka faze mapiranja, spremni ste za uparivanje entiteta. Faza uparivanja određuje kako kombinirati skupove podataka u objedinjeni skup podataka profila klijenta. Faza uparivanja zahtijeva najmanje [dva mapirana entiteta](map-entities.md).

## <a name="specify-the-match-order"></a>Zadavanje redoslijeda uparivanja

Idite na **Podaci** > **Objedini** > **Upari** i odaberite **Postavi redoslijed** za početak faze podudaranja.

Svako uparivanje objedinjuje dva ili više entiteta u jedan entitet, a istovremeno održava postojanost svakog objedinjenog zapisa klijenta. U sljedećem primjeru odabrali smo tri entiteta: **ContactCSV: TestData** kao **primarni** entitet, **WebAccountCSV: TestData** kao **entitet 2** i **CallRecordSmall: TestData** kao **entitet 3**. Dijagram iznad odabira ilustrira kako će se izvršiti redoslijed uparivanja.

> [!div class="mx-imgBorder"]
> ![Uređivanje redoslijeda uparivanja podataka](media/configure-data-match-order-edit-page.png "Uređivanje redoslijeda uparivanja podataka")
  
**Primarni** entitet uparuje se s **entitetom 2**. Skup podataka koji proizlazi iz prvog uparivanja uparuje se s **entitetom 3**.
U ovom smo primjeru odabrali samo dva uparivanja, ali sustav može podržati više.

> [!IMPORTANT]
> Entitet koji odaberete kao **primarni** entitet poslužit će kao osnova za vaš objedinjeni glavni skup podataka. Ovom entitetu dodat će se dodatni entiteti koji su odabrani tijekom faze uparivanja. Istodobno to ne znači da će objedinjeni entitet uključivati *sve* podatke uključene u ovaj entitet.
>
> Postoje dva razmatranja koja vam mogu pomoći da odaberete hijerarhiju entiteta:
>
> - Za koji entitet smatrate da ima najpotpunije i najpouzdanije podatke o klijentima?
> - Ima li entitet koji ste upravo identificirali atribute koje dijele i drugi entiteti (na primjer, ime, telefonski broj ili adresa e-pošte)? Ako ne, odaberite drugi najpouzdaniji entitet.

Odaberite **Gotovo** da biste spremili redoslijed uparivanja.

## <a name="define-rules-for-your-first-match-pair"></a>Definiranje pravila za prvi par usklađivanja

Nakon određivanja redoslijeda uparivanja vidjet ćete definirana uparivanja na stranici **Upari**. Pločice na vrhu zaslona bit će prazne dok ne pokrenete redoslijed uparivanja.

> [!div class="mx-imgBorder"]
> ![Definiranje pravila](media/configure-data-match-need-rules.png "Definiranje pravila")

Upozorenje **Potrebna pravila** upućuje na to da nijedno pravilo uparivanja nije definirano za par uparivanja. Pravila uparivanja određuju logiku kojom će se uparivati određeni par entiteta.

1. Da biste definirali prvo pravilo, otvorite okno **Definicija pravila** odabirom odgovarajućeg retka uparivanja u tablici uparivanja (1), a zatim odaberite **Izradi novo pravilo** (2).

   > [!div class="mx-imgBorder"]
   > ![Izrada novog pravila](media/configure-data-match-new-rule2.png "Izradi novo pravilo")

2. U oknu **Uredi pravilo** konfigurirajte uvjete za to pravilo. Svaki uvjet predstavljen je dvama recima koji uključuju obavezne odabire.

   > [!div class="mx-imgBorder"]
   > ![Okno Novo pravilo](media/configure-data-match-new-rule-condition.png "Okno Novo pravilo")

   Entitet/polje (prvo) - atribut koji će se koristiti za uparivanje iz entiteta para prvog uparivanja. Primjeri mogu uključivati telefonski broj ili adresu e-pošte. Odaberite atribut koji će vjerojatno biti jedinstven za klijenta.

   > [!TIP]
   > Izbjegavajte uparivanje na temelju atributa vrste aktivnosti. Drugim riječima, ako se čini da je atribut aktivnost, onda bi to mogli biti loši kriteriji za uparivanje.  

   Entitet/polje (drugo) - atribut koji će se koristiti za uparivanje iz entiteta para drugog uparivanja.

   Normalizacija - **Metoda normalizacije**: Za odabrane atribute dostupne su različite mogućnosti normalizacije. Na primjer, uklanjanje interpunkcije ili uklanjanje razmaka

   Za normalizaciju Naziva organizacije (pretpregled) možete odabrati i **Vrsta (telefon, naziv, organizacija)**

   > [!div class="mx-imgBorder"]
   > ![Normalizacija-B2B](media/match-normalization-b2b.png "Normalizacija-B2B")

   Razina preciznosti - Razina preciznosti koja će se koristiti za ovaj uvjet. Postavljanje razine preciznosti za uvjet uparivanja može imati dvije vrste: **Osnovno** i **Prilagođeno**.  
   - Osnovno: pruža vam četiri mogućnosti za odabir: nisko, srednje, visoko i točno. Odaberite **Točno** da biste uparili samo zapise s podudaranjem od 100 posto. Odaberite jednu od ostalih razina za uparivanje zapisa koji nisu 100 posto identični.
   - Prilagođeno: s pomoću klizača definirajte prilagođeni postotak uparivanja zapisa ili unesite vrijednost u polje **Prilagođeno**. Sustav će upariti samo zapise koji prelaze taj prag kao združene parove uparivanja. Vrijednosti na klizaču su između 0 i 1. Dakle, 0,64 predstavlja 64 posto.

3. Odaberite **Gotovo** da biste spremili pravilo.

### <a name="add-multiple-conditions"></a>Dodavanje više uvjeta

Da biste uparili entitete samo ako je ispunjeno više uvjeta, dodajte više uvjeta koji su povezani putem operatora AND.

1. U oknu **Uredi pravilo**, odaberite **Dodaj uvjet**. Uvjete možete izbrisati i odabirom gumba za uklanjanje pokraj postojećeg uvjeta.

2. Odaberite **Gotovo** da biste spremili pravilo.

## <a name="add-multiple-rules"></a>Dodavanje više pravila

Svaki uvjet primjenjuje se na jedan par atributa, dok pravila predstavljaju skupove uvjeta. Da bi se entiteti uparivali prema različitim skupovima atributa, možete dodati još pravila.

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Objedini** > **Prilagodi**.

2. Odaberite entitet koji želite ažurirati i odaberite **Dodaj pravila**.

3. Slijedite postupak koji je opisan u odjeljku [Definiranje pravila za prvi par uparivanja](#define-rules-for-your-first-match-pair).

> [!NOTE]
> Redoslijed pravila je važan. Algoritam uparivanja pokušava upariti na temelju prvog pravila i nastavlja s drugim pravilom samo ako nisu identificirana uparivanja pod prvim pravilom.

## <a name="define-deduplication-on-a-match-entity"></a>Definiranje uklanjanja duplikata na entitetu podudaranja

Uz specificiranje pravila podudaranja među entitetima kako je navedeno u gornjim odjeljcima, možete odrediti i pravila uklanjanja duplikata. *Uklanjanje duplikata* je proces. Identificira duplikate zapisa, spaja ih u jedan zapis i povezuje sve izvorne zapise s tim spojenim zapisom sa zamjenskim ID-jevima za spojeni zapis.

Nakon što se deduplicirani zapis identificira, taj će se zapis koristiti u procesu podudaranja među entitetima. Uklanjanje duplikata provodi se na razini entiteta i može se primijeniti na svaki entitet koji se koristi u procesu podudaranja.

### <a name="add-deduplication-rules"></a>Dodavanje pravila uklanjanja duplikata

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Objedini** > **Prilagodi**.

1. U odjeljku **Spojeni duplikati** odaberite **Postavi entitete**.

1. U odjeljku **Spoji preference** odaberite entitete na koje želite primijeniti uklanjanje duplikata.

1. Navedite kako spojiti duplikate zapisa i odaberite jednu od tri mogućnosti spajanja:
   - *Najispunjeniji*: Identificira zapis s najviše ispunjenih atributa kao pobjednički zapis. To je zadana mogućnost spajanja.
   - *Najnoviji*: Identificira pobjednički zapis na temelju nedavnosti. Zahtijeva datum ili numeričko polje za definiranje nedavnosti.
   - *Najstariji*: Identificira pobjednički zapis na temelju starosti. Zahtijeva datum ili numeričko polje za definiranje nedavnosti.
 
   > [!div class="mx-imgBorder"]
   > ![Korak 1 pravila uklanjanja duplikata](media/match-selfconflation.png "Korak 1 pravila uklanjanja duplikata")
 
1. Nakon što se odaberu entiteti i postave njihove preference spajanja, odaberite **Stvori novo pravilo** kako bi se definirala pravila uklanjanja duplikata na razini entiteta.
   - **Odaberi polje** navodi sva dostupna polja iz tog entiteta na kojem želite ukloniti duplikate izvornih podataka.
   - Navedite postavke normalizacije i točnosti na sličan način kao što je navedeno u podudaranju među entitetima.
   - Dodatne uvjete možete definirati odabirom **Dodaj uvjet**.
 
   > [!div class="mx-imgBorder"]
   > ![Korak 2 pravila uklanjanja duplikata](media/match-selfconflation-rules.png "Korak 2 pravila uklanjanja duplikata")

  Možete stvoriti više pravila za uklanjanje duplikata za entitet. 

1. Pokretanje procesa podudaranja sada grupira zapise na temelju uvjeta definiranih u pravilima za uklanjanje duplikata. Nakon grupiranja zapisa primjenjuje se politika spajanja za identificiranje pobjedničkog zapisa.

1. Taj se pobjednički zapis zatim prenosi na međusobno podudaranje entiteta, zajedno sa zapisima koji nisu pobjednički (na primjer, zamjenski ID-jevi) da bi se poboljšala kvaliteta podudaranja.

1. Bilo koja prilagođena pravila podudaranja definirana za pravila koja se uvijek podudaraju i nikada se ne podudaraju s preskočenim pravilima o uklanjanju duplikata. Ako pravilo o uklanjanju duplikata identificira podudarne zapise, a prilagođeno pravilo podudaranja postavi se tako da se nikada ne podudara s tim zapisima, tada se ova dva zapisa neće podudarati.

1. Nakon pokretanja postupka podudaranja vidjet ćete statistiku uklanjanja duplikata.
   
> [!NOTE]
> Navođenje pravila za uklanjanje duplikata nije obavezno. Ako takva pravila nisu konfigurirana, primjenjuju se pravila koja je definirao sustav. Oni sažimaju sve zapise koji dijele istu kombinaciju vrijednosti (točno podudaranje) iz primarnog ključa i polja u pravilima za podudaranje u jedan zapis prije prosljeđivanja podataka entiteta u podudaranje među entitetima radi poboljšane izvedbe i ispravnosti sustava.

## <a name="run-your-match-order"></a>Pokretanje redoslijeda uparivanja

Nakon definiranja pravila podudaranja, uključujući pravila za podudaranje i uklanjanje duplikata među entitetima, možete pokrenuti redoslijed podudaranja. Na stranici **Upari**, odaberite **Pokreni** da biste pokrenuli proces. Dovršetak algoritma uparivanja može potrajati. Ne možete mijenjati svojstva na stranici **Upari** dok se proces uparivanja ne dovrši. Vidjet ćete objedinjeni entitet profila klijenta koji je izrađen na stranici **Entiteti**. Objedinjeni entitet klijenta naziva se **ConflationMatchPairs : CustomerInsights**.

Da biste napravili dodatne promjene i ponovo pokrenuli korak, možete otkazati slaganje u tijeku. Odaberite tekst **Osvježavanje...** i odaberite **Otkaži posao** na dnu bočnog okna koje se pojavljuje.

Kada je postupak slaganja dovršen, tekst **Osvježavanje..** promijenit će se u **Uspješno** i ponovno možete koristiti sve funkcionalnosti stranice.

Proces prvog uparivanja rezultira izradom objedinjenog glavnog entiteta. Sva naknadna pokretanja uparivanja rezultiraju širenjem tog entiteta.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies). Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla. Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.

## <a name="deduplication-output-as-an-entity"></a>Izlazna vrijednost uklanjanja duplikata kao entitet
Osim objedinjenog glavnog entiteta stvorenog kao dio međusobnog podudaranja entiteta, postupak uklanjanja duplikata također generira novi entitet za svaki entitet iz naloga za podudaranje da bi se identificirali deduplicirani zapisi. Ti se entiteti mogu pronaći zajedno s **ConflationMatchPairs:CustomerInsights** u odjeljku **Sustav** na stranici **Entiteti** s nazivom **Deduplication_Datasource_Entity**.

Entitet izlazne vrijednosti uklanjanja duplikata sadrži sljedeće informacije:
- ID-jevi/ključevi
  - Polje primarnog ključa i njegovo zamjensko polje ID-ja. Polje zamjenskih ID-jeva sastoji se od svih zamjenskih ID-jeva identificiranih za zapis.
  - Polje Deduplication_GroupId prikazuje grupu ili klaster identificiran unutar entiteta koji grupira sve slične zapise na temelju navedenih polja uklanjanja duplikata. To se koristi u svrhu obrade sustava. Ako nisu navedena ručna pravila za uklanjanje duplikata i ako se primjenjuju pravila za uklanjanje duplikata koja je definirao sustav, ovo polje možda nećete pronaći u entitetu izlazne vrijednosti uklanjanja duplikata.
  - Deduplication_WinnerId: Ovo polje sadrži ID pobjednika iz identificiranih grupa ili klastera. Ako je Deduplication_WinnerId jednak vrijednosti primarnog ključa za zapis, to znači da je zapis pobjednički zapis.
- Polja koja se koriste za definiranje pravila za uklanjanje duplikata.
- Polja Pravilo i Ocjena označavaju koja su pravila za uklanjanja duplikata primijenjena i ocjenu koju vraća algoritam podudaranja.

## <a name="review-and-validate-your-matches"></a>Pregled i provjera valjanosti vaših uparivanja

Procijenite kvalitetu parova uparivanja i precizirajte je:

- Na stranici **Upari** vidjet ćete dvije pločice koje prikazuju početne uvide o podacima.

  - **Jedinstveni klijenti**: prikazuje broj jedinstvenih profila koje je sustav identificirao.
  - **Upareni zapisi**: prikazuje broj uparivanja u svim parovima uparivanja.

- U tablici **Redoslijed uparivanja** možete ocijeniti rezultate svakog para uparivanja usporedbom broja zapisa koji su proizašli iz tog entiteta para uparivanja u odnosu na postotak uspješno uparenih zapisa.

- U odjeljku entiteta **Pravila** u tablici **Redoslijed uparivanja** pronaći ćete postotak uspješno uparenih zapisa na razini pravila. Odabirom simbola tablice pokraj pravila možete pregledati sve te zapise na razini pravila. Preporučujemo da pregledate podskup zapisa da biste provjerili jesu li ispravno upareni.

- Eksperimentirajte s različitim pragovima preciznosti oko uvjeta da biste identificirali optimalnu vrijednost.

  1. Odaberite trotočku (...) za pravilo para uparivanja s kojim želite eksperimentirati i odaberite **Uredi**.

  2. Odaberite uvjet s kojim želite eksperimentirati. Svaki kriterij predstavlja jedan redak u oknu **Pravilo uparivanja**.

  3. Ono što ćete vidjeti na stranici **Pretpregled kriterija** ovisi o razini preciznosti koju ste odabrali za uvjet. Pronađite broj uparenih i neuparenih zapisa za odabrani uvjet.

     Usvojite bogato razumijevanje učinaka različitih razina praga. Možete usporediti koliko će se zapisa upariti ispod svake razine praga i pregledati zapise ispod svake mogućnosti. Odaberite svaku pločicu i pregledajte podatke u odjeljku tablice.

## <a name="optimize-your-matches"></a>Optimizacija uparivanja

Povećajte kvalitetu rekonfiguracijom nekih parametara uparivanja:

- **Promijenite redoslijed uparivanja** odabirom **Uredi** i promijenite polja redoslijeda uparivanja.

  > [!div class="mx-imgBorder"]
  > ![Uređivanje redoslijeda uparivanja podataka](media/configure-data-match-order-edit.png "Uređivanje redoslijeda uparivanja podataka")

- **Promijenite redoslijed pravila** ako ste definirali više pravila. Možete izmijeniti redoslijed pravila uparivanja odabirom mogućnosti **Premjesti gore** i **Premjesti dolje** u rešetki za pravila uparivanja.

  > [!div class="mx-imgBorder"]
  > ![Promjena redoslijeda pravila](media/configure-data-change-rule-order.png "Promjena redoslijeda pravila")

- **Duplicirajte pravila** ako ste definirali pravilo uparivanja i željeli biste izraditi slično pravilo s izmjenama. Učinite to odabirom **Dupliciraj**.

  > [!div class="mx-imgBorder"]
  > ![Dupliciranje pravila](media/configure-data-duplicate-rule.png "Dupliciranje pravila")

- **Deaktiviraj pravilo** zadržava pravilo podudaranja dok ga isključuje iz postupka podudaranja.

  > [!div class="mx-imgBorder"]
  > ![Deaktiviraj pravilo](media/configure-data-deactivate-rule.png "Deaktiviraj pravilo")

- **Uredite pravila** odabirom simbola **Uredi**. Možete izvršiti sljedeće promjene:

  - Promjena atributa za uvjet: Odaberite nove atribute unutar određenog retka uvjeta.
  - Promjena praga za uvjet: Prilagodite klizač preciznosti.
  - Promjena metode normalizacije za uvjet: Ažurirajte metodu normalizacije.

## <a name="specify-your-custom-match-records"></a>Određivanje prilagođenog uparivanja zapisa

Možete odrediti uvjete s kojima bi se određeni zapisi trebali uvijek ili nikada uparivati. Ta se pravila mogu skupno prenijeti u proces uparivanja.

1. Odaberite mogućnost **Prilagođeno uparivanje** na zaslonu **Redoslijed uparivanja**.

   > [!div class="mx-imgBorder"]
   > ![Izrada prilagođenog uparivanja](media/custom-match-create.png "Izrada prilagođenog uparivanja")

2. Ako nemate prenesenih entiteta, vidjet ćete novi dijaloški okvir **Prilagođeno uparivanje** koji zahtijeva da ispunite neke pojedinosti. Ako ste ranije naveli te pojedinosti, prijeđite na korak 8.

   > [!div class="mx-imgBorder"]
   > ![Dijaloški okvir Novo prilagođeno uparivanje](media/custom-match-new-dialog-box.png "Dijaloški okvir Novo prilagođeno uparivanje")

3. Odaberite **Ispuni predložak** da biste dobili datoteku predloška koja može odrediti koji se zapisi iz kojih entiteta trebaju uvijek ili nikada uparivati. Morat ćete zasebno ispuniti zapise "uvijek uparuj" i "nikada ne uparuj" u dvije različite datoteke.

4. Predložak sadrži polja za određivanje entiteta i vrijednosti primarnog ključa entiteta koji će se koristiti u prilagođenom uparivanju. Na primjer, ako želite da se primarni ključ 12345 iz entiteta Prodaja uvijek uparuje s primarnim ključem 34567 iz entiteta Kontakt, morat ćete navesti kako slijedi:
    - Entitet1: Prodaja
    - Ključ entiteta1: 12345
    - Entitet2: Kontakt
    - Ključ entiteta2: 34567

   Ista datoteka predloška može odrediti zapise prilagođenog uparivanja iz više entiteta.
   
   Ako želite navesti prilagođeno podudaranje za uklanjanje duplikata na entitetu, navedite isti entitet kao Entitet1 i Entitet2 i postavite različite vrijednosti primarnog ključa.

5. Nakon dodavanja svih poništavanja koje želite primijeniti, spremite datoteku predloška.

6. Idite na **Podaci** > **Izvori podataka** i unesite datoteke predloška kao nove entitete. Nakon uvođenja, možete ih koristiti za određivanje konfiguracije uparivanja.

7. Nakon što ste prenijeli datoteke i ako su entiteti dostupni, ponovno odaberite mogućnost **Prilagođeno uparivanje**. Vidjet ćete mogućnosti za određivanje entiteta koje želite uključiti. Odaberite tražene entitete s padajućeg izbornika.

   > [!div class="mx-imgBorder"]
   > ![Poništavanja prilagođenog uparivanja](media/custom-match-overrides.png "Poništavanja prilagođenog uparivanja")

8. Odaberite entitete koje želite koristiti za **Uvijek uparuj** i **Nikada ne uparuj** i odaberite **Gotovo**.

9. Odaberite **Spremi** na stranici **Upari** za konfiguraciju prilagođenog uparivanja koje ste upravo postavili.

10. Odaberite **Pokreni** na stranici **Upari** da biste pokrenuli proces uparivanja i konfiguracija prilagođenog uparivanja stupit će na snagu. Sva pravila koja odgovaraju sustavu poništavaju se skupom konfiguracije.

11. Nakon dovršetka uparivanja, možete provjeriti entitet **ConflationMatchPair** da biste potvrdili da su poništavanja primijenjena u združenim uparivanjima.

## <a name="next-step"></a>Sljedeći korak

Nakon dovršetka procesa uparivanja za barem jedan par uparivanja, moguće proturječnosti u podacima možete riješiti temom [**Spajanje**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]