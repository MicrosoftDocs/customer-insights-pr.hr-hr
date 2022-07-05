---
title: Analiziraj naklonost povratnih informacija o klijentu (pretpregled)
description: Saznajte kako koristiti model analize naklonosti na povratnim informacijama klijenata u sustavu Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: af1afd3eff8a795a9e199b1c1d411b79dc2841b4
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055527"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analiza naklonosti u povratnim informacijama korisnika (pretpregled)

Kupci ovih dana očekuju visokokvalitetne proizvode, usluge i iskustva. Pogotovo kupci koji dijele svoje povratne informacije. Organizacijama je vrlo izazovno analizirati sve veći obujam podataka bez smanjenja točnosti i većih troškova rada. Dynamics 365 Customer Insights nudi model analize sentimenta za povratne informacije kupaca koji omogućuje organizacijama da preciznije i po nižoj cijeni analiziraju svoje podatke.

Analiza naklonosti omogućuje vam sintezu raspoloženja kupaca i prepoznavanje poslovnih aspekata kao prilika za poboljšanje. Ova značajka Customer Insights pomaže vam razumjeti što dobro funkcionira i što trebate riješiti. Usredotočite se na najrelevantnija i najutjecajnija područja poslovanja kako biste poboljšali iskustvo za svoje kupce. U konačnici, može vam pomoći u pokretanju poslovnih akcija koje omogućuju iskustva koja rezultiraju visokim zadovoljstvom i lojalnošću kupaca.

## <a name="overview"></a>Pretpregled

Značajka analize naklonosti generira dva izvedena uvida po ID-u kupca. Ocjena naklonosti (od -5 do 5) i popis primjenjivih poslovnih aspekata (područja poslovanja) zajedno vam pomažu da bolje razumijete povratne informacije kupaca. 

Te vam informacije mogu pomoći u postizanju sljedećih rezultata: 
- Pregled osjećaja kupaca prema robnoj marki ili organizaciji
- Identificirajte kupce s negativnim osjećajem kako biste usmjerili svoje kampanje i angažmane i optimizirali za veći povrat  
- Prepoznavanje poslovnih aspekata s problemima koje su istaknuli kupci  
- Segmentiranje korisnika na temelju njihovog osjećaja za pokretanje personaliziranih kampanja s ciljanim naporima prodaje, marketinga i podrške
- Optimizirajte poslovanje rješavanjem problematičnih područja ili mogućnosti koje su spomenuli kupci
- Prepoznati poslovne aspekte koji dobro posluju i nagraditi sretne kupce kroz programe vjernosti i promocije

Kako biste osigurali da možete vjerovati rezultatima modela, pružamo transparentne informacije o tome kako modeli donose odluke. Dobit ćete popis riječi koje su utjecale na odluku modela da dodjeljuju određenu ocjenu raspoloženja ili poslovni aspekt komentarima povratnih informacija.  

Koristimo dva **modela** obrade prirodnog jezika (NLP): Prvi dodjeljuje svakom povratnom komentaru ocjenu naklonosti. Drugi model povezuje svaku povratnu informaciju sa svim primjenjivim poslovnim aspektima. Modeli su obučeni za javne podatke iz izvora iz društvenih medija, maloprodaje, restorana, potrošačkih proizvoda i automobilske industrije.    
  
Unaprijed definirani poslovni aspekti za model povezan s podacima povratnih informacija uključuju:
-   Upravljanje računom
-   Odjava i plaćanje
-   Korisnička podrška
-   Preuzimanje u trgovini
-   Pakiranje, otpremanje i povrat
-   Predbilježbe
-   Cijena
-   Zaštita privatnosti i sigurnost
-   Promocije i nagrade
-   Potvrda o plaćanju i jamstvo
-   Povrat u svrhu zamjene i otkazivanje
-   Točnost ispunjavanja
-   Kvaliteta web-mjesta/aplikacije

> [!NOTE]
> Trenutno podržavamo samo analizu raspoloženja na povratnim informacijama engleskog kupca. U budućnosti će biti podržano više jezika. Ako se prenesu povratne informacije na drugim jezicima, model će i dalje vraćati rezultate. Međutim, ovi rezultati neće biti točni. 

## <a name="prerequisites"></a>Preduvjeti

Analiza naklonosti temelji se na podacima s povratnim informacijama teksta koji su prošli kroz [postupak objedinjavanja podataka](data-unification.md). Toplo preporučujemo da prethodno konfigurirate [entitete podataka s povratnim informacijama kao entitete](map-entities.md#select-primary-key-and-semantic-type-for-attributes) aktivnosti semantičke vrste (vrsta povratnih informacija). 

Da biste konfigurirali model analize naklonosti, potrebna vam je barem [suradnik dozvola](permissions.md).

Customer Insights može obraditi do 10 milijuna zapisa povratnih informacija za jedan model. Model može analizirati povratne komentare do 128 riječi. Ako je komentar povratnih informacija duži, analiza uzima u obzir samo prvih 128 riječi.

### <a name="data-requirements"></a>Preduvjeti za podatke
  
Potrebni su sljedeći atributi podataka:
- Objedinjeni ID klijenta (UCID) za podudaranje zapisa podataka o povratnim informacijama teksta s pojedinačnim klijentom. Ovaj ID rezultat je postupka [objedinjavanja](data-unification.md) podataka.
- ID povratnih informacija
- Vremenska oznaka povratnih informacija
- Tekst povratnih informacija   

> [!TIP]
> Analiza naklonosti zahtijeva povratne informacije o tekstu vaših kupaca. Trenutno se može konfigurirati samo jedan entitet za povratne informacije. Ako postoji više entiteta povratnih informacija, možete ih objediniti Power Query prije početka gutanja podataka.

## <a name="configure-a-sentiment-analysis"></a>Konfiguriranje analize naklonosti 

1. U aplikaciji Customer Insights idite na **Inteligencija** > **Predviđanja**.

1. Na pločici Analiza naklonosti **kupca odaberite** Koristi model **.**

1. **U oknu Analiza naklonosti klijenta (pretpregled)** odaberite **Početak rada**.

1. U koraku **Naziv** modela navedite **naziv** za svoju analizu. 

1. Navedite naziv **izlaznog entiteta** poslovnog aspekta i naziv **izlaznog** entiteta rezultata naklonosti, a zatim odaberite **Dalje**.

1. U koraku Obavezni **podaci** odaberite **Dodaj podatke**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Dodajte protok podataka u model analize naklonosti.":::

1. **U oknu Dodavanje podataka** s popisa odaberite semantičku vrstu Povratne **informacije**.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Korak konfiguracije za odabir aktivnosti povratnih informacija za analizu naklonosti.":::

1. Odaberite aktivnosti koje će se koristiti za ovu analizu naklonosti, a zatim **dalje**.
 
1. Mapirajte atribute u podacima na atribute modela. Odaberite **Spremi** da biste primijenili odabire. 

1. Vidjet ćete stanje mapiranja podataka. Za nastavak odaberite **Dalje**. 

1. U koraku **Pregled pojedinosti o** modelu provjerite konfiguraciju analize naklonosti. Možete se vratiti na bilo koji dio konfiguracije predviđanje. Odaberite **Spremi i pokreni** da biste započeli analizu. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Pregled koraka za model naklonosti koji prikazuje sve konfigurirane stavke.":::

1. Odaberite **Gotovo** da biste napustili konfiguracijsko iskustvo. Postupak može potrajati nekoliko sati, ovisno o količini korištenih podataka. 

## <a name="review-analysis-status"></a>Pregled stanja analize

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
- **Zadnje osvježavanje**: datum kada je predviđanje osvježio rezultate u izlaznom entitetu.

## <a name="manage-sentiment-analysis"></a>Upravljanje analizom naklonosti

Možete optimizirati, otkloniti poteškoće, osvježiti ili izbrisati predviđanja. Pregledajte izvješće o upotrebljivosti ulaznih podataka da biste saznali kako predviđanje učiniti bržim i pouzdanijim. Dodatne informacije potražite u odjeljku [Upravljanje predviđanjima](manage-predictions.md).

## <a name="review-analysis-results"></a>Pregled rezultata analize
 
1. Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**. 
1. Odaberite naziv predviđanje za koju želite pregledati rezultate. U tom slučaju odaberite analizu naklonosti koju želite pregledati. 

### <a name="summary-tab"></a>Kartica sažetka

Unutar stranice s rezultatima nalaze se četiri primarna odjeljka podataka. 

- **Prosječna ocjena** naklonosti: pomaže vam razumjeti cjelokupno raspoloženje svih kupaca. Rezultati naklonosti grupirani su u tri kategorije: 
  1.    Negativno (-5 > 2)
  2.    Neutralno (-1 > 1)
  3.    Pozitivno (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizualni prikaz cjelokupnog raspoloženja kupaca.":::

- **Raspodjela kupaca prema ocjeni** raspoloženja: Kupci su kategorizirani u negativne, neutralne i pozitivne skupine na temelju njihovih ocjena raspoloženja. Zadržite pokazivač miša iznad traka u histogramu da biste vidjeli broj kupaca i prosječnu ocjenu naklonosti u svakoj grupi. Ti vam podaci mogu pomoći u [stvaranju segmenata kupaca](segments.md) na temelju njihovih rezultata naklonosti.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="trakasti grafikon prikazuje raspoloženje kupaca u tri grupe naklonosti.":::

- **Prosječna ocjena naklonosti tijekom vremena**: raspoloženje kupaca može se mijenjati tijekom vremena. Pružamo trendove u raspoloženju vaših kupaca za vremenski raspon vaših podataka. Ovaj vam prikaz može pomoći u procjeni učinka sezonskih promocija, lansiranja proizvoda ili drugih vremenski ograničenih intervencija na raspoloženje kupaca. Pogledajte grafikon odabirom godine interesa s padajućeg izbornika. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="grafikon povijesti s rezultatom osjećaja tijekom vremena predstavljenim kao linija.":::
 
- **Naklonost u svim poslovnim aspektima**: ova tablica navodi prosječno raspoloženje u svim poslovnim aspektima. Može vam pomoći da procijenite koji aspekti vašeg poslovanja već zadovoljavaju kupce ili aspekte koji zahtijevaju više pozornosti. Zapisi povratnih informacija koji se ne usklađuju ni s jednim podržanim poslovnim aspektom kategorizirani su u **Ostalo**. Tablica je sortirana abecednim redom prema zadanim postavkama. Sortiranje možete izmijeniti odabirom zaglavlja tablice.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Popis poslovnih aspekata s pridruženim vrijednost naklonosti i brojem kupaca koji ga spominju.":::
 
  Odaberite naziv poslovnog aspekta da biste vidjeli dodatne informacije o tome kako model identificira poslovni aspekt. U ovom oknu postoje dva dijela: 

  - **Utjecajne riječi**: prikazuje glavne riječi koje su utjecale na identifikaciju poslovnog aspekta modela umjetne inteligencije u povratnim informacijama kupaca. 
    **Prikaži uvredljive riječi**: Omogućuje vam uključivanje uvredljivih riječi na popis iz izvornih podataka o povratnim informacijama kupaca. Prema zadanim postavkama, isključen je.  Uvredljivo maskiranje riječi pokreće model umjetne inteligencije i možda neće otkriti sve uvredljive riječi. Nastavljamo s iteriranjem i obukom klasifikatora za optimalne performanse. Ako otkrijete uvredljivu riječ koja nije filtrirana kako se očekivalo, javite nam. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Popis utjecajnih riječi s preklopom za prikaz ili skrivanje uvredljivih riječi.":::
 
  - **Uzorci** povratnih informacija: prikazuje stvarne zapise povratnih informacija u vašim podacima. Riječi su označene bojama prema njihovom utjecaju na identifikaciju poslovnog aspekta. 


### <a name="influential-words-analysis-tab"></a>Kartica Analiza utjecajnih riječi

Postoje tri odjeljka dodatnih informacija koji objašnjavaju kako funkcionira model naklonosti.
  
1. **Glavne riječi koje doprinose pozitivnom raspoloženju**: prikazuje glavne riječi koje su utjecale na identifikaciju pozitivnog raspoloženja modela umjetne inteligencije u povratnim informacijama kupaca.  
2. **Glavne riječi koje doprinose** negativnom raspoloženju: prikazuje glavne riječi koje su utjecale na identifikaciju negativnog raspoloženja modela umjetne inteligencije u povratnim informacijama kupaca.  
3. **Uzorci** povratnih informacija: Prikazuje stvarne zapise povratnih informacija, jedan s negativnim osjećajem i jedan s pozitivnim osjećajem. Riječi u zapisima povratnih informacija istaknute su prema njihovom doprinosu dodijeljenoj ocjeni naklonosti. Riječi koje doprinose pozitivnom rezultatu raspoloženja istaknute su zelenom bojom. Riječi koje doprinose negativnoj ocjeni označene su crvenom bojom.
   Odaberite **Pogledajte više** da biste učitali više uzoraka povratnih informacija koji pružaju više informacija i kontekst funkcioniranja modela naklonosti.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Primjeri analize raspoloženja o povratnim informacijama kupaca.":::
 
**Prikaži uvredljive riječi**: Omogućuje vam uključivanje uvredljivih riječi na popis iz izvornih podataka o povratnim informacijama kupaca. Prema zadanim postavkama, isključen je.  Uvredljivo maskiranje riječi pokreće model umjetne inteligencije i možda neće otkriti sve uvredljive riječi. Nastavljamo s iteriranjem i obukom klasifikatora za optimalne performanse. Ako otkrijete uvredljivu riječ koja nije filtrirana kako se očekivalo, javite nam. 

## <a name="act-on-analysis-results"></a>Zakon o rezultatima analize

Možete jednostavno početi stvarati nove segmente kupaca sa stranice s rezultatima analize naklonosti tako da odaberete **Stvori segmente** pri vrhu stranice rezultata modela.

:::image type="content" source="media/create-segment-model.png" alt-text="Naredbena traka s opcijama na predviđanje modelima.":::
 
## <a name="potential-bias"></a>Potencijalna pristranost

Kao i kod svake značajke koja koristi prediktivnu umjetnu inteligenciju, trebali biste biti svjesni potencijalne pristranosti u podacima koje koristite za predviđanje raspoloženja kupaca. Na primjer, ako povratne informacije prikupljate samo digitalno, možete propustiti povratne informacije od kupaca koji prvenstveno osobno posluju s vama, što bi moglo utjecati na izlaz značajke.

Budući da ova značajka koristi automatizirana sredstva za procjenu podataka i predviđanje na temelju tih podataka, stoga ima mogućnost koristiti se kao metoda profiliranja, jer je taj pojam definiran Općom uredbom o zaštiti podataka ("GDPR"). Vaša upotreba ove značajke za obradu podataka može podlijegati GDPR-u ili drugim zakonima ili propisima. Odgovorni ste za osiguravanje da je vaša upotreba Dynamics 365 Customer Insights, uključujući analizu naklonosti, u skladu sa svim primjenjivim zakonima i propisima, uključujući zakone koji se odnose na privatnost, osobne podatke, biometrijske podatke, zaštitu podataka i povjerljivost komunikacija.

[!INCLUDE [footer-include](includes/footer-banner.md)]

