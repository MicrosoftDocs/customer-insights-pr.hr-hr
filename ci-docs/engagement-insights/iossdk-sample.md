---
title: Pokretanje iOS SDK uzorka
description: Uzorak projekta za učenje o iOS SDK-u
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036819"
---
# <a name="run-the-ios-sdk-sample"></a>Pokretanje iOS SDK uzorka

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovaj uzorak iOS projekta pomaže vam razumjeti kako SDK radi u aplikaciji. Ne morate programirati. Samo dodajte ključ za unošenje i odmah ćete vidjeti događaje u svom radnom prostoru.

## <a name="prerequisites"></a>Preduvjeti

- [Xcode verzije 9+](https://developer.apple.com/xcode/downloads/)
- [Ključ za unošenje](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Preuzimanje iOS SDK uzorka

1. [Preuzimanje iOS SDK uzorka za uvide o angažmanu](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Raspakirajte komprimiranu datoteku `ei-ios-sample.zip`.
1. Otvorite ogledni projekt aplikacije u Xcodeu.
1. U datoteci `EIConfig.plist` niz `“YOUR-INGESTION-KEY”` u polju `ingestionKey` zamijenite ključem za unošenje radnog prostora iz uvida o angažmanu na lokaciji **Administrator** > **Radni prostor** > **Vodič za instalaciju**.
1. Odaberite **Pokreni** za pokretanje oglednog projekta.
1. Pregledajte događaje u svom radnom prostoru.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
