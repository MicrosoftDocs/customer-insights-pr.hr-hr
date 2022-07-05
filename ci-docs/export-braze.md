---
title: Izvoz segmenata u Braze (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082676"
---
# <a name="export-segments-to-braze-preview"></a>Izvoz segmenata u Braze (pretpregled)

Izvezite segmente jedinstvenih profila kupaca u Braze i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduvjeti

- [Braze račun](https://www.braze.com/) i odgovarajuće administratorske vjerodajnice.
- Postojeći [segmenti u Brazeu](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Konfigurirani segmenti](segments.md) u customer insights.
- Jedinstveni profili kupaca u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte i Brazeov ID kupca.

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

1. **U polju Veza za izvoz** odaberite vezu iz odjeljka Braze. Ako ne vidite ovu sekciju, nema dostupnih veza ove vrste.  

1. **Dodajte zaslonsko ime** za izvoz.

1. Dodajte identifikator API-ja segmenta Braze u koji želite izvesti u **polje Identifikator** API segmenta braze. Identifikator možete pronaći u detaljima o segmentu na platformi Braze.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. **U polju ID** kupca odaberite polje koje predstavlja korisnikov ID braze. Potrebno je izvoziti segmente u Braze. Po želji možete odabrati više polja.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights prijenos podataka brazeu, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenijeti takve podatke prema vašim uputama, ali vi ste odgovorni za to da Braze ispunjava sve obveze privatnosti ili sigurnosti koje možda imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
