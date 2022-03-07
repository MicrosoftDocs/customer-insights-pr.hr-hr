---
title: Android SDK uzorak
description: Uzorak projekta za učenje o Android SDK-u
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229909"
---
# <a name="run-the-android-sdk-sample"></a>Pokretanje Android SDK uzorka

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovaj uzorak Android projekta pomaže vam razumjeti kako SDK radi u aplikaciji. Ne morate programirati. Samo dodajte ključ za unošenje i odmah ćete vidjeti događaje u svom radnom prostoru.

## <a name="prerequisites"></a>Preduvjeti

- [Android Studio](https://developer.android.com/studio)
- [Ključ za unošenje](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Preuzimanje Android SDK uzorka

1. [Preuzimanje Android SDK uzorka za uvide o angažmanu](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Raspakirajte komprimiranu datoteku `ei-android-sample.zip`.
1. Otvorite raspakiranu mapu u programu Android Studio.
1. U datoteci `AndroidManifest.xml` niz `"Your-Ingestion-Key"` zamijenite ključem za unošenje radnog prostora iz uvida o angažmanu na lokaciji **Administrator** > **Radni prostor** > **Vodič za instalaciju**. 

   > [!NOTE]
   > Ne trebate zamijeniti odjeljak `${applicationId}`. Automatski se popunjava.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Odaberite **Pokreni** za pokretanje oglednog projekta.
1. Pregledajte događaje u svom radnom prostoru.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
