---
title: Izvoz podataka o Customer Insights u Campaign Monitor
description: Saznajte kako konfigurirati vezu i izvesti u Campaign Monitor.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b351e491ee830b6360d4efe33d32a726c2e553ba
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642227"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Izvoz segmenata u Campaign Monitor (pretpregled)

Izvezite segmente objedinjenih profila klijenata u Campaign Monitor i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduvjeti

-   Imate [Račun Campaign Monitor](https://www.campaignmonitor.com/) i odgovarajuće vjerodajnice administratora.
-   Konfigurirali [ste segmente](segments.md) u customer insights.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Možete izvesti do 1 milijun profila klijenata po izvozu u Campaign Monitor.
- Izvoz u Campaign Monitor ograničen je na segmente.
- Izvoz do 1 milijun profila klijenata u Campaign Monitor može potrajati do 20 minuta. 
- Broj profila klijenata koje možete izvesti u Campaign Monitor ovisi i ograničen je ugovorom s uslugom Campaign Monitor.

## <a name="set-up-connection-to-campaign-monitor"></a>Postavljanje veze s Campaign Monitor

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **Campaign Monitor** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** za inicijalizaciju veze s Campaign Monitor.

1. Odaberite **Provjeri autentičnost uz Campaign Monitor** i pružite svoje administratorske vjerodajnice za Campaign Monitor.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Campaign Monitor. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Unesite svoj [**ID popisa za Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Generirajte ključ za API](https://www.campaignmonitor.com/api/getting-started/) iz **Postavke računa** u Campaign Monitor kao prvo da biste prikazali ID popisa za API.  

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. Obavezno je izvoziti segmente u Campaign Monitor.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Campaign Monitor dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Campaign Monitor ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
