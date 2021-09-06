---
title: Transakcijsko predviđanje gubitka
description: Predvidite postoji li opasnost da će klijent prestati kupovati vaše proizvode ili usluge.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f0d56fc6595fcbb226897fcb52148924d00306b6d75b617fc8cafbcc0aab0641
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034901"
---
# <a name="transactional-churn-prediction-preview"></a>Transakcijsko predviđanje gubitka (pretpregled)

Transakcijsko predviđanje gubitka pomaže predvidjeti hoće li klijent prestati kupovati vaše proizvode ili usluge u određenom vremenskom roku. Možete stvoriti nova predviđanja gubitka na **Obavještavanje** > **Predviđanja**. Odaberite **Moja predviđanja** da biste vidjeli druga predviđanja koja ste stvorili.

> [!TIP]
> Isprobajte korisnički priručnik za transakcijsko predviđanje gubitka pomoću uzorka podataka: [Uzorak vodiča za transakcijsko predviđanje gubitka (pretpregled)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Preduvjeti

- Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.
- Poznavanje poslovanja kako bi se razumjelo što gubitak znači za vaše poslovanje. Podržavamo vremenske definicije gubitka, što znači da se smatra da je klijent odustao nakon razdoblja bez kupnje.
- Podaci o vašim transakcijama/kupnjama i njihovoj povijesti:
    - Identifikatori transakcija za razlikovanje kupnji/transakcija.
    - Identifikatori klijenata za podudaranje transakcija s vašim klijentima.
    - Datumi transakcijskih događaja koji definiraju datume na koje se transakcija dogodila.
    - Shema semantičkih podataka za kupnje/transakcije zahtijeva sljedeće podatke:
        - **ID transakcije:** Jedinstveni identifikator kupnje ili transakcije.
        - **Datum transakcije:** Datum kupnje ili transakcije.
        - **Vrijednost transakcije:** Iznos valute/numeričke vrijednosti transakcije/stavke.
        - (Neobavezno) **Jedinstveni ID proizvoda:** ID kupljenog proizvoda ili usluge ako su vaši podaci na razini stavke retka.
        - (Neobavezno) **Je li ova transakcija bila povrat:** Polje točno/netočno koje identificira je li transakcija bila povrat ili nije. Ako je **Vrijednost transakcije** negativna, te ćemo podatke koristiti i za zaključivanje povrata.
- (Neobavezno) Podaci o aktivnostima klijenata:
    - Identifikatori aktivnosti za razlikovanje aktivnosti iste vrste.
    - Identifikatori klijenata za spajanje aktivnosti s klijentima.
    - Podaci o aktivnosti koji sadrže naziv i datum aktivnosti.
    - Semantička shema podataka za aktivnosti klijenata sadrži:
        - **Primarni ključ:** Jedinstveni identifikator aktivnosti. Na primjer, posjet web-mjestu ili zapis korištenja koji pokazuje da je klijent isprobao uzorak vašeg proizvoda.
        - **Vremenska oznaka:** Datum i vrijeme događaja identificirani pomoću primarnog ključa.
        - **Događaj:** Odredite naziv za događaj koji želite koristiti. Na primjer, polje pod nazivom „UserAction” u trgovini mješovite robe može biti kupon koji kupac koristi.
        - **Pojedinosti:** Detaljne informacije o događaju. Na primjer, polje pod nazivom „CouponValue” u trgovini mješovite robe može biti vrijednost valute kupona.
- Značajke predloženih podataka:
    - Dovoljno povijesnih podataka: Podaci o transakciji za najmanje dvostruko veći odabrani vremenski okvir. Ako je moguće, dvije do tri godine povijesti transakcija. 
    - Više kupnji po klijentu: Idealno najmanje dvije transakcije po klijentu.
    - Broj klijenata: Najmanje 10 profila klijenata, po mogućnosti više od 1 000 jedinstvenih klijenata. Model neće uspjeti s manje od 10 klijenata i nedovoljnim povijesnim podacima.
    - Kompletnost podataka: Manje od 20 % vrijednosti koje nedostaju u podatkovnom polju navedenog entiteta.

> [!NOTE]
> Za tvrtku s velikom učestalošću kupnji klijenata (svakih nekoliko tjedana) preporučuje se odabir kraćeg okvira predviđanja i definicije gubitka. Za nisku učestalost kupnje (svakih nekoliko mjeseci ili jednom godišnje) odaberite dulji okvir predviđanja i definicije gubitka.

## <a name="create-a-transactional-churn-prediction"></a>Stvaranje transakcijskog predviđanja gubitka

1. U aplikaciji Customer Insights idite na **Inteligencija** > **Predviđanja**.

1. Odaberite pločicu **Model gubitka klijenata (pretpregled)** i odaberite **Koristi ovaj model**.
   
1. U oknu **Model gubitka klijenata** odaberite **Transakcijski** i odaberite **Započni**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Snimka zaslona s odabranom transakcijskom mogućnosti u oknu modela gubitka klijenata.":::

### <a name="name-model"></a>Imenovanje modela

1. Navedite naziv modela da biste ga razlikovali od ostalih modela.

1. Navedite naziv za izlazni entitet samo slovima i brojevima, bez razmaka. To je naziv koji će entitet modela koristiti. 

1. Odaberite **Dalje**.

### <a name="define-customer-churn"></a>Definirajte gubitak klijenta

1. Postavite vremenski okvir dana za predviđanje gubitka u polju **Identificiraj klijente koji bi sljedeći mogli odustati**. Na primjer, predvidite rizik od gubitka klijenata tijekom sljedećih 90 dana kako biste se uskladili s vašim naporima zadržavanja marketinga. Predviđanje rizika od gubitka tijekom duljeg ili kraćeg vremenskog razdoblja može otežati adresiranje čimbenika u vašem profilu rizika od gubitka, ali to ovisi o vašim specifičnim poslovnim zahtjevima. 
   >[!TIP]
   > Možete odabrati **Spremi i zatvori** u bilo kojem trenutku kako biste predviđanje spremili kao skicu. Za nastavak, skicu predviđanja naći ćete na kartici **Moja predviđanja**.

1. Unesite broj dana za definiranje gubitka u polje **Klijent je odustao ako nije izvršio nikakvu kupnju u roku od:**. Na primjer, ako klijent nije obavio nijednu kupnju u posljednjih 30 dana, može se smatrati kao gubitak za vaše poslovanje. 

1. Za nastavak odaberite **Dalje**

### <a name="add-required-data"></a>Dodavanje obaveznih podataka

1. Odaberite **Dodaj podatke** za **Povijest kupnje** i odaberite entitet koji pruža informacije o povijesti transakcija/kupnji kao što je opisano u [preduvjetima](#prerequisites).

1. Mapirajte semantička polja na atribute unutar entiteta povijesti kupnje i odaberite **Sljedeće**. Za opis polja pogledajte [preduvjete](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Mapirajte semantička polja entiteta kupnje.":::

1. Ako polja u nastavku nisu popunjena, konfigurirajte odnos između entiteta povijesti kupnje i entiteta klijenta.
    1. Odaberite **Entitet povijesti kupnje**.
    1. Odaberite **Polje** koje identificira klijenta u entitetu povijesti kupnje. Mora se odnositi na primarni ID klijenta vašeg entiteta Klijent.
    1. Odaberite **Entitet klijenta** koji odgovara vašem primarnom entitetu klijenta.
    1. Unesite naziv koji opisuje odnos.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Stranica povijesti kupnje koja prikazuje stvaranje odnosa s klijentom.":::
   
1. Odaberite **Dalje**.

1. Ako želite, odaberite **Dodaj podatke** za **Aktivnosti klijenata**. Odaberite entitet koji pruža informacije o aktivnostima klijenata kao što je opisano u preduvjetima.

1. Mapirajte semantička polja na atribute unutar entiteta aktivnosti klijenta i odaberite **Sljedeće**. Za opis polja pogledajte [preduvjete](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Mapirajte polja klijenata za transakcijske podatke.":::

1. Odaberite vrstu aktivnosti koja odgovara vrsti aktivnosti klijenta koju konfigurirate. Odaberite **Stvori novo** i odaberite dostupnu vrstu aktivnosti ili stvorite novu vrstu.

1. Trebat ćete konfigurirati odnos između entiteta aktivnosti klijenta i entiteta klijenta.
    1. Odaberite polje koje identificira klijenta u tablici aktivnosti klijenta. Može se izravno povezati s primarnim ID-jem klijenta vašeg entiteta klijenta.
    1. Odaberite entitet klijenta koji odgovara vašem primarnom entitetu klijenta
    1. Unesite naziv koji opisuje odnos.

1. Odaberite **Spremi**.

1. Ako imate bilo koje druge aktivnosti klijenata koje biste željeli uključiti, ponovite prethodne korake.

1. Odaberite **Dalje**.

### <a name="set-schedule-and-review-configuration"></a>Postavite raspored i pregledajte konfiguraciju

1. Postavite učestalost ponovnog uvježbavanja svog modela. Ova je postavka važna za ažuriranje točnosti predviđanja jer se unose novi podaci. Većina tvrtki može ponovno uvježbavati jednom mjesečno i steći dobru točnost predviđanja.

1. Odaberite **Dalje**.

1. Pregledajte konfiguraciju predviđanja. Možete se vratiti na prethodne korake odabirom **Uredi** ispod prikazane vrijednosti. Također, možete odabrati korak konfiguracije s pokazatelja napretka.

1. Ako su sve vrijednosti pravilno konfigurirane, odaberite **Spremi i pokreni** za početak procesa predviđanja. Na kartici **Moja predviđanja** možete vidjeti status svojih predviđanja. Proces može potrajati nekoliko sati ovisno o količini podataka korištenih za predviđanje.

## <a name="review-a-prediction-status-and-results"></a>Pregled statusa i rezultata predviđanja

1. Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.

1. Odaberite predviđanje koje želite pregledati.
   - **Naziv predviđanja:** Naziv predviđanja naveden je pri stvaranju.
   - **Vrsta predviđanja:** Vrsta modela koji se koristi za predviđanje
   - **Entitet rezultata:** Naziv entiteta za pohranu rezultata predviđanja. Entitet ovog naziva možete pronaći u **Podaci** > **Entiteti**.    
     U izlaznom je entitetu *ChurnScore* predviđena vjerojatnost gubitka i *IsChurn* binarna oznaka koja se temelji na *ChurnScore* s pragom od 0,5. Zadani prag možda neće funkcionirati za vaš scenarij. [Stvorite novi segment](segments.md#create-a-new-segment) s vašim željenim pragom.
     Nisu svi klijenti nužno i aktivni klijenti. Neki od njih možda već dugo nisu imali nikakve aktivnosti i već se smatraju izgubljenima na temelju vaše definicije gubitka. Predviđanje rizika gubitka za klijente koji su već izgubljeni nije korisno jer nisu zanimljiva ciljna skupina.
   - **Predviđeno polje:** Ovo se polje popunjava samo za neke vrste predviđanja i ne koristi se u predviđanju gubitka.
   - **Stanje:** Stanje pokretanja predviđanja.
        - **U redu čekanja:** Predviđanje čeka da se drugi procesi pokrenu.
        - **Osvježavanje:** Predviđanje je trenutno pokrenuto za stvaranje rezultata koji će ići u izlazni entitet.
        - **Neuspjelo:** Pokretanje predviđanja nije uspjelo. [Pregledajte zapisnike](manage-predictions.md#troubleshoot-a-failed-prediction) za dodatne pojedinosti.
        - **Uspjelo:** Predviđanje je uspjelo. Odaberite **Prikaz** ispod okomitih točkica kako biste pregledali predviđanje
   - **Uređeno:** Promijenjen je datum konfiguriranja za predviđanje.
   - **Zadnji put osvježeno:** Datum kada je predviđanje osvježilo rezultate u entitetu rezultata.

1. Odaberite okomitu trotočku uz predviđanje čije rezultate želite pregledati i odaberite **Prikaz**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Pregledajte kontrolu da biste vidjeli rezultate predviđanja.":::   

1. Postoje tri primarna odjeljka podataka na stranici s rezultatima:
    1. **Performanse modela obuke:** Mogući rezultati su A, B ili C. Ovaj rezultat označava performanse predviđanja i može vam pomoći da donesete odluku o korištenju rezultata pohranjenih u entitetu rezultata. Rezultati se određuju na temelju sljedećih pravila:
         
         - **A** kada je model točno predvidio najmanje 50% ukupnih predviđanja i kada je postotak točnih predviđanja za klijente koji su odustali veći od osnovne stope za najmanje 10%.
            
         - **B** kada je model točno predvidio najmanje 50% ukupnih predviđanja i kada je postotak točnih predviđanja za klijente koji su odustali do 10% veći od osnovne stope.
            
         - **C** kada je model točno predvidio manje od 50% ukupnih predviđanja ili kada je postotak točnih predviđanja za klijente koji su odustali manji od osnovne stope.
               
         - **Osnovna stopa** kao ulaz za model uzima vremenski okvir predviđanja (na primjer, godinu dana) i model stvara različite dijelove vremena dijeleći ga s 2 dok ne dosegne mjesec dana ili manje. Koristi ove dijelove za stvaranje poslovnog pravila za klijente koji nisu kupovali u ovom vremenskom okviru. Smatra se da su ti klijenti odustali. Kao osnovni model odabrano je poslovno pravilo koje se temelji na vremenu s najvišom sposobnošću predviđanja tko će vjerojatno odustati.
            
    1. **Vjerojatnost gubitka (broj klijenata):** Grupe klijenata na temelju njihovog predviđenog rizika da budu izgubljeni. Ovi podaci mogu vam pomoći kasnije ako želite stvoriti segment klijenata s visokim rizikom da budu izgubljeni. Takvi segmenti pomažu vam da shvatite gdje bi trebao biti vaš prag za članstvo u segmentu.
       
    1. **Najutjecajniji faktori:** Mnogo je faktora koji se uzimaju u obzir prilikom izrade predviđanja. Svaki od čimbenika ima svoju važnost izračunatu za skupna predviđanja koja model stvara. Pomoću tih faktora možete potvrditi rezultate predviđanja. Također, ove podatke možete kasnije koristiti da [stvorite segmente](segments.md) koji mogu pomoći u smanjenju rizika od gubitka klijenata.

## <a name="manage-predictions"></a>Upravljanje predviđanjima

Predviđanja je moguće optimizirati, riješiti, osvježiti ili izbrisati. Pregledajte izvješće o upotrebljivosti ulaznih podataka da biste saznali kako predviđanje učiniti bržim i pouzdanijim. Dodatne informacije potražite u odjeljku [Upravljanje predviđanjima](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
