---
title: Upotreba izvora podataka za unos podataka
description: Saznajte način uvoza podataka iz različitih izvora.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085521"
---
# <a name="data-sources-overview"></a><span data-ttu-id="7b591-103">Pregled izvora podataka</span><span class="sxs-lookup"><span data-stu-id="7b591-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="7b591-104">Mogućnost uvida u ciljnu skupinu na platformi Dynamics 365 Customer Insights povezuje se s podacima iz širokog skupa izvora.</span><span class="sxs-lookup"><span data-stu-id="7b591-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="7b591-105">Povezivanje s izvorom podataka često se naziva postupkom *gutanja podataka*.</span><span class="sxs-lookup"><span data-stu-id="7b591-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="7b591-106">Nakon unosa podataka, možete ih [ujediniti](data-unification.md) i na njima raditi.</span><span class="sxs-lookup"><span data-stu-id="7b591-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="7b591-107">Dodaj izvor podataka</span><span class="sxs-lookup"><span data-stu-id="7b591-107">Add a data source</span></span>

<span data-ttu-id="7b591-108">Pogledajte iscrpne članke o načinu dodavanja izvora podataka, ovisno o odabranoj mogućnosti.</span><span class="sxs-lookup"><span data-stu-id="7b591-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="7b591-109">Izvor podataka možete dodati na tri osnovna načina:</span><span class="sxs-lookup"><span data-stu-id="7b591-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="7b591-110">Putem desetaka poveznika aplikacije Power Query</span><span class="sxs-lookup"><span data-stu-id="7b591-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="7b591-111">Iz mape Common Data Model</span><span class="sxs-lookup"><span data-stu-id="7b591-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="7b591-112">Iz svog vlastitog jezera aplikacije Common Data Service</span><span class="sxs-lookup"><span data-stu-id="7b591-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="7b591-113">Dodavanje podataka iz lokalnih izvora podataka</span><span class="sxs-lookup"><span data-stu-id="7b591-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="7b591-114">Unošenje podataka iz lokalnih izvora podataka u Audience Insights podržano je na temelju tijekova podataka platforme Power Platform.</span><span class="sxs-lookup"><span data-stu-id="7b591-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="7b591-115">Tijekovi podataka mogu se omogućiti u Customer Insights pomoću [pružanja URL-a okruženja Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) prilikom postavljanja okruženja.</span><span class="sxs-lookup"><span data-stu-id="7b591-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="7b591-116">Izvori podataka koji se stvaraju nakon pridruživanja okruženja Dataverse uz Customer Insights koristit će [Power Platform tijekove podataka](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) prema zadanim postavkama.</span><span class="sxs-lookup"><span data-stu-id="7b591-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="7b591-117">Tijekovi podataka podržavaju lokalnu povezivost pomoću pristupnika za podatke.</span><span class="sxs-lookup"><span data-stu-id="7b591-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="7b591-118">Uklonite i ponovno stvorite izvore podataka koji su postojali prije nego je okruženje Dataverse bilo povezano za [korištenje lokalnih pristupnika za podatke](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="7b591-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="7b591-119">Pristupnici za podatke iz postojećeg okruženja Power BI ili Power Apps bit će vidljivi i možete ih ponovno koristiti u Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7b591-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="7b591-120">Stranica izvora podataka prikazuje veze do okruženja Power Platform u kojem možete pregledavati i konfigurirati lokalne pristupnike za podatke.</span><span class="sxs-lookup"><span data-stu-id="7b591-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="7b591-121">Pregled unijetih podataka</span><span class="sxs-lookup"><span data-stu-id="7b591-121">Review ingested data</span></span>

<span data-ttu-id="7b591-122">Vidjet ćete naziv svakog unijetog izvor podataka, njegov status i zadnji put kada su podaci iz tog izvora osvježavani.</span><span class="sxs-lookup"><span data-stu-id="7b591-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="7b591-123">Popis izvora podataka možete sortirati prema svakom stupcu.</span><span class="sxs-lookup"><span data-stu-id="7b591-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7b591-124">![Dodan je izvor podataka](media/configure-data-datasource-added.png "Dodan je izvor podataka")</span><span class="sxs-lookup"><span data-stu-id="7b591-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="7b591-125">Stanje</span><span class="sxs-lookup"><span data-stu-id="7b591-125">Status</span></span>  |<span data-ttu-id="7b591-126">Opis</span><span class="sxs-lookup"><span data-stu-id="7b591-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="7b591-127">Uspješno</span><span class="sxs-lookup"><span data-stu-id="7b591-127">Successful</span></span>   |<span data-ttu-id="7b591-128">Izvor podataka je uspješno unesen ako je u stupcu **Osvježeno** navedeno vrijeme.</span><span class="sxs-lookup"><span data-stu-id="7b591-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="7b591-129">Nije pokrenuto</span><span class="sxs-lookup"><span data-stu-id="7b591-129">Not started</span></span>   |<span data-ttu-id="7b591-130">Izvor podataka još nema unesenih podataka ili je još uvijek u načinu skice.</span><span class="sxs-lookup"><span data-stu-id="7b591-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="7b591-131">Osvježavanje</span><span class="sxs-lookup"><span data-stu-id="7b591-131">Refreshing</span></span>    |<span data-ttu-id="7b591-132">U tijeku je unos podataka.</span><span class="sxs-lookup"><span data-stu-id="7b591-132">Data ingestion is in progress.</span></span> <span data-ttu-id="7b591-133">Ovu operaciju možete otkazati tako da odaberete **Prekini osvježavanje** u stupcu **Radnje**.</span><span class="sxs-lookup"><span data-stu-id="7b591-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="7b591-134">Ako prekinete osvježavanje, izvor podataka vratit će se na posljednje stanje osvježavanja.</span><span class="sxs-lookup"><span data-stu-id="7b591-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="7b591-135">Neuspjelo</span><span class="sxs-lookup"><span data-stu-id="7b591-135">Failed</span></span>     |<span data-ttu-id="7b591-136">Došlo je do pogreške pri unosu podataka.</span><span class="sxs-lookup"><span data-stu-id="7b591-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="7b591-137">Odaberite vrijednost u stupcu **Status** bilo kojeg izvora podataka za pregled više pojedinosti.</span><span class="sxs-lookup"><span data-stu-id="7b591-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="7b591-138">U oknu **Pojedinosti o napretku** proširite **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="7b591-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="7b591-139">Odaberite **Vidi pojedinosti** za više podataka o statusu osvježavanja, uključujući pojedinosti o pogreškama i ažuriranjima završnih procesa.</span><span class="sxs-lookup"><span data-stu-id="7b591-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="7b591-140">Učitavanje podataka može potrajati.</span><span class="sxs-lookup"><span data-stu-id="7b591-140">Loading data can take some time.</span></span> <span data-ttu-id="7b591-141">Nakon uspješnog osvježavanja umetnuti podaci mogu se pregledati na stranici **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="7b591-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="7b591-142">Dodatne informacije potražite u odjeljku [Entiteti](entities.md).</span><span class="sxs-lookup"><span data-stu-id="7b591-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="7b591-143">Osvježavanje izvora podataka</span><span class="sxs-lookup"><span data-stu-id="7b591-143">Refresh a data source</span></span>

<span data-ttu-id="7b591-144">Izvori podataka mogu se osvježiti prema automatskom rasporedu ili ručno na zahtjev.</span><span class="sxs-lookup"><span data-stu-id="7b591-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="7b591-145">Idite u odjeljak **Administrator** > **Sustav** > [**Raspored**](system.md#schedule-tab) za konfiguriranje zakazanih osvježavanja svih unesenih izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="7b591-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="7b591-146">Da biste osvježili izvor podataka na zahtjev, slijedite korake u nastavku:</span><span class="sxs-lookup"><span data-stu-id="7b591-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="7b591-147">U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**</span><span class="sxs-lookup"><span data-stu-id="7b591-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="7b591-148">Odaberite vertikalnu elipsu pored izvora podataka koji želite osvježiti i s padajućeg popisa odaberite **Osvježavanje**.</span><span class="sxs-lookup"><span data-stu-id="7b591-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="7b591-149">Izvor podataka sada se pokreće za ručno osvježavanje.</span><span class="sxs-lookup"><span data-stu-id="7b591-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="7b591-150">Osvježavanje izvora podataka ažurirat će i shemu entiteta i podatke za sve entitete navedene u izvoru podataka.</span><span class="sxs-lookup"><span data-stu-id="7b591-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="7b591-151">Odaberite **Zaustavljanje osvježavanja** ako želite otkazati postojeće osvježavanje i izvor podataka će se vratiti na posljednji status osvježavanja.</span><span class="sxs-lookup"><span data-stu-id="7b591-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="7b591-152">Brisanje izvora podataka</span><span class="sxs-lookup"><span data-stu-id="7b591-152">Delete a data source</span></span>

1. <span data-ttu-id="7b591-153">U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="7b591-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="7b591-154">Odaberite okomitu trotočku pored izvora podataka koju želite ukloniti i odaberite **Izbriši** iz padajućeg izbornika.</span><span class="sxs-lookup"><span data-stu-id="7b591-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="7b591-155">Potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="7b591-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
