---
title: Upotreba izvora podataka za unos podataka
description: Saznajte način uvoza podataka iz različitih izvora.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 68aa1b56fb634da80a0c64db72f778d57507104d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269689"
---
# <a name="data-sources-overview"></a><span data-ttu-id="67365-103">Pregled izvora podataka</span><span class="sxs-lookup"><span data-stu-id="67365-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="67365-104">Mogućnost uvida u ciljnu skupinu na platformi Dynamics 365 Customer Insights povezuje se s podacima iz širokog skupa izvora.</span><span class="sxs-lookup"><span data-stu-id="67365-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="67365-105">Povezivanje s izvorom podataka često se naziva postupkom *gutanja podataka*.</span><span class="sxs-lookup"><span data-stu-id="67365-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="67365-106">Nakon unosa podataka, možete ih [ujediniti](data-unification.md) i na njima raditi.</span><span class="sxs-lookup"><span data-stu-id="67365-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="67365-107">Dodaj izvor podataka</span><span class="sxs-lookup"><span data-stu-id="67365-107">Add a data source</span></span>

<span data-ttu-id="67365-108">Pogledajte iscrpne članke o načinu dodavanja izvora podataka, ovisno o odabranoj mogućnosti.</span><span class="sxs-lookup"><span data-stu-id="67365-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="67365-109">Izvor podataka možete dodati na tri osnovna načina:</span><span class="sxs-lookup"><span data-stu-id="67365-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="67365-110">Putem desetaka poveznika aplikacije Power Query</span><span class="sxs-lookup"><span data-stu-id="67365-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="67365-111">Iz mape Common Data Model</span><span class="sxs-lookup"><span data-stu-id="67365-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="67365-112">Iz svog vlastitog jezera aplikacije Common Data Service</span><span class="sxs-lookup"><span data-stu-id="67365-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="67365-113">Još uvijek ne možete dodati podatke iz lokalnih izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="67365-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="67365-114">Pregled unijetih podataka</span><span class="sxs-lookup"><span data-stu-id="67365-114">Review ingested data</span></span>

<span data-ttu-id="67365-115">Vidjet ćete naziv svakog unijetog izvor podataka, njegov status i zadnji put kada su podaci iz tog izvora osvježavani.</span><span class="sxs-lookup"><span data-stu-id="67365-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="67365-116">Popis izvora podataka možete sortirati prema svakom stupcu.</span><span class="sxs-lookup"><span data-stu-id="67365-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="67365-117">![Dodan je izvor podataka](media/configure-data-datasource-added.png "Dodan je izvor podataka")</span><span class="sxs-lookup"><span data-stu-id="67365-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="67365-118">Stanje</span><span class="sxs-lookup"><span data-stu-id="67365-118">Status</span></span>  |<span data-ttu-id="67365-119">Opis</span><span class="sxs-lookup"><span data-stu-id="67365-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="67365-120">Uspješno</span><span class="sxs-lookup"><span data-stu-id="67365-120">Successful</span></span>   |<span data-ttu-id="67365-121">Izvor podataka je uspješno unesen ako je u stupcu **Osvježeno** navedeno vrijeme.</span><span class="sxs-lookup"><span data-stu-id="67365-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="67365-122">Nije pokrenuto</span><span class="sxs-lookup"><span data-stu-id="67365-122">Not started</span></span>   |<span data-ttu-id="67365-123">Izvor podataka još nema unesenih podataka ili je još uvijek u načinu skice.</span><span class="sxs-lookup"><span data-stu-id="67365-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="67365-124">Osvježavanje</span><span class="sxs-lookup"><span data-stu-id="67365-124">Refreshing</span></span>    |<span data-ttu-id="67365-125">U tijeku je unos podataka.</span><span class="sxs-lookup"><span data-stu-id="67365-125">Data ingestion is in progress.</span></span> <span data-ttu-id="67365-126">Ovu operaciju možete otkazati tako da odaberete **Prekini osvježavanje** u stupcu **Radnje**.</span><span class="sxs-lookup"><span data-stu-id="67365-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="67365-127">Ako prekinete osvježavanje, izvor podataka vratit će se na posljednje stanje osvježavanja.</span><span class="sxs-lookup"><span data-stu-id="67365-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="67365-128">Neuspjelo</span><span class="sxs-lookup"><span data-stu-id="67365-128">Failed</span></span>     |<span data-ttu-id="67365-129">Došlo je do pogreške pri unosu podataka.</span><span class="sxs-lookup"><span data-stu-id="67365-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="67365-130">Odaberite vrijednost u stupcu **Status** bilo kojeg izvora podataka za pregled više pojedinosti.</span><span class="sxs-lookup"><span data-stu-id="67365-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="67365-131">U oknu **Pojedinosti o napretku** proširite **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="67365-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="67365-132">Odaberite **Vidi pojedinosti** za više podataka o statusu osvježavanja, uključujući pojedinosti o pogreškama i ažuriranjima završnih procesa.</span><span class="sxs-lookup"><span data-stu-id="67365-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="67365-133">Učitavanje podataka može potrajati.</span><span class="sxs-lookup"><span data-stu-id="67365-133">Loading data can take some time.</span></span> <span data-ttu-id="67365-134">Nakon uspješnog osvježavanja umetnuti podaci mogu se pregledati na stranici **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="67365-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="67365-135">Dodatne informacije potražite u odjeljku [Entiteti](entities.md).</span><span class="sxs-lookup"><span data-stu-id="67365-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="67365-136">Osvježavanje izvora podataka</span><span class="sxs-lookup"><span data-stu-id="67365-136">Refresh a data source</span></span>

<span data-ttu-id="67365-137">Izvori podataka mogu se osvježiti prema automatskom rasporedu ili ručno na zahtjev.</span><span class="sxs-lookup"><span data-stu-id="67365-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="67365-138">Idite u odjeljak **Administrator** > **Sustav** > [**Raspored**](system.md#schedule-tab) za konfiguriranje zakazanih osvježavanja svih unesenih izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="67365-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="67365-139">Da biste osvježili izvor podataka na zahtjev, slijedite korake u nastavku:</span><span class="sxs-lookup"><span data-stu-id="67365-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="67365-140">U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**</span><span class="sxs-lookup"><span data-stu-id="67365-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="67365-141">Odaberite vertikalnu elipsu pored izvora podataka koji želite osvježiti i s padajućeg popisa odaberite **Osvježavanje**.</span><span class="sxs-lookup"><span data-stu-id="67365-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="67365-142">Izvor podataka sada se pokreće za ručno osvježavanje.</span><span class="sxs-lookup"><span data-stu-id="67365-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="67365-143">Osvježavanjem izvora podataka ažurirat će se i shema entiteta, kao i podaci za sve entitete navedene u izvoru podataka.</span><span class="sxs-lookup"><span data-stu-id="67365-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="67365-144">Odaberite **Zaustavljanje osvježavanja** ako želite otkazati postojeće osvježavanje i izvor podataka će se vratiti na posljednji status osvježavanja.</span><span class="sxs-lookup"><span data-stu-id="67365-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="67365-145">Brisanje izvora podataka</span><span class="sxs-lookup"><span data-stu-id="67365-145">Delete a data source</span></span>

1. <span data-ttu-id="67365-146">U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="67365-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="67365-147">Odaberite okomitu trotočku pored izvora podataka koju želite ukloniti i odaberite **Izbriši** iz padajućeg izbornika.</span><span class="sxs-lookup"><span data-stu-id="67365-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="67365-148">Potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="67365-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]