---
title: Izvoz podataka iz Customer Insights u LinkedIn Ads
description: Saznajte kako konfigurirati vezu i izvesti u LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 867a6541734746f75a35faaa8d3861e0479d6114
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866879"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Izvoz segmenata u LinkedIn Ads (pretpregled)

Izvezite segmente objedinjenih profila klijenata u LinkedIn Ads kako biste stvorili podudarne ciljne skupine. Upotrijebite podudarne ciljne publike za ciljanje tvrtki i ciljanje kontakata.

## <a name="prerequisites"></a>Preduvjeti

-   Imate [LinkedIn Campaign Manager račun i](https://business.linkedin.com/marketing-solutions/ads) odgovarajuće administratorske vjerodajnice.
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

1. Navedite [svoj LinkedIn Campaign Manager ID računa](https://www.linkedin.com/help/lms/answer/a424270).

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** za inicijalizaciju veze s Campaign Monitor.

1. Odaberite **Provjeri autentičnost pomoću servisa LinkedIn i** unesite administratorske vjerodajnice za LinkedIn Campaign Manager.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka LinkedIn Ads. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Odaberite želite li izvesti podatke radi [ciljanja kontakata](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ili [ciljanja tvrtki](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) u usluzi LinkedIn. 

1. U odjeljku **Podudaranje podataka** za ciljanje kontakata odaberite barem jedno polje koje predstavlja adresu e-pošte klijenta, ID za Apple Ad, ID za Google Ad, ID korisnika tražilice Google ili ime i prezime. Ako odaberete ciljanje tvrtke, odaberite barem jedno polje koje predstavlja naziv tvrtke, domenu e-pošte, URL stranice LinkedIn, simbol Stock ili web-mjesto. Moguće je odabrati dodatna polja za dodatno definiranje izvoza. 

1. Odaberite segmente koje želite izvesti. Usklađena publika u LinkedIn Campaign Manager automatski će se stvoriti s nazivom segmenata koje ste odabrali za izvoz. Svaki će segment rezultirati zasebnom podudarnom ciljnom skupinom. 

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada Dynamics 365 Customer Insights omogućite prijenos podataka u LinkedIn Oglase, dopuštate prijenos podataka izvan granice usklađenosti radi Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da LinkedIn Ads ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights može ukloniti ovo odredište za izvoz u bilo kojem trenutku kako bi zaustavio korištenje ove funkcije.
