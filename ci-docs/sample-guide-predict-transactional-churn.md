---
title: Vodič uzorka za predviđanje transakcijskog gubitka
description: Upotrijebite ovaj uzorak vodiča da biste isprobali gotov model predviđanja transakcijskog gubitka,
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609675"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Vodič uzorka za predviđanje transakcijskog gubitka

Ovaj će vam vodič objasniti end-to-end primjer transakcijskog bućkanja predviđanje pomoću oglednih podataka. Preporučujemo da isprobate ovaj predviđanje [u novom okruženju](manage-environments.md).

## <a name="scenario"></a>Scenarij

Contoso je tvrtka koja proizvodi visokokvalitetne aparate za kavu i kavu. Proizvode prodaju putem svoje web stranice Contoso Coffee. Cilj im je znati koji će klijenti koji obično redovito kupuju njihove proizvode prestati biti aktivni kupci u sljedećih 60 dana. Znajući tko će od njihovih klijenata **vjerojatno prekinuti**, može im pomoći uštedjeti na marketinškim aktivnostima usredotočujući se na njihovo zadržavanje.

## <a name="prerequisites"></a>Preduvjeti

- Barem [Dozvole suradnika](permissions.md).

## <a name="task-1---ingest-data"></a>Zadatak 1 – Podaci za unos

Pregledajte članke [o gutanju](data-sources.md) podataka i [povezivanju s Power Query izvor podataka](connect-power-query.md). Sljedeće informacije pretpostavljaju da ste upoznati s gutanjem podataka općenito.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Unesite podatke o klijentima s platforme eCommerce

1. Stvorite izvor podataka pod nazivom **e-trgovina** i odaberite **poveznik Tekst/CSV**.

1. Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscontacts.

1. Tijekom uređivanja podataka odaberite **Pretvori**, a zatim **Koristi prvi redak kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:

   - **Datum rođenja**: Datum
   - **Datum izrade**: datum/vrijeme/vremenska zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite DoB u Datum.":::

1. U polju Naziv **na** desnom oknu preimenujte izvor podataka u **e-trgovineKontakti**

1. Spremite izvor podataka.

### <a name="ingest-online-purchase-data"></a>Unesite podatke o internetskoj kupnji

1. Dodajte još jedan skup podataka na isti izvor podataka **E-trgovina**. Ponovno odaberite konektor **Tekst/CSV**.

1. Unesite URL za podatke o https://aka.ms/ciadclassonline online kupnji.

1. Tijekom uređivanja podataka odaberite **Pretvori**, a zatim **Koristi prvi redak kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:

   - **PurchasedOn**: datum/vrijeme
   - **Ukupna cijena**: valuta

1. U polju Naziv **na** desnom oknu preimenujte izvor podataka u **eCommercePurchases**.

1. Spremite izvor podataka.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Unesite podatke o klijentima iz sheme vjernosti

1. Stvorite izvor podataka pod nazivom **LoyaltyScheme** i odaberite **poveznik Tekst/CSV**.

1. Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscustomerloyalty.

1. Tijekom uređivanja podataka odaberite **Pretvori**, a zatim **Koristi prvi redak kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:

   - **Datum rođenja**: Datum
   - **Nagradni bodovi**: cijeli broj
   - **Datum stvaranja**: datum/vrijeme

1. U polju Naziv **na** desnom oknu preimenujte izvor podataka u **loyCustomers**.

1. Spremite izvor podataka.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Zadatak 4 - Konfigurirajte predviđanje transakcijskog gubitka

S jedinstvenim profilima kupaca na mjestu i aktivnostima pokrenite transakcijski bućkanje predviđanje.

1. Idite na **Obavještajna** > **predviđanja**.

1. Na kartici **Stvaranje** odaberite **Koristi model** na modelu **kupca**.

1. Odaberite **Transakcijski** za vrstu bućkanja, a zatim **Početak rada**.

1. Imenujte model **Predviđanje transakcijskog gubitka OOB e-trgovine** i izlazni entitet **Predviđanje gubitka OOB e-trgovine**.

1. Odaberite **Dalje**.

1. Definiranje preferenci modela:

   - **predviđanje prozor**: **60** dana za definiranje koliko daleko u budućnost želimo predvidjeti bućkanje kupaca.

   - **Definicija** churna: **60** dana za označavanje trajanja bez kupnje nakon čega se kupac smatra bućkavim.

     :::image type="content" source="media/model-levers.PNG" alt-text="Odaberite preference modela predviđanje Prozor i Definicija churna.":::

1. Odaberite **Dalje**.

1. Odaberite **Povijest kupnje (obavezno)** i odaberite **Dodaj podatke** za povijest kupnje.

1. Odaberite **SalesOrderLine** i entitet eCommercePurchases, a zatim **Dalje**. Potrebni podaci automatski se popunjavaju iz aktivnosti. Odaberite **Spremi**, a zatim **Dalje**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pridružite entitetima e-trgovine.":::

1. Preskočite korak Dodatne **podatke (neobavezno).**

1. U koraku **Ažuriranja** podataka odaberite **Mjesečno** za raspored modela.

1. Nakon pregleda svih detalja odaberite **Spremi i pokreni**.

## <a name="task-5---review-model-results-and-explanations"></a>Zadatak 5 – Pregled rezultata modela i objašnjenja

Neka model dovrši obuku i bodovanje podataka. Pregledajte objašnjenja modela bućkanja. Dodatne informacije potražite u članku [Prikaz rezultata](predict-transactional-churn.md#view-prediction-results) predviđanje.

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Zadatak 6 – Stvaranje segmenta klijenta s visokim rizikom gubitka

Pokretanjem proizvodnog modela stvara se novi entitet koji je naveden u **entitetima** > **podataka**. Možete stvoriti novi segment na temelju entiteta stvorenog prema modelu.

1. Na stranici s rezultatima odaberite **Stvori segment**.

1. Stvorite pravilo pomoću entiteta **OOBeCommerceChurnPrediction** i definirajte segment:
   - **Polje**: ChurnScore
   - **Operator**: veći od
   - **Vrijednost**: 0,6

1. Odaberite **Spremi** i **Pokreni** segment.

Sada imate segment koji se dinamički ažurira i koji identificira kupce visokog rizika. Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).

> [!TIP]
> Segment za model predviđanje možete stvoriti i na **stranici Segmenti** tako da odaberete **Novo** i odaberete **Stvori iz** > **inteligencije**. Dodatne informacije potražite u članku [Stvaranje novog segmenta s brzim segmentima](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
