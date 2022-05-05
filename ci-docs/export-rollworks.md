---
title: Izvoz podataka iz Customer Insights u RollWorks
description: Saznajte kako konfigurirati vezu i izvesti u RollWorks.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ba63f9146b17ebf6daf5b0a9f39c0d6bc32a1bfa
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642386"
---
# <a name="export-segments-to-rollworks-preview"></a>Izvoz segmenata u RollWorks (pretpregled)

Izvezite segmente objedinjenih profila klijenata u RollWorks i koristite ih za oglašavanje. 

## <a name="prerequisites-for-a-connection"></a>Preduvjeti za vezu

-   Imate [Račun za RollWorks](https://www.rollworks.com/) i odgovarajuće vjerodajnice administratora.
-   Konfigurirali [ste segmente](segments.md) u customer insights.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Možete izvesti do 250 tisuća profila klijenata po izvozu u RollWorks.
- Ne možete izvesti segmente s manje od 100 profila klijenata u RollWorks. 
- Izvoz u RollWorks ograničen je na segmente.
- Izvoz do 250 tisuća profila klijenata u RollWorks može potrajati do 10 minuta. 
- Broj profila klijenata koje možete izvesti u RollWorks ovisi i ograničen je ugovorom s uslugom RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Postavljanje veze s RollWorks

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **RollWorks** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** za inicijalizaciju veze s RollWorks.

1. Odaberite **Provjeri autentičnost uz RollWorks** i pružite svoje administratorske vjerodajnice za RollWorks.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka RollWorks. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Unesite svoj **ID oglašivača za RollWorks** [Oglas za RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. Obavezno je izvoziti segmente u RollWorks.

1. Odaberite segmente koje želite izvesti. Odaberite segment s najmanje 100 članova. Ne možete izvesti manje segmente. Uz to, maksimalna veličina segmenta za izvoz je 250 000 članova po izvozu. 

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u RollWorks dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da RollWorks ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
