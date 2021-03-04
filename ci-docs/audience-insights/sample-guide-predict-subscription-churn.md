---
title: Vodič uzorka za predviđanje gubitka pretplate
description: Upotrijebite ovaj uzorak vodiča da biste isprobali gotov model predviđanja gubitka pretplate.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269827"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>Vodič uzorka za predviđanje gubitka pretplate (pretpregled)

Objasnit ćemo vam kroz primjer predviđanje odbijanja pretplate pomoću podataka uzorka navedenih u nastavku. 

## <a name="scenario"></a>Scenarij

Contoso je tvrtka koja proizvodi visokokvalitetnu kavu i aparate za kavu koje prodaju putem svoje web-stranice Contoso Coffee. Nedavno su pokrenuli pretplatu za svoje kupce kako bi redovito dobivali kavu. Cilj im je razumjeti koji bi pretplaćeni kupci mogli otkazati pretplatu u sljedećih nekoliko mjeseci. Znajući tko će od njihovih klijenata **vjerojatno prekinuti**, može im pomoći uštedjeti na marketinškim aktivnostima usredotočujući se na njihovo zadržavanje.

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

1. U polju **Naziv** u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **eCommerceContacts**

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

### <a name="ingest-subscription-information"></a>Informacije o unosu pretplate

1. Stvorite izvor podataka pod nazivom **Povijest pretplate**, odaberite opciju uvoza i odaberite poveznik **Tekst / CSV**.

1. Unesite URL za kontakte e-trgovine https://aka.ms/ciadchurnsubscriptionhistory.

1. Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:

   - **ID pretplate**: cijeli broj
   - **Iznos pretplate**: valuta
   - **Datum završetka pretplate**: datum/vrijeme
   - **Datum početka pretplate**: datum/vrijeme
   - **Datum transakcije**: datum/vrijeme
   - **IsRecurring**: točno/netočno
   - **Is_auto_renew**: točno/netočno
   - **Ponavljajuća frekvencija u mjesecima**: cijeli broj

1. U polju **Naziv** u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Povijest pretplate**.

1. Spremite izvor podataka.

### <a name="ingest-customer-data-from-website-reviews"></a>Unesite podatke o kupcima iz recenzija web-stranice

1. Stvorite izvor podataka pod nazivom **Web-stranica**, odaberite opciju uvoza i odaberite poveznik **Tekst / CSV**.

1. Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasswebsite.

1. Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.

1. Ažurirajte vrstu podataka za stupce navedene u nastavku:

   - **Ocjena pregleda**: cijeli broj
   - **Datum pregleda**: datum

1. U polju „Naziv” u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Recenzije web-stranice**.

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

1. Na padajućem popisu **Primarni** odaberite **Kontakti e-trgovine: etrgovina** kao primarni izvor i uključite sve zapise.

1. Na padajućem popisu **Entitet 2** odaberite **Odani klijenti: Shema odanosti** i uključite sve zapise.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="objedinite usklađivanje e-trgovine i odanost.":::

1. Odaberite **Stvaranje novog pravila**

1. Dodajte svoj prvi uvjet pomoću programa FullName.

   * Za eCommerceContacts u padajućem izborniku odaberite **Puni naziv**.
   * Za loyCustomers u padajućem izborniku odaberite **Puni naziv**.
   * Odaberite padajući izbornik **Normaliziraj** i odaberite **Vrsta (telefon, ime, adresa, ...)**.
   * Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.

1. Unesite naziv **Puno ime, e-pošta** za novo pravilo.

   * Odaberite drugi uvjet za adresu e-pošte tako da odaberete **Dodaj uvjet**
   * Za entitet eCommerceContacts u padajućem izborniku odaberite **E-pošta**.
   * Za entitet loyCustomers u padajućem izborniku odaberite **E-pošta**. 
   * Ostavite praznim polje Normaliziraj. 
   * Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="objedinite pravilo podudaranja za naziv i e-poštu.":::

7. Odaberite **Spremi** i **Pokreni**.

### <a name="merge"></a>Spoji

1. Idite na karticu **Spoji**.

1. U dijelu **ContactId** za entitet **loyCustomers** promijenite zaslonsko ime u **ContactIdLOYALTY** kako bi se razlikovao od ostalih unesenih identifikacijskih oznaka.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="preimenujte ID kontakta iz oznake ID za vjernost.":::

1. Odaberi **Spremi** i **Pokreni** da biste započeli postupak spajanja.


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Zadatak 3 - Konfigurirajte predviđanje gubitka pretplate

S uspostavljenim objedinjenim profilima klijenata, sada možemo pokrenuti predviđanje gubitka pretplate. Detaljne korake pogledajte u članku [Predviđanje odbijanja pretplate (pregled)](predict-subscription-churn.md). 

1. Idite na **Obavještavanje** > **Otkrij** i odaberite **Model gubitka klijenta**.

1. Odaberite opciju **Pretplata** i odaberite **Započni**.

1. Imenujte model **Predviđanje gubitka pretplate OOB** i izlazni entitet **Predviđanje gubitka pretplate OOB**.

1. Odredite dva uvjeta za model gubitka:

   * **Dana od završetka pretplate**: **najmanje 60** dana. Ako klijent ne obnovi svoju pretplatu tijekom ovog razdoblja nakon njezinog isteka, smatra se izgubljenom. 

   * **Definicija gubitka**: **najmanje 93** dana. Trajanje koje model predviđa za odbijanje klijenta. Što dalje gledate u budućnost, bit će manja preciznost rezultata.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Odaberite poluge modela Prozor predviđanja i definicija gubitka.":::

1. Odaberite **Dodajte potrebne podatke** i odaberite **Dodajte podatke** za povijest pretplate.

1. Dodajte entitet **Pretplata: SubscriptionHistory** i mapirajte polja iz e-trgovine u odgovarajuća polja koja model zahtijeva.

1. Pridružite **Pretplata: SubscriptionHistory** s **eCommerceContacts: eCommerce**, imenujte odnos **Pretplata na e-trgovinu**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Pridružite entitetima e-trgovine.":::

1. U odjeljku Aktivnosti klijenta dodajte entitet **webReviews: Web-stranica** i mapirajte polja iz recenzije web-stranice u odgovarajuća polja koja zahtijeva model. 
   - Primarni ključ: Id pregleda
   - Vremenska oznaka: datum pregleda
   - Događaj: ocjena pregleda

1. Konfigurirajte aktivnost za recenzije web-stranice. Odaberite aktivnost **Pregled** i pridružite entitet **webReviews: web-stranica** entitetu **eCommerceContacts: e-trgovina**.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]