---
title: Izvoz podataka usluge Customer Insights u DotDigital
description: Saznajte kako konfigurirati vezu i izvesti u DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f63a0f5f5f93e96681a88fd758381c012a404f43
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642191"
---
# <a name="export-segments-to-dotdigital-preview"></a>Izvoz segmenata u DotDigital (pretpregled)

Izvezite segmente objedinjenih profila klijenata u adresare usluge DotDigital i koristite ih za kampanje, marketing putem e-pošte i za izgradnju segmenata klijenata pomoću usluge DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Preduvjeti za vezu

-   Imate [račun za DotDigital](https://dotdigital.com/) i stvorili ste [korisnika API-ja](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Za stvaranje veze trebate koristiti vjerodajnice korisnika API -ja
-   DotDigital sadrži postojeće adresare i odgovarajuće ID-ove. ID se može pronaći u URL-u kada odaberete i otvorite adresar. Dodatne informacije potražite u [adresarima usluge DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Konfigurirali [ste segmente](segments.md) u customer insights.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 1 milijun profila klijenata po izvozu u DotDigital.
- Izvoz u DotDigital ograničen je na segmente.
- Izvoz segmenata s ukupno 1 milijun profila klijenata može potrajati i do 3 sata zbog ograničenja na strani davatelja usluga. 
- Broj profila klijenata koje možete izvesti u DotDigital ovisi i ograničen je ugovorom s uslugom DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Postavljanje veze s DotDigital

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **DotDigital** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **korisničko ime i lozinku API-ja za DotDigital**. 

1. Unesite svoj **[ID adresara usluge DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Povezivanje** za inicijalizaciju veze s uslugom DotDigital.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu. 

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka DotDigital. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.


1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. Ponovite iste korake za druga neobavezna polja kao što su **Ime**, **Prezime**, **Puno ime**, **Spol** i **Poštanski broj**.

1. Odaberite segmente koje želite izvesti. U DotDigital možete ukupno izvesti do 1 milijun profila klijenata.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 
 
U usluzi DotDigital sada možete pronaći svoje segmente u [adresaru usluge DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u DotDigital, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da DotDigital ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE [footer-include](includes/footer-banner.md)]
