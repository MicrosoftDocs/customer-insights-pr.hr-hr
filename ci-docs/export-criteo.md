---
title: Izvoz segmenata u Criteo (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082781"
---
# <a name="export-segments-to-criteo-preview"></a>Izvoz segmenata u Criteo (pretpregled)

Izvoz segmenata jedinstvenih korisničkih profila za generiranje kampanja, pružanje marketinga putem e-pošte i korištenje određenih grupa kupaca s Criteom.

## <a name="prerequisites-for-connection"></a>Preduvjeti za vezu

-   Imate [criteo dynamics retargeting račun](https://www.criteo.com/login/) i odgovarajuće administratorske vjerodajnice.
-   Imate [konfigurirane segmente](segments.md).
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milijun korisničkih profila po izvozu u Criteo.
- Izvoz u Criteo ograničen je na segmente.
- Izvoz segmenata s ukupno 1 milijun profila klijenata može potrajati do 30 minuta. 
- Broj korisničkih profila koje možete izvesti u Criteo ovisi i ograničen je na vaš ugovor s Criteom.

## <a name="set-up-connection-to-criteo"></a>Postavljanje veze s Criteom

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Criteo** da biste konfigurirali vezu.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Odaberite **Pristajem** potvrditi privatnost i usklađenost **podataka i odaberite** Poveži **se** da biste inicijalizirali vezu s Criteom.

1. Odaberite **Autentifikaciju pomoću tvrtke Criteo** i navedite korisničko ime i vjerodajnice administratora za Criteo. 

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. **U polju Veza za izvoz** odaberite vezu iz sekcije Criteo. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste. 

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. 

1. Po želji možete izvesti **ID** i **ime oglašivača**

1. Odaberite segmente koje želite izvesti. 

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights prijenos podataka u Criteo, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenijeti takve podatke prema vašim uputama, ali vi ste odgovorni za to da criteo ispunjava sve obveze privatnosti ili sigurnosti koje možda imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE[footer-include](includes/footer-banner.md)]
