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
# <a name="power-automate-connector-preview"></a><span data-ttu-id="e4130-103">Poveznik Power Automate (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="e4130-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="e4130-104">Postavite okidač da se određeni događaji dogode automatski kada se podaci promijene i upravljajte složenijim tijekovima izravno u servisu [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="e4130-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="e4130-105">Power Automate okidači</span><span class="sxs-lookup"><span data-stu-id="e4130-105">Power Automate triggers</span></span>

<span data-ttu-id="e4130-106">Možete koristiti razne okidače koji vam omogućuju stvarati protoke u cilju automatizacije ponavljajućih zadataka, poput obavijesti ili naprednijih radnji.</span><span class="sxs-lookup"><span data-stu-id="e4130-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="e4130-107">Okidanje kad osvježavanje izvora podataka ne uspije.</span><span class="sxs-lookup"><span data-stu-id="e4130-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="e4130-108">Okidanje kad osvježavanje izvora podataka uspije.</span><span class="sxs-lookup"><span data-stu-id="e4130-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="e4130-109">Okidanje kad se prijeđe prag na segmentu.</span><span class="sxs-lookup"><span data-stu-id="e4130-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="e4130-110">Okidanje je ograničeno na prelazak preko praga.</span><span class="sxs-lookup"><span data-stu-id="e4130-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="e4130-111">Okidanje kad se prijeđe prag na poslovnoj mjeri.</span><span class="sxs-lookup"><span data-stu-id="e4130-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="e4130-112">Okidanje je ograničeno na prelazak preko praga.</span><span class="sxs-lookup"><span data-stu-id="e4130-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="e4130-113">Okidanje kada se dovrši poptpuno osvježavanje (izvora podataka, segmenata, mjera...).</span><span class="sxs-lookup"><span data-stu-id="e4130-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="e4130-114">Uključi se kada završi osvježavanje postupka objedinjavanja (mapiranje, podudaranje, spajanje).</span><span class="sxs-lookup"><span data-stu-id="e4130-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="e4130-115">[Konfigurirajte okidače u aplikaciji Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="e4130-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="e4130-116">Radnje u aplikaciji Power Automate</span><span class="sxs-lookup"><span data-stu-id="e4130-116">Power Automate actions</span></span>
<span data-ttu-id="e4130-117">Poveznik aplikacije Power Automate pruža druge radnje u odnosu na dostupne okidače.</span><span class="sxs-lookup"><span data-stu-id="e4130-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="e4130-118">Dodatne informacije potražite na [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="e4130-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="e4130-119">Stvaranje tijeka servisa Power Automate u uvidima u ciljnu skupinu</span><span class="sxs-lookup"><span data-stu-id="e4130-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="e4130-120">U uvidima u ciljnu skupinu idite na **Administrator** > **Sustav**.</span><span class="sxs-lookup"><span data-stu-id="e4130-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="e4130-121">Na stranici **Sustav** odaberite karticu **Status**.</span><span class="sxs-lookup"><span data-stu-id="e4130-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="e4130-122">U odjeljku **Izvori podataka** odaberite **Tijekovi** i odaberite **Stvori tijek** s padajućeg popisa.</span><span class="sxs-lookup"><span data-stu-id="e4130-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e4130-123">![Poveznik Power Automate prikazuje radnju Stvaranje tijeka](media/power-automate-connector-create-flow.png "Poveznik Power Automate prikazuje radnju Stvaranje tijeka")</span><span class="sxs-lookup"><span data-stu-id="e4130-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="e4130-124">U servisu Power Automate odaberite jedan od dostupnih okidača kako biste stvorili željeni tijek.</span><span class="sxs-lookup"><span data-stu-id="e4130-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="e4130-125">Ako stvarate svoj prvi tijek, morate prvo provjeriti autentičnost uz poveznik Power Automate.</span><span class="sxs-lookup"><span data-stu-id="e4130-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
