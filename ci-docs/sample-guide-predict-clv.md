---
title: Uzorak vodiča za predviđanje cjeloživotne vrijednosti klijenta (CLV)
description: Koristite ovaj uzorak vodiča da biste isprobali model predviđanja cjeloživotne vrijednosti klijenta.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 2013533ed225a396d21e51e63297d7608ce58ac6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051628"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Uzorak vodiča za predviđanje cjeloživotne vrijednosti klijenta (CLV)

Ovaj vodič će vam detaljno objasniti primjer predviđanja cjeloživotne vrijednosti klijenta (CLV) u rješenju Customer Insights koristeći uzorke podataka.

## <a name="scenario"></a>Scenarij

Contoso je tvrtka koja proizvodi visokokvalitetne aparate za kavu i kavu. Proizvode prodaju putem svoje web stranice Contoso Coffee. Tvrtka želi razumjeti vrijednost (prihod) koju njihovi klijenti mogu stvoriti u sljedećih 12 mjeseci. Poznavanje očekivane vrijednosti njihovih klijenata u sljedećih 12 mjeseci pomoći će im da usmjere svoje marketinške napore na visokovrijedne klijente.

## <a name="prerequisites"></a>Preduvjeti

- Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.
- Preporučujemo da primijenite sljedeće korake [u novom okruženju](manage-environments.md).

## <a name="task-1---ingest-data"></a>Zadatak 1 – Podaci za unos

Pregledajte članke [o gutanju](data-sources.md) podataka i [uvozu izvora podataka pomoću Power Query poveznika](connect-power-query.md). Sljedeće informacije pretpostavljaju da ste se upoznali s unosom podataka općenito.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Unesite podatke o klijentima s platforme eCommerce

1. Stvorite izvor podataka pod nazivom **E-trgovina**, odaberite mogućnost uvoza i odaberite poveznik **Tekst/CSV**.

1. Unesite URL za kontakte e-trgovine [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog retka kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **Datum rođenja**: Datum
   - **Datum izrade**: datum/vrijeme/vremenska zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rođenja u datum.":::

1. U polju „Naziv” u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Kontakti e-trgovine**

1. **Spremi** izvor podataka.

### <a name="ingest-online-purchase-data"></a>Unesite podatke o internetskoj kupnji

1. Dodajte još jedan skup podataka na isti izvor podataka **E-trgovina**. Ponovno odaberite konektor **Tekst/CSV**.

1. Unesite URL za podatke za **Internetske kupnje** https://aka.ms/ciadclassonline.

1. Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **PurchasedOn**: datum/vrijeme
   - **Ukupna cijena**: valuta

1. U polju **Naziv** u bočnom oknu preimenujte svoj izvor podataka iz **Upit** u **eCommercePurchases**.

1. **Spremi** izvor podataka.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Unesite podatke o klijentima iz sheme vjernosti

1. Stvorite izvor podataka pod nazivom **LoyaltyScheme**, odaberite opciju uvoza i odaberite poveznik **Tekst/CSV**.

1. Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscustomerloyalty.

1. Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **Datum rođenja**: Datum
   - **Nagradni bodovi**: cijeli broj
   - **Datum stvaranja**: datum/vrijeme

1. U polju **Naziv** u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Odanost klijenata**.

1. **Spremi** izvor podataka.

### <a name="ingest-customer-data-from-website-reviews"></a>Unesite podatke o kupcima iz recenzija web-stranice

1. Stvorite izvor podataka pod nazivom **Web-stranica**, odaberite opciju uvoza i odaberite poveznik **Tekst / CSV**.

1. Unesite URL za kontakte e-trgovine https://aka.ms/CI-ILT/WebReviews.

1. Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:

   - **ReviewRating**: decimalni broj
   - **Datum pregleda**: datum

1. U polju "Naziv", u desnom oknu, preimenujte svoj izvor podataka sa **Upit** na **Pregledi**.

1. **Spremi** izvor podataka.

## <a name="task-2---data-unification"></a>Zadatak 2 - Objedinjavanje podataka

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Zadatak 3 - Konfiguracija predviđanja cjeloživotne vrijednosti klijenta

S postavljenim objedinjenim profilima klijenata, sada možemo pokrenuti predviđanje cjeloživotne vrijednosti klijenta. Detaljne korake potražite u članku [Životni vijek kupca predviđanje](predict-customer-lifetime-value.md).

1. Idite u odjeljak **Inteligencija**  > **Predviđanja** i odaberite **Model cjeloživotne vrijednosti klijenta**.

1. Pregledajte informacije u bočnom oknu i odaberite **Početak**.

1. Dajte modelu naziv **CLV predviđanje e-trgovine OOB-a**, a izlaznom entitetu **OOBeCommerceCLVPrediction**.

1. Definirajte preferencije modela za CLV model:
   - **Vremensko razdoblje predviđanja**: **12 mjeseci ili 1 godina**. Ova postavka definira koliko daleko u budućnosti treba predvidjeti cjeloživotnu vrijednost klijenta.
   - **Aktivni klijenti**: Navedite što aktivni klijenti znače za vaše poslovanje. Postavite povijesni vremenski okvir u kojem je klijent morao imati barem jednu transakciju da bi se smatrao aktivnim. Model će predvidjeti CLV samo za aktivne klijente. Odaberite između dopuštanja modelu da izračuna vremensko razdoblje na temelju povijesnih podataka o transakciji ili navedite određeni vremenski okvir. U ovom uzorku vodiča mi **dopuštamo modelu da izračuna interval kupnje**, što je zadana mogućnost.
   - **Visokovrijedni klijenti**: Visokovrijedne klijente definirajte kao percentil klijenata koji najviše plaćaju. Model ovaj unos koristi za pružanje rezultata koji odgovaraju vašoj poslovnoj definiciji visokovrijednih klijenata. Možete odabrati da dopustite modelu da definira visokovrijedne klijente. On koristi heurističko pravilo koje izvodi percentil. Visokovrijedne klijente možete definirati i kao percentil klijenata koji će najviše plaćati u budućnosti. U ovom uzorku vodiča ćemo ručno definirati visokovrijedne klijente kao **30% najaktivnih klijenata koji najviše plaćaju** i odabrati **Sljedeće**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Korak preferencija u vođenom iskustvu za CLV model.":::

1. U koraku **Potrebni podaci** odaberite **Dodaj podatke** za pružanje podataka o povijesti transakcija.

1. Dodajte entitet **eCommercePurchases : eCommerce** i preslikajte atribute koji su potrebni modelu:
   - ID transakcije: eCommerce.eCommercePurchases.PurchaseId
   - Datum transakcije: eCommerce.eCommercePurchases.PurchasedOn
   - Iznos transakcije: eCommerce.eCommercePurchases.TotalPrice
   - ID proizvoda: eCommerce.eCommercePurchases.ProductId

1. Odaberite **Dalje**.

1. Postavite odnos između entiteta **eCommercePurchases : eCommerce** i **eCommerceContacts : eCommerce**.

1. Korak **Dodatni podaci (neobavezno)** vam omogućuje dodavanje više podataka o aktivnostima klijenata. Ovi podaci mogu vam pomoći da dobijete više uvida o interakciji klijenata s vašom tvrtkom, što može pridonijeti CLV-u. Dodavanje ključnih interakcija s klijentima, poput web-zapisnika, zapisnika službe za korisnike ili povijesti programa nagrađivanja, može poboljšati točnost predviđanja. Odaberite **Dodaj podatke** za uključivanje više podataka o aktivnostima klijenata.

1. Dodajte entitet aktivnosti klijenta i preslikajte nazive njegovih polja u odgovarajuća polja koja zahtijeva model:
   - Entitet aktivnosti klijenta: Reviews:Website
   - Primarni ključ: Website.Reviews.ReviewId
   - Vremenska oznaka: Website.Reviews.ReviewDate
   - Događaj (naziv aktivnosti): Website.Reviews.ActivityTypeDisplay
   - Pojedinosti (iznos ili vrijednost): Website.Reviews.ReviewRating

1. Odaberite **Sljedeće** i konfigurirajte aktivnost i odnos između podataka o transakciji i podataka o klijentu:  
   - Vrsta aktivnosti: odaberite postojeće
   - Oznaka aktivnosti: recenzija
   - Odgovarajuća oznaka: Website.Reviews.UserId
   - Entitet klijenta: eCommerceContacts:eCommerce
   - Odnos: WebsiteReviews

1. Odaberite **Sljedeće** za postavljanje rasporeda modela.

   Model treba redovito obučavati kako bi naučio nove obrasce kada se unose novi podaci. Za ovaj primjer odaberite **Mjesečno**.

1. Nakon pregleda svih pojedinosti odaberite **Spremi i pokreni**.

## <a name="task-4---review-model-results-and-explanations"></a>Zadatak 4 – Pregled rezultata modela i objašnjenja

Neka model dovrši obuku i bodovanje podataka. Zatim možete pregledati rezultate i objašnjenja CLV modela. Više informacija pogledajte u [Pregledaj stanje i rezultate predviđanje](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Zadatak 5 - Stvaranje segmenta visokovrijednih klijenata

Pokretanje modela stvara novi entitet koji je naveden u odjeljku **Podaci** > **Entiteti**. Novi segment klijenta možete stvoriti na temelju entiteta koji je stvorio model.

1. Idite na **Segmenti**. 

1. Odaberite **Novo** i odaberite **Stvori iz** > **Obavještavanje**.

   ![Stvaranje segmenta s izlazom modela.](media/segment-intelligence.png)

1. Odaberite entitet **OOBeCommerceCLVPrediction** i definirajte segment:
  - Polje: CLVScore
  - Operator: veće je od
  - Vrijednost: 1500

1. Odaberite **Recenzija** i **Spremite** segment.

Sada imate segment koji identificira klijente za koje se predviđa da će u sljedećih 12 mjeseci donijeti više od $1500 prihoda. Ovaj se segment dinamički ažurira ako se unese više podataka.

Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).
