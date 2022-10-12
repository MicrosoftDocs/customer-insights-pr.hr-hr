---
title: Uzorak vodiča za predviđanje preporuka proizvoda
description: Koristite ovaj uzorak vodiča da biste isprobali gotove model predviđanja preporuka proizvoda.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610135"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Uzorak vodiča za predviđanje preporuka proizvoda

Ovaj vodič vodi vas kroz cjeloviti primjer preporuke proizvoda predviđanje upotrebom uzoraka podataka. Preporučujemo da isprobate ovaj predviđanje [u novom okruženju](manage-environments.md).

## <a name="scenario"></a>Scenarij

Contoso je tvrtka koja proizvodi visokokvalitetne aparate za kavu i kavu. Proizvode prodaju putem svoje web stranice Contoso Coffee. Cilj im je razumjeti koje proizvode trebaju preporučiti svojim redovnim klijentima. Saznanje o tome što kupci češće **kupuju** može im pomoći uštedjeti marketinške napore usredotočujući se na određene stavke.

## <a name="prerequisites"></a>Preduvjeti

- Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.

## <a name="task-1---ingest-data"></a>Zadatak 1 – Podaci za unos

Pregledajte članke [o gutanju](data-sources.md) podataka i [povezivanju s Power Query izvor podataka](connect-power-query.md). Sljedeće informacije pretpostavljaju da ste upoznati s gutanjem podataka općenito.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Unesite podatke o klijentima s platforme eCommerce

1. Stvorite Power Query izvor podataka pod nazivom **e-trgovina** i odaberite **poveznik Tekst/CSV**.

1. Unesite URL kontakata e-trgovine:https://aka.ms/ciadclasscontacts.

1. Tijekom uređivanja podataka odaberite **Pretvori**, a zatim **Koristi prvi redak kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **Datum rođenja**: Datum
   - **Datum izrade**: datum/vrijeme/vremenska zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rođenja u datum.":::

1. **U polju Naziv** na desnom oknu preimenujte izvor podataka u **e-TrgovineKontakti.**

1. **Spremi** izvor podataka.

### <a name="ingest-online-purchase-data"></a>Unesite podatke o internetskoj kupnji

1. Dodajte još jedan skup podataka na isti izvor podataka **E-trgovina**. Ponovno odaberite konektor **Tekst/CSV**.

1. Unesite URL za podatke o https://aka.ms/ciadclassonline online kupnji.

1. Tijekom uređivanja podataka odaberite **Pretvori**, a zatim **Koristi prvi redak kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **PurchasedOn**: datum/vrijeme
   - **Ukupna cijena**: valuta

1. **U polju Naziv** u bočnom oknu preimenujte izvor podataka u **e-trgovinePurchases**.

1. **Spremi** izvor podataka.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Unesite podatke o klijentima iz sheme vjernosti

1. Stvorite izvor podataka pod nazivom **LoyaltyScheme** i odaberite **poveznik Tekst/CSV**.

1. Unesite URL za vjerne klijente https://aka.ms/ciadclasscustomerloyalty.

1. Tijekom uređivanja podataka odaberite **Pretvori**, a zatim **Koristi prvi redak kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **Datum rođenja**: Datum
   - **Nagradni bodovi**: cijeli broj
   - **Datum stvaranja**: datum/vrijeme

1. U polju Naziv **na** desnom oknu preimenujte izvor podataka u **loyCustomers**.

1. **Spremi** izvor podataka.

## <a name="task-2---data-unification"></a>Zadatak 2 - Objedinjavanje podataka

Pregledajte članak [o objedinjavanju](data-unification.md) podataka. Sljedeće informacije pretpostavljaju da ste općenito upoznati s objedinjavanjem podataka.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Zadatak 3 - Stvaranje aktivnosti povijesti transakcija

Pregledajte članak [o aktivnostima](activities.md) kupaca. Sljedeće informacije pretpostavljaju da ste upoznati sa stvaranjem aktivnosti općenito.

1. Stvorite aktivnost pod nazivom **eCommercePurchases** pomoću *entiteta e-trgovinaPurchases:eCommerce* i njegovog primarnog ključa, **PurchaseId**.

1. Stvorite odnos između *e-trgovinePurchases:eCommerce* i *eCommerceContacts:eCommerce* s ContactID-om **kao** stranim ključem za povezivanje dvaju entiteta.

1. Odaberite **TotalPrice** za **EventActivity** i **PurchasedOn** za **TimeStamp**.

1. Odaberite **SalesOrderLine** za **vrstu** aktivnosti i semantički mapirajte podatke o aktivnostima.

1. Pokrenite aktivnost.

## <a name="task-4---configure-product-recommendation-prediction"></a>Zadatak 4 - Konfiguracija predviđanja preporuka proizvoda

Uz uspostavljene jedinstvene profile kupaca i stvorenu aktivnost, pokrenite preporuku proizvoda predviđanje.

1. Idite na **Obavještajna** > **predviđanja**.

1. Na kartici **Stvaranje** na pločici **Preporuke proizvoda (pretpregleda)** odaberite **Koristi model**.

1. Odaberite **Početak rada**.

1. Nazovite model **Previđanje modela preporuka proizvoda za OOB**, a izlazni entitet **Predviđanje modela preporuka proizvoda za OOB**.

1. Odaberite **Dalje**.

1. Definiranje preferenci modela:
   - **Broj proizvoda**: **5** da biste definirali koliko proizvoda želite preporučiti kupcima.
   - **Očekuje se** ponovljena kupnja: **Da** uključiti prethodno kupljene proizvode u preporuku.
   - **Osvrnite se na prozor:** **365 dana** da biste definirali koliko će se model osvrnuti prije nego što ponovno preporuči proizvod.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preference modela za model preporuke proizvoda.":::

1. Odaberite **Dalje**.

1. U koraku **Dodavanje povijesti kupnje** odaberite **Dodaj podatke**.

1. Odaberite **SalesOrderLine** i entitet eCommercePurchases, a zatim **Dalje**. Potrebni podaci automatski se popunjavaju iz aktivnosti. Odaberite **Spremi**, a zatim **Dalje**.

1. Preskočite korake Dodavanje informacija o proizvodu **i** filtara proizvoda jer nemamo podatke **o proizvodu.**

1. U koraku **Ažuriranja** podataka odaberite **Mjesečno** za raspored modela.

1. Odaberite **Dalje**.

1. Nakon pregleda svih detalja odaberite **Spremi i pokreni**.

## <a name="task-5---review-model-results-and-explanations"></a>Zadatak 5 – Pregled rezultata modela i objašnjenja

Neka model dovrši obuku i bodovanje podataka. Pregledajte objašnjenja [modela preporuka proizvoda](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Zadatak 6 - Stvaranje segmenta najčešće kupljenih proizvoda

Pokretanje modela stvara novi entitet koji je naveden u odjeljku **Podaci** > **Entiteti**. Možete stvoriti novi segment na temelju entiteta stvorenog prema modelu.

1. Na stranici s rezultatima odaberite **Stvori segment**.

1. Stvorite pravilo pomoću entiteta **OOBProductRecommendationModelPrediction** i definirajte segment:
   - **Polje**: IDproizvoda
   - **Vrijednost**: Odaberite prva tri ID-a proizvoda

1. Odaberite **Spremi** i **Pokreni** segment.

Sada imate segment koji se dinamički ažurira i identificira kupce koji bi mogli biti zainteresirani za kupnju pet najpreporučljivijih proizvoda. Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).

> [!TIP]
> Segment za model predviđanje možete stvoriti i na **stranici Segmenti** tako da odaberete **Novo** i odaberete **Stvori iz** > **inteligencije**. Dodatne informacije potražite u članku [Stvaranje novog segmenta s brzim segmentima](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
