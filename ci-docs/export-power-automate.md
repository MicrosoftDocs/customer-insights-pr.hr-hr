---
title: Power Automate poveznik (pretpregled) | Microsoftovi dokumenti
description: Stvorite tokove u servisu Microsoft Power Automate iz rješenja Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196109"
---
# <a name="power-automate-connector-preview"></a>Poveznik Power Automate (pretpregled)

Postavite okidač da se određeni događaji dogode automatski kada se podaci promijene i upravljajte složenijim tijekovima izravno u servisu [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Poznata ograničenja

- Najviše 100 poziva u 60 sekundi. [Koristite parametar](/connectors/customerinsights/#get-items-from-an-entity) $skip za pozivanje API-ja krajnja točka više puta.

## <a name="power-automate-triggers"></a>Power Automate okidači

Koristite okidače za stvaranje tokova oblaka i automatizaciju ponavljajućih zadataka, kao što su obavijesti ili naprednije mogućnosti. Okidače koristite kada:

- Osvježavanje izvor podataka ne uspijeva.
- Izvor podataka osvježavanje uspijeva.
- Prag se prelazi na segmentu. Okidanje je ograničeno na prelazak preko praga.
- Na poslovnoj mjeri prelazi se prag. Podržane su samo poslovne mjere bez dimenzija. Okidanje je ograničeno na prelazak preko praga.
- Potpuno zakazano osvježavanje je dovršeno. Okidač ne radi za ručno pokrenuta osvježavanja.
- Dovršeno je osvježavanje postupka ujedinjenja.

[Konfigurirajte okidače u aplikaciji Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Radnje u aplikaciji Power Automate

Poveznik aplikacije Power Automate pruža druge radnje u odnosu na dostupne okidače. Dodatne informacije potražite na [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Stvori tijek Power Automate

1. Idite na **Admin** > **Veze**.

1. Na pločici **Power Automate** odaberite **Postavi**.

1. Otvara se poveznik za Customer Insights (pretpregled) u usluzi Power Automate. **Prijavite se** u uslugu Power Automate.

1. Odaberite jedan od dostupnih okidača i dodajte više koraka svojem novom tijeku. Za dodatne informacije pogledajte [Stvaranje toka oblaka u Power Automate](/power-automate/get-started-logic-flow).

Primjeri upotrebe tokova: 
- Pošaljite poruku na kanal Microsoft Teams ako ne uspije osvježavanje izvora podataka . 
- Pošaljite e-poštu vlasnicima podataka kada se prijeđe prag na segmentu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
