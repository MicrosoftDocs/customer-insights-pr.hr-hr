---
title: Izvoz podataka usluge Customer Insights u SendGrid
description: Saznajte kako konfigurirati vezu i izvesti u SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 38dd782fdf06d5970e79e6deb6e8fc94252da585
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642380"
---
# <a name="export-segments-to-sendgrid-preview"></a>Izvoz segmenata u SendGrid (pretpregled)

Izvezite segmente objedinjenih profila klijenata u popise kontakata usluge SendGrid i koristite ih za kampanje i marketing putem e-pošte u usluzi SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Preduvjeti za vezu

-   Imate [račun za SendGrid](https://sendgrid.com/) i odgovarajuće vjerodajnice administratora.
-   SendGrid sadrži postojeće popise kontakata i odgovarajuće ID-jeve. Za dodatne informacije pogledajte [SendGrid – Upravljanje kontaktima](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Konfigurirali [ste segmente](segments.md) u customer insights.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Ukupno do 100 tisuća profila klijenata na SendGrid.
- Izvoz u SendGrid ograničen je na segmente.
- Izvoz do 100 tisuća profila klijenata u SendGrid može potrajati nekoliko sati. 
- Broj profila klijenata koje možete izvesti u SendGrid ovisi i ograničen je ugovorom s uslugom SendGrid.

## <a name="set-up-connection-to-sendgrid"></a>Postavljanje veze sa SendGrid

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **SendGrid** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj **Ključ za API za SendGrid** [Ključ za API za SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** za inicijalizaciju veze s uslugom SendGrid.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka SendGrid. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Unesite svoj **[ID popisa usluge SendGridI](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. Ponovite iste korake za ostala neobavezna polja kao što su **Ime**, **Prezime**, **Zemlja/Regija**, **Država**, **Grad** i **Poštanski broj**.

1. Odaberite segmente koje želite izvesti. Snažno **preporučujemo da ne izvozite više od ukupno 100 000 profila klijenata** u uslugu SendGrid. 

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u SendGrid, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da SendGrid ispunjava sve obaveze zaštite privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE [footer-include](includes/footer-banner.md)]
