---
title: Uzorak vodiča za predviđanje cjeloživotne vrijednosti klijenta (CLV)
description: Koristite ovaj uzorak vodiča da biste isprobali model predviđanja cjeloživotne vrijednosti klijenta.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609629"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Uzorak vodiča za predviđanje cjeloživotne vrijednosti klijenta (CLV)

Ovaj vodič vodi vas kroz end-to-end primjer doživotne vrijednosti kupca (CLV) predviđanje u Customer Insights pomoću oglednih podataka. Preporučujemo da isprobate ovaj predviđanje [u novom okruženju](manage-environments.md).

## <a name="scenario"></a>Scenarij

Contoso je tvrtka koja proizvodi visokokvalitetne aparate za kavu i kavu. Proizvode prodaju putem svoje web stranice Contoso Coffee. Tvrtka želi razumjeti vrijednost (prihod) koju njihovi klijenti mogu stvoriti u sljedećih 12 mjeseci. Poznavanje očekivane vrijednosti njihovih klijenata u sljedećih 12 mjeseci pomoći će im da usmjere svoje marketinške napore na visokovrijedne klijente.

## <a name="prerequisites"></a>Preduvjeti

- Barem [Dozvole suradnika](permissions.md).

## <a name="task-1---ingest-data"></a>Zadatak 1 – Podaci za unos

Pregledajte članke [o gutanju](data-sources.md) podataka i [povezivanju s Power Query izvor podataka](connect-power-query.md). Sljedeće informacije pretpostavljaju da ste upoznati s gutanjem podataka općenito.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Unesite podatke o klijentima s platforme eCommerce

1. Stvorite Power Query izvor podataka pod nazivom **e-trgovina** i odaberite **poveznik Tekst/CSV**.

1. Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscontacts.

1. Tijekom uređivanja podataka odaberite **Pretvori**, a zatim **Koristi prvi redak kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **Datum rođenja**: Datum
   - **Datum izrade**: datum/vrijeme/vremenska zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rođenja u datum.":::

1. U polju Naziv **na** desnom oknu preimenujte izvor podataka u **e-trgovineKontakti**

1. **Spremi** izvor podataka.

### <a name="ingest-online-purchase-data"></a>Unesite podatke o internetskoj kupnji

1. Dodajte još jedan skup podataka na isti izvor podataka **E-trgovina**. Ponovno odaberite konektor **Tekst/CSV**.

1. Unesite URL za podatke za **Internetske kupnje** https://aka.ms/ciadclassonline.

1. Tijekom uređivanja podataka odaberite **Pretvori**, a zatim **Koristi prvi redak kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **PurchasedOn**: datum/vrijeme
   - **Ukupna cijena**: valuta

1. **U polju Naziv** u bočnom oknu preimenujte izvor podataka u **e-trgovinePurchases**.

1. **Spremi** izvor podataka.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Unesite podatke o klijentima iz sheme vjernosti

1. Stvorite izvor podataka pod nazivom **LoyaltyScheme** i odaberite **poveznik Tekst/CSV**.

1. Unesite URL za klijente vjernosti https://aka.ms/ciadclasscustomerloyalty.

1. Tijekom uređivanja podataka odaberite **Pretvori**, a zatim **Koristi prvi redak kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **Datum rođenja**: Datum
   - **Nagradni bodovi**: cijeli broj
   - **Datum stvaranja**: datum/vrijeme

1. U polju Naziv **na** desnom oknu preimenujte izvor podataka u **loyCustomers**.

1. **Spremi** izvor podataka.

### <a name="ingest-customer-data-from-website-reviews"></a>Unesite podatke o kupcima iz recenzija web-stranice

1. Stvorite izvor podataka pod nazivom **Web-mjesto** i odaberite **poveznik Tekst/CSV**.

1. Unesite URL za recenzije web- mjesta https://aka.ms/CI-ILT/WebReviews.

1. Tijekom uređivanja podataka odaberite **Pretvori**, a zatim **Koristi prvi redak kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **ReviewRating**: decimalni broj
   - **Datum pregleda**: datum

1. U polju Naziv **na** desnom oknu preimenujte izvor podataka u **Recenzije**.

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

1. Dodajte drugu aktivnost i mapirajte njezine nazive polja u odgovarajuća polja:
   - **Entitet** aktivnosti: Recenzije:Web-mjesto
   - **Primarni ključ**: ReviewId
   - **Vremenska oznaka**: Datumi pregleda
   - **Aktivnost** događaja: ActivityTypeDisplay
   - **Dodatni detalji**: ReviewRating
   - **Vrsta** aktivnosti: pregled

1. Pokrenite aktivnost.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Zadatak 4 - Konfiguracija predviđanja cjeloživotne vrijednosti klijenta

Uz uspostavljene jedinstvene profile kupaca i stvorenu aktivnost, pokrenite predviđanje vrijednosti životnog vijeka klijenta (CLV). Detaljne korake potražite u odjeljku [Životni vijek kupca predviđanje](predict-customer-lifetime-value.md).

1. Idite na **Obavještajna** > **predviđanja**.

1. Na kartici **Stvaranje** odaberite **Koristi model** na pločici Vrijednost životnog vijeka **kupca**.

1. Odaberite **Početak rada**.

1. Dajte modelu naziv **CLV predviđanje e-trgovine OOB-a**, a izlaznom entitetu **OOBeCommerceCLVPrediction**.

1. Definiranje preferenci modela:
   - **predviđanje vremensko razdoblje**: **12 mjeseci ili 1 godina** za definiranje koliko daleko u budućnost predvidjeti CLV.
   - **Aktivni kupci**: **Neka model izračuna interval** kupnje koji je vremenski okvir u kojem je kupac morao imati barem jednu transakciju da bi se smatrao aktivnom.
   - **Kupac** visoke vrijednosti: ručno definirajte kupce visoke vrijednosti kao **prvih 30% aktivnih kupaca**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Korak preferencija u vođenom iskustvu za CLV model.":::

1. Odaberite **Dalje**.

1. U koraku **Potrebni podaci** odaberite **Dodaj podatke** za pružanje podataka o povijesti transakcija.

    :::image type="content" source="media/clv-model-required.png" alt-text="Dodajte potreban korak podataka u vođeno iskustvo za CLV model.":::

1. Odaberite **SalesOrderLine** i entitet eCommercePurchases, a zatim **Dalje**. Potrebni podaci automatski se popunjavaju iz aktivnosti. Odaberite **Spremi**, a zatim **Dalje**.

1. Korak **Dodatni podaci (neobavezno)** omogućuje vam dodavanje više podataka o aktivnostima kupaca kako biste dobili više uvida u interakcije s kupcima. U ovom primjeru odaberite **Dodaj podatke** i dodajte aktivnost web-pregleda.

1. Odaberite **Dalje**.

1. U koraku **Ažuriranja** podataka odaberite **Mjesečno** za raspored modela.

1. Odaberite **Dalje**.

1. Nakon pregleda svih detalja odaberite **Spremi i pokreni**.

## <a name="task-5---review-model-results-and-explanations"></a>Zadatak 5 – Pregled rezultata modela i objašnjenja

Neka model dovrši obuku i bodovanje podataka. Pregledajte rezultate i objašnjenja [modela](predict-customer-lifetime-value.md#view-prediction-results) CLV.

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Zadatak 6 - Stvaranje segmenta visokovrijednih klijenata

Pokretanje modela stvara novi entitet koji je naveden u odjeljku **Podaci** > **Entiteti**. Novi segment klijenta možete stvoriti na temelju entiteta koji je stvorio model.

1. Na stranici s rezultatima odaberite **Stvori segment**.

1. Stvorite pravilo pomoću entiteta **OOBeCommerceCLVPrediction** i definirajte segment:
   - **Polje**: CLVScore
   - **Operator**: veći od
   - **Vrijednost**: 1500

1. Odaberite **Spremi** i **Pokreni** segment.

Sada imate segment koji identificira klijente za koje se predviđa da će u sljedećih 12 mjeseci donijeti više od $1500 prihoda. Ovaj se segment dinamički ažurira ako se unese više podataka. Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).

> [!TIP]
> Segment za model predviđanje možete stvoriti i na **stranici Segmenti** tako da odaberete **Novo** i odaberete **Stvori iz** > **inteligencije**. Dodatne informacije potražite u članku [Stvaranje novog segmenta s brzim segmentima](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
