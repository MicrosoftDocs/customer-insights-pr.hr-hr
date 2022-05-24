---
title: Uzorak vodiča za predviđanje preporuka proizvoda
description: Koristite ovaj uzorak vodiča da biste isprobali gotove model predviđanja preporuka proizvoda.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762677"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Uzorak vodiča za predviđanje preporuka proizvoda

Preko primjera ćemo vas provesti kroz predviđanje preporuka proizvoda pomoću uzorka podataka navedenih u nastavku.

## <a name="scenario"></a>Scenarij

Contoso je tvrtka koja proizvodi visokokvalitetnu kavu i aparate za kavu koje prodaju putem svoje web-stranice Contoso Coffee. Cilj im je razumjeti koje proizvode trebaju preporučiti svojim redovnim klijentima. Znanje o tome što će klijenti **vjerojatnije kupiti** može im pomoći sačuvati marketinške napore usredotočujući se na određene stavke.

## <a name="prerequisites"></a>Preduvjeti

- Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.
- Preporučujemo da primijenite sljedeće korake [u novom okruženju](manage-environments.md).

## <a name="task-1---ingest-data"></a>Zadatak 1 – Podaci za unos

Pregledajte članke [o gutanju](data-sources.md) podataka i [uvozu izvora podataka pomoću Power Query konektora](connect-power-query.md) posebno. Sljedeće informacije pretpostavljaju da ste se upoznali s unosom podataka općenito.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Unesite podatke o klijentima s platforme eCommerce

1. Stvorite izvor podataka pod nazivom **E-trgovina**, odaberite opciju uvoza i odaberite poveznik **Tekst/CSV**.

1. Unesite URL kontakata e-trgovine: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **Datum rođenja**: Datum
   - **Datum izrade**: datum/vrijeme/vremenska zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rođenja u datum.":::

1. U polju „Naziv” u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Kontakti e-trgovine**

1. **Spremi** izvor podataka.

### <a name="ingest-online-purchase-data"></a>Unesite podatke o internetskoj kupnji

1. Dodajte još jedan skup podataka na isti izvor podataka **E-trgovina**. Ponovno odaberite konektor **Tekst/CSV**.

1. Unesite URL podataka o **online kupnji**[https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **PurchasedOn**: datum/vrijeme
   - **Ukupna cijena**: valuta

1. U polju **Naziv** u bočnom oknu preimenujte svoj izvor podataka iz **Upit** u **eCommercePurchases**.

1. **Spremi** izvor podataka.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Unesite podatke o klijentima iz sheme vjernosti

1. Stvorite izvor podataka pod nazivom **LoyaltyScheme**, odaberite opciju uvoza i odaberite poveznik **Tekst/CSV**.

1. Unesite URL za kontakte [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty) e-trgovine.

1. Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **Datum rođenja**: Datum
   - **Nagradni bodovi**: cijeli broj
   - **Datum stvaranja**: datum/vrijeme

1. U polju **Naziv** u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Odanost klijenata**.

1. **Spremi** izvor podataka.

## <a name="task-2---data-unification"></a>Zadatak 2 - Objedinjavanje podataka

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Zadatak 3 - Konfiguracija predviđanja preporuka proizvoda

S jedinstvenim profilima kupaca, sada možemo pokrenuti preporuku proizvoda predviđanje.

1. Idite na **Inteligencija** > **Predviđanje** i odaberite **Preporuka proizvoda**.

1. Odaberite **Početak rada**.

1. Nazovite model **Previđanje modela preporuka proizvoda za OOB**, a izlazni entitet **Predviđanje modela preporuka proizvoda za OOB**.

1. Definirajte tri uvjeta za model:

   - **Broj proizvoda**: Postavite ovu vrijednost na **5**. Ova postavka definira koliko proizvoda želite preporučiti svojim klijentima.

   - **Očekivane ponovne kupnje**: Odaberite **Da** kako biste naznačili da u preporuku želite uključiti proizvode koje su vaši klijenti ranije kupili.

   - **Pogled unatrag:** Odaberite barem **365 dana**. Ova postavka definira koliko će unatrag model pregledavati aktivnosti klijenata da bi to iskoristio kao ulazne vrijednosti za preporuke.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preference modela za model preporuke proizvoda.":::

1. U koraku **Dodavanje potrebnih podataka** odaberite **Dodaj podatke**.

1. **U oknu Dodavanje podataka** odaberite **SalesOrderLine** kao entitet povijesti nabave. U ovom trenutku vjerojatno još nije konfiguriran. Otvorite vezu u oknu da biste stvorili aktivnost sljedećim koracima:
   1. **Unesite naziv** aktivnosti i odaberite *entitet* e-trgovinaPurchases:e-trgovina **kao** aktivnost. Primarni **ključ** je *PurchaseId*.
   1. Definirajte i imenujte odnos s entitetom *e*-trgovineKontacts:e-trgovina i odaberite **ContactId** kao strani ključ.
   1. Za ujedinjenje aktivnosti postavite **aktivnost događaja kao** TotalPrice *i Timestamp na* PurchasedOn *·*. Možete navesti više polja kako je navedeno u [aktivnostima](activities.md) kupca.
   1. Za **vrstu aktivnosti odaberite** SalesOrderLine *·*. Preslikajte sljedeća polja aktivnosti:
      - ID retka naloga: ID nabave
      - ID naloga: ID nabave
      - Podaci o narudžbi: PurchasedOn
      - ID proizvoda: ID proizvoda
      - Iznos: TotalPrice
   1. Pregledajte i dovršite aktivnost prije nego što se vratite na konfiguraciju modela.

1. U koraku **Odabir aktivnosti** odaberite novostvorenu aktivnost u **odjeljku Aktivnosti**. Odaberite **Dalje** i mapiranje atributa već je ispunjeno. Odaberite **Spremi**.

1. U ovom oglednom vodiču preskačemo skup add informacija o proizvodu **i** filtara proizvoda jer nemamo podatke **o informacijama** o proizvodu.

1. U koraku **Ažuriranja** podataka postavite raspored modela.

   Model je potrebno redovito obučavati da bi naučio nove obrasce kada se unose novi podaci. Za ovaj primjer odaberite **Mjesečno**.

1. Nakon pregleda svih detalja odaberite **Spremi i pokreni**. Trebat će nekoliko minuta da se model pokrene prvi put.

## <a name="task-4---review-model-results-and-explanations"></a>Zadatak 4 – Pregled rezultata modela i objašnjenja

Neka model dovrši obuku i bodovanje podataka. Sada možete pregledati objašnjenja modela preporuka proizvoda. Više informacija pogledajte u [Pregledaj stanje i rezultate predviđanje](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Zadatak 5 - Stvaranje segmenta najčešće kupljenih proizvoda

Pokretanje proizvodnog modela stvara novi entitet u kojem možete vidjeti **Podaci** > **Entiteti**.

Možete stvoriti novi segment na temelju entiteta stvorenog prema modelu.

1. Idite na **Segmenti**. Odaberite **Novo**, a zatim **Stvori iz inteligencije**.

   ![Stvaranje segmenta s izlazom modela.](media/segment-intelligence.png)

1. Odaberite krajnju točku **OOBProductRecommendationModelPrediction** i definirajte segment:

   - Polje: ProductID
   - Vrijednost: Odaberite prva tri ID-ja proizvoda

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Stvorite segment iz rezultata modela.":::

Sada imate segment koji se dinamički ažurira i identificira kupce koji bi mogli biti zainteresirani za kupnju tri najpreporučljivija proizvoda.

Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
