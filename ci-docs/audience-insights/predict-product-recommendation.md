---
title: Predviđanje preporuka proizvoda
description: Predvidite proizvode koje će klijent vjerojatno kupiti ili s kojima će biti u interakciji.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270477"
---
# <a name="product-recommendation-prediction-preview"></a>Predviđanje preporuka proizvoda (pretpregled)

Model preporuke proizvoda stvara skupove prediktivnih preporuka proizvoda. Preporuke se temelje na prethodnom ponašanju pri kupnji i klijentima sa sličnim obrascima kupnje. Nova predviđanja preporuka proizvoda možete stvoriti na stranici **Inteligencija** > **Predviđanja**. Odaberite **Moja predviđanja** da biste vidjeli druga predviđanja koja ste stvorili.

Preporuke proizvoda mogu podlijegati lokalnim zakonima i propisima, kao i očekivanjima klijenata, za što model nije napravljen da bi to posebno uzeo u obzir.  Kao korisnik ove mogućnosti predviđanja, **morate pregledati preporuke prije nego što ih dostavite svojim klijentima** kako biste osigurali da se pridržavate svih važećih zakona i propisa, kao i očekivanja klijenata u vezi s onim što možete preporučiti. 

Osim toga, rezultat ovog modela dat će vam preporuke na temelju ID-a proizvoda. Vaš mehanizam isporuke trebat će uzeti predviđene ID-ove proizvoda i mapirati ih u odgovarajući sadržaj za vaše klijente da bi se uzeli u obzir lokalizacija, slikovni sadržaj i drugi sadržaj ili ponašanje specifično za poslovanje.

## <a name="sample-guide"></a>Uzorak vodiča

Ako ste zainteresirani za isprobavanje ove značajke, ali nemate podatke za ispunjavanje zahtjeva navedenih u nastavku, možete [stvoriti uzorak implementacije](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Preduvjeti

- Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.
- Poslovno znanje za razumijevanje različitih vrsta proizvoda za vaše poslovanje i načina na koji vaši klijenti stupaju u interakciju s njima. Podržavamo preporučivanje proizvoda koje su prethodno kupili vaši klijenti ili preporuke za nove proizvode.
- Podaci o vašim transakcijama, kupnjama i njihovoj povijesti:
    - Identifikatori transakcija za razlikovanje kupnji ili transakcija.
    - Identifikatori klijenata za mapiranje transakcija s vašim klijentima.
    - Datumi transakcijskih događaja koji navode datume na koje se transakcija dogodila.
    - (Neobavezno) Podaci o ID-u proizvoda za transakciju.
    - (Neobavezno) Je li transakcija povrat ili nije.
    - Shema semantičkih podataka zahtijeva sljedeće podatke:
        - **ID transakcije:** Jedinstveni identifikator kupnje ili transakcije.
        - **Datum transakcije:** datum kupnje ili transakcije.
        - **Vrijednost transakcije:** numerička vrijednost kupnje ili transakcije.
        - **Jedinstveni ID proizvoda:** ID kupljenog proizvoda ili usluge ako su vaši podaci na razini stavke retka.
        - (Neobavezno) **Kupnja ili povrat:** polje točno/netočno koje identificira je li transakcija bila povrat ili nije. Ako je **Vrijednost transakcije** negativna, te ćemo podatke koristiti i za zaključivanje povrata.


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

1. Ako ste odabrali da *nećete* preporučiti nedavno kupljene proizvode, postavite **Prozor pogleda unatrag**. Ova postavka određuje vremenski okvir koji model uzima u obzir prije ponovnog preporučivanja proizvoda korisniku. Na primjer, naznačite da klijent kupuje prijenosno računalo svake 2 godine. Ovaj će prozor pogledati povijest kupnji za posljednje 2 godine, a ako pronađu stavku, stavka će se filtrirati iz preporuka.

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

### <a name="set-schedule-and-review-configuration"></a>Postavite raspored i pregledajte konfiguraciju

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
   - **Predviđeno polje:** Ovo se polje popunjava samo za neke vrste predviđanja i ne koristi se u predviđanju gubitka.
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

1. Postoje tri primarna odjeljka podataka na stranici s rezultatima:
    1. **Performanse modela obuke:** Mogući rezultati su A, B ili C. Ovaj rezultat označava performanse predviđanja i može vam pomoći da donesete odluku o korištenju rezultata pohranjenih u entitetu rezultata.
        - Rezultati se određuju na temelju sljedećih pravila:
            - **A** Model će se smatrati **A** kvalitete ako je metrika "Uspjeh @ K" barem 10 % veća od osnovne vrijednosti. 
            - **B** Model će se smatrati **B** kvalitete ako je metrika "Uspjeh @ K" 0 do 10 % veća od osnovne vrijednosti.
            - **C** Model će se smatrati **C** kvalitete ako je metrika "Uspjeh @ K" manja od osnovne vrijednosti.
               
               > [!div class="mx-imgBorder"]
               > ![Prikaz rezultata performansi modela](media/product-recommendation-modelperformance.PNG "Prikaz rezultata performansi modela")
            - **Osnovna vrijednost**: Model uzima najviše preporučene proizvode prema broju kupnji kod svih klijenata i koristi naučena pravila koja je identificirao model za stvaranje skupa preporuka za klijente. Predviđanja se zatim uspoređuju s najboljim proizvodima, što se računa brojem klijenata koji su kupili proizvod. Ako klijent ima barem jedan proizvod u preporučenim proizvodima, što se također vidi u najčešće kupljenim proizvodima, smatra se dijelom osnovne vrijednosti. Kad bi od ukupno 100 klijenata 10 kupilo preporučeni proizvod, polazište bi bilo 10%.
            - **Uspjeh @ K**: Korištenjem skupa provjere vremenskog razdoblja transakcija stvaraju se preporuke za sve klijente i uspoređuju se sa skupom provjere transakcija. Na primjer, u razdoblju od 12 mjeseci, 12. mjesec može se izdvojiti kao skup provjere podataka. Ako model predvidi barem jednu stvar koju biste kupili u 12. mjesecu na temelju onoga što je naučio iz prethodnih 11 mjeseci, klijent će povećati metriku "Uspjeh @ K".
    
    1. **Najviše predloženi proizvodi (s iznosom):** najboljih 5 proizvoda koji su predviđeni za vaše klijente.
       > [!div class="mx-imgBorder"]
       > ![Grafikon koji prikazuje 5 najviše preporučenih proizvoda](media/product-recommendation-topproducts.PNG "Grafikon koji prikazuje 5 najviše preporučenih proizvoda")
    
    1. **Preporuke proizvoda s visokom pouzdanošću:** Uzorak preporuka koji se pruža vašim klijentima, a za koje model smatra da će ih klijent vjerojatno kupiti.
       > [!div class="mx-imgBorder"]
       > ![Popis koji prikazuje prijedloge visoke pouzdanosti za odabrani skup pojedinačnih klijenata](media/product-recommendation-highconfidence.PNG "Popis koji prikazuje prijedloge visoke pouzdanosti za odabrani skup pojedinačnih klijenata")

## <a name="fix-a-failed-prediction"></a>Popravak neuspjelog predviđanja

1. Idite na karticu **Moja predviđanja** pod **Inteligencija** > **Predviđanja**.

1. Odaberite predviđanje čije zapisnike o pogreškama želite pregledati i odaberite **Zapisnici**.

1. Pregledajte sve pogreške. Može se dogoditi nekoliko vrsta pogrešaka i one opisuju kakvo je stanje prouzročilo pogrešku. Na primjer, pogreška za koju nema dovoljno podataka da bi se točno predvidjela obično se razrješava učitavanjem dodatnih podataka u Customer Insights.

## <a name="refresh-a-prediction"></a>Osvježavanje predviđanja

Predviđanja se automatski osvježavaju prema istom [rasporedu prema kojem se osvježavaju podaci](system.md#schedule-tab) kako je konfigurirano u postavkama.

1. Idite na karticu **Moja predviđanja** pod **Inteligencija** > **Predviđanja**.

1. Odaberite okomitu trotočku uz predviđanje koje želite osvježiti.

1. Odaberite **Osvježi**.

## <a name="delete-a-prediction"></a>Brisanje predviđanja

Brisanjem predviđanja uklonit će se i njegov izlazni entitet.

1. Idite na karticu **Moja predviđanja** pod **Inteligencija** > **Predviđanja**.

1. Odaberite okomitu trotočku uz predviđanje koje želite izbrisati.

1. Odaberite **Obriši**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]