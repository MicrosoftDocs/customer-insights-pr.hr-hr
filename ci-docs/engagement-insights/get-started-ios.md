---
title: Početak rada s iOS SDK-om
description: Saznajte kako personalizirati i pokrenuti iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: f05929435eeee9cf3f891ab18842c5861e39d5ba
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494221"
---
# <a name="get-started-with-the-ios-sdk"></a>Početak za iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovaj korisnički priručnik vodi vas kroz instrumentaciju aplikacije sustava iOS SDK-om uvida u angažman aplikacije Dynamics 365 Customer Insights. Događaje na svom portalu počet ćete viđati za pet minuta ili prije.

## <a name="configuration-options"></a>Mogućnosti konfiguracije

Sljedeće opcije konfiguracije mogu se proslijediti SDK-u preko isporučene datoteke `EIConfig.plist`:

- **ingestionKey**: ključ za unošenje koji se koristi za slanje događaja u vaš projekt.
- **autocollectAction** : Booleova vrijednost za omogućavanje ili onemogućavanje automatske instrumentacije događaja radnje.
- **autocollectView** : Booleova vrijednost za omogućavanje ili onemogućavanje automatske instrumentacije događaja prikaza.
- **endpointUrl** : URL krajnje točke na koji će se usmjeravati događaji.

## <a name="prerequisites"></a>Preduvjeti

- Xcode verzije 9+
- iOS verzije 8.2+
- Ključ za unošenje (pogledajte dolje upute za dobivanje)

## <a name="integrate-the-sdk-into-your-application"></a>Integracija SDK-a u aplikaciju

Započnite postupak odabirom radnog prostora u kojem ćete raditi, odabirom mobilne platforme iOS i preuzimanjem SDK-a.

- Pomoću izmjenjivača radnog prostora u lijevom navigacijskom oknu odaberite svoj radni prostor.

- Ako nemate postojeći radni prostor, odaberite  **Novi radni prostor** i slijedite korake za stvaranje [novog radnog prostora](create-workspace.md).

- Nakon što stvorite radni prostor, idite na **Administrator** > **Radni prostor**, a zatim odaberite **Vodič za instalaciju**.

## <a name="configure-the-sdk"></a>Konfiguracija SDK-a

Nakon što preuzmete SDK, možete raditi s njim u Xcodeu kako biste omogućili i definirali događaje. Postoje dva načina da to učinite

### <a name="option-1-using-cocoapods-recommended"></a>Mogućnost 1: Korištenje CocoaPods (preporučeno)
CocoaPods upravitelj je ovisnosti za projekte Swift i Objective-C Cocoa. Njegovo korištenje olakšava integraciju SDK uvida u angažman za iOS. CocoaPods omogućuje i nadogradnju na najnoviju verziju SDK uvida u angažman. Evo kako se koristi CocoaPods za integraciju SDK za uvide u angažman u vaš projekt Xcode. 

1. Instalacija aplikacije CocoaPods. 

1. Stvorite novu datoteku pod nazivom Podfile unutar korijenskog direktorija projekta i dodajte joj sljedeće izraze.Zamijenite YOUR_TARGET_PROJECT_NAME nazivom svojeg projekta Xcode. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Gornja konfiguracija pod sadrži verzije za otklanjanje pogrešaka i izdanje SDK-a. Odaberite ono što je najbolje za vaš projekt.

1. Instalirajte pod izvršavanjem sljedeće naredbe: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Mogućnost 2: Korištenje veze za preuzimanje

1. Preuzmite [iOS SDK uvida o angažmanu](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) i smjestite datoteku `EIObjC.xcframework` u mapu `Frameworks`.

1. Ako mapa `Frameworks` ne postoji, stvorite je u mapi projekta.

## <a name="enable-auto-instrumentation"></a>Omogućavanje automatske instrumentacije
 
Jednostavno možete omogućiti automatsku instrumentaciju bez programiranja. Kad se projekt pokrene, automatski će pratiti događaje `view` i `action` pomoću konfiguriranog ključa za unošenje. 

1. Ažurirajte i uključite isporučenu datoteku `EIConfig.plist` u mapi direktorija projekta za sljedeća polja:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = DA
    - autocollectAction = DA

2. Zatim dodajte datoteku `EIConfig.plist` u svoj projekt u Xcodeu. 



Da biste onemogućili automatsku instrumentaciju, ažurirajte sljedeća polja u isporučenoj datoteci `EIConfig.plist` u mapi direktorija projekta. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Implementacija prilagođenih događaja

1. Otvorite svoj projekt u Xcodeu i pomaknite se na postavke **Općenito**. 
1. Dodajte `EIObjC.xcframework` projektu u odjeljku "Okviri, knjižnice i ugrađeni sadržaj".

1. Uvezite datoteku zaglavlja okvira u datoteku AppDelegate.m sa sljedećim isječkom:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Inicijalizirajte SDK uvida u angažman iz apikacije: didFinishLaunchingWithOptions.
1. Kopirajte XML isječak iz **Vodiča za instalaciju**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Praćenje događaja:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Postavljanje korisničkih podataka za vaš događaj

SDK vam omogućuje definiranje korisničkih podataka koji se mogu poslati uz svaki događaj. Korisničke podatke možete odrediti pozivom API-ja `setUser:(nonnull EIUser *)user` na SDK-u.

Navođenje korisničkih podataka na razini `Analytics` znači da će sve telemetrije imati ove informacije. Međutim, ako navedete na razini događaja pozivanjem API-ja `setUser:(nonnull EIUser *)user` na objektu EIEvent, samo će taj određeni događaj sadržavati informacije.

Klasa podataka `EIUser` sadrži sljedeća svojstva niza NSString:

- **localId**: lokalni ID korisnika.
- **authId**: provjereni ID korisnika.
- **authType**: vrsta provjere autentičnosti koja se koristi za dobivanje provjerenog ID-a korisnika.
- **ime**: ime korisnika.
- **e-pošta**: korisnikova adresa e-pošte.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
