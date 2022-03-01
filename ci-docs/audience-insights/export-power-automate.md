---
title: Poveznik programa Power Automate | Microsoft Docs
description: Stvaranje tijekova u povezniku Microsoft Power Automate iz usluge Dynamics 365 Customer Insights,
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405294"
---
# <a name="power-automate-connector-preview"></a>Poveznik Power Automate (pretpregled)

Postavite okidač da se određeni događaji dogode automatski kada se podaci promijene i upravljajte složenijim tijekovima izravno u servisu [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate okidači

Možete koristiti razne okidače koji vam omogućuju stvarati protoke u cilju automatizacije ponavljajućih zadataka, poput obavijesti ili naprednijih radnji. 

- Okidanje kad osvježavanje izvora podataka ne uspije. 
- Okidanje kad osvježavanje izvora podataka uspije.
- Okidanje kad se prijeđe prag na segmentu. Okidanje je ograničeno na prelazak preko praga.
- Okidanje kad se prijeđe prag na poslovnoj mjeri. Okidanje je ograničeno na prelazak preko praga.
- Okidanje kada se dovrši poptpuno osvježavanje (izvora podataka, segmenata, mjera...).
- Uključi se kada završi osvježavanje postupka objedinjavanja (mapiranje, podudaranje, spajanje).

[Konfigurirajte okidače u aplikaciji Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Radnje u aplikaciji Power Automate
Poveznik aplikacije Power Automate pruža druge radnje u odnosu na dostupne okidače. Dodatne informacije potražite na [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Stvaranje tijeka servisa Power Automate u uvidima u ciljnu skupinu

1. U uvidima u ciljnu skupinu idite na **Administrator** > **Sustav**.

1. Na stranici **Sustav** odaberite karticu **Status**.

1. U odjeljku **Izvori podataka** odaberite **Tijekovi** i odaberite **Stvori tijek** s padajućeg popisa.
   > [!div class="mx-imgBorder"]
   > ![Poveznik Power Automate prikazuje radnju Stvaranje tijeka](media/power-automate-connector-create-flow.png "Poveznik Power Automate prikazuje radnju Stvaranje tijeka")

1. U servisu Power Automate odaberite jedan od dostupnih okidača kako biste stvorili željeni tijek. Ako stvarate svoj prvi tijek, morate prvo provjeriti autentičnost uz poveznik Power Automate.
