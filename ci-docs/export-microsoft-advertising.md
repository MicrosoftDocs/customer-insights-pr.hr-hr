---
title: Izvoz segmenata u Microsoftovo oglašavanje (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Microsoftovo oglašavanje.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca37159ec6473ad5c331a0ce1aa8424d277529ff
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082802"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Izvoz segmenata u Microsoftovo oglašavanje (pretpregled)

Izvezite segmente usluge Customer Insights u Microsoftovo oglašavanje da biste stvorili ciljne skupine Podudaranje klijenta. Upotrijebite ove ciljne skupine za svoje reklamne kampanje.

## <a name="prerequisites"></a>Preduvjeti

-   [Račun za Microsoftovo oglašavanje](https://ads.microsoft.com/) i odgovarajuće vjerodajnice administratora.
-   Prihvatili ste uvjete korištenja Podudaranja klijenata. 
-   [Konfigurirani segmenti](segments.md) u customer insights.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje s adresom e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Možete izvesti do 500 tisuća profila klijenata po izvozu u Microsoft Advertising.
- Izvoz u Microsoftovo oglašavanje ograničen je na segmente.
- Izvoz do 500 tisuća profila klijenata u Microsoft Advertising može potrajati do 10 minuta. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Postavljanje veze s Microsoftovim oglašavanjem

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **Microsoftovo oglašavanje** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Zadana postavka su administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** za inicijalizaciju veze s Microsoftovim oglašavanjem.

1. Odaberite **Provjeri autentičnost uz Microsoftovo oglašavanje** i pružite svoje administratorske vjerodajnice za Microsoftovo oglašavanje.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Microsoftovo oglašavanje. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Odaberite segmente za izvoz. Ciljne skupine Podudaranje klijenata u Microsoftovom oglašavanju stvaraju se automatski s nazivom segmenata odabranih za izvoz. Svaki će segment rezultirati zasebnom ciljnom skupinom Podudaranje klijenata. 

1. Unesite svoj **ID klijenta Microsoftova oglašavanja i ID računa**. ID klijenta (`cid`) i ID računa (`aid`) možete pronaći u parametrima URL-a kada ste prijavljeni u Microsoftovo oglašavanje.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje s adresom e-pošte klijenta. Obavezno je izvoziti segmente u Microsoftovo oglašavanje.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Microsoftovo oglašavanje, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Microsoftovo oglašavanje ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
