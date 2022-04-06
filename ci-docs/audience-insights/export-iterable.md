---
title: Izvoz podataka korisničkih uvida u iterable
description: Saznajte kako konfigurirati vezu i izvesti u Iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4de499fcc4a5a0dcc2dfd3bae02913c81a59647b
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524580"
---
# <a name="export-segment-lists-to-iterable-preview"></a>Izvoz popisa segmenata u iterable (pretpregled)

Izvezite segmente jedinstvenih profila kupaca u Iterable i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduvjeti

-   Imate račun [koji](https://iterable.com/) se može iterirati i odgovarajuće administratorske vjerodajnice.
-   Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Izvoz u Iterable ograničen je na segmente.
- Izvoz do milijun korisničkih profila u Iterable može potrajati i do 30 minuta. 
- Broj korisničkih profila koje možete izvesti u Iterable ovisi i ograničen je na vaš ugovor s programom Iterable.

## <a name="set-up-connection-to-iterable"></a>Postavljanje veze s programom Iterable

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Iterable** da biste konfigurirali vezu.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite svoj [API ključ](https://support.iterable.com/hc/en-us/articles/360043464871) koji se može iterirati da biste se nastavili prijavljivati. 

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** se da biste inicijalizirali vezu s iterableom.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. **U polju Veza za izvoz** odaberite vezu iz odjeljka Iterable ( Iterable). Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

3. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. Potrebno je izvesti segmente u Iterable.Popis kreiran u Iterableu dobit će točno isti naziv kao i naziv vašeg segmenta u Dynamics 365 Customer Insights sustavu.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights prijenos podataka na Iterable, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenijeti takve podatke prema vašim uputama, ali vi ste odgovorni za to da Iterable ispunjava sve obveze privatnosti ili sigurnosti koje možda imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
