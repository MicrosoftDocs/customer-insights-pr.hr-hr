---
title: Transakcijski bućkanje predviđanje (sadrži videozapise)
description: Predvidite postoji li opasnost da će klijent prestati kupovati vaše proizvode ili usluge.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610503"
---
# <a name="predict-transaction-churn"></a>Predviđanje gubitka transakcija

Transakcijsko predviđanje gubitka pomaže predvidjeti hoće li klijent prestati kupovati vaše proizvode ili usluge u određenom vremenskom roku.

Morate imati poslovno znanje da biste razumjeli što bućkuriš znači za vaše poslovanje. Podržavamo vremenske definicije gubitka, što znači da se smatra da je klijent odustao nakon razdoblja bez kupnje.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Za okruženja koja se temelje na poslovnim računima, možemo predvidjeti gubitak transakcije za račun, a također i kombinaciju računa i drugu razinu informacija poput kategorije proizvoda. Na primjer, dodavanje dimenzije može pomoći u određivanju vjerojatnosti da će račun "Contoso" prestati kupovati kategoriju proizvoda "uredski pribor". Osim toga, za poslovne račune možemo također koristiti umjetnu inteligenciju za generiranje popisa mogućih razloga zašto će se račun vjerojatno izgubiti zbog kategorije podataka sekundarne razine.

> [!TIP]
> Isprobajte transakcijski bućkanje predviđanje pomoću oglednih podataka: [Transakcijski bućkanje predviđanje vodič za uzorke](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Preduvjeti

- Barem [Dozvole suradnika](permissions.md).
- Najmanje 10 korisničkih profila, po mogućnosti više od 1.000 jedinstvenih kupaca.
- Identifikator kupca, jedinstveni identifikator koji odgovara transakcijama s vašim klijentima.
- Podaci o transakcijama za barem dvostruko veći od odabranog vremenskog razdoblja, kao što su dvije do tri godine povijesti transakcija. U idealnom slučaju najmanje dvije transakcije po kupcu. Povijest transakcija mora sadržavati:
  - **ID** transakcije: jedinstveni identifikator kupnje ili transakcije.
  - **Datum** transakcije: datum kupnje ili transakcije.
  - **Vrijednost transakcije**: Valuta ili iznos brojčane vrijednosti transakcije.
  - **Jedinstveni ID** proizvoda: ID proizvoda ili usluge kupljene ako su vaši podaci na razini stavke retka.
  - **Je li ta transakcija bila povrat**: polje true/false koje određuje je li transakcija bila povrat ili ne. **Ako je vrijednost transakcije** negativna, zaključit ćemo povrat.
- Podaci o aktivnostima korisnika:
  - Identifikator klijenta, jedinstveni identifikator za mapiranje aktivnosti klijentima.
  - **Primarni ključ:** jedinstveni identifikator aktivnosti. Na primjer, posjet web-mjestu ili zapis korištenja koji pokazuje da je klijent isprobao uzorak vašeg proizvoda.
  - **Vremenska oznaka:** Datum i vrijeme događaja identificirani primarnim ključem.
  - **Događaj:** naziv događaja koji želite koristiti. Na primjer, polje pod nazivom „UserAction” u trgovini mješovite robe može biti kupon koji kupac koristi.
  - **Pojedinosti:** Detaljne informacije o događaju. Na primjer, polje pod nazivom „CouponValue” u trgovini mješovite robe može biti vrijednost valute kupona.
- Manje od 20% vrijednosti koje nedostaju u podatkovnom polju navedenog entiteta

Za poslovne račune (B-do-B) dodajte podatke o kupcima usklađene sa statičnijim atributima kako biste osigurali najbolje rezultate modela:
- **ID klijenta:** Jedinstveni identifikator kupca.
- **Datum kreiranja:** datum kada je kupac prvotno dodan.
- **Država ili pokrajina:** državna ili pokrajinska lokacija kupca.
- **Zemlja:** zemlja kupca.
- **Industrija:** Industrijska vrsta kupca. Na primjer, polje pod nazivom Industrija u pržionici kave može ukazivati na to je li klijent bio iz maloprodajnog sektora.
- **Klasifikacija:** Kategorizacija kupca za vaše poslovanje. Na primjer, polje pod nazivom ValueSegment u pržionici kave može biti razina klijenta na temelju veličine klijenta.

> [!NOTE]
> Za tvrtku s velikom učestalošću kupnji klijenata (svakih nekoliko tjedana) preporučuje se odabir kraćeg okvira predviđanja i definicije gubitka. Za nisku učestalost kupnje (svakih nekoliko mjeseci ili jednom godišnje) odaberite dulji okvir predviđanja i definicije gubitka.

## <a name="create-a-transaction-churn-prediction"></a>Stvaranje predviđanja gubitka transakcija

1. Idite na **Obavještajna** > **predviđanja**.

1. Na kartici **Stvaranje** **odaberite Koristi model** na pločici Model **modela kupca**.

1. Odaberite **Transakcija** za vrstu bućkanja, a zatim **Početak rada**.

1. **Nazovite ovaj model** i **Naziv izlaznog entiteta** kako bi se razlikovali od ostalih modela ili entiteta.

1. Odaberite **Dalje**.

### <a name="define-customer-churn"></a>Definirajte gubitak klijenta

U bilo kojem trenutku odaberite **Spremi skicu** da biste predviđanje spremili kao skicu. Skica predviđanje prikazuje se na **kartici Moja predviđanja**.

1. **Postavite prozor** predviđanje. Na primjer, predvidite rizik od gubitka klijenata tijekom sljedećih 90 dana kako biste se uskladili s vašim naporima zadržavanja marketinga. Predviđanje rizika od gubitka tijekom duljeg ili kraćeg vremenskog razdoblja može otežati adresiranje čimbenika u vašem profilu rizika od gubitka, ali to ovisi o vašim specifičnim poslovnim zahtjevima.

1. Unesite broj dana za definiranje bućkanja u polje Definicija **Churn**. Na primjer, ako kupac nije izvršio kupnju u posljednjih 30 dana, može se smatrati da je bućkan za vašu tvrtku.

1. Odaberite **Dalje**.

### <a name="add-purchase-history"></a>Dodajte povijest kupnje

1. Odaberite **Dodaj podatke** za **povijest** transakcija kupca.

1. Odaberite vrstu semantičke aktivnosti, **SalesOrder** ili **SalesOrderLine**, koja sadrži podatke o povijesti transakcija. Ako aktivnost nije postavljena, odaberite ovdje **i** stvorite je.

1. U odjeljku **Aktivnosti**, ako su atributi aktivnosti semantički mapirani prilikom stvaranja aktivnosti odaberite određene atribute ili entitet na koji želite da se izračun usredotoči. Ako nije došlo do semantičkog mapiranja, odaberite **Uređivanje** i mapiranje podataka.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Bočno okno koje prikazuje odabir određenih aktivnosti prema semantičkoj vrsti.":::

1. Odaberite **Dalje** i pregledajte atribute potrebne za ovaj model.

1. Odaberite **Spremi**.

1. Dodajte još aktivnosti ili odaberite **Dalje**.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Dodavanje dodatnih podataka (neobavezno)

1. Odaberite **Dodaj podatke** za **aktivnosti** klijenta.

1. Odaberite vrstu semantičke aktivnosti koja sadrži podatke koje želite koristiti. Ako aktivnost nije postavljena, odaberite ovdje **i** stvorite je.

1. U odjeljku **Aktivnosti**, ako su atributi aktivnosti semantički mapirani prilikom stvaranja aktivnosti odaberite određene atribute ili entitet na koji želite da se izračun usredotoči. Ako nije došlo do semantičkog mapiranja, odaberite **Uređivanje** i mapiranje podataka.

1. Odaberite **Dalje** i pregledajte atribute potrebne za ovaj model.

1. Odaberite **Spremi**.

1. Odaberite **Sljedeće**

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

### <a name="select-prediction-level"></a>Odabir razine predviđanja

Većina predviđanja izrađuje se na razini klijenta. U nekim situacijama to možda nije dovoljno detaljno da zadovolji vaše poslovne potrebe. Koristite ovu značajku za predviđanje bućkanja za podružnicu kupca, na primjer, a ne za kupca u cjelini.

1. Odaberite **Odaberite entitet za sekundarnu razinu**. Ako opcija nije dostupna, provjerite jeste li dovršili prethodni odjeljak.

1. Proširite entitete iz kojih želite odabrati sekundarnu razinu ili upotrijebite okvir za filtriranje pretraživanja da biste filtrirali odabrane opcije.

1. Odaberite atribut koji želite koristiti kao sekundarnu razinu, a zatim odaberite **Dodaj**.

1. Odaberite **Dalje**.

> [!NOTE]
> Entiteti dostupni u ovom odjeljku prikazani su jer imaju odnos s entitetom koji ste odabrali u prethodnom odjeljku. Ako ne vidite entitet koji želite dodati, provjerite ima li važeći odnos u opciji **Odnosi**. Za ovu konfiguraciju vrijede samo odnosi jedan-na-jedan i više-na-jedan.

### <a name="add-additional-data-optional"></a>Dodavanje dodatnih podataka (neobavezno)

1. Odaberite **Dodaj podatke** za **aktivnosti** klijenta.

1. Odaberite vrstu semantičke aktivnosti koja sadrži podatke koje želite koristiti. Ako aktivnost nije postavljena, odaberite ovdje **i** stvorite je.

1. U odjeljku **Aktivnosti**, ako su atributi aktivnosti semantički mapirani prilikom stvaranja aktivnosti odaberite određene atribute ili entitet na koji želite da se izračun usredotoči. Ako nije došlo do semantičkog mapiranja, odaberite **Uređivanje** i mapiranje podataka.

1. Odaberite **Dalje** i pregledajte atribute potrebne za ovaj model.

1. Odaberite **Spremi**.

1. Odaberite **Sljedeće**

1. Po želji odaberite **Dodaj podatke** za opciju **Podaci o klijentima**.

1. Preslikajte semantičke atribute u polja u vlastitim podacima o klijentima kao što je identificirano. Podaci u korištenim poljima ne bi se trebali često mijenjati kako bi se osigurale najbolje performanse modela. Na primjer, odabirom polja za Klasifikaciju koje se mijenjalo svaki mjesec dobila bi se samo posljednja vrijednost korištena u predviđanju, iako se povijesno ista vrijednost možda ne bi odnosila na klijenta pri stvaranju uzoraka predviđanja.

1. Odaberite **Dalje**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Navedite neobavezni popis standardiziranih računa

Dodajte popis poslovnih klijenata i računa koje želite koristiti kao referentne vrijednosti. Pojedinosti [za ove referentne račune](#view-prediction-results) uključuju njihovu ocjenu bućkanja i najutjecajnije značajke koje su utjecale na njihov bućkanje predviđanje.

1. Odaberite **+ Dodaj klijente**.

1. Odaberite klijente koji djeluju kao referentna vrijednost.

1. Odaberite **Dalje**.

---

### <a name="set-update-schedule"></a>Postavljanje rasporeda ažuriranja

1. **Za korak Ažuriranja** podataka odaberite učestalost prekvalifikacije modela. Ova je postavka važna za ažuriranje točnosti predviđanja jer se novi podaci unose u Customer Insights. Većina tvrtki može ponovno uvježbavati jednom mjesečno i steći dobru točnost predviđanja.

1. Odaberite **Dalje**.

### <a name="review-and-run-the-model-configuration"></a>Pregled i pokretanje konfiguracije modela

Korak **Pregled i izvođenje** prikazuje sažetak konfiguracije i pruža priliku za promjene prije stvaranja predviđanje.

1. Na **bilo kojem od koraka za pregled i unos promjena odaberite Uredi**.

1. Ako ste zadovoljni odabirom, odaberite **Spremi i pokreni** da biste započeli s pokretanjem modela. Odaberite **Gotovo**. Kartica **Moja predviđanja** prikazuje se tijekom stvaranja predviđanje. Proces može potrajati nekoliko sati ovisno o količini podataka korištenih za predviđanje.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prikaz rezultata predviđanje

1. Idite na **Obavještajna** > **predviđanja**.

1. Na kartici **Moja predviđanja** odaberite predviđanje koji želite pregledati.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

Postoje tri primarna odjeljka podataka na stranici s rezultatima:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

Postoje tri primarna odjeljka podataka na stranici s rezultatima:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Stranica **s informacijama o analizi** utjecajnih značajki sadrži četiri odjeljka podataka:

- U desnom oknu odaberite stavku najboljih **kupaca** ili **benchmark kupaca**. Oba popisa su poredana prema silaznoj vrijednosti ocjene gubitka, bilo da je ocjena samo za klijenta ili kombinirana ocjena za klijente i sekundarnu razinu poput kategorije proizvoda. Odabrana stavka određuje sadržaj na ovoj stranici.

  - **Najbolji klijenti**: Popis 10 klijenata koji imaju najveći rizik od gubitka i najmanji rizik od gubitka na temelju njihovih ocjena o gubitku.
  - **Referentni klijenti**: Popis do 10 klijenata koji su odabrani prilikom konfiguriranja modela.

- **Ocjena opasnosti od gubitka:** Prikazuje ocjenu opasnosti od gubitka za odabranu stavku u desnom oknu.

- **Distribucija rizika bucmastog rizika:** Prikazuje raspodjelu rizika bućkanja među kupcima i percentil u kojem se nalazi odabrani kupac.

- **Glavne značajke koje povećavaju i smanjuju rizik od bućkanja:** Navodi prvih pet značajki koje su povećale i smanjile rizik od bušenja za odabranu stavku u desnom oknu. Prikazuje vrijednost značajke za tu stavku i njezin utjecaj na rezultat bućkanja za svaku utjecajnu značajku. Prikazana je i prosječna vrijednost svake značajke u segmentima klijenata s niskim, srednjim i visokim rizikom od gubitka. Pomaže u boljoj kontekstualizaciji vrijednosti najvažnijih utjecajnih značajki za odabranu stavku i uspoređuje je sa segmentima klijenata s niskim, srednjim i visokim rizikom od gubitka.

  - Niska: računi ili kombinacije računa i sekundarne razine s ocjenom između 0 i 0,33.
  - Srednje: računi ili kombinacije računa i sekundarnih razina s ocjenom između 0,33 i 0,66.
  - Visoka: računi ili kombinacije računa i sekundarnih razina s ocjenom bućkuriša većom od 0,66.

  Kada predvidite gubitak na razini računa, svi se računi uzimaju u obzir pri izvođenju prosječnih vrijednosti značajki za segmente gubitka. Za predviđanja gubitka na sekundarnoj razini za svaki račun, izvođenje segmenata gubitka ovisi o sekundarnoj razini stavke odabrane u bočnom oknu. Na primjer, ako artikl ima sekundarnu razinu kategorije proizvoda (uredski materijal), tada se pri izvođenju prosječnih vrijednosti značajki za segmente bućkanja uzimaju u obzir samo artikli koji imaju uredski materijal kao kategoriju proizvoda. Ova se logika primjenjuje kako bi se osigurala pravedna usporedba vrijednosti značajki stavke s prosječnim vrijednostima u segmentima s niskim, srednjim i visokim rizikom od gubitka.

  U nekim slučajevima, prosječna vrijednost segmenata niskog, srednjog ili visokog rizika od gubitka prazna je ili nije dostupna, jer ne postoje stavke koje pripadaju odgovarajućim segmentima gubitka na temelju prethodno navedene definicije.

  Tumačenje vrijednosti u prosječnim niskim, srednjim i visokim stupcima razlikuje se za kategoričke značajke, kao što su zemlja ili industrija. Budući da se pojam „prosječne” vrijednosti značajke ne primjenjuje na kategoričke značajke, vrijednosti u tim stupcima udio su klijenata u segmentima s niskim, srednjim ili visokim odljevom koji imaju istu vrijednost kategoričke značajke u usporedbi sa stavkom odabranom na bočnoj ploči.

---

 > [!NOTE]
 > U izlaznom entitetu za ovaj model ChurnScore *prikazuje predviđenu vjerojatnost bućkanja,* a *IsChurn* je binarna oznaka koja se temelji na *ChurnScoreu* s pragom od 0,5. Ako taj zadani prag ne funkcionira za vaš scenarij, [stvorite novi segment](segments.md#create-a-segment) s željenim pragom. Nisu svi klijenti nužno i aktivni klijenti. Neki od njih možda već dugo nisu imali nikakve aktivnosti i već se smatraju izgubljenima na temelju vaše definicije gubitka. Predviđanje opasnosti od gubitka za klijente koji su već izgubljeni nije korisno jer nisu ciljna skupina.
>
> Da biste prikazali rezultat, idite na **Entiteti** > **podataka** i pogledajte karticu podataka za izlazni entitet koji ste definirali za ovaj model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
