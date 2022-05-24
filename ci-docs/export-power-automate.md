---
title: Poveznik programa Power Automate | Microsoft Docs
description: Stvorite tokove u servisu Microsoft Power Automate iz rješenja Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d22c4c785695b23a257a89f1ffa519fdc18b443e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741170"
---
# <a name="power-automate-connector-preview"></a>Poveznik Power Automate (pretpregled)

Postavite okidač da se određeni događaji dogode automatski kada se podaci promijene i upravljajte složenijim tijekovima izravno u servisu [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Poznata ograničenja

- Možete obaviti najviše 100 poziva u 60 sekundi. API možete nazvati krajnja točka više puta pomoću parametra $skip. [Saznajte više o parametru $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Power Automate okidači

Koristite okidače za stvaranje tokova oblaka i automatizaciju ponavljajućih zadataka, kao što su obavijesti ili naprednije mogućnosti.

- Okidanje kad osvježavanje izvora podataka ne uspije.
- Okidanje kad osvježavanje izvora podataka uspije.
- Okidanje kad se prijeđe prag na segmentu. Okidanje je ograničeno na prelazak preko praga.
- Okidanje kad se prijeđe prag na poslovnoj mjeri. Podržane su samo poslovne mjere bez dimenzija. Okidanje je ograničeno na prelazak preko praga.
- Okidanje kada se dovrši potpuno osvježavanje (izvora podataka, segmenata, mjera...).
- Aktivirajte se kada se dovrši osvježavanje postupka ujedinjenja.

[Konfigurirajte okidače u aplikaciji Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Radnje u aplikaciji Power Automate

Poveznik aplikacije Power Automate pruža druge radnje u odnosu na dostupne okidače. Dodatne informacije potražite na [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Stvori tijek Power Automate

1. Otvorite **Administrator** > **Izvozna odredišta**.

1. Na pločici **Power Automate** odaberite **Postavi**.

1. Otvara se poveznik za Customer Insights (pretpregled) u usluzi Power Automate. **Prijavite se** u uslugu Power Automate.

1. Odaberite jedan od dostupnih okidača i dodajte više koraka svojem novom tijeku. Za dodatne informacije pogledajte [Stvaranje toka oblaka u Power Automate](/power-automate/get-started-logic-flow).

Primjeri upotrebe tokova: 
- Pošaljite poruku na kanal Microsoft Teams ako ne uspije osvježavanje izvora podataka . 
- Pošaljite e-poštu vlasnicima podataka kada se prijeđe prag na segmentu.



[!INCLUDE [footer-include](includes/footer-banner.md)]
