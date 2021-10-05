---
title: Napredni scenariji web SDK
description: Napredni scenariji koje treba uzeti u obzir prilikom uređivanja web-mjesta s SDK-om.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 4c6646ecadbb604000d6c95b685cf6e420969a6d
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558692"
---
# <a name="advanced-web-sdk-instrumentation"></a>Napredno uređivanje web-mjesta uz SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovaj vas članak vodi kroz napredne scenarije koje trebate uzeti u obzir prilikom [uređivanja web-mjesta](instrument-website.md) SDK-om uvida u angažman aplikacije Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Postavljanje korisničkih detalja za događaj

SDK vam omogućuje definiranje korisničkih podataka koji se mogu poslati uz svaki događaj. Možete odrediti korisničke detalje u svojstvu koje se zove `user` (očekivani podaci za to svojstvo je objekt `IUser`), slično kao `src`, `name` i `cfg` u konfiguraciji isječka koda.

Objekt `IUser` sadrži sljedeća svojstva niza:

- **localId**: lokalni ID korisnika.
- **authId**: provjereni ID korisnika.
- **authType**: vrsta provjere autentičnosti koja se koristi za dobivanje provjerenog ID-a korisnika.
- **ime**: ime korisnika.
- **e-pošta**: korisnikova adresa e-pošte.

Sljedeći primjer prikazuje isječak koda koji šalje korisničke podatke. Tamo gdje funkciji prethodi simbol zvjezdice *, zamijenite funkciju prilagođenom implementacijom:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Korisničke podatke možete odrediti i pozivom na API `setUser(user: IUser)`. Telemetrija poslana nakon što ste pozvali API `setUser` sadržavat će korisničke podatke.

## <a name="adding-custom-properties-for-each-event"></a>Dodavanje prilagođenih svojstava za svaki događaj

SDK vam omogućuje određivanje prilagođenih svojstava koja se mogu poslati uz svaki događaj. Prilagođena svojstva možete navesti kao objekt koji sadrži parove ključ-vrijednost (vrijednost može biti vrste `string | number | boolean`). Objekt možete dodati u svojstvo koje se zove `props`, slično svojstvu `src`, `name` i `cfg` u konfiguraciji isječka koda.

Sljedeći primjer prikazuje isječak koda koji šalje prilagođena svojstva:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Prilagođena svojstva možete odrediti i tako da pozovete API `setProperty(name: string, value: string | number | boolean)`.

## <a name="sending-custom-events"></a>Slanje prilagođenih događaja

SDK možete koristiti za slanje prilagođenih događaja. Morate navesti naziv događaja i svojstva koja će se poslati s događajem.

Sljedeći primjer prikazuje isječak koda koji prati prilagođeni događaj. NAME je vrijednost u ključu `name` u konfiguraciji isječka. To je također naziv varijable u objektu prozora u koji se učitava SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
