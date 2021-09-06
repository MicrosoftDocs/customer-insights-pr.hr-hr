---
title: Izvoz podataka usluge Customer Insights u AdRoll
description: Saznajte kako konfigurirati vezu i izvesti u AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e48f67ec21bb9b883dd30544ccf4dcfbf487acb1abaf0a0557764bc3d955e41a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032062"
---
# <a name="export-segments-to-adroll-preview"></a>Izvoz segmenata u AdRoll (pretpregled)

Izvezite segmente objedinjenih profila klijenata u AdRoll i upotrijebite ih za oglašavanje. 

## <a name="prerequisites-for-a-connection"></a>Preduvjeti za vezu

-   Imate [račun za AdRoll](https://www.adroll.com/) i odgovarajuće vjerodajnice administratora.
-   Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Odjednom možete izvesti najviše 250.000 profila u AdRoll.
- Ne možete izvesti segmente s manje od 100 profila u AdRoll. 
- Izvoz u AdRoll ograničen je na segmente.
- Izvoz do 250.000 profila u AdRoll može potrajati do 10 minuta. 
- Broj profila koje možete izvesti u AdRoll ovisi o vašem ugovoru sa servisom AdRoll.

## <a name="set-up-connection-to-adroll"></a>Postavljanje veze s AdRoll

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **AdRoll** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** za inicijalizaciju veze s uslugom AdRoll.

1. Odaberite mogućnost **Provjera autentičnosti pomoću usluge AdRoll** i unesite svoje vjerodajnice administratora za AdRoll. 

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka AdRoll. Ako ne vidite naziv ovog odjeljka, tada vam nisu dostupne veze ove vrste.

1. Unesite svoj **ID oglašivača za AdRoll**. Za više informacija pogledajte članak [Profili oglašivača za AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta. Potrebno je izvesti segmente u AdRoll.

1. Odaberite segmente koje želite izvesti. Odaberite segment s najmanje 100 članova. Ne možete izvesti manje segmente. Uz to, maksimalna veličina segmenta za izvoz je 250.000 članova po izvozu. 

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). 

Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u AdRoll, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da AdRoll ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
