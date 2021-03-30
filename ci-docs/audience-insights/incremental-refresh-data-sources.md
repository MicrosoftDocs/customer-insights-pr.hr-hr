---
title: Inkrementalno osvježavanje za izvore podataka koji se temelje na dodatku Power Query
description: Osvježite nove i ažurirane podatke za velike izvore podataka koji se temelje na platformi Power Query.
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 03f76bcfc7336d8430146e8a26ffa649c6a17db0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596812"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="6fa3c-103">Dodatno osvježavanje izvora podataka koji se temelje na platformi Power Query</span><span class="sxs-lookup"><span data-stu-id="6fa3c-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="6fa3c-104">Dodatno osvježavanje izvora podataka pruža sljedeće prednosti:</span><span class="sxs-lookup"><span data-stu-id="6fa3c-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="6fa3c-105">**Brže se osvježava** - osvježavaju se samo podaci koji su se promijenili.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="6fa3c-106">Na primjer, možete osvježiti samo posljednjih pet dana povijesnog skupa podataka.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="6fa3c-107">**Povećana pouzdanost** - uz manja osvježenja, ne morate dugo održavati veze s nestalnim sustavima izvora, čime se smanjuje opasnost od problema s vezom.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="6fa3c-108">**Smanjena potrošnja resursa** - osvježavanje samo podskupine ukupnih podataka dovodi do učinkovitije upotrebe računalnih resursa i smanjuje ekološki otisak.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="6fa3c-109">Konfiguriranje postupnog osvježavanja</span><span class="sxs-lookup"><span data-stu-id="6fa3c-109">Configure incremental refresh</span></span>

<span data-ttu-id="6fa3c-110">Uvidi u ciljnu skupinu omogućuju inkrementalno osvježavanje za izvore podataka uvezene putem dodatka Power Query koji podržava inkrementalnu obradu.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="6fa3c-111">Na primjer, baze podataka Azure SQL s poljima datuma i vremena, koja pokazuju kada su zapisi podataka posljednji put ažurirani.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="6fa3c-112">[Stvorite novi izvor podataka koji se temelji na platformi Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="6fa3c-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="6fa3c-113">Unesite naziv izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="6fa3c-114">Odaberite izvor podataka koji podržava inkrementalno osvježavanje, poput baze podataka Azure SQL.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="6fa3c-115">Odaberite entitete ili tablice koje ćete unijeti.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="6fa3c-116">Dovršite korake pretvaranja i odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="6fa3c-117">U dijaloškom okviru **Postavljanje inkrementalnog osvježavanja** odaberite **Postavljanje** da biste otvorili **Postavke inkrementalnog osvježavanja**.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="6fa3c-118">Ako odaberete **Preskoči**, izvor podataka osvježit će cijeli skup podataka.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="6fa3c-119">Kasnije možete primijeniti i inkrementalno osvježavanje uređivanjem postojećeg izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="6fa3c-120">U odjeljku **Postavke inkrementalnog osvježavanja** konfigurirat ćete inkrementalno osvježavanje za sve entitete koje ste odabrali prilikom izrade izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6fa3c-121">![Konfiguriranje entiteta u izvoru podataka za inkrementalno osvježavanje](media/incremental-refresh-settings.png "Konfiguriranje entiteta u izvoru podataka za inkrementalno osvježavanje")</span><span class="sxs-lookup"><span data-stu-id="6fa3c-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="6fa3c-122">Odaberite entitet i navedite sljedeće podatke:</span><span class="sxs-lookup"><span data-stu-id="6fa3c-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="6fa3c-123">**Definiranje primarnog ključa**: odaberite primarni ključ za entitet ili tablicu.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="6fa3c-124">**Definirajte polje "zadnji put ažurirano"**: ovo polje prikazuje samo atribute datuma ili vremena vrste.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="6fa3c-125">Odaberite atribut koji pokazuje kada su zapisi zadnji put ažurirani.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="6fa3c-126">Upotrijebit će se za prepoznavanje zapisa koji ulaze u vremenski okvir dodatnog osvježavanja.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="6fa3c-127">**Provjeri ima li ažuriranja svakih**: navedite vremenski okvir za inkrementalno osvježavanje.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="6fa3c-128">Odaberite **Spremi** da biste dovršili izradu izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="6fa3c-129">Početno osvježavanje podataka bit će potpuno osvježavanje.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="6fa3c-130">Nakon toga, inkrementalno osvježavanje podataka izvodi se kao što je konfigurirano u prethodnom koraku.</span><span class="sxs-lookup"><span data-stu-id="6fa3c-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]