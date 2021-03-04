---
title: Poveznik programa Power Automate | Microsoft Docs
description: Stvaranje tijekova u povezniku Microsoft Power Automate iz usluge Dynamics 365 Customer Insights,
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268815"
---
# <a name="power-automate-connector-preview"></a>Poveznik Power Automate (pretpregled)

Postavite okidač da se određeni događaji dogode automatski kada se podaci promijene i upravljajte složenijim tijekovima izravno u servisu [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate okidači

Koristite okidače za stvaranje tokova oblaka i automatizaciju ponavljajućih zadataka, kao što su obavijesti ili naprednije mogućnosti. 

- Okidanje kad osvježavanje izvora podataka ne uspije. 
- Okidanje kad osvježavanje izvora podataka uspije.
- Okidanje kad se prijeđe prag na segmentu. Okidanje je ograničeno na prelazak preko praga.
- Okidanje kad se prijeđe prag na poslovnoj mjeri. Okidanje je ograničeno na prelazak preko praga.
- Okidanje kada se dovrši poptpuno osvježavanje (izvora podataka, segmenata, mjera...).
- Uključi se kada završi osvježavanje postupka objedinjavanja (mapiranje, podudaranje, spajanje).

[Konfigurirajte okidače u aplikaciji Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Radnje u aplikaciji Power Automate
Poveznik aplikacije Power Automate pruža druge radnje u odnosu na dostupne okidače. Dodatne informacije potražite na [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Stvori tijek Power Automate

1. U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.

1. Na pločici **Power Automate** odaberite **Postavi**.

1. Otvara se poveznik za Customer Insights (pretpregled) u usluzi Power Automate. **Prijavite se** u uslugu Power Automate.

1. Odaberite jedan od dostupnih okidača i dodajte više koraka svojem novom tijeku. Za dodatne informacije pogledajte [Stvaranje toka oblaka u Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).

Primjeri korištenja tijekova: 
- Pošaljite poruku na kanal Microsoft Teams ako ne uspije osvježavanje izvora podataka . 
- Pošaljite e-poštu vlasnicima podataka kada se prijeđe prag na segmentu.



[!INCLUDE[footer-include](../includes/footer-banner.md)]