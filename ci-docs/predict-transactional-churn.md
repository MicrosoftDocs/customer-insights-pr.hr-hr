---
title: Transakcijski bućkanje predviđanje (sadrži videozapise)
description: Predvidite postoji li opasnost da će klijent prestati kupovati vaše proizvode ili usluge.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: e55ca8c6926fa0bda05aaf52fd799ca25f7f585f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642956"
---
# <a name="transaction-churn-prediction"></a>Predviđanje gubitka transakcija

Transakcijsko predviđanje gubitka pomaže predvidjeti hoće li klijent prestati kupovati vaše proizvode ili usluge u određenom vremenskom roku. Možete stvoriti nova predviđanja gubitka na **Obavještavanje** > **Predviđanja**. Odaberite **Moja predviđanja** da biste vidjeli druga predviđanja koja ste stvorili. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Za okruženja koja se temelje na poslovnim računima, možemo predvidjeti gubitak transakcije za račun, a također i kombinaciju računa i drugu razinu informacija poput kategorije proizvoda. Dodavanjem dimenzije možete saznati koliko je vjerojatno da će račun „Contoso” prestati kupovati kategoriju proizvoda „uredski pribor”. Osim toga, za poslovne račune možemo također koristiti umjetnu inteligenciju za generiranje popisa mogućih razloga zašto će se račun vjerojatno izgubiti zbog kategorije podataka sekundarne razine.

> [!TIP]
> Isprobajte vodič za transakcijski bućkanje predviđanje pomoću oglednih podataka: [Transakcijski bućkanje predviđanje ogledni vodič](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Preduvjeti

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.
- Poznavanje poslovanja kako bi se razumjelo što gubitak znači za vaše poslovanje. Podržavamo vremenske definicije gubitka, što znači da se smatra da je klijent odustao nakon razdoblja bez kupnje.
- Podaci o vašim transakcijama/kupnjama i njihovoj povijesti:
    - Identifikatori transakcija za razlikovanje kupnji/transakcija.
    - Identifikatori klijenata za podudaranje transakcija s vašim klijentima.
    - Datumi transakcijskih događaja koji definiraju datume na koje se transakcija dogodila.
    - Shema semantičkih podataka za kupnje/transakcije zahtijeva sljedeće podatke:
        - **ID transakcije**: Jedinstveni identifikator kupnje ili transakcije.
        - **Datum transakcije:**: Datum kupnje ili transakcije.
        - **Vrijednost transakcije**: Iznos valute/numeričke vrijednosti transakcije/stavke.
        - (Neobavezno) **Jedinstveni ID proizvoda**: ID kupljenog proizvoda ili usluge ako su vaši podaci na razini stavke retka.
        - (Neobavezno) **Je li ova transakcija bila povrat**: Polje točno/netočno koje identificira je li transakcija bila povrat ili nije. Ako je **Vrijednost transakcije** negativna, te ćemo podatke koristiti i za zaključivanje povrata.
- (Neobavezno) Podaci o aktivnostima klijenata:
    - Identifikatori aktivnosti za razlikovanje aktivnosti iste vrste.
    - Identifikatori klijenata za spajanje aktivnosti s klijentima.
    - Podaci o aktivnosti koji sadrže naziv i datum aktivnosti.
    - Semantička shema podataka za aktivnosti klijenata sadrži:
        - **Primarni ključ:** Jedinstveni identifikator aktivnosti. Na primjer, posjet web-mjestu ili zapis korištenja koji pokazuje da je klijent isprobao uzorak vašeg proizvoda.
        - **Vremenska oznaka:** Datum i vrijeme događaja identificirani pomoću primarnog ključa.
        - **Događaj:** Odredite naziv za događaj koji želite koristiti. Na primjer, polje pod nazivom „UserAction” u trgovini mješovite robe može biti kupon koji kupac koristi.
        - **Pojedinosti:** Detaljne informacije o događaju. Na primjer, polje pod nazivom „CouponValue” u trgovini mješovite robe može biti vrijednost valute kupona.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

- Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.
- Poznavanje poslovanja kako bi se razumjelo što gubitak znači za vaše poslovanje. Podržavamo vremenske definicije gubitka, što znači da se smatra da je klijent odustao nakon razdoblja bez kupnje.
- Podaci o vašim transakcijama/kupnjama i njihovoj povijesti:
    - Identifikatori transakcija za razlikovanje kupnji/transakcija.
    - Identifikatori klijenata za podudaranje transakcija s vašim klijentima.
    - Datumi transakcijskih događaja koji definiraju datume na koje se transakcija dogodila.
    - Shema semantičkih podataka za kupnje/transakcije zahtijeva sljedeće podatke:
        - **ID transakcije**: Jedinstveni identifikator kupnje ili transakcije.
        - **Datum transakcije:**: Datum kupnje ili transakcije.
        - **Vrijednost transakcije**: Iznos valute/numeričke vrijednosti transakcije/stavke.
        - (Neobavezno) **Jedinstveni ID proizvoda**: ID kupljenog proizvoda ili usluge ako su vaši podaci na razini stavke retka.
        - (Neobavezno) **Je li ova transakcija bila povrat**: Polje točno/netočno koje identificira je li transakcija bila povrat ili nije. Ako je **Vrijednost transakcije** negativna, te ćemo podatke koristiti i za zaključivanje povrata.
- (Neobavezno) Podaci o aktivnostima klijenata:
    - Identifikatori aktivnosti za razlikovanje aktivnosti iste vrste.
    - Identifikatori klijenata za spajanje aktivnosti s klijentima.
    - Podaci o aktivnosti koji sadrže naziv i datum aktivnosti.
    - Semantička shema podataka za aktivnosti klijenata sadrži:
        - **Primarni ključ:** Jedinstveni identifikator aktivnosti. Na primjer, posjet web-mjestu ili zapis korištenja koji pokazuje da je klijent isprobao uzorak vašeg proizvoda.
        - **Vremenska oznaka:** Datum i vrijeme događaja identificirani pomoću primarnog ključa.
        - **Događaj:** Odredite naziv za događaj koji želite koristiti. Na primjer, polje pod nazivom „UserAction” u trgovini mješovite robe može biti kupon koji kupac koristi.
        - **Pojedinosti:** Detaljne informacije o događaju. Na primjer, polje pod nazivom „CouponValue” u trgovini mješovite robe može biti vrijednost valute kupona.
- (Neobavezno) Podaci o vašim klijentima:
    - Ti bi se podaci trebali poravnati prema statičnijim atributima kako bi se osiguralo najbolje funkcioniranje modela.
    - Shema semantičkih podataka za podatke o klijentima uključuje:
        - **ID klijenta:** Jedinsteni identifikator za klijenta.
        - **Datum stvaranja:** Datum kada je klijent prvobitno dodan.
        - **Savezn država ili pokrajina:** Država ili pokrajina klijenta.
        - **Zemlja:** Zemlja klijenta.
        - **Industrija:** Industrijska vrsta klijenta. Na primjer, polje pod nazivom Industrija u pržionici kave može ukazivati na to je li klijent bio iz maloprodajnog sektora.
        - **Klasifikacija:** Kategorizacija klijenta za vaše poslovanje. Na primjer, polje pod nazivom ValueSegment u pržionici kave može biti razina klijenta na temelju veličine klijenta.

---

- Značajke predloženih podataka:
    - Dovoljno povijesnih podataka: Podaci o transakciji za najmanje dvostruko veći odabrani vremenski okvir. Ako je moguće, dvije do tri godine povijesti transakcija. 
    - Više kupnji po klijentu: Idealno najmanje dvije transakcije po klijentu.
    - Broj klijenata: Najmanje 10 profila klijenata, po mogućnosti više od 1 000 jedinstvenih klijenata. Model neće uspjeti s manje od 10 klijenata i nedovoljnim povijesnim podacima.
    - Kompletnost podataka: Manje od 20 % vrijednosti koje nedostaju u podatkovnom polju navedenog entiteta.

> [!NOTE]
> Za tvrtku s velikom učestalošću kupnji klijenata (svakih nekoliko tjedana) preporučuje se odabir kraćeg okvira predviđanja i definicije gubitka. Za nisku učestalost kupnje (svakih nekoliko mjeseci ili jednom godišnje) odaberite dulji okvir predviđanja i definicije gubitka.

## <a name="create-a-transaction-churn-prediction"></a>Stvaranje predviđanja gubitka transakcija

1. U aplikaciji Customer Insights idite na **Inteligencija** > **Predviđanja**.

1. Odaberite pločicu **modela** kupca i odaberite **Koristi ovaj model**.

1. U oknu **Model gubitka klijenta** odaberite **Transakcija**, a zatim odaberite **Početak**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Snimka zaslona s odabranom opcijom transakcije u oknu modela gubitka klijenta.":::
 
### <a name="name-model"></a>Imenovanje modela

1. Navedite naziv modela da biste ga razlikovali od ostalih modela.

1. Navedite naziv za izlazni entitet samo slovima i brojevima, bez razmaka. To je naziv koji će entitet modela koristiti. 

1. Odaberite **Dalje**.

### <a name="define-customer-churn"></a>Definirajte gubitak klijenta

1. **Postavite prozor predviđanje**. Na primjer, predvidite rizik od gubitka klijenata tijekom sljedećih 90 dana kako biste se uskladili s vašim naporima zadržavanja marketinga. Predviđanje rizika od gubitka tijekom duljeg ili kraćeg vremenskog razdoblja može otežati adresiranje čimbenika u vašem profilu rizika od gubitka, ali to ovisi o vašim specifičnim poslovnim zahtjevima.
   >[!TIP]
   > Skicu **možete odabrati** u bilo kojem trenutku da biste spremili predviđanje kao skicu. Za nastavak, skicu predviđanja naći ćete na kartici **Moja predviđanja**.

1. Unesite broj dana za definiranje bućkanja u polje Definicija **Churn**. Na primjer, ako klijent nije obavio nijednu kupnju u posljednjih 30 dana, može se smatrati kao gubitak za vaše poslovanje. 

1. Za nastavak odaberite **Dalje**.

### <a name="add-required-data"></a>Dodajte potrebne podatke

1. Odaberite **Dodaj podatke** i odaberite vrstu aktivnosti na bočnom oknu koje sadrži potrebne podatke o transakcijama ili povijesti kupnje.

1. U odjeljku **Odabir aktivnosti** odaberite određene aktivnosti iz odabrane vrste aktivnosti na koju želite usredotočiti izračun.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Bočno okno koje prikazuje odabir određenih aktivnosti prema semantičkoj vrsti.":::

   Ako još niste mapirali aktivnost u semantičku vrstu, odaberite **Uredi** da biste to učinili. Otvara se vođeno iskustvo za mapiranje semantičkih aktivnosti. Mapirajte svoje podatke u odgovarajuća polja u odabranoj vrsti aktivnosti.

1. Mapirajte semantičke atribute u polja koja su potrebna za pokretanje modela. Ako polja u nastavku nisu popunjena, konfigurirajte odnos između entiteta povijesti kupnje i entiteta *Klijent*. Odaberite **Spremi**.

1. U koraku **Dodavanje potrebnih podataka** odaberite **Dalje** da biste nastavili ako ne želite dodati više aktivnosti.


# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Dodavanje dodatnih podataka (neobavezno)

Konfigurirajte odnos između entiteta aktivnosti klijenta i entiteta *Klijent*.

1. Odaberite polje koje identificira klijenta u tablici aktivnosti klijenta. Može se izravno povezati s primarnim ID-jem klijenta vašeg entiteta *Klijent*.

1. Odaberite entitet koji vam je primarni entitet *Klijent*.

1. Unesite naziv koji opisuje odnos.

#### <a name="customer-activities"></a>Aktivnosti klijenta

1. Ako želite, odaberite **Dodaj podatke** za **Aktivnosti klijenata**.

1. Odaberite vrstu semantičke aktivnosti koja sadrži podatke koje želite koristiti, a zatim odaberite jednu ili više aktivnosti u odjeljku **Aktivnosti**.

1. Odaberite vrstu aktivnosti koja odgovara vrsti aktivnosti klijenta koju konfigurirate. Odaberite **Stvori novo** i odaberite dostupnu vrstu aktivnosti ili stvorite novu vrstu.

1. Odaberite **Dalje**, a zatim **Spremi**.

1. Ako imate bilo koje druge aktivnosti klijenata koje biste željeli uključiti, ponovite prethodne korake.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

### <a name="select-prediction-level"></a>Odabir razine predviđanja

Većina predviđanja izrađuje se na razini klijenta. U nekim situacijama to možda nije dovoljno detaljno da zadovolji vaše poslovne potrebe. Ovu značajku možete koristiti za predviđanje, na primjer, gubitka za granu klijenta, a ne za klijenta u cjelini.

1. Za stvaranje predviđanja na detaljnijoj razini od klijenta odaberite **Odabir entiteta za sekundarnu razinu**. Ako opcija nije dostupna, provjerite jeste li dovršili prethodni odjeljak.

1. Proširite entitete iz kojih želite odabrati sekundarnu razinu ili upotrijebite okvir za filtriranje pretraživanja da biste filtrirali odabrane opcije.

1. Odaberite atribut koji želite koristiti kao sekundarnu razinu, a zatim odaberite **Dodaj**.

1. Odaberite **Dalje**.

> [!NOTE]
> Entiteti dostupni u ovom odjeljku prikazani su jer imaju odnos s entitetom koji ste odabrali u prethodnom odjeljku. Ako ne vidite entitet koji želite dodati, provjerite ima li važeći odnos u opciji **Odnosi**. Za ovu konfiguraciju vrijede samo odnosi jedan-na-jedan i više-na-jedan.

### <a name="add-additional-data-optional"></a>Dodavanje dodatnih podataka (neobavezno)

Konfigurirajte odnos između entiteta aktivnosti klijenta i entiteta *Klijent*.

1. Odaberite polje koje identificira klijenta u tablici aktivnosti klijenta. Može se izravno povezati s primarnim ID-jem klijenta vašeg entiteta *Klijent*.

1. Odaberite entitet koji vam je primarni entitet *Klijent*.

1. Unesite naziv koji opisuje odnos.

#### <a name="customer-activities"></a>Aktivnosti klijenta

1. Ako želite, odaberite **Dodaj podatke** za **Aktivnosti klijenata**.

1. Odaberite vrstu semantičke aktivnosti koja sadrži podatke koje želite koristiti, a zatim odaberite jednu ili više aktivnosti u odjeljku **Aktivnosti**.

1. Odaberite vrstu aktivnosti koja odgovara vrsti aktivnosti klijenta koju konfigurirate. Odaberite **Stvori novo** i odaberite dostupnu vrstu aktivnosti ili stvorite novu vrstu.

1. Odaberite **Dalje**, a zatim **Spremi**.

1. Ako imate bilo koje druge aktivnosti klijenata koje biste željeli uključiti, ponovite prethodne korake.

#### <a name="customers-data"></a>Podaci o klijentima

1. Po želji odaberite **Dodaj podatke** za opciju **Podaci o klijentima**.

1. Preslikajte semantičke atribute u polja u vlastitim podacima o klijentima kao što je identificirano. Podaci u korištenim poljima ne bi se trebali često mijenjati kako bi se osigurale najbolje performanse modela. Na primjer, odabirom polja za Klasifikaciju koje se mijenjalo svaki mjesec dobila bi se samo posljednja vrijednost korištena u predviđanju, iako se povijesno ista vrijednost možda ne bi odnosila na klijenta pri stvaranju uzoraka predviđanja.

1. Odaberite **Dalje**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Navedite neobavezni popis standardiziranih računa

Dodajte popis poslovnih klijenata i računa koje želite koristiti kao referentne vrijednosti. Dobit ćete [pojedinosti o tim računima referentnih vrijednosti](#review-a-prediction-status-and-results), uključujući njihov rezultat gubitaka i najutjecajnije značajke koje su utjecale na predviđanje gubitka.

1. Odaberite **+ Dodaj klijente**.

1. Odaberite klijente koji djeluju kao referentna vrijednost.

1. Za nastavak odaberite **Dalje**.

---

### <a name="set-schedule-and-review-configuration"></a>Postavite raspored i pregledajte konfiguraciju

1. Postavite učestalost ponovnog uvježbavanja svog modela. Ova je postavka važna za ažuriranje točnosti predviđanja jer se unose novi podaci. Većina tvrtki može ponovno uvježbavati jednom mjesečno i steći dobru točnost predviđanja.

1. Odaberite **Dalje**.

1. Pregledajte konfiguraciju predviđanja. Možete se vratiti na prethodne korake odabirom **Uredi** ispod prikazane vrijednosti. Također, možete odabrati korak konfiguracije s pokazatelja napretka.

1. Ako su sve vrijednosti pravilno konfigurirane, odaberite **Spremi i pokreni** za početak procesa predviđanja. Na kartici **Moja predviđanja** možete vidjeti status svojih predviđanja. Proces može potrajati nekoliko sati ovisno o količini podataka korištenih za predviđanje.

## <a name="review-a-prediction-status-and-results"></a>Pregled statusa i rezultata predviđanja

1. Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.

1. Odaberite predviđanje koje želite pregledati.
   - **Naziv predviđanja:**: naziv predviđanja naveden pri stvaranju.
   - **Vrsta predviđanja**: vrsta modela koji se koristi za predviđanje
   - **Entitet rezultata**: naziv entiteta za pohranu rezultata predviđanja. Entitet ovog naziva možete pronaći u **Podaci** > **Entiteti**.
     U izlaznom je entitetu *ChurnScore* predviđena vjerojatnost gubitka i *IsChurn* binarna oznaka koja se temelji na *ChurnScore* s pragom od 0,5. Zadani prag možda neće funkcionirati za vaš scenarij. [Stvorite novi segment](segments.md#create-a-new-segment) s vašim željenim pragom.
     Nisu svi klijenti nužno i aktivni klijenti. Neki od njih možda već dugo nisu imali nikakve aktivnosti i već se smatraju izgubljenima na temelju vaše definicije gubitka. Predviđanje opasnosti od gubitka za klijente koji su već izgubljeni nije korisno jer nisu ciljna skupina.
   - **Predviđeno polje**: Ovo se polje popunjava samo za neke vrste predviđanja i ne koristi se u predviđanju gubitka.
   - **Status**: status pokretanja predviđanja.
        - **U redu čekanja**: Predviđanje čeka da se pokrenu drugi procesi.
        - **Osvježavanje**: Predviđanje je trenutačno pokrenuto za stvaranje rezultata koji će ići u izlazni entitet.
        - **Neuspjelo**: pokretanje predviđanja nije uspjelo. [Pregledajte zapisnike](manage-predictions.md#troubleshoot-a-failed-prediction) za dodatne pojedinosti.
        - **Uspjelo**: predviđanje je uspjelo. Odaberite **Prikaz** ispod okomitih točkica kako biste pregledali predviđanje
   - **Uređeno**: promijenjen je datum konfiguriranja za predviđanje.
   - **Zadnji put osvježeno**: datum kada je predviđanje osvježilo rezultate u izlaznom entitetu.

1. Odaberite okomitu trotočku uz predviđanje čije rezultate želite pregledati i odaberite **Prikaz**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Pregledajte kontrolu da biste vidjeli rezultate predviđanja.":::

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

1. Postoje tri primarna odjeljka podataka na stranici s rezultatima:
   - **Performanse modela obuke**: Mogući rezultati su A, B ili C. Ovaj rezultat označava performanse predviđanja i može vam pomoći da donesete odluku o korištenju rezultata pohranjenih u izlaznom entitetu. Rezultati se određuju na temelju sljedećih pravila: 
        - **A** kada je model točno predvidio najmanje 50% ukupnih predviđanja i kada je postotak točnih predviđanja za klijente koji su odustali veći od osnovne stope za najmanje 10%.
            
        - **B** kada je model točno predvidio najmanje 50% ukupnih predviđanja i kada je postotak točnih predviđanja za klijente koji su odustali do 10% veći od osnovne stope.
            
        - **C** kada je model točno predvidio manje od 50% ukupnih predviđanja ili kada je postotak točnih predviđanja za klijente koji su odustali manji od osnovne stope.
               
        - **Osnovna stopa** kao ulaz za model uzima vremenski okvir predviđanja (na primjer, godinu dana) i model stvara različite dijelove vremena dijeleći ga s 2 dok ne dosegne mjesec dana ili manje. Koristi ove dijelove za stvaranje poslovnog pravila za klijente koji nisu kupovali u ovom vremenskom okviru. Smatra se da su ti klijenti odustali. Kao osnovni model odabrano je poslovno pravilo koje se temelji na vremenu s najvišom sposobnošću predviđanja tko će vjerojatno odustati.
            
    - **Vjerojatnost gubitka (broj klijenata)**: Grupe klijenata na temelju njihovog predviđenog rizika da budu izgubljeni. Ovi podaci mogu vam pomoći kasnije ako želite stvoriti segment klijenata s visokim rizikom da budu izgubljeni. Takvi segmenti pomažu vam da shvatite gdje bi trebao biti vaš prag za članstvo u segmentu.
       
    - **Najutjecajniji faktori**: Mnogo je faktora koji se uzimaju u obzir prilikom izrade predviđanja. Svaki od čimbenika ima svoju važnost izračunatu za skupna predviđanja koja model stvara. S pomoću tih faktora možete potvrditi rezultate predviđanja ili možete koristiti te podatke kasnije kako biste [stvorili segmente](segments.md) koji bi mogli utjecati na opasnost od gubitka klijenata.


# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

1. Postoje tri primarna odjeljka podataka na stranici s rezultatima:
   - **Performanse modela obuke**: Mogući rezultati su A, B ili C. Ovaj rezultat označava performanse predviđanja i može vam pomoći da donesete odluku o korištenju rezultata pohranjenih u izlaznom entitetu. Rezultati se određuju na temelju sljedećih pravila: 
        - **A** kada je model točno predvidio najmanje 50% ukupnih predviđanja i kada je postotak točnih predviđanja za klijente koji su odustali veći od osnovne stope za najmanje 10%.
            
        - **B** kada je model točno predvidio najmanje 50% ukupnih predviđanja i kada je postotak točnih predviđanja za klijente koji su odustali do 10% veći od osnovne stope.
            
        - **C** kada je model točno predvidio manje od 50% ukupnih predviđanja ili kada je postotak točnih predviđanja za klijente koji su odustali manji od osnovne stope.
               
        - **Osnovna stopa** kao ulaz za model uzima vremenski okvir predviđanja (na primjer, godinu dana) i model stvara različite dijelove vremena dijeleći ga s 2 dok ne dosegne mjesec dana ili manje. Koristi ove dijelove za stvaranje poslovnog pravila za klijente koji nisu kupovali u ovom vremenskom okviru. Smatra se da su ti klijenti odustali. Kao osnovni model odabrano je poslovno pravilo koje se temelji na vremenu s najvišom sposobnošću predviđanja tko će vjerojatno odustati.
            
    - **Vjerojatnost gubitka (broj klijenata)**: Grupe klijenata na temelju njihovog predviđenog rizika da budu izgubljeni. Ovi podaci mogu vam pomoći kasnije ako želite stvoriti segment klijenata s visokim rizikom da budu izgubljeni. Takvi segmenti pomažu vam da shvatite gdje bi trebao biti vaš prag za članstvo u segmentu.
       
    - **Najutjecajniji faktori**: Mnogo je faktora koji se uzimaju u obzir prilikom izrade predviđanja. Svaki od čimbenika ima svoju važnost izračunatu za skupna predviđanja koja model stvara. S pomoću tih faktora možete potvrditi rezultate predviđanja ili možete koristiti te podatke kasnije kako biste [stvorili segmente](segments.md) koji bi mogli utjecati na opasnost od gubitka klijenata.


1. Za poslovne račune pronaći ćete stranicu s informacijama **Analiza utjecajnih značajki**. Sadrži četiri odjeljka podataka:

    - Stavka odabrana u desnom oknu određuje sadržaj te stranice. Odaberite stavku iz opcije **Najbolji klijenti** ili **Referentni klijenti**. Oba popisa su poredana prema silaznoj vrijednosti ocjene gubitka, bilo da je ocjena samo za klijenta ili kombinirana ocjena za klijente i sekundarnu razinu poput kategorije proizvoda.
        
        - **Najbolji klijenti**: Popis 10 klijenata koji imaju najveći rizik od gubitka i najmanji rizik od gubitka na temelju njihovih ocjena o gubitku. 
        - **Referentni klijenti**: Popis do 10 klijenata koji su odabrani prilikom konfiguriranja modela.
 
    - **Ocjena opasnosti od gubitka:** Prikazuje ocjenu opasnosti od gubitka za odabranu stavku u desnom oknu.
    
    - **Raspodjela rizika od gubitka:** Prikazuje raspodjelu rizika od gubitka po klijentima i postotak u kojem se nalazi odabrani kupac. 
    
    - **Glavne značajke koje povećavaju i smanjuju rizik od gubitka:** Za odabranu stavku u desnom oknu navedeno je pet glavnih značajki koje su povećale i smanjile rizik od gubitka. Za svaku utjecajnu značajku pronaći ćete vrijednost značajke za tu stavku i njezin utjecaj na ocjenu opasnosti od gubitka. Prikazana je i prosječna vrijednost svake značajke u segmentima klijenata s niskim, srednjim i visokim rizikom od gubitka. Pomaže u boljoj kontekstualizaciji vrijednosti najvažnijih utjecajnih značajki za odabranu stavku i uspoređuje je sa segmentima klijenata s niskim, srednjim i visokim rizikom od gubitka.

       - Nisko: računi ili kombinacije računa i sekundarne razine s ocjenom gubitka između 0 i 0,33
       - Srednje: računi ili kombinacije računa i sekundarne razine s ocjenom gubitka između 0,33 i 0,66
       - Visoko: računi ili kombinacije računa i sekundarne razine s ocjenom gubitka većom od 0,66
    
       Kada predvidite gubitak na razini računa, svi se računi uzimaju u obzir pri izvođenju prosječnih vrijednosti značajki za segmente gubitka. Za predviđanja gubitka na sekundarnoj razini za svaki račun, izvođenje segmenata gubitka ovisi o sekundarnoj razini stavke odabrane u bočnom oknu. Na primjer, ako stavka ima sekundarnu razinu kategorije proizvoda = uredski pribor, tada se samo one stavke koje imaju uredski pribor kao kategoriju proizvoda uzimaju u obzir pri izvođenju prosječnih vrijednosti svojstava za segmente gubitka. Ova se logika primjenjuje kako bi se osigurala pravedna usporedba vrijednosti značajki stavke s prosječnim vrijednostima u segmentima s niskim, srednjim i visokim rizikom od gubitka.

       U nekim slučajevima, prosječna vrijednost segmenata niskog, srednjog ili visokog rizika od gubitka prazna je ili nije dostupna, jer ne postoje stavke koje pripadaju odgovarajućim segmentima gubitka na temelju prethodno navedene definicije.
       
       > [!NOTE]
       > Tumačenje vrijednosti u prosječnim niskim, srednjim i visokim stupcima razlikuje se za kategoričke značajke, kao što su zemlja ili industrija. Budući da se pojam „prosječne” vrijednosti značajke ne primjenjuje na kategoričke značajke, vrijednosti u tim stupcima udio su klijenata u segmentima s niskim, srednjim ili visokim odljevom koji imaju istu vrijednost kategoričke značajke u usporedbi sa stavkom odabranom na bočnoj ploči.

---

## <a name="manage-predictions"></a>Upravljanje predviđanjima

Predviđanja je moguće optimizirati, riješiti, osvježiti ili izbrisati. Pregledajte izvješće o upotrebljivosti ulaznih podataka da biste saznali kako predviđanje učiniti bržim i pouzdanijim. Dodatne informacije potražite u odjeljku [Upravljanje predviđanjima](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
