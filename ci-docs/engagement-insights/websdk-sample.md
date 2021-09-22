---
title: Pokretanje web SDK uzorka
description: Saznajte kako personalizirati i pokrenuti web SDK uzorak.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036594"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Pokretanje web SDK uzorka za mogućnost uvida u angažman servisa Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Web SDK biblioteka mogućnosti uvida u angažman je JavaScript biblioteka s uzorkom koda koji možete koristiti na svojem web-mjestu.

## <a name="prerequisites"></a>Preduvjeti

- Instalirajte [Visual Studio Code](https://code.visualstudio.com/).
- [Instalirajte proširenje Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) u alatu Visual Studio Code i upoznajte se s pokretanjem proširenja Live Server.
- Morate imati [ključ za unos](instrument-website.md).

## <a name="run-sample"></a>Pokretanje uzorka

1. [Preuzmite web SDK uzorak](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Raspakirajte komprimiranu datoteku `ei_websdk_sample.zip`.

1. Otvorite raspakiranu mapu u alatu Visual Studio Code.

1. U datoteci `ei_websdk_sample.html` zamijenite niz "INGESTION_KEY" svojim ključem za unos s portala mogućnosti uvida u angažman, a niz "NAME" globalnim nazivom za koji želite da SDK bude instanciran. Obavezno zamijenite sve slučajeve.

1. Otvorite datoteku `ei_websdk_sample.html` pomoću proširenja Live Server u alatu Visual Studio Code odabirom mogućnosti **Emitiraj uživo** iz trake stanja.

1. Prilikom otvaranja stranice bi se događaj pregleda trebao poslati automatski. Klikom na bilo koji od gumba na stranici poslat će se akcijski događaji. Gumb **Praćenje događaja** također će poslati prilagođene događaje. Odabir gumba **Idi na Bing** će poslati akcijski događaj prije otvaranja web-mjesta Bing.

1. Pogledajte događaje koji teku tijekom navigacije do vašeg radnog prostora. Ovaj je radni prostor povezan s ključem za unos unesenim u koraku 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]