---
title: Početak rada sa Android SDK-om
description: Saznajte kako personalizirati i pokrenuti Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c678c2dafbb77926269b5602bca363c678ec6b3f
ms.sourcegitcommit: ef823f3d7fa28d3a90cfde9409be9465ffa2cf09
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/19/2021
ms.locfileid: "7655333"
---
# <a name="get-started-with-the-android-sdk"></a>Početak rada s Android SDK-om

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovaj vodič vodi vas kroz proces instrumentiranja vaše Android aplikacije s Dynamics 365 Customer Insights uvidima u angažman SDK- a. Događaje na svom portalu počet ćete viđati za pet minuta ili prije.

## <a name="configuration-options"></a>Mogućnosti konfiguracije
Sljedeće opcije konfiguracije mogu se proslijediti SDK-u:

- **ingestionKey**: ključ za unošenje koristi se za slanje događaja u vaš radni prostor.

## <a name="prerequisites"></a>Preduvjeti

- Android Studio

- Minimalna razina API-ja Android: 16 (žele grah)

- Ključ za unošenje (pogledajte dolje upute za dobivanje)

## <a name="integrate-the-sdk-into-your-application"></a>Integracija SDK-a u aplikaciju
Započnite postupak odabirom radnog prostora, odabirom Android mobilne platforme i preuzimanjem Android SDK-a.

- Pomoću izmjenjivača radnog prostora u lijevom navigacijskom oknu odaberite svoj radni prostor.

- Ako nemate postojeći radni prostor, odaberite  **Novi radni prostor** i slijedite korake za stvaranje [novog radnog prostora](create-workspace.md).

- Nakon što stvorite radni prostor, idite na **Administrator** > **Radni prostor**, a zatim odaberite  **Vodič za instalaciju**.

## <a name="configure-the-sdk"></a>Konfiguracija SDK-a

Nakon što preuzmete SDK, možete raditi s njim u Android Studio kako biste omogućili i definirali događaje. Postoje dva načina da to učinite:
### <a name="option-1-use-jitpack-recommended"></a>Opcija 1: Koristite JitPack (preporučeno)
1. Dodajte spremište JitPack u svoj korijen `build.gradle`:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Dodajte ovisnost:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>Druga mogućnost: korištenje veze za preuzimanje
1. Preuzmite uvide u [angažman Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) i stavite datoteku u `eiandroidsdk-debug.aar``libs` mapu.

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

## <a name="enable-auto-instrumentation"></a>Omogućavanje automatske instrumentacije

1. Dodajte dozvolu za mrežu i internet u svoju datoteku `AndroidManifest.xml` koja se nalazi u mapi `manifests`.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Postavite konfiguraciju SDK uvida u angažman preko svoje datoteke `AndroidManifest.xml`.

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

   >[!NOTE]
   >`Action` događaje treba dodati ručno.

1. (Izborno) Ostale konfiguracije uključuju postavljanje URL-a kolektora krajnje točke. Mogu se dodati pod metapodatke ključa za gutanje u programu `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Implementacija prilagođenih događaja

Nakon što inicijalizirate SDK možete raditi s događajima i njihovim svojstvima u okruženju `MainActivity`.


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

## <a name="set-user-details-for-your-event-optional"></a>Postavljanje korisničkih podataka za vaš događaj (nije obavezno)

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
