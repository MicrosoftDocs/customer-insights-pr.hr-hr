---
title: Izvoz podataka usluge Customer Insights u Mailchimp
description: Saznajte kako konfigurirati vezu i izvesti u Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759869"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a>Izvoz popisa segmenata u Mailchimp (pretpregled)

Izvezite segmente objedinjenih profila klijenata u Mailchimp da biste stvorili biltene i kampanje e-pošte.

## <a name="prerequisites-for-connection"></a>Preduvjeti za vezu

-   Imate [račun za Mailchimp](https://mailchimp.com/) i odgovarajuće vjerodajnice administratora.
-   Mailchimp sadrži postojeće ciljne skupine i odgovarajuće ID-ove. Dodatne informacije potražite u [ciljnim skupinama usluge Mailchimp](https://mailchimp.com/help/create-audience/).
-   Imate [konfigurirane segmente](segments.md)
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 1 milijun profila po izvozu u Mailchimp.
- Izvoz u Mailchimp ograničen je na segmente.
- Izvoz segmenata s 1 milijun profila može potrajati do tri sata. 
- Broj profila koje možete izvesti u Mailchimp ovisi i ograničen je vašim ugovorom s tvrtkom Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Postavljanje veze s Mailchimp

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **Autopilot** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** za inicijalizaciju veze s Mailchimp.

1. Odaberite mogućnost **Provjera autentičnosti pomoću usluge Mailchimp** i unesite svoje vjerodajnice za Mailchimp.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu. 

## <a name="configure-the-connector"></a>Konfiguracija poveznika

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci**> **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Mailchimp. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Unesite svoj **[ID ciljne skupine za Mailchimp](https://mailchimp.com/help/find-audience-id/)**

3. U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta. 

1. Neobavezno možete izvesti **Ime** i **Prezime** za stvaranje personaliziranije e-pošte. Odaberite **Dodavanje atributa** za mapiranje ovih polja.

1. Odaberite segmente koje želite izvesti. U Mailchimp možete ukupno izvesti do 1 milijun profila klijenata.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Mailchimp, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Mailchimp ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
