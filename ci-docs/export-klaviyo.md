---
title: Izvoz segmenata u Klaviyo (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Klaviyo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e2b60d9818a753e81e69f2bee6b1663e1840cb10
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051306"
---
# <a name="export-segments-to-klaviyo-preview"></a>Izvoz segmenata u Klaviyo (pretpregled)

Izvezite segmente objedinjenih profila kupaca u Klaviyo i upotrijebite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduvjeti

-   Imate [Klaviyo račun](https://www.klaviyo.com/) i odgovarajuće vjerodajnice administratora.
-   Konfigurirali [ste segmente](segments.md) u customer insights.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Možete izvesti do 100 tisuća profila klijenata po izvozu u Klaviyo.
- Izvoz u Klaviyo ograničen je na segmente.
- Izvoz do 1 milijun profila klijenata u Klaviyo može potrajati do 20 minuta. 
- Broj profila klijenata koje možete izvesti u Klaviyo ovisi i ograničen je ugovorom s uslugom Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>Postavljanje veze sa servisom Klaviyo

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Klaviyo** da biste konfigurirali vezu.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite svoj [ključ Klaviyo API-ja](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) za nastavak prijave. 

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** za pokretanje veze sa servisom Klaviyo.

1. Odaberite **Provjera autentičnost sa servisom Klaviyo** i navedite svoje administratorske vjerodajnice za Klaviyo.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Klaviyo. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Unesite svoj [**Klaviyo ID popisa**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. Obvezno je izvoziti segmente u Klaviyo.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kad omogućite Dynamics 365 Customer Insights za prijenos podataka u Klaviyo dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke poput osobnih podataka. Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Klaviyo ispunjava sve obveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
