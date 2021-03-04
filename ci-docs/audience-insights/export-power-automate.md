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
# <a name="power-automate-connector-preview"></a><span data-ttu-id="fdd2a-103">Poveznik Power Automate (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="fdd2a-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="fdd2a-104">Postavite okidač da se određeni događaji dogode automatski kada se podaci promijene i upravljajte složenijim tijekovima izravno u servisu [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="fdd2a-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="fdd2a-105">Power Automate okidači</span><span class="sxs-lookup"><span data-stu-id="fdd2a-105">Power Automate triggers</span></span>

<span data-ttu-id="fdd2a-106">Koristite okidače za stvaranje tokova oblaka i automatizaciju ponavljajućih zadataka, kao što su obavijesti ili naprednije mogućnosti.</span><span class="sxs-lookup"><span data-stu-id="fdd2a-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="fdd2a-107">Okidanje kad osvježavanje izvora podataka ne uspije.</span><span class="sxs-lookup"><span data-stu-id="fdd2a-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="fdd2a-108">Okidanje kad osvježavanje izvora podataka uspije.</span><span class="sxs-lookup"><span data-stu-id="fdd2a-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="fdd2a-109">Okidanje kad se prijeđe prag na segmentu.</span><span class="sxs-lookup"><span data-stu-id="fdd2a-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="fdd2a-110">Okidanje je ograničeno na prelazak preko praga.</span><span class="sxs-lookup"><span data-stu-id="fdd2a-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="fdd2a-111">Okidanje kad se prijeđe prag na poslovnoj mjeri.</span><span class="sxs-lookup"><span data-stu-id="fdd2a-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="fdd2a-112">Okidanje je ograničeno na prelazak preko praga.</span><span class="sxs-lookup"><span data-stu-id="fdd2a-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="fdd2a-113">Okidanje kada se dovrši poptpuno osvježavanje (izvora podataka, segmenata, mjera...).</span><span class="sxs-lookup"><span data-stu-id="fdd2a-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="fdd2a-114">Uključi se kada završi osvježavanje postupka objedinjavanja (mapiranje, podudaranje, spajanje).</span><span class="sxs-lookup"><span data-stu-id="fdd2a-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="fdd2a-115">[Konfigurirajte okidače u aplikaciji Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="fdd2a-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="fdd2a-116">Radnje u aplikaciji Power Automate</span><span class="sxs-lookup"><span data-stu-id="fdd2a-116">Power Automate actions</span></span>
<span data-ttu-id="fdd2a-117">Poveznik aplikacije Power Automate pruža druge radnje u odnosu na dostupne okidače.</span><span class="sxs-lookup"><span data-stu-id="fdd2a-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="fdd2a-118">Dodatne informacije potražite na [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="fdd2a-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="fdd2a-119">Stvori tijek Power Automate</span><span class="sxs-lookup"><span data-stu-id="fdd2a-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="fdd2a-120">U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.</span><span class="sxs-lookup"><span data-stu-id="fdd2a-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fdd2a-121">Na pločici **Power Automate** odaberite **Postavi**.</span><span class="sxs-lookup"><span data-stu-id="fdd2a-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="fdd2a-122">Otvara se poveznik za Customer Insights (pretpregled) u usluzi Power Automate.</span><span class="sxs-lookup"><span data-stu-id="fdd2a-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="fdd2a-123">**Prijavite se** u uslugu Power Automate.</span><span class="sxs-lookup"><span data-stu-id="fdd2a-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="fdd2a-124">Odaberite jedan od dostupnih okidača i dodajte više koraka svojem novom tijeku.</span><span class="sxs-lookup"><span data-stu-id="fdd2a-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="fdd2a-125">Za dodatne informacije pogledajte [Stvaranje toka oblaka u Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="fdd2a-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="fdd2a-126">Primjeri korištenja tijekova:</span><span class="sxs-lookup"><span data-stu-id="fdd2a-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="fdd2a-127">Pošaljite poruku na kanal Microsoft Teams ako ne uspije osvježavanje izvora podataka .</span><span class="sxs-lookup"><span data-stu-id="fdd2a-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="fdd2a-128">Pošaljite e-poštu vlasnicima podataka kada se prijeđe prag na segmentu.</span><span class="sxs-lookup"><span data-stu-id="fdd2a-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]