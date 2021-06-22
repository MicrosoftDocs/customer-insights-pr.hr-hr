---
title: Predviđanje preporuka proizvoda
description: Predvidite proizvode koje će klijent vjerojatno kupiti ili s kojima će biti u interakciji.
ms.date: 03/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 01704f78cfe1f6ceeee19ff825fc65150894d4ed
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095547"
---
# <a name="product-recommendation-prediction-preview"></a>Predviđanje preporuka proizvoda (pretpregled)

Model preporuke proizvoda stvara skupove prediktivnih preporuka proizvoda. Preporuke se temelje na prethodnom ponašanju pri kupnji i klijentima sa sličnim obrascima kupnje. Nova predviđanja preporuka proizvoda možete stvoriti na stranici **Inteligencija** > **Predviđanja**. Odaberite **Moja predviđanja** da biste vidjeli druga predviđanja koja ste stvorili.

Preporuke proizvoda mogu podlijegati lokalnim zakonima, uredbama i očekivanjima klijenata čiji model nije napravljen da bi ga se posebno uzelo u obzir.  Kao korisnik ove mogućnosti predviđanja **morate pregledati preporuke prije nego što ih dostavite svojim klijentima** kako biste bili sigurni da se pridržavate svih važećih zakona, uredbi i očekivanja klijenata u vezi s onim što možete preporučiti. 

Osim toga, rezultat ovog modela dat će vam preporuke na temelju ID-a proizvoda. Vaš mehanizam isporuke morat će mapirati predviđene ID-jeve proizvoda u odgovarajući sadržaj za vaše klijente kako bi se uzela u obzir lokalizacija, slikovni sadržaj i ostali sadržaj ili ponašanje specifično za tvrtku.

## <a name="sample-guide"></a>Uzorak vodiča

Ako ste zainteresirani za isprobavanje ove značajke, ali nemate podatke za ispunjavanje zahtjeva navedenih u nastavku, možete [stvoriti uzorak implementacije](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Preduvjeti

- Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.

- Poslovno znanje za razumijevanje različitih vrsta proizvoda za vaše poslovanje i načina na koji vaši klijenti stupaju u interakciju s njima. Podržavamo preporučivanje proizvoda koje su prethodno kupili vaši klijenti ili preporuke za nove proizvode.

- Podaci o vašim transakcijama, kupnjama i njihovoj povijesti:
    - Identifikatori transakcija za razlikovanje kupnji ili transakcija.
    - Identifikatori klijenata za mapiranje transakcija s vašim klijentima.
    - Datumi transakcijskih događaja koji navode datume na koje se transakcija dogodila.
    - Informacije o ID-ju proizvoda za transakciju.
    - (Neobavezno) Entitet podataka kataloga proizvoda za korištenje filtra proizvoda.
    - (Neobavezno) Je li transakcija povrat ili nije.
    - Shema semantičkih podataka zahtijeva sljedeće podatke:
        - **ID transakcije:** Jedinstveni identifikator kupnje ili transakcije.
        - **Datum transakcije:** Datum kupnje ili transakcije.
        - **Vrijednost transakcije:** numerička vrijednost kupnje ili transakcije.
        - **Jedinstveni ID proizvoda:** ID kupljenog proizvoda ili usluge ako su vaši podaci na razini stavke retka.
        - (Neobvezno) **Kupnja ili povrat:** Booleovo polje u kojem vrijednost *true* identificira da je transakcija bila povrat. Ako podaci o kupnji ili povratu nisu navedeni, model i **Vrijednost transakcije** su negativni, pa ćemo i ove podatke koristiti za naznačivanje povrata.
- Značajke predloženih podataka:
    - Dovoljno povijesnih podataka: Najmanje jedna godina transakcijskih podataka, po mogućnosti dvije do tri godine kako bi se uključila određena sezonalnost.
    - Više kupnji po klijentu: Tri ili više transakcija po ID-ju klijenta
    - Broj klijenata: Najmanje 100 klijenata, po mogućnosti više od 10 000 klijenata. Model neće uspjeti s manje od 100 klijenata.

> [!NOTE]
> - Model zahtijeva povijest transakcija vaših klijenata. Definicija transakcije prilično je fleksibilna. Svi podaci koji opisuju interakciju korisnika i proizvoda mogu funkcionirati kao ulaz. Na primjer, kupnja proizvoda, pohađanje nastave ili prisustvovanje događaju.
> - Trenutno se može konfigurirati samo jedan entitet povijesti transakcija. Ako postoji više entiteta za kupnju, spojite ih u Power Query prije unosa podataka.
> - Ako su narudžba i pojedinosti o narudžbi različiti entiteti, spojite ih prije korištenja u modelu. Model ne funkcionira samo s ID-jem narudžbe ili ID-jem potvrde u entitetu.


## <a name="create-a-product-recommendation-prediction"></a>Stvaranje predviđanja preporuka proizvoda

1. U aplikaciji Customer Insights idite na **Inteligencija** > **Predviđanja**.

1. Odaberite pločicu **Model preporuka proizvoda (pretpregled)** i odaberite **Koristi ovaj model**.
   > [!div class="mx-imgBorder"]
   > ![Pločica modela preporuka proizvoda s gumbom Koristi ovaj model](media/product-recommendation-usethismodel.PNG "Pločica modela preporuka proizvoda s gumbom Koristi ovaj model")

1. Pregledajte informacije o zahtjevima modela. Ako imate potrebne podatke, odaberite **Početak**.

### <a name="name-model"></a>Imenovanje modela

1. Navedite naziv modela da biste ga razlikovali od ostalih modela.

1. Unesite naziv za izlazni entitet koristeći samo slova i brojeve, bez razmaka. To je naziv koji će entitet modela koristiti. Zatim odaberite **Dalje**.

### <a name="define-product-recommendation-configuration"></a>Definiranje konfiguracije preporuka proizvoda

1. Postavite **Broj proizvoda** koje želite preporučiti klijentu. Ova vrijednost ovisi o tome kako vaš način isporuke ispunjava podatke. Ako možete preporučiti tri proizvoda, postavite ovu vrijednost u skladu s tim.
   
   >[!TIP]
   > Možete odabrati **Spremi i zatvori** u bilo kojem trenutku kako biste predviđanje spremili kao skicu. Skicu predviđanja pronaći ćete na kartici **Moja predviđanja**.

1. Odaberite da li želite **predložiti proizvode koje su klijenti nedavno kupili**.

1. Ako ste odabrali da *nećete* preporučiti nedavno kupljene proizvode, postavite **Prozor pogleda unatrag**. Ova postavka određuje vremenski okvir koji model uzima u obzir prije ponovnog preporučivanja proizvoda korisniku. Na primjer, naznačite da klijent kupuje prijenosno računalo svake dvije godine. Ovaj će okvir pogledati u povijest kupnje u posljednje dvije godine, a ako pronađe stavku, stavka će se filtrirati iz preporuka.

1. Odaberite **Sljedeće**

### <a name="add-required-data"></a>Dodajte potrebne podatke

1. Odaberite **Dodaj podatke** za **Povijest transakcija klijenta** i odaberite entitet koji pruža informacije o povijesti transakcija/kupnji kao što je opisano u [preduvjetima](#prerequisites).

1. Mapirajte semantička polja na atribute unutar entiteta povijesti kupnje i odaberite **Sljedeće**. Za opis polja pogledajte [preduvjete](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definiranje odnosa entiteta](media/product-recommendation-purchasehistorymapping.PNG "Stranica povijesti kupnji koja prikazuje semantičke atribute koji su mapirani u polja u odabranom entitetu povijesti kupnji")

1. Ako polja nisu popunjena, konfigurirajte odnos između entiteta povijesti kupnji i entiteta *Klijent*.
    1. Odaberite **Entitet povijesti kupnje**.
    1. Odaberite **Polje** koje identificira klijenta u entitetu povijesti kupnje. Mora se odnositi na primarni ID klijenta vašeg entiteta *Klijent*.
    1. Odaberite **Entitet klijenta** koji odgovara vašem primarnom entitetu klijenta.
    1. Unesite naziv koji opisuje odnos.
       > [!div class="mx-imgBorder"]
       > ![Stranica povijesti kupnji koja prikazuje stvaranje odnosa s klijentom](media/model-purchase-join.png "Stranica povijesti kupnji koja prikazuje stvaranje odnosa s klijentom")

1. Odaberite **Spremi**.

1. Odaberite **Dalje**.

### <a name="configure-product-filters"></a>Konfiguracija filtara proizvoda

Ponekad su samo određeni proizvodi korisni ili prikladni za vrstu predviđanja koju izrađujete. Filtri proizvoda omogućuju vam prepoznavanje podskupa proizvoda sa specifičnim značajkama koje ćete preporučiti svojim klijentima. Model će koristiti sve dostupne proizvode za učenje uzoraka, ali će koristiti samo proizvode koji odgovaraju filtru proizvoda u svojem izlazu.

1. U koraku **Dodaj informacije o proizvodu** dodajte katalog proizvoda s informacijama za svaki proizvod. Mapirajte potrebne informacije u odabiru **Sljedeće**.

3. U koraku **Filtri proizvoda** odaberite između sljedećih mogućnosti.

   * **Bez filtara**: Koristite sve proizvode u predviđanju preporuke za proizvod.

   * **Definirajte određene filtre proizvoda**: Koristite određene proizvode u predviđanju preporuke za proizvod.

1. Odaberite **Dalje**.

1. Ako odlučite definirati filtar proizvoda, trebate ga definirati odmah. U oknu **Atributi kataloga proizvoda** odaberite atribute iz *Entitet kataloga proizvoda* koje želite uključiti u filtar.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Bočno okno prikazuje atribut u entitetu kataloga proizvoda za odabir za filtre proizvoda.":::

1. Odaberite želite li da filtar proizvoda koristi poveznike **and** ili **or** za logičko kombiniranje vašeg odabira atributa iz kataloga proizvoda.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Uzorak konfiguracije filtara proizvoda u kombinaciji s logičkim AND poveznicima.":::

1. Odaberite **Dalje**.

### <a name="set-update-schedule-and-review-configuration"></a>Postavljanje rasporeda ažuriranja i pregled konfiguracije

1. Postavite učestalost ponovnog uvježbavanja svog modela. Ova je postavka važna za ažuriranje točnosti predviđanja jer se novi podaci uvoze u Customer Insights. Većina tvrtki može ponovno uvježbavati jednom mjesečno i steći dobru točnost predviđanja.

1. Odaberite **Dalje**.

1. Pregledajte konfiguraciju. Možete se vratiti bilo kojem dijelu konfiguracije predviđanja odabirom **Uredi** ispod prikazane vrijednosti. Također, možete odabrati korak konfiguracije s pokazatelja napretka.

1. Ako su sve vrijednosti pravilno konfigurirane, odaberite **Spremi i pokreni** za početak procesa predviđanja. Na kartici **Moja predviđanja** možete vidjeti status svojih predviđanja. Proces može potrajati nekoliko sati ovisno o količini podataka korištenih za predviđanje.

## <a name="review-a-prediction-status-and-results"></a>Pregled statusa i rezultata predviđanja

1. Idite na karticu **Moja predviđanja** pod **Inteligencija** > **Predviđanja**.
   > [!div class="mx-imgBorder"]
   > ![Pogledajte stranicu Moja predviđanja](media/product-recommendation-mypredictions.PNG "Pogledajte stranicu Moja predviđanja")

1. Odaberite predviđanje koje želite pregledati.
   - **Naziv predviđanja:** Naziv predviđanja naveden prilikom njegovog stvaranja.
   - **Vrsta predviđanja:** Vrsta modela korištenog za to predviđanje
   - **Entitet rezultata:** Naziv entiteta za pohranu rezultata predviđanja. Entitet ovog naziva možete pronaći u **Podaci** > **Entiteti**.    
      *Ocjena* u izlaznom entitetu kvantitativna je mjera preporuke. Model preporučuje proizvode s višom ocjenom u odnosu na proizvode s nižom ocjenom.
   - **Predviđeno polje:** Ovo se polje popunjava samo za neke vrste predviđanja i ne koristi se u predviđanju preporuke za proizvod.
   - **Status:** Trenutačni status izvršenja predviđanja.
        - **Na čekanju:** Predviđanje trenutno čeka na pokretanje drugih procesa.
        - **Osvježava se:** Predviđanje je trenutačno u fazi „ocjene” obrade za dobivanje rezultata koji će se preliti u entitet rezultata.
        - **Neuspješno:** Predviđanje nije uspjelo. Za više detalja odaberite **Zapisnici**.
        - **Uspješno:** Predviđanje je uspjelo. Odaberite **Prikaz** ispod okomitih točkica kako biste pregledali predviđanje
   - **Uređeno:** Promijenjen je datum konfiguriranja za predviđanje.
   - **Zadnji put osvježeno:** Datum kada je predviđanje osvježilo rezultate u entitetu rezultata.

1. Odaberite okomitu trotočku uz predviđanje čije rezultate želite pregledati i odaberite **Prikaz**.
   > [!div class="mx-imgBorder"]
   > ![Prikaz izbornika okomite trotočke s mogućnostima za predviđanje, u koje spadaju uređivanje, osvježavanje, prikaz, zapisnici i brisanje](media/product-recommendation-verticalellipses.PNG "Prikaz izbornika okomite trotočke s mogućnostima za predviđanje, u koje spadaju uređivanje, osvježavanje, prikaz, zapisnici i brisanje")

1. Na stranici rezultata nalazi se pet primarnih odjeljaka podataka:
    1. **Performanse modela obuke:** Mogući rezultati su A, B ili C. Ovaj rezultat označava performanse predviđanja i može vam pomoći da donesete odluku o korištenju rezultata pohranjenih u entitetu rezultata.
        - Rezultati se određuju na temelju sljedećih pravila:
            - **A** Model će se smatrati **A** kvalitete ako je metrika "Uspjeh @ K" barem 10 % veća od osnovne vrijednosti. 
            - **B** Model će se smatrati **B** kvalitetom ako je metrika „Uspjeh @ K” 0 % do 10 % veća od osnovne vrijednosti.
            - **C** Model će se smatrati **C** kvalitetom ako je metrika „Uspjeh @ K” manja od osnovne vrijednosti.
               
               > [!div class="mx-imgBorder"]
               > ![Prikaz rezultata performansi modela](media/product-recommendation-modelperformance.PNG "Prikaz rezultata performansi modela")
            - **Osnovna vrijednost**: Model uzima najviše preporučene proizvode prema broju kupnji kod svih klijenata i koristi naučena pravila koja je identificirao model za stvaranje skupa preporuka za klijente. Predviđanja se zatim uspoređuju s najboljim proizvodima, što se računa brojem klijenata koji su kupili proizvod. Ako klijent ima barem jedan proizvod u preporučenim proizvodima, što se također vidi u najčešće kupljenim proizvodima, smatra se dijelom osnovne vrijednosti. Kad bi od ukupno 100 klijenata 10 kupilo preporučeni proizvod, polazište bi bilo 10%.
            - **Uspjeh @ K**: Korištenjem skupa provjere vremenskog razdoblja transakcija stvaraju se preporuke za sve klijente i uspoređuju se sa skupom provjere transakcija. Na primjer, u razdoblju od 12 mjeseci, 12. mjesec može se izdvojiti kao skup provjere podataka. Ako model predvidi barem jednu stvar koju biste kupili u 12. mjesecu na temelju onoga što je naučio iz prethodnih 11 mjeseci, klijent će povećati metriku "Uspjeh @ K".
    
    1. **Najčešće predlagani proizvodi (s brojačem):** Pet najboljih proizvoda predviđenih za vaše klijente.
       > [!div class="mx-imgBorder"]
       > ![Grafikon koji prikazuje 5 najviše preporučenih proizvoda](media/product-recommendation-topproducts.PNG "Grafikon koji prikazuje 5 najviše preporučenih proizvoda")
    
    1. **Ključni čimbenici preporuke:** Model koristi povijest transakcija klijenata za davanje preporuka za proizvode. Uči uzorke na temelju prošlih kupnji i pronalazi sličnosti između klijenata i proizvoda. Te se sličnosti zatim koriste za generiranje preporuka za proizvode.
    U nastavku se nalaze čimbenici koji mogu utjecati na preporuke za proizvode koje generira model. 
        - **Prošle transakcije**: Uzorke kupnje u prošlosti model je iskoristio za generiranje preporuka za proizvode. Na primjer, model može preporučiti _Miš s površinskim lukom_ ako je netko nedavno kupio _Surface Book 3_ i _Surface Pen_. Model je naučio da su u prošlosti mnogi klijenti kupili _Miš s površinskim lukom_ nakon kupnje _Surface Book 3_ i _Surface Pen_.
        - **Sličnost klijenata**: Preporučeni proizvod u prošlosti su kupovali drugi klijenti koji pokazuju slične uzorke kupnje. Na primjer, Ivanu su preporučene slušalice _Surface Headphones 2_ jer su Marica i Branko nedavno kupili slušalice _Surface Headphones 2_. Model vjeruje da je Ivan sličan Marici i Branku jer su u prošlosti imali slične uzorke kupnje.
        - **Sličnost proizvoda**: Preporučeni proizvod sličan je ostalim proizvodima koje je klijent ranije kupio. Model smatra da su dva proizvoda slična ako su kupljeni zajedno ili ako su ih kupili slični klijenti. Na primjer, netko dobije preporuku za _USB pogon za pohranu_ jer je ranije kupio _USB-C za USB prilagodnik_ i model vjeruje da je _USB pogon za pohranu_ sličan _USB-C za USB prilagodnik_ na temelju povijesnih uzoraka kupnje.

        Na svaku preporuku za proizvod utječe jedan ili više ovih čimbenika. Postotak preporuka u kojima je svaki čimbenik utjecaja igrao ulogu prikazan je na grafikonu. U sljedećem primjeru na 100 % preporuka utjecale su prošle transakcije, 60 % sličnost klijenata i 22 % sličnost proizvoda. Zadržite pokazivač iznad traka na grafikonu da biste vidjeli točan postotak doprinosa čimbenika utjecaja.

        > [!div class="mx-imgBorder"]
        > ![Ključni faktori preporuke](media/product-recommendation-keyrecommendationfactors.png "Ključni čimbenici za preporuku koje je model naučio za generiranje preporuka za proizvode")
       
     
   1. **Statistika podataka**: Daje pregled broja transakcija, klijenata i proizvoda koje je model razmatrao. Temelji se na ulaznim podacima koji su korišteni za učenje uzoraka i generiranje preporuka za proizvode.

      > [!div class="mx-imgBorder"]
      > ![Statistički podaci](media/product-recommendation-datastatistics.png "Statistika podataka oko ulaznih podataka koje model koristi za učenje uzoraka")

      Ovaj odjeljak prikazuje statistiku oko podatkovnih točaka koje je model koristio za učenje uzoraka i generiranje preporuka za proizvode. Filtriranje, kako je konfigurirano u konfiguraciji modela, primijenit će se na izlaz koji generira model. Međutim, model koristi sve dostupne podatke za učenje uzoraka. Stoga ako u konfiguraciji modela koristite filtriranje proizvoda, ovaj će odjeljak prikazati ukupni broj proizvoda koje je model analizirao kako bi naučio uzorke koji se mogu razlikovati od broja proizvoda koji odgovaraju definiranim kriterijima filtriranja.

   1. **Preporuke proizvoda s visokom pouzdanošću:** Uzorak preporuka koji se pruža vašim klijentima, a za koje model smatra da će ih klijent vjerojatno kupiti.    
      Ako se doda katalog proizvoda, ID-jevi proizvoda zamjenjuju se nazivima proizvoda. Nazivi proizvoda pružaju djelotvornije i intuitivnije informacije o predviđanjima.
       > [!div class="mx-imgBorder"]
       > ![Popis koji prikazuje prijedloge visoke pouzdanosti za odabrani skup pojedinačnih klijenata](media/product-recommendation-highconfidence.PNG "Popis koji prikazuje prijedloge visoke pouzdanosti za odabrani skup pojedinačnih klijenata")

## <a name="manage-predictions"></a>Upravljanje predviđanjima

Predviđanja je moguće optimizirati, riješiti, osvježiti ili izbrisati. Pregledajte izvješće o upotrebljivosti ulaznih podataka da biste saznali kako predviđanje učiniti bržim i pouzdanijim. Dodatne informacije potražite u odjeljku [Upravljanje predviđanjima](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
