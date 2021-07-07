---
title: Poveznik programa Power Automate | Microsoft Docs
description: Stvorite tokove u servisu Microsoft Power Automate iz rješenja Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305055"
---
# <a name="power-automate-connector-preview"></a>Poveznik Power Automate (pretpregled)

Postavite okidač da se određeni događaji dogode automatski kada se podaci promijene i upravljajte složenijim tijekovima izravno u servisu [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate okidači

Koristite okidače za stvaranje tokova oblaka i automatizaciju ponavljajućih zadataka, kao što su obavijesti ili naprednije mogućnosti. 

- Okidanje kad osvježavanje izvora podataka ne uspije. 
- Okidanje kad osvježavanje izvora podataka uspije.
- Okidanje kad se prijeđe prag na segmentu. Okidanje je ograničeno na prelazak preko praga.
- Okidanje kad se prijeđe prag na poslovnoj mjeri. Podržane su samo poslovne mjere bez dimenzija. Okidanje je ograničeno na prelazak preko praga.
- Okidanje kada se dovrši potpuno osvježavanje (izvora podataka, segmenata, mjera...).
- Uključi se kada završi osvježavanje postupka objedinjavanja (mapiranje, podudaranje, spajanje).

[Konfigurirajte okidače u aplikaciji Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Radnje u aplikaciji Power Automate

Poveznik aplikacije Power Automate pruža druge radnje u odnosu na dostupne okidače. Dodatne informacije potražite na [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Stvori tijek Power Automate

1. U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.

1. Na pločici **Power Automate** odaberite **Postavi**.

1. Otvara se poveznik za Customer Insights (pretpregled) u usluzi Power Automate. **Prijavite se** u uslugu Power Automate.

1. Odaberite jedan od dostupnih okidača i dodajte više koraka svojem novom tijeku. Za dodatne informacije pogledajte [Stvaranje toka oblaka u Power Automate](/power-automate/get-started-logic-flow).

Primjeri upotrebe tokova: 
- Pošaljite poruku na kanal Microsoft Teams ako ne uspije osvježavanje izvora podataka . 
- Pošaljite e-poštu vlasnicima podataka kada se prijeđe prag na segmentu.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
