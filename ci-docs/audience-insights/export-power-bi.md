---
title: Poveznik za Power BI
description: Saznajte kako upotrebljavati poveznik značajke Dynamics 365 Customer Insights u programu Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477079"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="b43d6-103">Poveznik za Power BI (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="b43d6-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="b43d6-104">Stvorite vizualne prikaze za svoje podatke pomoću usluge Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="b43d6-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="b43d6-105">Generirajte dodatne uvide i izradite izvješća s objedinjenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="b43d6-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b43d6-106">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="b43d6-106">Prerequisites</span></span>

- <span data-ttu-id="b43d6-107">Imate objedinjene profile klijenata.</span><span class="sxs-lookup"><span data-stu-id="b43d6-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="b43d6-108">Najnovija verzija usluge [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) instalirana je na vašem računalu.</span><span class="sxs-lookup"><span data-stu-id="b43d6-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="b43d6-109">[Saznajte više o Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="b43d6-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="b43d6-110">Konfiguracija poveznika za Power BI</span><span class="sxs-lookup"><span data-stu-id="b43d6-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="b43d6-111">U Power BI Desktop odaberite **Datoteka** > **Dohvati podatke**.</span><span class="sxs-lookup"><span data-stu-id="b43d6-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="b43d6-112">Odaberite **Vidi više** i potražite **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="b43d6-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="b43d6-113">Odaberite **Poveži**.</span><span class="sxs-lookup"><span data-stu-id="b43d6-113">Select **Connect**.</span></span>

1. <span data-ttu-id="b43d6-114">Odaberite **Prijavi se** s istim računom tvrtke ili ustanove koji koristite za aplikaciju Customer Insights i odaberite **Poveži**.</span><span class="sxs-lookup"><span data-stu-id="b43d6-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="b43d6-115">Račun koji navedete u ovom koraku upotrebljava se za dohvaćanje podataka iz aplikacije Customer Insights i ne mora biti isti na koji ste prijavljeni u uslugu Power BI.</span><span class="sxs-lookup"><span data-stu-id="b43d6-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="b43d6-116">Da biste ponovno postavili račun koji se koristi za dohvaćanje podataka, otvorite Power BI i idite u odjeljak **Datoteka** > **Mogućnosti** > **Postavke** > **Postavke izvora podataka**.</span><span class="sxs-lookup"><span data-stu-id="b43d6-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="b43d6-117">Na popisu izvora podataka odaberite **Prijava u aplikaciju Dynamics 365 Customer Insights** i odaberite **Obriši dozvole**.</span><span class="sxs-lookup"><span data-stu-id="b43d6-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="b43d6-118">U dijaloškom okviru **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="b43d6-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="b43d6-119">vidjet ćete popis svih okruženja kojima imate pristup.</span><span class="sxs-lookup"><span data-stu-id="b43d6-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="b43d6-120">Proširite okruženje i otvorite bilo koju mapu (entiteti, mjere, segmenti, obogaćenja).</span><span class="sxs-lookup"><span data-stu-id="b43d6-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="b43d6-121">Na primjer, otvorite mapu **Entiteti** da prikažete sve entitete koje možete uvesti.</span><span class="sxs-lookup"><span data-stu-id="b43d6-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="b43d6-122">![Navigator poveznika programa Power BI](media/power-bi-navigator.png "Navigator poveznika programa Power BI")</span><span class="sxs-lookup"><span data-stu-id="b43d6-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="b43d6-123">Odaberite potvrdne okvire pored entiteta koje treba uključiti i **Učitaj**.</span><span class="sxs-lookup"><span data-stu-id="b43d6-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="b43d6-124">Možete odabrati više entiteta iz više okruženja.</span><span class="sxs-lookup"><span data-stu-id="b43d6-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="b43d6-125">Vidjet ćete dijaloški okvir za učitavanje dok se entiteti učitavaju.</span><span class="sxs-lookup"><span data-stu-id="b43d6-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="b43d6-126">Nakon što se učitaju svi odabrani entiteti, možete koristiti mogućnosti usluge Power BI za vizualizaciju podataka.</span><span class="sxs-lookup"><span data-stu-id="b43d6-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="b43d6-127">Veliki skupovi podataka</span><span class="sxs-lookup"><span data-stu-id="b43d6-127">Large data sets</span></span>

<span data-ttu-id="b43d6-128">Priključak za Customer Insights za Power BI dizajniran je da funkcionira za skupove podataka koji sadrže do 1 milijun korisničkih profila.</span><span class="sxs-lookup"><span data-stu-id="b43d6-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="b43d6-129">Uvoz većih skupova podataka može funkcionirati, ali to traje dugo.</span><span class="sxs-lookup"><span data-stu-id="b43d6-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="b43d6-130">Osim toga, postupak bi mogao biti vremenski ograničen zbog ograničenja za Power BI.</span><span class="sxs-lookup"><span data-stu-id="b43d6-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="b43d6-131">Za više informacija pogledajte [Power BI: Preporuke za velike skupove podataka](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="b43d6-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="b43d6-132">Rad s podskupom podataka</span><span class="sxs-lookup"><span data-stu-id="b43d6-132">Work with a subset of data</span></span>

<span data-ttu-id="b43d6-133">Razmislite o radu s podskupom podataka.</span><span class="sxs-lookup"><span data-stu-id="b43d6-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="b43d6-134">Na primjer, možete stvarati [segmente](segments.md) umjesto izvoza svih zapisa klijenata u Power BI.</span><span class="sxs-lookup"><span data-stu-id="b43d6-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b43d6-135">Otklanjanje poteškoća</span><span class="sxs-lookup"><span data-stu-id="b43d6-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="b43d6-136">Okruženje Customer Insights ne prikazuje se u Power BI</span><span class="sxs-lookup"><span data-stu-id="b43d6-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="b43d6-137">Okruženja koja imaju više od jednog [odnosa](relationships.md) definirana između dva identična entiteta u uvidima u ciljnu skupinu neće biti dostupni u povezniku usluge Power BI.</span><span class="sxs-lookup"><span data-stu-id="b43d6-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="b43d6-138">Možete identificirati i ukloniti duplicirane odnose.</span><span class="sxs-lookup"><span data-stu-id="b43d6-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="b43d6-139">U uvidima u ciljnu skupinu idite na **Podaci** > **Odnosi** u okruženju koje vam nedostaje u Power BI.</span><span class="sxs-lookup"><span data-stu-id="b43d6-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="b43d6-140">Identificiranje dupliciranih odnosa:</span><span class="sxs-lookup"><span data-stu-id="b43d6-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="b43d6-141">Provjerite postoji li više odnosa definiranih između dvaju istih entiteta.</span><span class="sxs-lookup"><span data-stu-id="b43d6-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="b43d6-142">Provjerite postoji li odnos stvoren između dvaju entiteta koja su oba uključena u proces objedinjavanja.</span><span class="sxs-lookup"><span data-stu-id="b43d6-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="b43d6-143">Definiran je implicitni odnos između svih entiteta uključenih u proces objedinjavanja.</span><span class="sxs-lookup"><span data-stu-id="b43d6-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="b43d6-144">Uklonite sve identificirane duplicirane odnose.</span><span class="sxs-lookup"><span data-stu-id="b43d6-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="b43d6-145">Nakon uklanjanja dupliciranih odnosa, pokušajte ponovno konfigurirati poveznik za Power BI.</span><span class="sxs-lookup"><span data-stu-id="b43d6-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="b43d6-146">Okruženje bi sada trebalo biti dostupno.</span><span class="sxs-lookup"><span data-stu-id="b43d6-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

