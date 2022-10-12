---
title: Vodič uzorka za predviđanje gubitka pretplate
description: Upotrijebite ovaj uzorak vodiča da biste isprobali gotov model predviđanja gubitka pretplate.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609997"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Vodič uzorka za predviđanje gubitka pretplate

Ovaj će vam vodič objasniti end-to-end primjer pretplate bućkanje predviđanje pomoću oglednih podataka. Preporučujemo da isprobate ovaj predviđanje [u novom okruženju](manage-environments.md).

## <a name="scenario"></a>Scenarij

Contoso je tvrtka koja proizvodi visokokvalitetne aparate za kavu i kavu. Proizvode prodaju putem svoje web stranice Contoso Coffee. Nedavno su pokrenuli pretplatu za svoje kupce kako bi redovito dobivali kavu. Njihov je cilj razumjeti koji bi pretplaćeni kupci mogli otkazati pretplatu u sljedećih nekoliko mjeseci. Znajući koji će od njihovih kupaca **vjerojatno bućkati** može im pomoći da uštede marketinške napore usredotočujući se na njihovo zadržavanje.

## <a name="prerequisites"></a>Preduvjeti

- Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.

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

1. Spremite izvor podataka.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Unesite podatke o klijentima iz sheme vjernosti

1. Stvorite izvor podataka pod nazivom **LoyaltyScheme** i odaberite **poveznik Tekst/CSV**.

1. Unesite URL za klijente vjernosti https://aka.ms/ciadclasscustomerloyalty.

1. Tijekom uređivanja podataka odaberite **Pretvori**, a zatim **Koristi prvi redak kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **Datum rođenja**: Datum
   - **Nagradni bodovi**: cijeli broj
   - **Datum stvaranja**: datum/vrijeme

1. U polju Naziv **na** desnom oknu preimenujte izvor podataka u **loyCustomers**.

1. Spremite izvor podataka.

### <a name="ingest-subscription-information"></a>Informacije o unosu pretplate

1. Stvorite izvor podataka pod nazivom **Pretplata** i odaberite **poveznik Tekst/CSV**.

1. Unesite URL za pretplate https://aka.ms/ciadchurnsubscriptionhistory.

1. Tijekom uređivanja podataka odaberite **Pretvori**, a zatim **Koristi prvi redak kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **ID pretplate**: cijeli broj
   - **Iznos pretplate**: valuta
   - **Datum završetka pretplate**: datum/vrijeme
   - **Datum početka pretplate**: datum/vrijeme
   - **Datum transakcije**: datum/vrijeme
   - **IsRecurring**: točno/netočno
   - **Is_auto_renew**: točno/netočno
   - **Ponavljajuća frekvencija u mjesecima**: cijeli broj

1. U polju Naziv **u** desnom oknu preimenujte izvor podataka u **SubscriptionHistory**.

1. Spremite izvor podataka.

### <a name="ingest-customer-data-from-website-reviews"></a>Unesite podatke o kupcima iz recenzija web-stranice

1. Stvorite izvor podataka pod nazivom **Web-mjesto** i odaberite **poveznik Tekst/CSV**.

1. Unesite URL za recenzije https://aka.ms/ciadclasswebsite web- mjesta.

1. Tijekom uređivanja podataka odaberite **Pretvori**, a zatim **Koristi prvi redak kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **Ocjena pregleda**: cijeli broj
   - **Datum pregleda**: datum

1. U polju Naziv **u** desnom oknu preimenujte izvor podataka u **prikaze** web-prikaza.

## <a name="task-2---data-unification"></a>Zadatak 2 - Objedinjavanje podataka

Pregledajte članak [o objedinjavanju](data-unification.md) podataka. Sljedeće informacije pretpostavljaju da ste općenito upoznati s objedinjavanjem podataka.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Zadatak 3 - Stvaranje aktivnosti povijesti transakcija

Pregledajte članak [o aktivnostima](activities.md) kupaca. Sljedeće informacije pretpostavljaju da ste upoznati sa stvaranjem aktivnosti općenito.

1. Stvorite aktivnost pod nazivom **Pretplata** s entitetom *Pretplata* i njegovim primarnim ključem, **CustomerId**.

1. Stvorite odnos između *SubscriptionHistory:Subscription* i *eCommerceContacts:eCommerce* s CustomerID-om **kao** stranim ključem za povezivanje dvaju entiteta.

1. Odaberite **SubscriptionType** za **EventActivity** i **SubscriptionEndDate** za **TimeStamp**.

1. Odaberite **Pretplata** **za vrstu** aktivnosti i semantički mapirajte podatke o aktivnostima.

1. Pokrenite aktivnost.

1. Dodajte drugu aktivnost i mapirajte njezine nazive polja u odgovarajuća polja:
   - Entitet aktivnosti klijenta: Reviews:Website
   - Primarni ključ: Website.Reviews.ReviewId
   - Vremenska oznaka: Website.Reviews.ReviewDate
   - Događaj (naziv aktivnosti): Website.Reviews.ActivityTypeDisplay
   - Pojedinosti (iznos ili vrijednost): Website.Reviews.ReviewRating

1. Pokrenite aktivnost.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Zadatak 4 - Konfigurirajte predviđanje gubitka pretplate

S jedinstvenim profilima kupaca na mjestu i stvorenim aktivnostima, pokrenite pretplatu predviđanje. Detaljne korake potražite u članku [Pretplata bućkajuća predviđanje](predict-subscription-churn.md).

1. Idite na **Obavještajna** > **predviđanja**.

1. Na kartici **Stvaranje** **odaberite Koristi model** na pločici Model **modela kupca**.

1. Odaberite **Pretplata** za vrstu bućkanja, a zatim **Početak rada**.

1. Imenujte model **Predviđanje gubitka pretplate OOB** i izlazni entitet **Predviđanje gubitka pretplate OOB**.

1. Definiranje preferenci modela:
   - **Dani od završetka** pretplate: **60** dana za označavanje da se korisnik smatra bućkanjem ako ne obnovi pretplatu u tom razdoblju nakon završetka pretplate.
   - **Dani za istraživanje budućnosti za predviđanje bućkanja**: **93** dana koliko je trajanje koje model predviđa koji bi kupci mogli bućkati. Što dalje gledate u budućnost, bit će manja preciznost rezultata.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Odaberite preference modela i definiciju bućkanja.":::

1. Odaberite **Dalje**.

1. U koraku Obavezni **podaci** odaberite **Dodaj podatke** da biste naveli povijest pretplata.

1. Odaberite **Pretplata** i entitet Pretplata, a zatim **Dalje**. Potrebni podaci automatski se popunjavaju iz aktivnosti. Odaberite **Spremi**.

1. U odjeljku Aktivnosti klijenta odaberite **Dodaj podatke**.

1. U ovom primjeru dodajte aktivnost web-pregleda.

1. Odaberite **Dalje**.

1. U koraku **Ažuriranja** podataka odaberite **Mjesečno** za raspored modela.

1. Nakon pregleda svih detalja odaberite **Spremi i pokreni**.

## <a name="task-5---review-model-results-and-explanations"></a>Zadatak 5 – Pregled rezultata modela i objašnjenja

Neka model dovrši obuku i bodovanje podataka. Pregledajte objašnjenja modela bućkanja pretplate. Dodatne informacije potražite u članku [Prikaz rezultata](predict-subscription-churn.md#view-prediction-results) predviđanje.

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Zadatak 6 – Stvaranje segmenta klijenta s visokim rizikom gubitka

Pokretanje modela stvara novi entitet koji je naveden u odjeljku **Podaci** > **Entiteti**. Možete stvoriti novi segment na temelju entiteta stvorenog prema modelu.

1. Na stranici s rezultatima odaberite **Stvori segment**.

1. Stvorite pravilo pomoću entiteta **OOBSubscriptionChurnPrediction** i definirajte segment:
   - **Polje**: ChurnScore
   - **Operator**: veći od
   - **Vrijednost**: 0,6

1. Odaberite **Spremi** i **Pokreni** segment.

Sada imate segment koji se dinamički ažurira i koji identificira kupce s visokim rizikom za ovu pretplatu. Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).

> [!TIP]
> Segment za model predviđanje možete stvoriti i na **stranici Segmenti** tako da odaberete **Novo** i odaberete **Stvori iz** > **inteligencije**. Dodatne informacije potražite u članku [Stvaranje novog segmenta s brzim segmentima](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
