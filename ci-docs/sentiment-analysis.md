---
title: Analiziraj naklonost povratnih informacija o klijentu (pretpregled)
description: Saznajte kako koristiti model analize naklonosti na povratnim informacijama klijenata u sustavu Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610451"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analiza naklonosti u povratnim informacijama korisnika (pretpregled)

Analiza naklonosti omogućuje vam sintezu raspoloženja kupaca i prepoznavanje poslovnih aspekata kao prilika za poboljšanje. Ova značajka Customer Insights pomaže vam razumjeti što dobro funkcionira i što trebate riješiti. Može vam pomoći u pokretanju poslovnih akcija koje omogućuju iskustva koja rezultiraju visokim zadovoljstvom kupaca i lojalnošću.

## <a name="overview"></a>Pretpregled

Značajka analize naklonosti generira dva izvedena uvida po ID-u kupca. Ocjena naklonosti (od -5 do 5) i popis primjenjivih poslovnih aspekata (područja poslovanja) koji vam zajedno pomažu da bolje razumijete povratne informacije kupaca.

Ova analiza pomaže vam:
- Pregled osjećaja kupaca prema robnoj marki ili organizaciji
- Identificirajte kupce s negativnim osjećajem kako biste usmjerili svoje kampanje i angažmane i optimizirali za veći povrat  
- Prepoznavanje poslovnih aspekata s problemima koje su istaknuli kupci  
- Segmentiranje korisnika na temelju njihovog osjećaja za pokretanje personaliziranih kampanja s ciljanim naporima prodaje, marketinga i podrške
- Optimizirajte poslovanje rješavanjem problematičnih područja ili mogućnosti koje su spomenuli kupci
- Prepoznati poslovne aspekte koji dobro posluju i nagraditi sretne kupce kroz programe vjernosti i promocije

Model pruža popis riječi koje su utjecale na odluku modela da dodijeli određenu ocjenu raspoloženja ili poslovni aspekt komentarima povratnih informacija.  

Koristimo dva **modela** obrade prirodnog jezika (NLP): Prvi dodjeljuje svakom povratnom komentaru ocjenu naklonosti. Drugi model povezuje svaku povratnu informaciju sa svim primjenjivim poslovnim aspektima. Modeli su obučeni za javne podatke iz izvora iz društvenih medija, maloprodaje, restorana, potrošačkih proizvoda i automobilske industrije.
  
Unaprijed definirani poslovni aspekti za model povezan s podacima povratnih informacija uključuju:
- Upravljanje računom
- Odjava i plaćanje
- Korisnička podrška
- Preuzimanje u trgovini
- Pakiranje, otpremanje i povrat
- Predbilježbe
- Cijena
- Zaštita privatnosti i sigurnost
- Promocije i nagrade
- Potvrda o plaćanju i jamstvo
- Povrat u svrhu zamjene i otkazivanje
- Točnost ispunjavanja
- Kvaliteta web-mjesta/aplikacije

> [!NOTE]
> Trenutno podržavamo samo analizu raspoloženja na povratnim informacijama engleskog kupca. U budućnosti će biti podržano više jezika. Ako se prenesu povratne informacije na drugim jezicima, model će i dalje vraćati rezultate. Međutim, ovi rezultati neće biti točni.

## <a name="prerequisites"></a>Preduvjeti

- Najmanje [suradnik dozvola](permissions.md)
- [Objedinjeni](data-unification.md) podaci o povratnim informacijama teksta. Toplo preporučujemo da podatkovne entitete povratnih informacija konfigurirate [kao entitete](map-entities.md#select-primary-key-and-semantic-type-for-attributes) aktivnosti semantičke vrste (vrsta povratnih informacija).
- Objedinjeni ID klijenta (UCID) iz objedinjavanja podataka radi podudaranja zapisa podataka s povratnim informacijama o tekstu s pojedinačnim klijentom.
- ID povratnih informacija
- Vremenska oznaka povratnih informacija
- Tekst povratnih informacija

Customer Insights može obraditi do 10 milijuna zapisa povratnih informacija za jedan model. Model može analizirati povratne komentare do 128 riječi. Ako je komentar povratnih informacija duži, analiza uzima u obzir samo prvih 128 riječi.

> [!NOTE]
> Može se konfigurirati samo jedan entitet povratnih informacija. Ako postoji više entiteta za povratne informacije, kombinirajte ih Power Query prije gutanja podataka.

## <a name="configure-a-sentiment-analysis"></a>Konfiguriranje analize naklonosti

1. Idite na **Obavještajna** > **predviđanja**.

1. Na kartici **Stvaranje** odaberite **Koristi model** na **pločici Analiza naklonosti kupca (pretpregled).**

1. Odaberite **Početak rada**.

1. **Navedite** analizu i navedite naziv **izlaznog entiteta** poslovnog aspekta i naziv izlaznog entiteta **ocjene naklonosti**.

1. Odaberite **Dalje**.

1. Odaberite **Dodaj podatke** za **povratne informacije** korisnika.

1. Odaberite vrstu semantičke aktivnosti **Povratne informacije** koje sadrže podatke o povratnim informacijama. Ako aktivnost nije postavljena, odaberite ovdje **i** stvorite je.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Korak konfiguracije za odabir aktivnosti povratnih informacija za analizu naklonosti.":::

1. Odaberite aktivnosti koje će se koristiti za ovu analizu naklonosti, a zatim **dalje**.

1. Mapirajte atribute u podacima na atribute modela. 

1. Odaberite **Spremi**.

1. Odaberite **Dalje**. Korak **Pregled i pokretanje** prikazuje sažetak konfiguracije i pruža priliku za promjene prije stvaranja analize.

1. Na **bilo kojem od koraka za pregled i unos promjena odaberite Uredi**.

1. Ako ste zadovoljni odabirom, odaberite **Spremi i pokreni** da biste započeli s pokretanjem modela. Odaberite **Gotovo**. Kartica **Moja predviđanja** prikazuje se tijekom stvaranja predviđanje. Proces može potrajati nekoliko sati ovisno o količini podataka korištenih za predviđanje.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Prikaz rezultata analize

1. Idite na **Obavještajna** > **predviđanja**.

1. Na kartici **Moja predviđanja** odaberite predviđanje koju želite pregledati.

Postoje dvije kartice rezultata.

### <a name="sumary-tab"></a>Kartica Sažetak

Unutar stranice s rezultatima nalaze se četiri primarna odjeljka podataka.

- **Prosječna ocjena** naklonosti: ocjene raspoloženja pomažu vam razumjeti cjelokupno raspoloženje svih kupaca.
  - **Negativno** (-5 > 2)
  - **Neutralno** (-1 > 1)
  - **Pozitivno** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizualni prikaz cjelokupnog raspoloženja kupaca.":::

- **Raspodjela kupaca prema ocjeni** raspoloženja: Kupci su kategorizirani u negativne, neutralne i pozitivne skupine na temelju njihovih ocjena raspoloženja. Zadržite pokazivač miša iznad traka u histogramu da biste vidjeli broj kupaca i prosječnu ocjenu naklonosti u svakoj grupi. Ti vam podaci mogu pomoći u [stvaranju segmenata kupaca](prediction-based-segment.md) na temelju njihovih rezultata naklonosti.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="trakasti grafikon prikazuje raspoloženje kupaca u tri grupe naklonosti.":::

- **Prosječna ocjena naklonosti tijekom vremena**: raspoloženje kupaca može se mijenjati tijekom vremena. Pružamo trendove u raspoloženju vaših kupaca za vremenski raspon vaših podataka. Ovaj prikaz pomaže vam procijeniti učinak sezonskih promocija, lansiranja proizvoda ili drugih vremenski ograničenih intervencija na raspoloženje kupaca. Pogledajte grafikon odabirom godine interesa s padajućeg izbornika.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="grafikon povijesti s rezultatom osjećaja tijekom vremena predstavljenim kao linija.":::

- **Raspoloženje u svim poslovnim aspektima**: Prosječno raspoloženje u svim poslovnim aspektima pomaže vam procijeniti koji aspekti vašeg poslovanja već zadovoljavaju kupce ili zahtijevaju više pozornosti. Zapisi povratnih informacija koji se ne usklađuju ni s jednim podržanim poslovnim aspektom kategorizirani su u **Ostalo**. Sortirajte podatke odabirom bilo kojeg stupca.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Popis poslovnih aspekata s pridruženim vrijednost naklonosti i brojem kupaca koji ga spominju.":::

  Odaberite naziv poslovnog aspekta da biste vidjeli kako model prepoznaje poslovni aspekt:

  - **Utjecajne riječi**: glavne riječi koje su utjecale na identifikaciju poslovnog aspekta modela umjetne inteligencije u povratnim informacijama kupaca.
    **Prikaži uvredljive riječi**: Omogućuje vam uključivanje uvredljivih riječi na popis iz izvornih podataka o povratnim informacijama kupaca. Prema zadanim postavkama, isključen je.  Uvredljivo maskiranje riječi pokreće model umjetne inteligencije i možda neće otkriti sve uvredljive riječi. Ako otkrijete uvredljivu riječ koja nije filtrirana kako se očekivalo, javite nam.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Popis utjecajnih riječi s preklopom za prikaz ili skrivanje uvredljivih riječi.":::

  - **Uzorci** povratnih informacija: stvarni zapisi povratnih informacija u vašim podacima. Riječi su označene bojama prema njihovom utjecaju na identifikaciju poslovnog aspekta.

### <a name="influential-words-analysis-tab"></a>Kartica Analiza utjecajnih riječi

Postoje tri odjeljka dodatnih informacija koji objašnjavaju kako funkcionira model naklonosti.
  
- **Glavne riječi koje doprinose pozitivnom raspoloženju: Glavne** riječi koje su utjecale na identifikaciju pozitivnog raspoloženja modela umjetne inteligencije u povratnim informacijama kupaca.  

- **Glavne riječi koje doprinose negativnom raspoloženju: Glavne riječi koje su utjecale** na identifikaciju negativnog raspoloženja modela umjetne inteligencije u povratnim informacijama kupaca.

- **Uzorci** povratnih informacija: Stvarni zapisi povratnih informacija, jedan s negativnim osjećajem i jedan s pozitivnim osjećajem. Riječi u zapisima povratnih informacija istaknute su prema njihovom doprinosu dodijeljenoj ocjeni naklonosti. Riječi koje doprinose pozitivnom rezultatu raspoloženja istaknute su zelenom bojom. Riječi koje doprinose negativnoj ocjeni označene su crvenom bojom.
   Odaberite **Pogledajte više** da biste učitali više uzoraka povratnih informacija.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Primjeri analize raspoloženja o povratnim informacijama kupaca.":::

**Prikaži uvredljive riječi**: Omogućuje vam uključivanje uvredljivih riječi na popis iz izvornih podataka o povratnim informacijama kupaca. Prema zadanim postavkama, isključen je.  Uvredljivo maskiranje riječi pokreće model umjetne inteligencije i možda neće otkriti sve uvredljive riječi. Ako otkrijete uvredljivu riječ koja nije filtrirana kako se očekivalo, javite nam.

## <a name="act-on-analysis-results"></a>Zakon o rezultatima analize

Da biste kreirali nove segmente kupaca iz rezultata analize naklonosti, odaberite **Kreiraj segmente** pri vrhu stranice rezultata modela.

## <a name="potential-bias"></a>Potencijalna pristranost

Kao i kod svake značajke koja koristi prediktivnu umjetnu inteligenciju, u podacima koje koristite za predviđanje raspoloženja kupaca mogla bi postojati potencijalna pristranost. Na primjer, ako povratne informacije prikupljate samo digitalno, možda ćete propustiti povratne informacije od kupaca koji prvenstveno osobno posluju s vama, što utječe na izlaz značajke.

Budući da ova značajka koristi automatizirana sredstva za procjenu podataka i predviđanje na temelju tih podataka, stoga ima mogućnost koristiti se kao metoda profiliranja, jer je taj pojam definiran Općom uredbom o zaštiti podataka ("GDPR"). Vaša upotreba ove značajke za obradu podataka može podlijegati GDPR-u ili drugim zakonima ili propisima. Odgovorni ste za osiguravanje da je vaša upotreba Dynamics 365 Customer Insights, uključujući analizu naklonosti, u skladu sa svim primjenjivim zakonima i propisima, uključujući zakone koji se odnose na privatnost, osobne podatke, biometrijske podatke, zaštitu podataka i povjerljivost komunikacija.

[!INCLUDE [footer-include](includes/footer-banner.md)]

