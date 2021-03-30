---
title: Uzorak vodiča za predviđanje preporuka proizvoda
description: Koristite ovaj uzorak vodiča da biste isprobali gotove model predviđanja preporuka proizvoda.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595264"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Uzorak vodiča za predviđanje preporuka proizvoda (pretpregled)

Preko primjera ćemo vas provesti kroz predviđanje preporuka proizvoda pomoću uzorka podataka navedenih u nastavku.

## <a name="scenario"></a>Scenarij

Contoso je tvrtka koja proizvodi visokokvalitetnu kavu i aparate za kavu koje prodaju putem svoje web-stranice Contoso Coffee. Cilj im je razumjeti koje proizvode trebaju preporučiti svojim redovnim klijentima. Znanje o tome što će klijenti **vjerojatnije kupiti** može im pomoći sačuvati marketinške napore usredotočujući se na određene stavke.

## <a name="prerequisites"></a>Preduvjeti

- Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.
- Preporučujemo da primijenite sljedeće korake [u novom okruženju](manage-environments.md).

## <a name="task-1---ingest-data"></a>Zadatak 1 – Podaci za unos

Pregledajte članke [o unosu podataka](data-sources.md) i posebice o [uvozu izvora podataka pomoću konektora Power Query](connect-power-query.md). Sljedeće informacije pretpostavljaju da ste se upoznali s unosom podataka općenito.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Unesite podatke o klijentima s platforme eCommerce

1. Stvorite izvor podataka pod nazivom **E-trgovina**, odaberite opciju uvoza i odaberite poveznik **Tekst/CSV**.

1. Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscontacts.

1. Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **Datum rođenja**: Datum
   - **Datum izrade**: datum/vrijeme/vremenska zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rođenja u datum.":::

5. U polju „Naziv” u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Kontakti e-trgovine**

6. **Spremi** izvor podataka.

### <a name="ingest-online-purchase-data"></a>Unesite podatke o internetskoj kupnji

1. Dodajte još jedan skup podataka na isti izvor podataka **E-trgovina**. Ponovno odaberite konektor **Tekst/CSV**.

1. Unesite URL za podatke za **Internetske kupnje** https://aka.ms/ciadclassonline.

1. Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:
   - **PurchasedOn**: datum/vrijeme
   - **Ukupna cijena**: valuta

1. U polju **Naziv** u bočnom oknu preimenujte svoj izvor podataka iz **Upit** u **eCommercePurchases**.

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

2. Odaberite entitete koji predstavljaju profil klijenta – **Kontakti e-trgovine** i **Odani kupci**.

   ![objedinite izvore podataka o e-trgovini i vjernosti.](media/unify-ecommerce-loyalty.png)

3. Odaberite **ContactId** kao primarni ključ za **eCommerceContacts** i **LoyaltyID** kao primarni ključ za **loyCustomers**.

   ![Objedinite LoyaltyId kao primarni ključ.](media/unify-loyaltyid.png)

### <a name="match"></a>Usklađivanje

1. Idite na karticu **Usklađivanje** i odaberite **Naruči**.

2. Na padajućem popisu **Primarni** odaberite **Kontakti e-trgovine: etrgovina** kao primarni izvor i uključite sve zapise.

3. Na padajućem popisu **Entitet 2** odaberite **Odani klijenti: Shema odanosti** i uključite sve zapise.

   ![objedinite usklađivanje e-trgovine i odanost.](media/unify-match-order.png)

4. Odaberite **Stvaranje novog pravila**

5. Dodajte svoj prvi uvjet pomoću programa FullName.

   - Za eCommerceContacts u padajućem izborniku odaberite **Puni naziv**.
   - Za loyCustomers u padajućem izborniku odaberite **Puni naziv**.
   - Odaberite padajući izbornik **Normaliziraj** i odaberite **Vrsta (telefon, ime, adresa, ...)**.
   - Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.

6. Unesite naziv **Puno ime, e-pošta** za novo pravilo.

   - Odaberite drugi uvjet za adresu e-pošte tako da odaberete **Dodaj uvjet**
   - Za entitet eCommerceContacts u padajućem izborniku odaberite **E-pošta**.
   - Za entitet loyCustomers u padajućem izborniku odaberite **E-pošta**.
   - Ostavite praznim polje Normaliziraj.
   - Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.

   ![objedinite pravilo podudaranja za naziv i e-poštu.](media/unify-match-rule.png)

7. Odaberite **Spremi** i **Pokreni**.

### <a name="merge"></a>Spoji

1. Idite na karticu **Spoji**.

1. U dijelu **ContactId** za entitet **loyCustomers** promijenite zaslonsko ime u **ContactIdLOYALTY** kako bi se razlikovao od ostalih unesenih identifikacijskih oznaka.

   ![preimenujte ID kontakta iz oznake ID za vjernost.](media/unify-merge-contactid.png)

1. Odaberi **Spremi** i **Pokreni** da biste započeli postupak spajanja.

## <a name="task-3---configure-product-recommendation-prediction"></a>Zadatak 3 - Konfiguracija predviđanja preporuka proizvoda

S uspostavljenim objedinjenim profilima klijenata, sada možemo pokrenuti predviđanje gubitka pretplate.

1. Idite na **Inteligencija** > **Predviđanje** i odaberite **Preporuka proizvoda**.

1. Odaberite **Početak rada**.

1. Nazovite model **Previđanje modela preporuka proizvoda za OOB**, a izlazni entitet **Predviđanje modela preporuka proizvoda za OOB**.

1. Definirajte tri uvjeta za model:

   - **Broj proizvoda**: Postavite ovu vrijednost na **5**. Ova postavka definira koliko proizvoda želite preporučiti svojim klijentima.

   - **Predložiti proizvode koje su klijenti nedavno kupili?**: Odaberite **Da** da biste naznačili da u preporuku želite uključiti proizvode koje su vaši klijenti ranije kupili.

   - **Pogled unatrag:** Odaberite barem **365 dana**. Ova postavka definira koliko će unatrag model pregledavati aktivnosti klijenata da bi to iskoristio kao ulazne vrijednosti za preporuke.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preference modela za model preporuke proizvoda.":::

1. Odaberite **Potrebni podaci** i odaberite **Dodaj podatke** za povijest kupnje.

1. Dodajte entitet **Kupovine e-trgovine: e-trgovina** i mapirajte polja iz e-trgovine u odgovarajuća polja koja model zahtijeva.

1. Pridružite entitet **Kupovine e-trgovine: e-trgovina** entitetu **Kontakti e-trgovine: e-trgovina**.

   ![Pridružite entitetima e-trgovine.](media/model-purchase-join.png)

1. Odaberite **Sljedeće** za postavljanje rasporeda modela.

   Model je potrebno redovito obučavati da bi naučio nove obrasce kada se unose novi podaci. Za ovaj primjer odaberite **Mjesečno**.

1. Nakon pregleda svih detalja odaberite **Spremi i pokreni**.


## <a name="task-4---review-model-results-and-explanations"></a>Zadatak 4 – Pregled rezultata modela i objašnjenja

Neka model dovrši obuku i bodovanje podataka. Sada možete pregledati objašnjenja modela preporuka proizvoda. Više informacija pogledajte u [Pregledaj stanje i rezultate predviđanje](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Zadatak 5 - Stvaranje segmenta najčešće kupljenih proizvoda

Pokretanje proizvodnog modela stvara novi entitet u kojem možete vidjeti **Podaci** > **Entiteti**.

Možete stvoriti novi segment na temelju entiteta stvorenog prema modelu.

1. Idite na **Segmenti**. Odaberite **Novo** i odaberite **Stvori iz** > **Obavještavanje**.

   ![Stvaranje segmenta s izlazom modela.](media/segment-intelligence.png)

1. Odaberite krajnju točku **OOBProductRecommendationModelPrediction** i definirajte segment:

   - Polje: ProductID
   - Operator: Vrijednost
   - Vrijednost: Odaberite prva tri ID-ja proizvoda

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Stvorite segment iz rezultata modela.":::

Sada imate segment koji se dinamički ažurira, a koji identificira klijente koji su spremniji kupiti tri najčešće preporučena proizvoda 

Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]