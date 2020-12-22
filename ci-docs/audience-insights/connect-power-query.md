---
title: Unos podataka putem konektora Power Query
description: Poveznici za izvore podataka koji se temelje na platformi Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405318"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="664f3-103">Povezivanje s izvorom podataka platforme Power Query</span><span class="sxs-lookup"><span data-stu-id="664f3-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="664f3-104">Power Query nudi širok skup poveznika za unos podataka.</span><span class="sxs-lookup"><span data-stu-id="664f3-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="664f3-105">Većinu ovih poveznika podržava aplikacija Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="664f3-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="664f3-106">Dodavanje izvora podataka koji se temelje na poveznicima platforme Power Query obično slijedi korake navedene u sljedećem odjeljku.</span><span class="sxs-lookup"><span data-stu-id="664f3-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="664f3-107">Međutim, ovisno o povezniku koji upotrebljavate, potrebni su različiti podaci.</span><span class="sxs-lookup"><span data-stu-id="664f3-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="664f3-108">Dodatne informacije potražite u dokumentaciji o pojedinim poveznicima u odjeljku [Reference poveznika platforme Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="664f3-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="664f3-109">Izrada novog izvora podataka</span><span class="sxs-lookup"><span data-stu-id="664f3-109">Create a new data source</span></span>

1. <span data-ttu-id="664f3-110">U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="664f3-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="664f3-111">Odaberite **Dodaj izvor podataka**.</span><span class="sxs-lookup"><span data-stu-id="664f3-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="664f3-112">Odaberite način **Uvoz podataka** i zatim **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="664f3-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="664f3-113">Navedite **Naziv** izvora podataka i odaberite **Dalje** kako biste stvorili izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="664f3-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="664f3-114">Odaberite jedan od [dostupnih poveznika](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="664f3-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="664f3-115">Za ovaj primjer odabiremo poveznik **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="664f3-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="664f3-116">Unesite potrebne pojedinosti u **Postavke veze** za odabrani poveznike i odaberite **Dalje** kako biste vidjeli pregled podataka.</span><span class="sxs-lookup"><span data-stu-id="664f3-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="664f3-117">Odaberite **Pretvori podatke**.</span><span class="sxs-lookup"><span data-stu-id="664f3-117">Select **Transform data**.</span></span> <span data-ttu-id="664f3-118">U ovom ćete koraku dodati entitete u izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="664f3-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="664f3-119">Entiteti su skupovi podataka.</span><span class="sxs-lookup"><span data-stu-id="664f3-119">Entities are datasets.</span></span> <span data-ttu-id="664f3-120">Ako imate bazu podataka koja sadrži više skupova podataka, svaki je skup podataka vlastiti entitet.</span><span class="sxs-lookup"><span data-stu-id="664f3-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="664f3-121">Dijaloški okvir **Power Query – Uređivanje upita** omogućuje pregled i pročišćavanje podataka.</span><span class="sxs-lookup"><span data-stu-id="664f3-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="664f3-122">Entiteti koje su sustavi identificirali u vašem odabranom izvoru podataka prikazuju se u lijevom oknu.</span><span class="sxs-lookup"><span data-stu-id="664f3-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="664f3-123">![Dijaloški okvir uređivanja upita](media/data-manager-configure-edit-queries.png "Dijaloški okvir uređivanja upita")</span><span class="sxs-lookup"><span data-stu-id="664f3-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="664f3-124">Podatke možete i pretvoriti.</span><span class="sxs-lookup"><span data-stu-id="664f3-124">You can also transform your data.</span></span> <span data-ttu-id="664f3-125">Odaberite entitet koji želite urediti ili pretvoriti.</span><span class="sxs-lookup"><span data-stu-id="664f3-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="664f3-126">Upotrijebite mogućnosti u prozoru platforme Power Query za primjenu pretvorbi.</span><span class="sxs-lookup"><span data-stu-id="664f3-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="664f3-127">Svaka se pretvorba navodi pod stavkom **Primijenjeni koraci**.</span><span class="sxs-lookup"><span data-stu-id="664f3-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="664f3-128">Power Query pruža brojne unaprijed izgrađene mogućnosti pretvorbe.</span><span class="sxs-lookup"><span data-stu-id="664f3-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="664f3-129">Dodatne informacije potražite u odjeljku [Pretvorbe platforme Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="664f3-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="664f3-130">U izvor podataka možete dodati dodatne entitete tako da odaberete **Dohvati podatke** u dijalogu **Uređivanje upita**.</span><span class="sxs-lookup"><span data-stu-id="664f3-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="664f3-131">Preporučene su sljedeće pretvorbe:</span><span class="sxs-lookup"><span data-stu-id="664f3-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="664f3-132">Ako unosite podatke iz CSV datoteke, prvi redak često sadrži zaglavlja.</span><span class="sxs-lookup"><span data-stu-id="664f3-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="664f3-133">Idite na stavku **Tablica pretvorbe** i odaberite mogućnost **Uporaba zaglavlja kao prvog reda**.</span><span class="sxs-lookup"><span data-stu-id="664f3-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="664f3-134">Provjerite je li vrsta podataka postavljena na odgovarajući način.</span><span class="sxs-lookup"><span data-stu-id="664f3-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="664f3-135">Pri dnu prozora platforme Power Query odaberite **Spremi** kako biste spremili pretvorbe.</span><span class="sxs-lookup"><span data-stu-id="664f3-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="664f3-136">Nakon spremanja pronaći ćete svoj izvor podataka u stavci **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="664f3-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="664f3-137">Na stranici **Izvori podataka** primijetit ćete da je novi izvor podataka u statusu **Osvježavanje**.</span><span class="sxs-lookup"><span data-stu-id="664f3-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="664f3-138">Dostupni izvori podataka platforme Power Query</span><span class="sxs-lookup"><span data-stu-id="664f3-138">Available Power Query data sources</span></span>

<span data-ttu-id="664f3-139">Pogledajte članak [Referenca poveznika platforme Power Query](https://docs.microsoft.com/power-query/connectors/) za ažurirani popis poveznika koje možete odabrati za uvoz podataka u aplikaciju Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="664f3-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="664f3-140">Poveznici s kvačicom u stupcu **Customer Insights (tijekovi podataka)** dostupni su za stvaranje novih izvora podataka koji se temelje na platformi Power Query.</span><span class="sxs-lookup"><span data-stu-id="664f3-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="664f3-141">Pregledajte dokumentaciju određenog poveznika kako biste saznali više o njegovim preduvjetima, ograničenjima i ostalim pojedinostima.</span><span class="sxs-lookup"><span data-stu-id="664f3-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="664f3-142">Uređivanje izvora podataka platforme Power Query</span><span class="sxs-lookup"><span data-stu-id="664f3-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="664f3-143">Možda nećete moći izmijeniti izvore podataka koji se trenutačno koriste u jednom od postupaka aplikacije (npr. *segmentacija*, *podudaranje* ili *spajanje*).</span><span class="sxs-lookup"><span data-stu-id="664f3-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="664f3-144">Pomoću stranice **Postavke** možete pratiti napredak pojedinih aktivnih postupaka.</span><span class="sxs-lookup"><span data-stu-id="664f3-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="664f3-145">Kada se postupak dovrši, možete se vratiti na stranicu **Izvori podataka** i unijeti promjene.</span><span class="sxs-lookup"><span data-stu-id="664f3-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="664f3-146">U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="664f3-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="664f3-147">Odaberite okomitu trotočku pored izvora podataka koju želite promijeniti i odaberite **Uredi** iz padajućeg izbornika.</span><span class="sxs-lookup"><span data-stu-id="664f3-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="664f3-148">![Uređivanje mogućnosti](media/edit-option-data-sources.png "Uređivanje mogućnosti")</span><span class="sxs-lookup"><span data-stu-id="664f3-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="664f3-149">Primijenite svoje promjene i pretvorbe u dijaloškom okviru **Power Query – Uređivanje upita** onako kao je opisano u odjeljku [Stvaranje novog izvora podataka](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="664f3-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="664f3-150">Kako biste nakon dovršetka uređivanja spremili promjene na platformu Power Query, odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="664f3-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
