---
title: Izvoz segmenata u Google Ads (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b7f08936d7d90322cb4e62396a2961fe06273b76
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082991"
---
# <a name="export-segments-to-google-ads-preview"></a>Izvoz segmenata u Google Ads (pretpregled)

Izvezite segmente objedinjenih korisničkih profila na popis publike servisa Google Ads i upotrijebite ih za oglašavanje na servisima Google Search, Gmail, YouTube i Google Display Network. 


## <a name="prerequisites-for-connection"></a>Preduvjeti za vezu

-   Imate [račun za Google Ads](https://ads.google.com/) i odgovarajuće vjerodajnice administratora.
-   Ispunjavate zahtjeve [Pravila podudaranja klijenata](https://support.google.com/adspolicy/answer/6299717).
-   Ispunjavate zahtjeve [veličina popisa ponovno zainteresiranih](https://support.google.com/google-ads/answer/7558048).
-   Imate [konfigurirane segmente](segments.md).
-   Jedinstveni profili kupaca u izvezenim segmentima sadrže polja koja predstavljaju adresu e-pošte, telefon, ID mobilnog oglašivača, korisnički ID treće strane ili adresu.

## <a name="known-limitations"></a>Poznata ograničenja

- Izvoz u Google Ads ograničen je na segmente.
- Izvoz segmenata s ukupno 1 milijun profila klijenata može potrajati i do 30 minuta zbog ograničenja na strani davatelja usluga. 
- Podudaranje u usluzi Google Ads može potrajati do 48 sati.

## <a name="set-up-connection-to-google-ads"></a>Postavljanje veze s Google Ads

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **Google Ads** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj **[ID klijenta za Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite mogućnost **Provjera autentičnosti pomoću usluge Google Ads** i unesite svoje vjerodajnice za Google Ads.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu. 

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Google Ads. Ako ne vidite naziv ovog odjeljka, tada vam nisu dostupne veze ove vrste.

1. Ako želite izraditi novi publika, polje Google publika ID ostavite prazno. Automatski ćemo izraditi novu publika na vašem Google Ads računu i upotrijebiti naziv izvezenog segmenta. Ako želite ažurirati postojeći Google Ads publika, unesite Svoj [Google Ads publika ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. **U odjeljku Podudaranje** podataka odaberite jedno ili više podatkovnih polja za izvoz i odaberite polje koje predstavlja odgovarajuća podatkovna polja u odjeljku Customer Insights.

1. Odaberite segmente koje želite izvesti. 

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). 

Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Google Ads, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Google Ads ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE [footer-include](includes/footer-banner.md)]
