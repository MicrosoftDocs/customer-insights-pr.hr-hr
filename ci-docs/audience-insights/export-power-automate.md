---
title: Poveznik programa Power Automate | Microsoft Docs
description: Stvorite tokove u servisu Microsoft Power Automate iz rješenja Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976079"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="1b5d4-103">Poveznik Power Automate (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="1b5d4-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="1b5d4-104">Postavite okidač da se određeni događaji dogode automatski kada se podaci promijene i upravljajte složenijim tijekovima izravno u servisu [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="1b5d4-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="1b5d4-105">Power Automate okidači</span><span class="sxs-lookup"><span data-stu-id="1b5d4-105">Power Automate triggers</span></span>

<span data-ttu-id="1b5d4-106">Koristite okidače za stvaranje tokova oblaka i automatizaciju ponavljajućih zadataka, kao što su obavijesti ili naprednije mogućnosti.</span><span class="sxs-lookup"><span data-stu-id="1b5d4-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="1b5d4-107">Okidanje kad osvježavanje izvora podataka ne uspije.</span><span class="sxs-lookup"><span data-stu-id="1b5d4-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="1b5d4-108">Okidanje kad osvježavanje izvora podataka uspije.</span><span class="sxs-lookup"><span data-stu-id="1b5d4-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="1b5d4-109">Okidanje kad se prijeđe prag na segmentu.</span><span class="sxs-lookup"><span data-stu-id="1b5d4-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="1b5d4-110">Okidanje je ograničeno na prelazak preko praga.</span><span class="sxs-lookup"><span data-stu-id="1b5d4-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="1b5d4-111">Okidanje kad se prijeđe prag na poslovnoj mjeri.</span><span class="sxs-lookup"><span data-stu-id="1b5d4-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="1b5d4-112">Podržane su samo poslovne mjere bez dimenzija.</span><span class="sxs-lookup"><span data-stu-id="1b5d4-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="1b5d4-113">Okidanje je ograničeno na prelazak preko praga.</span><span class="sxs-lookup"><span data-stu-id="1b5d4-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="1b5d4-114">Okidanje kada se dovrši poptpuno osvježavanje (izvora podataka, segmenata, mjera...).</span><span class="sxs-lookup"><span data-stu-id="1b5d4-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="1b5d4-115">Uključi se kada završi osvježavanje postupka objedinjavanja (mapiranje, podudaranje, spajanje).</span><span class="sxs-lookup"><span data-stu-id="1b5d4-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="1b5d4-116">[Konfigurirajte okidače u aplikaciji Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="1b5d4-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="1b5d4-117">Radnje u aplikaciji Power Automate</span><span class="sxs-lookup"><span data-stu-id="1b5d4-117">Power Automate actions</span></span>
<span data-ttu-id="1b5d4-118">Poveznik aplikacije Power Automate pruža druge radnje u odnosu na dostupne okidače.</span><span class="sxs-lookup"><span data-stu-id="1b5d4-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="1b5d4-119">Dodatne informacije potražite na [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="1b5d4-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="1b5d4-120">Stvori tijek Power Automate</span><span class="sxs-lookup"><span data-stu-id="1b5d4-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="1b5d4-121">U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.</span><span class="sxs-lookup"><span data-stu-id="1b5d4-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1b5d4-122">Na pločici **Power Automate** odaberite **Postavi**.</span><span class="sxs-lookup"><span data-stu-id="1b5d4-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="1b5d4-123">Otvara se poveznik za Customer Insights (pretpregled) u usluzi Power Automate.</span><span class="sxs-lookup"><span data-stu-id="1b5d4-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="1b5d4-124">**Prijavite se** u uslugu Power Automate.</span><span class="sxs-lookup"><span data-stu-id="1b5d4-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="1b5d4-125">Odaberite jedan od dostupnih okidača i dodajte više koraka svojem novom tijeku.</span><span class="sxs-lookup"><span data-stu-id="1b5d4-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="1b5d4-126">Za dodatne informacije pogledajte [Stvaranje toka oblaka u Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="1b5d4-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="1b5d4-127">Primjeri korištenja tijekova:</span><span class="sxs-lookup"><span data-stu-id="1b5d4-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="1b5d4-128">Pošaljite poruku na kanal Microsoft Teams ako ne uspije osvježavanje izvora podataka .</span><span class="sxs-lookup"><span data-stu-id="1b5d4-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="1b5d4-129">Pošaljite e-poštu vlasnicima podataka kada se prijeđe prag na segmentu.</span><span class="sxs-lookup"><span data-stu-id="1b5d4-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
