---
title: Izvoz podataka customer insights u Braze
description: Saznajte kako konfigurirati vezu i izvesti u Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642230"
---
# <a name="export-segment-lists-to-braze-preview"></a>Izvoz popisa segmenata u Braze (pretpregled)

Izvezite segmente jedinstvenih profila kupaca u Braze i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduvjeti

-   Imate [Braze račun](https://www.braze.com/) i odgovarajuće administratorske vjerodajnice.
-   Konfigurirali [ste segmente](segments.md) u customer insights.
-   Jedinstveni profili kupaca u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte i Brazeov ID kupca. 

## <a name="known-limitations"></a>Poznata ograničenja

- Izvoz u Braze ograničen je na segmente.
- Izvoz do milijun korisničkih profila u Braze može potrajati i do 40 minuta. 
- Broj profila kupaca koje možete izvesti u Braze ovisi i ograničen je na vaš ugovor s Brazeom.

## <a name="set-up-connection-to-braze"></a>Postavljanje veze s Brazeom

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim Braze **da** biste konfigurirali vezu.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite ključ [Braze API-ja](https://www.braze.com/docs/api/basics/) da biste se nastavili prijavljivati. 

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** se da biste inicijalizirali vezu s Brazeom.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. **U polju Veza za izvoz** odaberite vezu iz odjeljka Braze. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.  

3. **U odjeljku Podudaranje** podataka u **polju E-pošta** odaberite polje koje predstavlja adresu e-pošte klijenta, u polju "ID kupca" odaberite polje koje predstavlja ID braze kupca. Potrebno je izvoziti segmente u Braze. Segmenti u Brazama nastaju s istim nazivom segmenta kao i u Dynamics 365 Customer Insights. Možete odabrati dodatna, neobavezna polja za podudarne podatke. 

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights prijenos podataka brazeu, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će takve podatke prenijeti prema vašim uputima, ali vi ste odgovorni za to da Braze ispunjava sve obveze privatnosti ili sigurnosti koje možda imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
