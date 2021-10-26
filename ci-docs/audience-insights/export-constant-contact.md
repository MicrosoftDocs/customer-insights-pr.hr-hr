---
title: Izvoz podataka o Customer Insights u Constant Contact
description: Saznajte kako konfigurirati vezu i izvesti u Constant Contact.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b25e4f11e21d059c2d867e925c0ae5635a87addc
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/08/2021
ms.locfileid: "7619110"
---
# <a name="export-segments-to-constant-contact-preview"></a>Izvoz segmenata u Constant Contact (pretpregled)

Izvezite segmente objedinjenih profila klijenata u Constant Contact i koristite ih za marketinške aktivnosti. 

## <a name="prerequisites-for-a-connection"></a>Preduvjeti za vezu

-   Imate [Račun Constant Contact](https://www.constantcontact.com/account-home) i odgovarajuće vjerodajnice administratora.
-   Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Možete izvesti do 1 milijun profila klijenata po izvozu u Constant Contact.
- Izvoz u Constant Contact ograničen je na segmente.
- Izvoz do 1 milijun profila klijenata u Constant Contact može potrajati do 1 sat. 
- Broj profila klijenata koje možete izvesti u Constant Contact ovisi i ograničen je ugovorom s uslugom Constant Contact.

## <a name="set-up-connection-to-constant-contact"></a>Postavljanje veze s Constant Contact

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **Constant Contact** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** za inicijalizaciju veze s Constant Contact.

1. Odaberite **Provjeri autentičnost stalnim kontaktom** i dostavite svoje administratorske vjerodajnice za stalni kontakt. 

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Constant Contact. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Unesite svoje [**ID popisa za Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists). Otvorite popis u Constant Contact da biste pronašli ID popisa u URL-u.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. Obavezno je izvoziti segmente u Constant Contact.

1. Ako želite, možete izvesti stavke Ime i Prezime kao dodatna polja za stvaranje osobnijih poruka e-pošte. Odaberite **Dodavanje atributa** za mapiranje ovih polja.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Constant Contact dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Constant Contact ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
