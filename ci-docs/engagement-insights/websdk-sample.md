---
title: Pokretanje web SDK uzorka
description: Saznajte kako personalizirati i pokrenuti web SDK uzorak.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225322"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Pokretanje web SDK uzorka za mogućnost uvida u angažman servisa Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Web SDK biblioteka mogućnosti uvida u angažman je JavaScript biblioteka s uzorkom koda koji možete koristiti na svojem web-mjestu.

## <a name="prerequisites"></a>Preduvjeti

- Instalirajte [Visual Studio Code](https://code.visualstudio.com/).
- [Instalirajte proširenje Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) u alatu Visual Studio Code i upoznajte se s pokretanjem proširenja Live Server.
- Morate imati [radni prostor uvida u angažman](create-workspace.md).

## <a name="run-sample"></a>Pokretanje uzorka

1. [Preuzmite web SDK uzorak](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Raspakirajte komprimiranu datoteku `ei_websdk_sample.zip`.

1. Otvorite raspakiranu mapu u alatu Visual Studio Code.

1. Idite na portal uvida u angažman za svoj radni prostor. Odaberite **Administrator** > **Radni prostor** te **Vodič za instalaciju**. Slijedite prvu opciju i odaberite **Kopiraj kôd** za kopiranje isječka koda funkcije JavaScript.

1. U datoteci `ei_websdk_sample.html` zalijepite isječak koda koji ste upravo kopirali u ovaj redak:

   - <-- ZALIJEPITE ISJEČAK KODA JAVASCRIPT S PORTALA UVIDA U ANGAŽMAN ISPOD OVOG RETKA -->

1. Otvorite datoteku `ei_websdk_sample.html` pomoću proširenja Live Server u alatu Visual Studio Code odabirom mogućnosti **Emitiraj uživo** iz trake stanja.

1. Prilikom otvaranja stranice bi se događaj pregleda trebao poslati automatski. Klikom na bilo koji od gumba na stranici poslat će se akcijski događaji. Gumb **Praćenje događaja** također će poslati prilagođene događaje. Odabir gumba **Idi na Bing** će poslati akcijski događaj prije otvaranja web-mjesta Bing.

1. Pogledajte događaje koji teku tijekom navigacije do vašeg radnog prostora. Ovaj je radni prostor povezan s ključem za unos unesenim u koraku 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
