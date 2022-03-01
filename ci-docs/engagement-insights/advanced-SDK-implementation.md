---
title: Napredni scenariji web SDK
description: Napredni scenariji koje treba uzeti u obzir prilikom uređivanja web-mjesta s SDK-om.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036319"
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
    
Sljedeći primjer prikazuje isječak koda koji šalje korisničke podatke. Tamo gdje vidite funkcije označene s * zamijenite ih implementacijom pozivanja tih vrijednosti:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
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

Korisničke podatke možete odrediti i pozivanjem API-ja `setUser(user: IUser)` na SDK-u. Telemetrija poslana nakon pozivanja `setUser API` sadržavat će korisničke podatke.

## <a name="adding-custom-properties-for-each-event"></a>Dodavanje prilagođenih svojstava za svaki događaj

SDK vam omogućuje određivanje prilagođenih svojstava koja se mogu poslati uz svaki događaj. Prilagođena svojstva možete navesti kao objekt koji sadrži parove ključ-vrijednost (vrijednost može biti vrste `string | number | boolean`). Objekt se može dodati u svojstvo pod nazivom `props`, slično kao `src`, `name` i `cfg` u konfiguraciji isječka koda. 

Sljedeći primjer prikazuje isječak koda koji šalje prilagođena svojstva:

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
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

Također možete pojedinačno navesti prilagođena svojstva pozivanjem API-ja `setProperty(name: string, value: string | number | boolean)` na SDK-u.

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