---
title: Izvoz segmenata u Snapchat (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Snapchat.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: abe04cd1464c3f7df969da3c769329382d603d7e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051904"
---
# <a name="export-segments-to-snapchat-preview"></a>Izvoz segmenata u Snapchat (pretpregled)

Izvezite segmente objedinjenih profila klijenata u Snapchat i koristite ih za oglašavanje. 

## <a name="prerequisites-for-a-connection"></a>Preduvjeti za vezu

-   Imate [Snapchat poslovni račun](https://business.snapchat.com/), [Snapchat Ads račun](https://ads.snapchat.com/) i odgovarajuće administratorske vjerodajnice. YOu mora barem biti član računa tvrtke ili ustanove i upravitelj podataka određenog oglasnog računa. 
-   Imate barem jednu publika u Snapchatu publika menadžer tipa SAM (Snap publika Match). 
-   Konfigurirali [ste segmente](segments.md) u customer insights.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Izvoz u Snapchat ograničen je na segmente.
- Izvoz do 1 milijun profila klijenata u Snapchat može potrajati do 15 minuta. 

## <a name="set-up-connection-to-snapchat"></a>Postavljanje veze za Snapchat

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **Snapchat** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** za inicijalizaciju veze sa Snapchat.

1. Odaberite **Provjeri autentičnost uz Snapchat** i pružite svoje administratorske vjerodajnice za Snapchat. 

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Snapchat. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. [**Unesite Snapchat segment / publika ID**](https://businesshelp.snapchat.com/s/article/custom-audiences). ID publika može se naći u URL-u nakon odabira publika u Snapchat publika Manageru. 

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. Obavezno je izvoziti segmente u Snapchat.

1. Odaberite segmente koje želite izvesti. 

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Snapchat dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Snapchat ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
