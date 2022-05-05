---
title: Izvoz podataka iz Customer Insights u Omnisend
description: Saznajte kako konfigurirati vezu i izvesti u Omnisend.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 70bd94ea5e4060094c3d215e3fc263a98df51229
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642368"
---
# <a name="export-segments-to-omnisend-preview"></a>Izvoz segmenata u Omnisend (pretpregled)

Izvezite segmente objedinjenih profila klijenata u Omnisend i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduvjeti

-   Imate [Račun za Omnisend](https://www.omnisend.com/) i odgovarajuće vjerodajnice administratora.
-   Konfigurirali [ste segmente](segments.md) u customer insights.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Možete izvesti do 1 milijun profila klijenata po izvozu u Omnisend, a dovršetak može potrajati do 4 sata.
- Izvoz u Omnisend ograničen je na segmente.
- Broj profila klijenata koje možete izvesti u Omnisend ovisi o ugovoru s uslugom Omnisend.

## <a name="set-up-connection-to-omnisend"></a>Postavljanje veze s uslugom Omnisend

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **Omnisend** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj [Ključ za API za Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** za inicijalizaciju veze s uslugom Omnisend.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Omnisend. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. Obavezno je izvoziti segmente u Omnisend. Ako želite, možete izvesti Ime, Prezime, Adresu, Državu/Regiju, Državu, Grad i Poštanski broj za stvaranje personaliziranije e-pošte. Odaberite **Dodavanje atributa** za mapiranje ovih polja.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Ommisend, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Omnisend ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
