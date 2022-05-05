---
title: Pretplata churn predviđanje (sadrži videozapis)
description: Predvidite postoji li opasnost da će klijent prestati koristiti pretplaćene proizvode ili usluge vaše tvrtke.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 415cd5d675512b4f434998afaa8265c8e45c562b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642876"
---
# <a name="subscription-churn-prediction"></a>Predviđanje gubitka pretplate

Predviđanje gubitaka pretplate pomaže u predviđanju postoji li opasnost da će klijent prestati koristiti pretplaćene proizvode ili usluge vaše tvrtke. Možete stvoriti novo predviđanje gubitaka pretplate na stranici **Inteligencija** > **Predviđanja**. Odaberite **Moja predviđanja** da biste vidjeli druga predviđanja koja ste stvorili.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Isprobajte korisnički priručnik za predviđanje odbijanja pretplate pomoću uzorka podataka: [Uzorak vodiča za predviđanje odbijanja pretplate](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Preduvjeti

- Barem [Dozvole suradnika](permissions.md).
- Poznavanje poslovanja kako bi se razumjelo što gubitak znači za vaše poslovanje. Podržavamo vremenske definicije gubitka, što znači da se klijent smatra izgubljenim nakon određenog vremena po isteku pretplate.
- Podaci o vašim pretplatama i njihovoj povijesti:
    - Identifikatori pretplate za razlikovanje pretplata.
    - Identifikatori klijenata za spajanje pretplata s klijentima.
    - Datumi događaja pretplate koji određuju datume početka, datume završetka i datume kada se pretplaćivanje dogodilo.
    - Informacije o pretplati za određivanje je li u pitanju ponavljajuća pretplata i koliko često se obnavlja.
    - Semantička shema podataka za pretplate zahtijeva sljedeće informacije:
        - **ID pretplate:** Jedinstveni identifikator pretplate.
        - **Datum završetka pretplate:** Datum isteka pretplate za klijenta.
        - **Datum početka pretplate:** Datum početka pretplate za klijenta.
        - **Datum transakcije:** Datum kada se dogodila promjena pretplate. Na primjer, klijent kupuje ili otkazuje pretplatu.
        - **Je li to ponavljajuća pretplata:** Polje točno/netočno koje određuje hoće li se pretplata obnoviti istim ID-om pretplate bez intervencije kupca
        - **Učestalost ponavljanja (u mjesecima):** Za ponavljajuće pretplate to je razdoblje nakon kojeg će se pretplata obnoviti. Izražena je u mjesecima. Na primjer, godišnja pretplata koja se klijentu automatski obnavlja svake godine na još godinu dana ima vrijednost 12.
        - (Nije obavezno) **Iznos pretplate:** Količina valute koju klijent plaća za obnovu pretplate. Može vam pomoći utvrditi obrasce za različite razine pretplate.
- Podaci o aktivnostima klijenta:
    - Identifikatori aktivnosti za razlikovanje aktivnosti iste vrste.
    - Identifikatori klijenata za spajanje aktivnosti s klijentima.
    - Podaci o aktivnosti koji sadrže naziv i datum aktivnosti.
    - Semantička shema podataka za aktivnosti klijenata sadrži:
        - **Primarni ključ:** Jedinstveni identifikator aktivnosti. Na primjer, posjet web-mjestu ili zapis o upotrebi koji prikazuje da je klijent gledao epizodu neke TV emisije.
        - **Vremenska oznaka:** Datum i vrijeme događaja identificirani pomoću primarnog ključa.
        - **Događaj:** Odredite naziv za događaj koji želite koristiti. Na primjer, polje pod nazivom „UserAction” u usluzi strujanja videa moglo bi imati vrijednost „Prikazano”.
        - **Pojedinosti:** Detaljne informacije o događaju. Na primjer, polje pod nazivom „ShowTitle” u usluzi strujanja videa moglo bi imati vrijednost naziva videa koji je klijent pogledao.
- Značajke predloženih podataka:
    - Dovoljno povijesnih podataka: Podaci o pretplati za najmanje dvostruko veći odabrani vremenski okvir. Po mogućnosti dvije do tri godine podataka o pretplati.
    - Status pretplate: Podaci uključuju aktivne i neaktivne pretplate za svakog klijenta, tako da postoji više unosa po ID-ju klijenta.
    - Broj klijenata: Najmanje 10 profila klijenata, po mogućnosti više od 1 000 jedinstvenih klijenata. Model neće uspjeti s manje od 10 klijenata i nedovoljnim povijesnim podacima.
    - Kompletnost podataka: Manje od 20 % vrijednosti koje nedostaju u podatkovnom polju navedenog entiteta.
   
   > [!NOTE]
   > Trebat će vam najmanje dva zapisa aktivnosti za 50% klijenata za koje želite izračunati gubitak.

## <a name="create-a-subscription-churn-prediction"></a>Izrada predviđanja gubitaka pretplate

1. Idite na **IntelligencePredictions** > **·**.
1. Odaberite pločicu **Model** modela s dobavljačem Pretplata i odaberite **Koristi ovaj model**.
   > [!div class="mx-imgBorder"]
   > ![Pločica modela gubitka pretplate s gumbom Koristi ovaj model.](media/subscription-churn-usethismodel.PNG "Pločica Predviđanje gubitaka pretplate, pomoću gumba Koristi ovaj model")

### <a name="name-model"></a>Imenovanje modela

1. Navedite naziv modela da biste ga razlikovali od ostalih modela.
1. Navedite naziv za izlazni entitet samo slovima i brojevima, bez razmaka. To je naziv koji će entitet modela koristiti. Zatim odaberite **Dalje**.

### <a name="define-customer-churn"></a>Definirajte gubitak klijenta

1. Unesite broj **Dana od isteka pretplate** za koju vaša tvrtka smatra da predstavlja izgubljenog klijenta. Ovo se razdoblje obično vezuje uz poslovne aktivnosti poput ponuda ili drugih marketinških napora kojima se pokušava spriječiti gubitak klijenta.
1. Unesite broj **Dana u budućnosti za predviđanje gubitka** da biste postavili prozor za predviđanje gubitka. Na primjer, za predviđanje rizika gubitka za vaše klijente tijekom sljedećih 90 dana kako bi se uskladili s vašim naporima da zadržite marketing. Predviđanje rizika gubitka na dulja ili kraća vremenska razdoblja može otežati adresiranje čimbenika u vašem profilu rizika gubitka, ovisno o vašim specifičnim poslovnim zahtjevima. Za nastavak odaberite **Dalje**
   >[!TIP]
   > Skicu **možete odabrati** u bilo kojem trenutku da biste spremili predviđanje kao skicu. Za nastavak, skicu predviđanja naći ćete na kartici **Moja predviđanja**.

### <a name="add-required-data"></a>Dodajte potrebne podatke

1. Odaberite **Dodaj podatke** za **Povijest pretplate** i odaberite entitet koji pruža informacije o povijesti pretplate, kao što je opisano u [preduvjetima](#prerequisites).
1. Ako polja u nastavku nisu popunjena, konfigurirajte odnos iz entiteta povijesti pretplate u entitet klijenta.
    1. Odaberite **Entitet povijesti pretplate**.
    1. Odaberite **Polje** koje identificira klijenta u entitetu povijesti pretplate. Mora se odnositi na primarni ID klijenta vašeg entiteta Klijent.
    1. Odaberite **Entitet klijenta** koji odgovara vašem primarnom entitetu klijenta.
    1. Unesite naziv koji opisuje odnos.
       > [!div class="mx-imgBorder"]
       > ![Stranica povijesti pretplate koja pokazuje stvaranje odnosa prema klijentu.](media/subscription-churn-subscriptionhistoryrelationship.PNG "Stranica povijesti pretplate pokazuje stvaranje odnosa prema kupcu")
1. Odaberite **Dalje**.
1. Mapirajte semantička polja u atribute unutar entiteta povijesti pretplate i odaberite **Spremi**. Za opis polja pogledajte [preduvjete](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Stranica povijesti pretplate koja pokazuje semantičke atribute koji su mapirani na polja u odabranom entitetu povijesti pretplate.](media/subscription-churn-subscriptionhistorymapping.PNG "Stranica povijesti pretplate koja prikazuje semantičke atribute koji su mapirani na polja u odabranom entitetu povijesti pretplate")
1. Odaberite **Dodaj podatke** za **Aktivnosti klijenta** i odaberite entitet koji pruža informacije o aktivnosti klijenta kako je opisano u preduvjetima.
1. Odaberite vrstu aktivnosti koja odgovara vrsti aktivnosti klijenta koju konfigurirate.  Odaberite **Stvori novo** i unesite naziv ako ne vidite opciju koja odgovara potrebnoj vrsti aktivnosti.
1. Trebat ćete konfigurirati odnos između entiteta aktivnosti klijenta i entiteta klijenta.
    1. U tablici aktivnosti klijenta odaberite polje koje identificira klijenta, a koje se može izravno odnositi na primarni ID klijenta vašeg entiteta klijenta.
    1. Odaberite entitet klijenta koji odgovara vašem primarnom entitetu klijenta
    1. Unesite naziv koji opisuje odnos.
1. Odaberite **Dalje**.
1. Mapirajte semantička polja u atribute unutar entiteta aktivnosti klijenta i odaberite **Spremi**. Za opis polja pogledajte [preduvjete](#prerequisites).
1. (Neobavezno) Ako imate bilo koju drugu aktivnost klijenta koju želite uključiti, ponovite gore navedene korake.
   > [!div class="mx-imgBorder"]
   > ![Definirajte odnos entiteta.](media/subscription-churn-customeractivitiesmapping.PNG "Stranica aktivnosti klijenta koja prikazuje semantičke atribute koji su mapirani na polja u odabranom entitetu aktivnosti klijenta")
1. Odaberite **Dalje**.

### <a name="set-schedule-and-review-configuration"></a>Postavite raspored i pregledajte konfiguraciju

1. Postavite učestalost ponovnog uvježbavanja svog modela. Ova je postavka važna za ažuriranje točnosti predviđanja jer se novi podaci unose u Customer Insights. Većina tvrtki može ponovno uvježbavati jednom mjesečno i steći dobru točnost predviđanja.
1. Odaberite **Dalje**.
1. Pregledajte konfiguraciju. Možete se vratiti bilo kojem dijelu konfiguracije predviđanja odabirom **Uredi** ispod prikazane vrijednosti. Također, možete odabrati korak konfiguracije s pokazatelja napretka.
1. Ako su sve vrijednosti pravilno konfigurirane, odaberite **Spremi i pokreni** za početak procesa predviđanja. Na kartici **Moja predviđanja** možete vidjeti status svojih predviđanja. Proces može potrajati nekoliko sati ovisno o količini podataka korištenih za predviđanje.

## <a name="review-a-prediction-status-and-results"></a>Pregled statusa i rezultata predviđanja

1. Idite na karticu **Moja predviđanja** pod **Inteligencija** > **Predviđanja**.
   > [!div class="mx-imgBorder"]
   > ![Prikaz stranice Moja predviđanja.](media/subscription-churn-mypredictions.PNG "Pogledajte stranicu Moja predviđanja")
1. Odaberite predviđanje koje želite pregledati.
   - **Naziv predviđanja:** Naziv predviđanja naveden prilikom njegovog stvaranja.
   - **Vrsta predviđanja:** Vrsta modela korištenog za to predviđanje
   - **Entitet rezultata:** Naziv entiteta za pohranu rezultata predviđanja. Entitet ovog naziva možete pronaći u **Podaci** > **Entiteti**.    
     U izlaznom je entitetu *ChurnScore* predviđena vjerojatnost gubitka i *IsChurn* binarna oznaka koja se temelji na *ChurnScore* s pragom od 0,5. Zadani prag možda neće funkcionirati za vaš scenarij. [Stvorite novi segment](segments.md#create-a-new-segment) s vašim željenim pragom.
   - **Polje predviđanja:** Ovo polje popunjava se samo za neke vrste predviđanja i ne koristi se za predviđanje gubitka pretplate.
   - **Status:** Trenutačni status izvršenja predviđanja.
        - **Na čekanju:** Predviđanje trenutno čeka na pokretanje drugih procesa.
        - **Osvježava se:** Predviđanje je trenutačno u fazi „ocjene” obrade za dobivanje rezultata koji će se preliti u entitet rezultata.
        - **Neuspješno:** Predviđanje nije uspjelo. Za više detalja odaberite **Zapisnici**.
        - **Uspješno:** Predviđanje je uspjelo. Odaberite **Prikaz** ispod okomitih točkica kako biste pregledali predviđanje
   - **Uređeno:** Promijenjen je datum konfiguriranja za predviđanje.
   - **Zadnji put osvježeno:** Datum kada je predviđanje osvježilo rezultate u entitetu rezultata.
1. Odaberite okomitu trotočku uz predviđanje čije rezultate želite pregledati i odaberite **Prikaz**.
   > [!div class="mx-imgBorder"]
   > ![Prikaz mogućnosti u izborniku okomitog trotočja za predviđanje, uključujući uređivanje, osvježavanje, prikaz, zapisnike i brisanje.](media/subscription-churn-verticalellipses.PNG "Prikaz izbornika okomite trotočke s mogućnostima za predviđanje, u koje spadaju uređivanje, osvježavanje, prikaz, zapisnici i brisanje")
1. Postoje tri primarna odjeljka podataka na stranici s rezultatima:
    1. **Performanse modela obuke:** Mogući rezultati su A, B ili C. Ovaj rezultat označava performanse predviđanja i može vam pomoći da donesete odluku o korištenju rezultata pohranjenih u entitetu rezultata.
        - Rezultati se određuju na temelju sljedećih pravila:
            - **A** – kada je model točno predvidio najmanje 50 % ukupnih predviđanja i kada je postotak točnih predviđanja za klijente koji su imali gubitke veći od povijesne prosječne stope gubitka za najmanje 10 % povijesne prosječne stope gubitka.
            - **B** – kada je model točno predvidio najmanje 50 % ukupnih predviđanja i kada je postotak točnih predviđanja za klijente koji su imali gubitke veći od povijesne prosječne stope gubitka za najviše 10 % povijesne prosječne stope gubitka.
            - **C** – kada je model točno predvidio manje od 50 % ukupnih predviđanja ili kada je postotak točnih predviđanja za klijente koji su imali gubitke manji od povijesne prosječne stope gubitka.
               > [!div class="mx-imgBorder"]
               > ![Prikaz rezultata performansi modela.](media/subscription-churn-modelperformance.PNG "Prikaz rezultata performansi modela")
    1. **Vjerojatnost gubitka (broj klijenata):** Grupe klijenata na temelju njihovog predviđenog rizika da budu izgubljeni. Ovi podaci mogu vam pomoći kasnije ako želite stvoriti segment klijenata s visokim rizikom da budu izgubljeni. Takvi segmenti pomažu vam da shvatite gdje bi trebao biti vaš prag za članstvo u segmentu.
       > [!div class="mx-imgBorder"]
       > ![Grafikon koji pokazuje raspodjelu rezultata gubitka, podijeljen na raspone od 0 – 100 %.](media/subscription-churn-resultdistribution.PNG "Grafikon koji prikazuje raspodjelu rezultata gubitka, izdijeljen na raspone od 0 – 100 %")
    1. **Najutjecajniji faktori:** Mnogo je faktora koji se uzimaju u obzir prilikom izrade predviđanja. Svaki od tih faktora ima svoju važnost izračunatu za skupna predviđanja koja model stvara. Pomoću tih faktora možete potvrditi rezultate predviđanja. Također, ove podatke možete kasnije koristiti da [stvorite segmente](segments.md) koji mogu pomoći u smanjenju rizika od gubitka klijenata.
       > [!div class="mx-imgBorder"]
       > ![Popis pokazuje utjecajne čimbenike i njihovu važnost u predviđanju rezultata gubitka.](media/subscription-churn-influentialfactors.PNG "Popis pokazuje utjecajne faktore i njihovu važnost u predviđanju rezultata gubitka")

## <a name="manage-predictions"></a>Upravljanje predviđanjima

Predviđanja je moguće optimizirati, riješiti, osvježiti ili izbrisati. Pregledajte izvješće o upotrebljivosti ulaznih podataka da biste saznali kako predviđanje učiniti bržim i pouzdanijim. Dodatne informacije potražite u odjeljku [Upravljanje predviđanjima](manage-predictions.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
