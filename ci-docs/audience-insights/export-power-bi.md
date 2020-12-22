---
title: Poveznik za Power BI
description: Saznajte kako upotrebljavati poveznik značajke Dynamics 365 Customer Insights u programu Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405299"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="5aa19-103">Poveznik za Power BI (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="5aa19-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="5aa19-104">Stvorite vizualne prikaze za svoje podatke pomoću usluge Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="5aa19-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="5aa19-105">Generirajte dodatne uvide i izradite izvješća s objedinjenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="5aa19-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5aa19-106">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="5aa19-106">Prerequisites</span></span>

- <span data-ttu-id="5aa19-107">Imate objedinjene profile klijenata.</span><span class="sxs-lookup"><span data-stu-id="5aa19-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="5aa19-108">Najnovija verzija usluge [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) instalirana je na vašem računalu.</span><span class="sxs-lookup"><span data-stu-id="5aa19-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="5aa19-109">[Saznajte više o Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="5aa19-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="5aa19-110">Konfiguracija poveznika za Power BI</span><span class="sxs-lookup"><span data-stu-id="5aa19-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="5aa19-111">U Power BI Desktop odaberite **Datoteka** > **Dohvati podatke**.</span><span class="sxs-lookup"><span data-stu-id="5aa19-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="5aa19-112">Odaberite **Vidi više** i potražite **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="5aa19-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="5aa19-113">Odaberite rezultat i odaberite **Poveži**.</span><span class="sxs-lookup"><span data-stu-id="5aa19-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="5aa19-114">Odaberite **Prijavi se** s istim računom tvrtke ili ustanove koji koristite za aplikaciju Customer Insights i odaberite **Poveži**.</span><span class="sxs-lookup"><span data-stu-id="5aa19-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="5aa19-115">Račun koji navedete u ovom koraku upotrebljava se za dohvaćanje podataka iz aplikacije Customer Insights i ne mora biti isti na koji ste prijavljeni u uslugu Power BI.</span><span class="sxs-lookup"><span data-stu-id="5aa19-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="5aa19-116">Da biste ponovno postavili račun koji se koristi za dohvaćanje podataka, otvorite Power BI i idite u odjeljak **Datoteka** > **Mogućnosti** > **Postavke** > **Postavke izvora podataka**.</span><span class="sxs-lookup"><span data-stu-id="5aa19-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="5aa19-117">Na popisu izvora podataka odaberite **Prijava u aplikaciju Dynamics 365 Customer Insights** i odaberite **Obriši dozvole**.</span><span class="sxs-lookup"><span data-stu-id="5aa19-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="5aa19-118">U dijaloškom okviru **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="5aa19-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="5aa19-119">vidjet ćete popis svih okruženja kojima imate pristup.</span><span class="sxs-lookup"><span data-stu-id="5aa19-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="5aa19-120">Proširite okruženje i otvorite bilo koju mapu (entiteti, mjere, segmenti, obogaćenja).</span><span class="sxs-lookup"><span data-stu-id="5aa19-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="5aa19-121">Na primjer, otvorite mapu **Entiteti** da prikažete sve entitete koje možete uvesti.</span><span class="sxs-lookup"><span data-stu-id="5aa19-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="5aa19-122">![Navigator poveznika programa Power BI](media/power-bi-navigator.png "Navigator poveznika programa Power BI")</span><span class="sxs-lookup"><span data-stu-id="5aa19-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="5aa19-123">Odaberite potvrdne okvire pored entiteta koje treba uključiti i **Učitaj**.</span><span class="sxs-lookup"><span data-stu-id="5aa19-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="5aa19-124">Možete odabrati više entiteta iz više okruženja.</span><span class="sxs-lookup"><span data-stu-id="5aa19-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="5aa19-125">Vidjet ćete dijaloški okvir za učitavanje dok se entiteti učitavaju.</span><span class="sxs-lookup"><span data-stu-id="5aa19-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="5aa19-126">Nakon što se učitaju svi odabrani entiteti, možete koristiti mogućnosti usluge Power BI za vizualizaciju podataka.</span><span class="sxs-lookup"><span data-stu-id="5aa19-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="5aa19-127">Veliki skupovi podataka</span><span class="sxs-lookup"><span data-stu-id="5aa19-127">Large data sets</span></span>

<span data-ttu-id="5aa19-128">Priključak za Customer Insights za Power BI dizajniran je da funkcionira za skupove podataka koji sadrže do 1 milijun korisničkih profila.</span><span class="sxs-lookup"><span data-stu-id="5aa19-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="5aa19-129">Uvoz većih skupova podataka može funkcionirati, ali to traje dugo.</span><span class="sxs-lookup"><span data-stu-id="5aa19-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="5aa19-130">Osim toga, postupak bi mogao biti vremenski ograničen zbog ograničenja za Power BI.</span><span class="sxs-lookup"><span data-stu-id="5aa19-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="5aa19-131">Za više informacija pogledajte [Power BI: Preporuke za velike skupove podataka](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="5aa19-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="5aa19-132">Rad s podskupom podataka</span><span class="sxs-lookup"><span data-stu-id="5aa19-132">Work with a subset of data</span></span>

<span data-ttu-id="5aa19-133">Razmislite o radu s podskupom podataka.</span><span class="sxs-lookup"><span data-stu-id="5aa19-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="5aa19-134">Na primjer, možete stvarati [segmente](segments.md) umjesto izvoza svih zapisa klijenata u Power BI.</span><span class="sxs-lookup"><span data-stu-id="5aa19-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
