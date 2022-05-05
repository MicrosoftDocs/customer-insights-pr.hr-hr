---
title: Vodič uzorka za predviđanje transakcijskog gubitka
description: Upotrijebite ovaj uzorak vodiča da biste isprobali gotov model predviđanja transakcijskog gubitka,
ms.date: 11/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 05c221c634b8e0f582a6c6d3f4d90e971aa9707e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642837"
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

Nakon unosa podataka, sada započinjemo postupak **Karta, podudaranje, spajanje** za stvaranje objedinjenog profila kupca. Dodatne informacije potražite u odjeljku [Objedinjavanje podataka](data-unification.md).

### <a name="map"></a>Mapa

1. Nakon unosa podataka, mapirajte kontakte iz e-trgovine i podataka o vjernosti u uobičajene vrste podataka. Idite na **Podaci** > **Objedini** > **Mapiraj**.

1. Odaberite entitete koji predstavljaju profil klijenta – **Kontakti e-trgovine** i **Odani kupci**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="objedinite izvore podataka o e-trgovini i vjernosti.":::

1. Odaberite **ContactId** kao primarni ključ za **eCommerceContacts** i **LoyaltyID** kao primarni ključ za **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Objedinite LoyaltyId kao primarni ključ.":::

### <a name="match"></a>Usklađivanje

1. Idite na karticu **Usklađivanje** i odaberite **Naruči**.

1. Na padajućem popisu **Primarni** odaberite **eCommerceContacts: eCommerce** kao primarni izvor i uključite sve zapise.

1. Na padajućem popisu **Entitet 2** odaberite **loyCustomers: LoyaltyScheme** i uključite sve zapise.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="objedinite usklađivanje e-trgovine i odanost.":::

1. Odaberite **Stvaranje novog pravila**

1. Dodajte svoj prvi uvjet pomoću programa FullName.

   * Za eCommerceContacts odaberite **FullName** na padajućem popisu.
   * Za loyCustomers odaberite **FullName** na padajućem popisu.
   * Odaberite padajući izbornik **Normaliziraj** i odaberite **Vrsta (telefon, ime, adresa, ...)**.
   * Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.

1. Unesite naziv **Puno ime, e-pošta** za novo pravilo.

   * Odaberite drugi uvjet za adresu e-pošte tako da odaberete **Dodaj uvjet**
   * Za entitet eCommerceContacts odaberite **E-pošta** na padajućem popisu.
   * Za entitet loyCustomers odaberite **E-pošta** na padajućem popisu. 
   * Ostavite praznim polje Normaliziraj. 
   * Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="objedinite pravilo podudaranja za naziv i e-poštu.":::

7. Odaberite **Spremi** i **Pokreni**.

### <a name="merge"></a>Spoji

1. Idite na karticu **Spoji**.

1. U dijelu **ContactId** za entitet **loyCustomers** promijenite zaslonsko ime u **ContactIdLOYALTY** kako bi se razlikovao od ostalih unesenih identifikacijskih oznaka.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="preimenujte ID kontakta iz oznake ID za vjernost.":::

1. Odaberi **Spremi** i **Pokreni** da biste započeli postupak spajanja.



## <a name="task-3---configure-transaction-churn-prediction"></a>Zadatak 3 - Konfigurirajte predviđanje transakcijskog gubitka

S uspostavljenim objedinjenim profilima klijenata, sada možemo pokrenuti predviđanje gubitka pretplate. Detaljne korake potražite u članku Konverzija predviđanje [pretplate](predict-subscription-churn.md). 

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

Neka model dovrši obuku i bodovanje podataka. Sada možete pregledati objašnjenja modela gubitka pretplate. Više informacija pogledajte u [Pregledaj stanje i rezultate predviđanje](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Zadatak 5 – Stvaranje segmenta klijenta s visokim rizikom gubitka

Pokretanje proizvodnog modela stvara novi entitet u kojem možete vidjeti **Podaci** > **Entiteti**.   

Možete stvoriti novi segment na temelju entiteta stvorenog prema modelu.

1.  Idite na **Segmenti**. Odaberite **Novo** i odaberite **Stvori iz** > **Obavještavanje**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Stvaranje segmenta s izlazom modela.":::

1. Odaberite krajnju točku **Predviđanje gubitka pretplate OOB** i definirajte segment: 
   - Polje: rezultat odbijanja
   - Operator: veće je od
   - Vrijednost: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Postavite segment gubitka pretplate.":::

Sada imate segment koji se dinamički ažurira i koji identificira kupce s visokim rizikom za ovu pretplatu.

Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]