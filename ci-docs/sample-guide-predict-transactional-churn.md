---
title: Vodič uzorka za predviđanje transakcijskog gubitka
description: Upotrijebite ovaj uzorak vodiča da biste isprobali gotov model predviđanja transakcijskog gubitka,
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741310"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Vodič uzorka za predviđanje transakcijskog gubitka

Ovaj će vam vodič objasniti kroz primjer predviđanje transakcijskog gubitka u usluzi Customer Insights s pomoću podataka uzorka navedenih u nastavku. Svi podaci koji se koriste u ovom vodiču nisu stvarni podaci o klijentu i dio su skupa podataka Contoso koji se nalazi u okruženju *Demo* unutar pretplate na Customer Insights.

## <a name="scenario"></a>Scenarij

Contoso je tvrtka koja proizvodi visokokvalitetnu kavu i aparate za kavu koje prodaju putem svoje web-stranice Contoso Coffee. Cilj im je znati koji će klijenti koji obično redovito kupuju njihove proizvode prestati biti aktivni kupci u sljedećih 60 dana. Znajući tko će od njihovih klijenata **vjerojatno prekinuti**, može im pomoći uštedjeti na marketinškim aktivnostima usredotočujući se na njihovo zadržavanje.

## <a name="prerequisites"></a>Preduvjeti

- Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.
- Preporučujemo da primijenite sljedeće korake [u novom okruženju](manage-environments.md).

## <a name="task-1---ingest-data"></a>Zadatak 1 – Podaci za unos

Pregledajte članke [o gutanju](data-sources.md) podataka i [uvozu izvora podataka pomoću Power Query konektora](connect-power-query.md) posebno. Sljedeće informacije pretpostavljaju da ste se upoznali s unosom podataka općenito. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Unesite podatke o klijentima s platforme eCommerce

1. Stvorite izvor podataka pod nazivom **E-trgovina**, odaberite opciju uvoza i odaberite poveznik **Tekst/CSV**.

1. Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscontacts.

1. Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:

   - **Datum rođenja**: Datum
   - **Datum izrade**: datum/vrijeme/vremenska zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite DoB u Datum.":::

1. U polju **Naziv** u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **eCommerceContacts**

1. Spremite izvor podataka.

### <a name="ingest-online-purchase-data"></a>Unesite podatke o internetskoj kupnji

1. Dodajte još jedan skup podataka na isti izvor podataka **E-trgovina**. Ponovno odaberite konektor **Tekst/CSV**.

1. Unesite URL za podatke za **Internetske kupnje** https://aka.ms/ciadclassonline.

1. Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:

   - **PurchasedOn**: datum/vrijeme
   - **Ukupna cijena**: valuta
   
1. U polju **Naziv** u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **eCommercePurchases**.

1. Spremite izvor podataka.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Unesite podatke o klijentima iz sheme vjernosti

1. Stvorite izvor podataka pod nazivom **LoyaltyScheme**, odaberite opciju uvoza i odaberite poveznik **Tekst/CSV**.

1. Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscustomerloyalty.

1. Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:

   - **Datum rođenja**: Datum
   - **Nagradni bodovi**: cijeli broj
   - **Datum stvaranja**: datum/vrijeme

1. U polju **Naziv** u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Odanost klijenata**.

1. Spremite izvor podataka.

## <a name="task-2---data-unification"></a>Zadatak 2 - Objedinjavanje podataka

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Zadatak 3 - Konfigurirajte predviđanje transakcijskog gubitka

S jedinstvenim profilima kupaca na mjestu, sada možemo pokrenuti transakcijski bućkanje predviđanje. Detaljne korake potražite u [članku Transaction churn predviđanje](predict-transactional-churn.md). 

1. Idite na **Obavještavanje** > **Otkrij** i odaberite **Model gubitka klijenta**.

1. Odaberite opciju **Transakcijski** i odaberite **Započni**.

1. Imenujte model **Predviđanje transakcijskog gubitka OOB e-trgovine** i izlazni entitet **Predviđanje gubitka OOB e-trgovine**.

1. Odredite dva uvjeta za model gubitka:

   * **Prozor predviđanja**: **najmanje 60** dana. Ova postavka definira za koje razdoblje u budućnosti želimo predvidjeti gubitak klijenta.

   * **Definicija gubitka**: **najmanje 60** dana. Trajanje bez kupnje nakon kojeg se kupac smatra odbačenim.

     :::image type="content" source="media/model-levers.PNG" alt-text="Odaberite poluge modela Prozor predviđanja i definicija gubitka.":::

1. Odaberite **Povijest kupnje (obavezno)** i odaberite **Dodaj podatke** za povijest kupnje.

1. Dodajte entitet **Kupovine e-trgovine: e-trgovina** i mapirajte polja iz e-trgovine u odgovarajuća polja koja model zahtijeva.

1. Pridružite entitet **Kupovine e-trgovine: e-trgovina** entitetu **Kontakti e-trgovine: e-trgovina**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pridružite entitetima e-trgovine.":::

1. Odaberite **Sljedeće** za postavljanje rasporeda modela.

   Model je potrebno redovito obučavati da bi naučio nove obrasce kada se unose novi podaci. Za ovaj primjer odaberite **Mjesečno**.

1. Nakon pregleda svih detalja odaberite **Spremi i pokreni**.

## <a name="task-4---review-model-results-and-explanations"></a>Zadatak 4 – Pregled rezultata modela i objašnjenja

Neka model dovrši obuku i bodovanje podataka. Sada možete pregledati objašnjenja modela bućkanja. Više informacija pogledajte u [Pregledaj stanje i rezultate predviđanje](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Zadatak 5 – Stvaranje segmenta klijenta s visokim rizikom gubitka

Pokretanje proizvodnog modela stvara novi entitet u kojem možete vidjeti **Podaci** > **Entiteti**.   

Možete stvoriti novi segment na temelju entiteta stvorenog prema modelu.

1.  Idite na **Segmenti**. Odaberite **Novo** i odaberite **Stvori iz** > **Obavještavanje**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Stvaranje segmenta s izlazom modela.":::

1. **Odaberite OOBeCommerceChurnPrediction** krajnja točka i definirajte segment: 
   - Polje: rezultat odbijanja
   - Operator: veće je od
   - Vrijednost: 0,6

Sada imate segment koji se dinamički ažurira i koji identificira kupce visokog rizika.

Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
