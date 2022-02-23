---
title: Analiza raspoloženja za povratne informacije kupaca
description: Saznajte kako koristiti model analize sentimenta na povratnim informacijama korisnika u sustavu Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 8a4473c1c395bbcf8efa2bfa24cddb82e1784279
ms.sourcegitcommit: 15ec8c5f54242feda9489e7665726ec5e0983dc9
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 01/19/2022
ms.locfileid: "8008756"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analiza raspoloženja u povratnim informacijama korisnika (Pretpregled)

Kupci ovih dana očekuju visokokvalitetne proizvode, usluge i iskustva. Pogotovo kupci koji dijele svoje povratne informacije. Tvrtkama i ustanovama vrlo je izazovno analizirati sve veću količinu podataka bez smanjenja točnosti i većih troškova rada. Dynamics 365 Customer Insights nudi model analize raspoloženja za povratne informacije kupaca koji tvrtkama i ustanovama omogućuje točnije i jeftinije analizu podataka.

Analiza raspoloženja omogućuje vam sintetizaciju raspoloženja kupaca i prepoznavanje poslovnih aspekata kao prilika za poboljšanje. Ova značajka Customer Insights pomaže vam da shvatite što dobro funkcionira i što trebate riješiti. Usredotočite se na najrelevantnija i najutjecajnija područja poslovanja kako biste poboljšali iskustvo za svoje klijente. U konačnici, može vam pomoći u pokretanju poslovnih akcija koje omogućuju iskustva koja rezultiraju visokim zadovoljstvom i lojalnošću kupaca.

## <a name="overview"></a>Pretpregled

Značajka analize raspoloženja generira dva izvedena uvida po ID-u kupca. Ocjena raspoloženja (od -5 do 5) i popis primjenjivih poslovnih aspekata (područja poslovanja) zajedno vam pomažu da bolje razumijete povratne informacije kupaca. 

Te vam informacije mogu pomoći u postizanju sljedećih rezultata: 
- Pregled raspoloženja kupaca prema robnoj marki ili organizaciji
- Prepoznajte korisnike s negativnim osjećajem da biste usmjerili kampanje i angažmane te optimizirali za veći povrat  
- Prepoznavanje poslovnih aspekata s problemima koje su istaknuli kupci  
- Klijenti segmenta na temelju osjećaja za pokretanje personaliziranih kampanja uz ciljane napore u prodaji, marketingu i podršci
- Optimizirajte poslovanje rješavanjem područja zabrinutosti ili mogućnosti koje su spomenuli kupci
- Prepoznajte poslovne aspekte koji dobro rade i nagradite sretne kupce kroz programe vjernosti i promocije

Kako bismo osigurali da možete vjerovati rezultatima modela, pružamo transparentne informacije o tome kako modeli donose odluke. Dobit ćete popis riječi koje su utjecale na odluku modela da dodjeljuju određeni rezultat osjećaja ili poslovni aspekt komentarima povratnih informacija.  

Koristimo dva **modela** obrade prirodnog jezika (NLP): Prvi svakom komentaru povratnih informacija dodjeljuje ocjenu sentimenta. Drugi model povezuje svaku povratnu informaciju sa svim primjenjivim poslovnim aspektima. Modeli su osposobljeni za javne podatke iz izvora iz društvenih medija, maloprodaje, restorana, potrošačkih proizvoda i automobilske industrije.    
  
Unaprijed definirani poslovni aspekti koje model može povezati s povratnim podacima uključuju:
-   Upravljanje računom
-   Odjava i plaćanje
-   Korisnička podrška
-   Preuzimanje u trgovini
-   Pakiranje, otpremanje i povrat
-   Prednarudžbe
-   Cijena
-   Zaštita privatnosti i sigurnost
-   Promocije i nagrade
-   Potvrda o plaćanju i jamstvo
-   Povrat u svrhu zamjene i otkazivanje
-   Točnost ispunjavanja
-   Kvaliteta web-mjesta/aplikacije

> [!NOTE]
> Trenutno podržavamo analizu raspoloženja samo na engleskim povratnim informacijama kupaca. Ubuduće će biti podržano više jezika. Ako se prenesu povratne informacije na drugim jezicima, model će i dalje vraćati rezultate. Međutim, ovi rezultati neće biti točni. 

## <a name="prerequisites"></a>Preduvjeti

Analiza raspoloženja temelji se na podacima povratnih informacija teksta koji su prošli kroz postupak ujedinjenja [podataka](data-unification.md). Preporučujemo da prethodno konfigurirate [entitete podataka s povratnim informacijama kao entitete](map-entities.md#select-primary-key-and-semantic-type-for-attributes) aktivnosti semantičke vrste (vrsta povratnih informacija). 

Da biste konfigurirali model analize raspoloženja, potrebne su vam barem [suradnik dozvole](permissions.md).

Customer Insights može obraditi do 10 milijuna zapisa povratnih informacija za jednu vožnju modela. Model može analizirati povratne komentare do 128 riječi. Ako je komentar povratnih informacija duži, analiza uzima u obzir samo prvih 128 riječi.

### <a name="data-requirements"></a>Preduvjeti za podatke
  
Potrebni su sljedeći atributi podataka:
- Objedinjeni ID klijenta (UCID) za podudaranje zapisa podataka s povratnim informacijama teksta s pojedinačnim klijentom. Ovaj ID rezultat je postupka [ujedinjenja](data-unification.md) podataka.
- ID povratnih informacija
- Vremenska oznaka povratnih informacija
- Tekst povratnih informacija   

> [!TIP]
> Analiza raspoloženja zahtijeva tekstualne povratne informacije vaših kupaca. Trenutno se može konfigurirati samo jedan entitet povratnih informacija. Ako postoji više entiteta za povratne informacije, možete ih udružiti Power Query prije početka unosa podataka.

## <a name="configure-a-sentiment-analysis"></a>Konfiguriranje analize sentimenta 

1. U aplikaciji Customer Insights idite na **Inteligencija** > **Predviđanja**.

1. Na pločici **Analiza** raspoloženja kupca odaberite **Koristi model**.

1. U oknu **Analiza raspoloženja klijenta (pretpregled)** odaberite **Početak rada**.

1. U koraku **Naziv** modela navedite **naziv** analize. 

1. Navedite naziv **izlaznog** entiteta poslovnog aspekta i naziv **izlaznog** entiteta rezultata sentimenta, a zatim odaberite **Dalje**.

1. U koraku Obavezni podaci odaberite **Dodaj podatke**.**·**

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Dodajte protok podataka u modelu analize raspoloženja.":::

1. U oknu **Dodavanje podataka** odaberite semantičku vrstu **Povratne informacije** s popisa.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Korak konfiguracije za odabir aktivnosti povratnih informacija za analizu sentimenta.":::

1. Odaberite aktivnosti koje će se koristiti za ovu analizu sentimenta, a zatim **dalje**.
 
1. Mapirajte atribute u podacima u atribute modela. Odaberite **Spremi** da biste primijenili odabire. 

1. Vidjet ćete stanje preslikavanja podataka. Za nastavak odaberite **Dalje**. 

1. U koraku **Pregled pojedinosti modela** provjerite konfiguraciju analize raspoloženja. Možete se vratiti na bilo koji dio konfiguracije predviđanje. Odaberite **Spremi i pokreni** da biste započeli analizu. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Pregledajte korak za model sentimenta koji prikazuje sve konfigurirane stavke.":::

1. Odaberite **Gotovo** da biste napustili doživljaj konfiguracije. Postupak može potrajati nekoliko sati, ovisno o količini korištenih podataka. 

## <a name="review-analysis-status"></a>Stanje analize pregleda

1.  Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.
2.  Odaberite predviđanje koje želite pregledati.
- **Naziv predviđanja:**: naziv predviđanja naveden pri stvaranju.
- **vrsta** predviđanje: Vrsta modela koji se koristi za predviđanje.
- **Entitet rezultata**: naziv entiteta za pohranu rezultata predviđanja. Idite u odjeljak **Podaci** > **Entiteti** da biste pronašli entitet s ovim nazivom.
- **Predviđeno polje**: Ovo se polje popunjava samo za neke vrste predviđanja i ne koristi se u predviđanju cjeloživotne vrijednosti klijenta.
- **Status**: status pokretanja predviđanja.
  - **U redu čekanja**: predviđanje čeka da se drugi procesi dovrše.
  - **Osvježavanje**: predviđanje je trenutno pokrenuto za stvaranje rezultata koji će ići u izlazni entitet.
  - **Neuspjelo**: pokretanje predviđanja nije uspjelo. Pregledajte zapisnike za dodatne pojedinosti.
  - **Uspjelo**: predviđanje je uspjelo. Odaberite Prikaz ispod vertikalnih elipsi za pregled rezultata predviđanja.
- **Uređeno**: promijenjen je datum konfiguriranja za predviđanje.
- **Zadnje osvježavanje**: datum osvježavanja predviđanje u izlaznom entitetu.

## <a name="manage-sentiment-analysis"></a>Upravljanje analizom raspoloženja

Predviđanja možete optimizirati, otkloniti, osvježiti ili izbrisati. Pregledajte izvješće o upotrebljivosti ulaznih podataka da biste saznali kako predviđanje učiniti bržim i pouzdanijim. Dodatne informacije potražite u odjeljku [Upravljanje predviđanjima](manage-predictions.md).

## <a name="review-analysis-results"></a>Pregled rezultata analize
 
1. Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**. 
1. Odaberite naziv predviđanje za koju želite pregledati rezultate. U tom slučaju odaberite analizu sentimenta koju želite pregledati. 

### <a name="summary-tab"></a>Kartica sažetka

Na stranici rezultata nalaze se četiri primarna odjeljka podataka. 

- **Prosječna ocjena raspoloženja**: pomaže vam razumjeti cjelokupno raspoloženje svih kupaca. Ocjene raspoloženja grupirane su u tri kategorije: 
  1.    Negativno (-5 > 2)
  2.    Neutralno (-1 > 1)
  3.    Pozitivno (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizualni prikaz cjelokupnog raspoloženja kupaca.":::

- **Distribucija kupaca prema ocjeni** sentimenta: kupci su kategorizirani u negativne, neutralne i pozitivne skupine na temelju njihovih rezultata raspoloženja. Zadržite pokazivač miša iznad traka u histogramu da biste vidjeli broj kupaca i prosječnu ocjenu raspoloženja u svakoj grupi. Ti vam podaci mogu pomoći u [stvaranju segmenata klijenata](segments.md) na temelju njihovih rezultata raspoloženja.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="trakasti grafikon pokazujući raspoloženje kupaca u tri grupe osjećaja.":::

- **Prosječna ocjena raspoloženja tijekom vremena**: raspoloženje kupaca može se s vremenom promijeniti. Pružamo trendove u raspoloženjima vaših kupaca za vremenski raspon vaših podataka. Ovaj prikaz može vam pomoći da procijenite učinak sezonskih promocija, lansiranja proizvoda ili drugih vremenski ograničenih intervencija na raspoloženje kupaca. Pogledajte grafikon odabirom godine interesa s padajućeg izbornika. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="grafikon povijesti s rezultatom osjećaja tijekom vremena predstavljenim kao linija.":::
 
- **Raspoloženje u poslovnim aspektima**: u ovoj se tablici navodi prosječno raspoloženje u poslovnim aspektima. To vam može pomoći da procijenite koji aspekti vašeg poslovanja već zadovoljavaju kupce ili aspekte koji zahtijevaju više pozornosti. Zapisi povratnih informacija koji se ne podudaraju ni s jednom od podržanih poslovnih aspekata kategorizirani su u odjeljku **Ostalo**. Tablica je po zadanom sortirana abecednim redom. Sortiranje možete izmijeniti odabirom zaglavlja tablice.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Popis poslovnih aspekata s pridruženim vrijednost naklonosti i broj kupaca koji ga spominju.":::
 
  Odaberite naziv poslovnog aspekta da biste vidjeli dodatne informacije o tome kako model identificira poslovni aspekt. U ovom oknu postoje dva dijela: 

  - **Utjecajne riječi**: Prikazuje glavne riječi koje su utjecale na identifikaciju poslovnog aspekta modela AI u povratnim informacijama kupaca. 
    **Pokaži uvredljive riječi**: omogućuje vam uključivanje uvredljivih riječi na popis iz izvornih podataka o povratnim informacijama korisnika. Prema zadanim postavkama je isključen.  Uvredljivo maskiranje riječi pokreće model AI i možda neće otkriti sve uvredljive riječi. Nastavljamo s iteriranjem i obukom klasifikatora za optimalne performanse. Ako otkrijete uvredljivu riječ koja nije filtrirana prema očekivanjima, javite nam. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Popis utjecajnih riječi s preklopnikom za prikaz ili skrivanje uvredljivih riječi.":::
 
  - **Uzorci** povratnih informacija: prikazuje stvarne zapise povratnih informacija u vašim podacima. Riječi su označene bojama prema njihovom utjecaju na identifikaciju poslovnog aspekta. 


### <a name="influential-words-analysis-tab"></a>Kartica za analizu utjecajnih riječi

Postoje tri odjeljka dodatnih informacija koji objašnjavaju kako funkcionira model sentimenta.
  
1. **Glavne riječi koje pridonose pozitivnom raspoloženju**: Prikazuje glavne riječi koje su utjecale na prepoznavanje pozitivnog raspoloženja modela AI u povratnim informacijama kupaca.  
2. **Glavne riječi koje pridonose negativnom raspoloženju**: Prikazuje glavne riječi koje su utjecale na identifikaciju negativnog raspoloženja modela AI u povratnim informacijama kupaca.  
3. **Uzorci** povratnih informacija: Prikazuje stvarne zapise povratnih informacija, jedan s negativnim osjećajem i jedan s pozitivnim osjećajem. Riječi u zapisima povratnih informacija istaknute su u skladu s njihovim doprinosom dodijeljenom rezultatu sentimenta. Riječi koje doprinose pozitivnom rezultatu osjećaja istaknute su zelenom bojom. Riječi koje pridonose negativnom rezultatu označene su crvenom bojom.
   Odaberite **Pogledajte više** da biste učitali više uzoraka povratnih informacija koji pružaju više informacija i konteksta rada modela sentimenta.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Primjeri analize raspoloženja o povratnim informacijama kupaca.":::
 
**Pokaži uvredljive riječi**: omogućuje vam uključivanje uvredljivih riječi na popis iz izvornih podataka o povratnim informacijama korisnika. Prema zadanim postavkama je isključen.  Uvredljivo maskiranje riječi pokreće model AI i možda neće otkriti sve uvredljive riječi. Nastavljamo s iteriranjem i obukom klasifikatora za optimalne performanse. Ako otkrijete uvredljivu riječ koja nije filtrirana prema očekivanjima, javite nam. 

## <a name="act-on-analysis-results"></a>Zakon o rezultatima analize

Nove segmente kupaca možete jednostavno početi stvarati na stranici rezultata analize raspoloženja tako da odaberete **Stvori segmente** pri vrhu stranice rezultata modela.

:::image type="content" source="media/create-segment-model.png" alt-text="Naredbena traka s mogućnostima na predviđanje modelima.":::
 
## <a name="potential-bias"></a>Potencijalna pristranost

Kao i kod svake značajke koja koristi prediktivnu umjetnu inteligenciju, trebali biste biti svjesni potencijalne pristranosti u podacima koje koristite za predviđanje raspoloženja kupaca. Na primjer, ako prikupljate povratne informacije samo digitalno, mogli biste propustiti povratne informacije od korisnika koji prvenstveno osobno posluju s vama, što bi moglo utjecati na izlaz značajke.

Budući da ova značajka koristi automatizirana sredstva za procjenu podataka i predviđanja na temelju tih podataka, stoga ima mogućnost korištenja kao metoda profiliranja jer je taj pojam definiran Općom uredbom o zaštiti podataka ("GDPR"). Vaša upotreba ove značajke za obradu podataka može podlijegati GDPR-u ili drugim zakonima ili propisima. Vi ste odgovorni za osiguravanje da je vaša upotreba Dynamics 365 Customer Insights, uključujući analizu osjećaja, u skladu sa svim primjenjivim zakonima i propisima, uključujući zakone koji se odnose na privatnost, osobne podatke, biometrijske podatke, zaštitu podataka i povjerljivost komunikacija.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

