---
title: Početak rada s Android SDK-om
description: Saznajte kako personalizirati i pokrenuti Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036909"
---
# <a name="get-started-with-the-android-sdk"></a>Početak za Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovaj korisnički priručnik vodi vas kroz postupak instrumentacije aplikacije sustava Android SDK-om uvida u angažman aplikacije Dynamics 365 Customer Insights. Događaje na svom portalu počet ćete viđati za pet minuta ili prije.

## <a name="configuration-options"></a>Mogućnosti konfiguracije
Sljedeće opcije konfiguracije mogu se proslijediti SDK-u:

- **ingestionKey**: ključ za unošenje koristi se za slanje događaja u vaš radni prostor.

## <a name="prerequisites"></a>Preduvjeti

- Android Studio

- Minimalna razina Android API-ja: 16 (Jelly Bean)

- Ključ za unošenje (pogledajte dolje upute za dobivanje)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>1. korak Integracija SDK-a u aplikaciju
Započnite postupak odabirom radnog prostora, odabirom mobilne platforme Android i preuzimanjem Android SDK-a.

- Pomoću izmjenjivača radnog prostora u lijevom navigacijskom oknu odaberite svoj radni prostor.

- Ako nemate postojeći radni prostor, odaberite  **Novi radni prostor** i slijedite korake za stvaranje [novog radnog prostora](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>2. korak Konfiguracija SDK-a

1. Nakon što stvorite radni prostor, idite na **Administrator** > **Radni prostor**, a zatim odaberite  **Vodič za instalaciju**. 

1. Preuzmite [Android SDK uvida o angažmanu](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) i smjestite datoteku `eiandroidsdk-debug.aar` u mapu `libs`.

1. Otvorite datoteku `build.gradle` na razini projekta i dodajte sljedeće isječke:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Postavite konfiguraciju SDK-a uvida o angažmanu preko svoje datoteke `AndroidManifest.xml` smještene u mapi `manifests`. 
1. Kopirajte XML isječak iz **Vodiča za instalaciju**. `Your-Ingestion-Key` treba se automatski popuniti.

   > [!NOTE]
   > Ne trebate zamijeniti odjeljak `${applicationId}`. Automatski se popunjava.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Omogućite ili onemogućite automatsko bilježenje događaja `View` postavljanjem gore navedenog polja `autoCapture` na `true` ili `false`.

1. (Izborno) Ostale konfiguracije uključuju postavljanje URL-a kolektora krajnje točke. Mogu se dodati pod metapodacima ključa za unos u `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>3. korak Inicijalizirajte SDK iz MainActivity 

Nakon što inicijalizirate SDK možete raditi s događajima i njihovim svojstvima u okruženju MainActivity.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Postavljanje svojstva za sve događaje (nije obavezno)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Sljedeće su vrste podržane za svojstva kontekstnih događaja:
- String
- Datum
- Dvostruko
- Dugi
- Boolean
- UUID

### <a name="track-an-event"></a>Praćenje događaja

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Postavljanje korisničkih podataka za vaš događaj (nije obavezno)

SDK vam omogućuje definiranje korisničkih podataka koji se mogu poslati uz svaki događaj. Korisničke podatke možete odrediti pozivom API-ja `setUser(user: User)` na razini `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Klasa podataka `User` sadrži sljedeća svojstva niza:

- **localId**: lokalni ID korisnika.
- **authId**: provjereni ID korisnika.
- **authType** : Vrsta provjere autentičnosti koja se koristi za dobivanje autentificiranog korisničkog ID-a.
- **ime**: ime korisnika.
- **e-pošta**: korisnikova adresa e-pošte.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
