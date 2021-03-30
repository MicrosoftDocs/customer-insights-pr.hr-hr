---
title: Povežite se s entitetima u upravljanom jezeru servisa Common Data Service
description: Uvoz podataka iz rješenja Data Lake kojim upravlja platforma Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596950"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="613ce-103">Povezivanje s podacima iz rješenja Data Lake kojim upravlja platforma Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="613ce-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="613ce-104">U ovom članku nalaze se informacije o načinu na koji se postojeći korisnici sustava Dynamics 365 mogu brzo povezati sa svojim analitičkim entitetima u jezeru kojim upravlja Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="613ce-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="613ce-105">Morate biti administrator u tvrtki ili ustanovi platforme Common Data Service kako biste nastavili i vidjeli popis entiteta dostupnih u upravljanom jezeru.</span><span class="sxs-lookup"><span data-stu-id="613ce-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="613ce-106">Važne stavke</span><span class="sxs-lookup"><span data-stu-id="613ce-106">Important considerations</span></span>

<span data-ttu-id="613ce-107">Podaci pohranjeni u internetskom servisu kao što je Azure Data Lake Storage mogu biti pohranjeni na mjestu drugačijem od onoga na kojemu se podaci obrađuju ili pohranjuju u sustavu Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="613ce-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="613ce-108"> Uvozom ili povezivanjem s podacima pohranjenima u internetskim servisima slažete se da se podaci mogu prenijeti i pohraniti sa sustavom Dynamics 365 Customer Insights. [Saznajte više u programu Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="613ce-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="613ce-109">Povezivanje s jezerom za upravljanje Common Data Service</span><span class="sxs-lookup"><span data-stu-id="613ce-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="613ce-110">U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="613ce-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="613ce-111">Odaberite **Dodaj izvor podataka**.</span><span class="sxs-lookup"><span data-stu-id="613ce-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="613ce-112">Odaberite **Poveži se s opcijom Common Data Service** i odaberite **Sljedeće**.</span><span class="sxs-lookup"><span data-stu-id="613ce-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="613ce-113">Unesite **Naziv** za izvor podataka i odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="613ce-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="613ce-114">Imenujte smjernice:</span><span class="sxs-lookup"><span data-stu-id="613ce-114">Name guidelines:</span></span> 
   - <span data-ttu-id="613ce-115">Započnite slovom.</span><span class="sxs-lookup"><span data-stu-id="613ce-115">Start with a letter.</span></span>
   - <span data-ttu-id="613ce-116">Koristite samo slova i brojeve.</span><span class="sxs-lookup"><span data-stu-id="613ce-116">Use letters and numbers only.</span></span> <span data-ttu-id="613ce-117">Nisu dopušteni posebni znakovi i razmaci.</span><span class="sxs-lookup"><span data-stu-id="613ce-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="613ce-118">Koristite između 3 i 64 znaka.</span><span class="sxs-lookup"><span data-stu-id="613ce-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="613ce-119">Navedite **Adresu poslužitelja** za svoju tvrtku ili ustanovu Common Data Service i odaberite **Prijava**.</span><span class="sxs-lookup"><span data-stu-id="613ce-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="613ce-120">![Dijaloški okvir za unos adrese poslužitelja značajke Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="613ce-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="613ce-121">Odaberite entitete koje želite unijeti s dostupnog popisa.</span><span class="sxs-lookup"><span data-stu-id="613ce-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="613ce-122">Ako su neki entiteti već odabrani, mogle bi ih koristiti druge aplikacije Dynamics 365 (poput Dynamics 365 Sales Insights ili Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="613ce-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="613ce-123">Taj odabir ne možete promijeniti.</span><span class="sxs-lookup"><span data-stu-id="613ce-123">You can't change the selection.</span></span> <span data-ttu-id="613ce-124">Ti će entiteti biti dostupni kada se stvori izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="613ce-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="613ce-125">![Dijaloški okvir s popisom entiteta u tvrtki ili ustanovi Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="613ce-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="613ce-126">Spremite svoj odabir da biste pokrenuli sinkronizaciju odabranih entiteta s jezerom za upravljanje Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="613ce-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="613ce-127">Novu dodanu vezu pronaći ćete na stranici **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="613ce-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="613ce-128">Stavit će se u red za osvježavanje i prikazati broj entiteta kao 0 dok se svi entiteti ne sinkroniziraju.</span><span class="sxs-lookup"><span data-stu-id="613ce-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="613ce-129">Samo jedan izvor podataka okruženja može istovremeno koristiti isto upravljano jezero servisa Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="613ce-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="613ce-130">Uređivanje izvora podataka jezera za upravljanje Common Data Service</span><span class="sxs-lookup"><span data-stu-id="613ce-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="613ce-131">Odabir entiteta uređujete tek nakon što stvorite izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="613ce-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="613ce-132">Na primjer, ako su platformi Common Data Service dodani dodatni entiteti, a i njih također želite uvesti.</span><span class="sxs-lookup"><span data-stu-id="613ce-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="613ce-133">Da biste povezali drugi Common Data Service, [stvorite novi izvor podataka](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="613ce-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="613ce-134">U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="613ce-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="613ce-135">Pored izvora podataka koji želite ažurirati odaberite elipsu.</span><span class="sxs-lookup"><span data-stu-id="613ce-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="613ce-136">S popisa odaberite mogućnost **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="613ce-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="613ce-137">Odaberite dodatne entitete s dostupnog popisa entiteta i odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="613ce-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]