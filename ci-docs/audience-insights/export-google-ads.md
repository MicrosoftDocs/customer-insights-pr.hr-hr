---
title: Izvoz podataka usluge Customer Insights u Google Ads
description: Saznajte kako konfigurirati vezu i izvesti u Google Ads.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ce9579f3d31207e666665237fd8935bb86889f8d
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617909"
---
# <a name="export-segments-to-google-ads-preview"></a>Izvoz segmenata u Google Ads (pretpregled)

Izvezite segmente objedinjenih korisničkih profila na popis publike servisa Google Ads i upotrijebite ih za oglašavanje na servisima Google Search, Gmail, YouTube i Google Display Network. 

> [!IMPORTANT]
> Trenutačno možete stvoriti novu vezu i izvoziti podatke u Google Ads ako već imate odobreni token za razvojne inženjere usluge Google Ads. Zbog promjena pravila uskoro ćemo ažurirati izvoz usluge Google Ads i pružiti opciju izvoza koja neće zahtijevati token razvojnog inženjera kako bi se osigurao kontinuitet vašeg iskustva i pojednostavio izvoz u Google Ads. Preporučujemo da ne postavljate više veza s uslugom Google Ads radi lakšeg prelaska na novu opciju izvoza.

## <a name="prerequisites-for-connection"></a>Preduvjeti za vezu

-   Imate [račun za Google Ads](https://ads.google.com/) i odgovarajuće vjerodajnice administratora.
-   Imate [odobreni token za Google Ads Developer](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   Ispunjavate zahtjeve [Pravila podudaranja klijenata](https://support.google.com/adspolicy/answer/6299717).
-   Ispunjavate zahtjeve [veličina popisa ponovno zainteresiranih](https://support.google.com/google-ads/answer/7558048).
-   Google Ads sadrži postojeće ciljne skupine i odgovarajuće ID-ove. Dodatne informacije potražite u [ciljnim skupinama usluge Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Imate [konfigurirane segmente](segments.md).
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polja koja predstavljaju adresu e-pošte, ime i prezime.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 1 milijun profila klijenata po izvozu u Google Ads.
- Izvoz u Google Ads ograničen je na segmente.
- Izvoz segmenata s ukupno 1 milijun profila klijenata može potrajati i do 5 minuta zbog ograničenja na strani davatelja usluga. 
- Podudaranje u usluzi Google Ads može potrajati do 48 sati.

## <a name="set-up-connection-to-google-ads"></a>Postavljanje veze s Google Ads

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **Google Ads** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj **[ID klijenta za Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Unesite svoj **[token razvojnog inženjera koji je odobren za Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite mogućnost **Provjera autentičnosti pomoću usluge Google Ads** i unesite svoje vjerodajnice za Google Ads.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu. 

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Google Ads. Ako ne vidite naziv ovog odjeljka, tada vam nisu dostupne veze ove vrste.

1. Unesite svoj **[ID ciljne skupine za Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i odaberite **Povezivanje** za inicijalizaciju veze s uslugom Google Ads.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta.

1. Odaberite segmente koje želite izvesti. U Google Ads možete ukupno izvesti do 1 milijun profila klijenata.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). 

Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Google Ads, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Google Ads ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
