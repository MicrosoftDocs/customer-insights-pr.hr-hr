---
title: Izvoz podataka iz Customer Insights u LinkedIn Ads
description: Saznajte kako konfigurirati vezu i izvesti u LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7a6bb466652b8703a4784329a5e675965f557e82
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231094"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Izvoz segmenata u LinkedIn Ads (pretpregled)

Izvezite segmente objedinjenih profila klijenata u LinkedIn Ads kako biste stvorili podudarne ciljne skupine. Upotrijebite podudarne ciljne publike za ciljanje tvrtki i ciljanje kontakata.

## <a name="prerequisites"></a>Preduvjeti

-   Imate [Račun za LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) i odgovarajuće vjerodajnice administratora.
-   Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.
-   Profili klijenata u izvezenim segmentima sadrže polje s adresom e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Vaš segment u customer insights mora sadržavati najmanje 300 jedinstvenih profila. 
- Možete izvesti do 100 tisuća profila klijenata po izvozu u LinkedIn Ads.
- Izvoz u LinkedIn Ads ograničen je na segmente.
- Izvoz do 100 tisuća profila klijenata u LinkedIn Ads može potrajati do 10 minuta. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Postavljanje veze s uslugom LinkedIn Ads

1. U uvidima u ciljnu skupinu idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **LinkedIn Ads** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite svoj [ID računa za LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** za inicijalizaciju veze s Campaign Monitor.

1. Odaberite **Provjeri autentičnost uz LinkedIn** i pružite svoje administratorske vjerodajnice za LinkedIn Campaign Manager.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka LinkedIn Ads. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Odaberite želite li izvesti podatke radi [ciljanja kontakata](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ili [ciljanja tvrtki](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) u usluzi LinkedIn. 

1. U odjeljku **Podudaranje podataka** za ciljanje kontakata odaberite barem jedno polje koje predstavlja adresu e-pošte klijenta, ID za Apple Ad, ID za Google Ad, ID korisnika tražilice Google ili ime i prezime. Ako odaberete ciljanje tvrtke, odaberite barem jedno polje koje predstavlja naziv tvrtke, domenu e-pošte, URL stranice LinkedIn, simbol Stock ili web-mjesto. Moguće je odabrati dodatna polja za dodatno definiranje izvoza. 

1. Odaberite segmente koje želite izvesti. Podudarne ciljne skupine u alatu LinkedIn Campaign Manager automatski će se stvoriti s nazivom segmenata koje ste odabrali za izvoz. Svaki će segment rezultirati zasebnom podudarnom ciljnom skupinom. 

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u LinkedIn Ads, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da LinkedIn Ads ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
