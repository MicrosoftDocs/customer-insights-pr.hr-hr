---
title: Pokretanje web SDK uzorka
description: Saznajte kako personalizirati i pokrenuti web SDK uzorak.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606189"
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
