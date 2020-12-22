---
title: Povežite se s entitetima u upravljanom jezeru servisa Common Data Service
description: Uvoz podataka iz rješenja Data Lake kojim upravlja platforma Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643389"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="a72bb-103">Povezivanje s podacima iz rješenja Data Lake kojim upravlja platforma Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a72bb-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a72bb-104">U ovom članku nalaze se informacije o načinu na koji se postojeći korisnici sustava Dynamics 365 mogu brzo povezati sa svojim analitičkim entitetima u jezeru kojim upravlja Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a72bb-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="a72bb-105">Morate biti administrator u tvrtki ili ustanovi platforme Common Data Service kako biste nastavili i vidjeli popis entiteta dostupnih u upravljanom jezeru.</span><span class="sxs-lookup"><span data-stu-id="a72bb-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="a72bb-106">Važne stavke</span><span class="sxs-lookup"><span data-stu-id="a72bb-106">Important considerations</span></span>

<span data-ttu-id="a72bb-107">Podaci pohranjeni u internetskom servisu kao što je Azure Data Lake Storage mogu biti pohranjeni na mjestu drugačijem od onoga na kojemu se podaci obrađuju ili pohranjuju u sustavu Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a72bb-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="a72bb-108"> Uvozom ili povezivanjem s podacima pohranjenima u internetskim servisima slažete se da se podaci mogu prenijeti i pohraniti sa sustavom Dynamics 365 Customer Insights. [Saznajte više u programu Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="a72bb-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="a72bb-109">Povezivanje s jezerom za upravljanje Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a72bb-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="a72bb-110">U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="a72bb-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="a72bb-111">Odaberite **Dodaj izvor podataka**.</span><span class="sxs-lookup"><span data-stu-id="a72bb-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="a72bb-112">Odaberite **Poveži se s opcijom Common Data Service** i odaberite **Sljedeće**.</span><span class="sxs-lookup"><span data-stu-id="a72bb-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="a72bb-113">Unesite **Naziv** za izvor podataka i odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="a72bb-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="a72bb-114">Navedite **Adresu poslužitelja** za svoju tvrtku ili ustanovu Common Data Service i odaberite **Prijava**.</span><span class="sxs-lookup"><span data-stu-id="a72bb-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a72bb-115">![Dijaloški okvir za unos adrese poslužitelja značajke Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="a72bb-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="a72bb-116">Odaberite entitete koje želite unijeti s dostupnog popisa.</span><span class="sxs-lookup"><span data-stu-id="a72bb-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="a72bb-117">Ako su neki entiteti već odabrani, mogle bi ih koristiti druge aplikacije Dynamics 365 (poput Dynamics 365 Sales Insights ili Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="a72bb-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="a72bb-118">Taj odabir ne možete promijeniti.</span><span class="sxs-lookup"><span data-stu-id="a72bb-118">You can't change the selection.</span></span> <span data-ttu-id="a72bb-119">Ti će entiteti biti dostupni kada se stvori izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="a72bb-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a72bb-120">![Dijaloški okvir s popisom entiteta u tvrtki ili ustanovi Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="a72bb-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="a72bb-121">Spremite svoj odabir da biste pokrenuli sinkronizaciju odabranih entiteta s jezerom za upravljanje Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a72bb-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="a72bb-122">Novu dodanu vezu pronaći ćete na stranici **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="a72bb-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="a72bb-123">Stavit će se u red za osvježavanje i prikazati broj entiteta kao 0 dok se svi entiteti ne sinkroniziraju.</span><span class="sxs-lookup"><span data-stu-id="a72bb-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="a72bb-124">Samo jedan izvor podataka okruženja može istovremeno koristiti isto upravljano jezero servisa Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a72bb-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="a72bb-125">Uređivanje izvora podataka jezera za upravljanje Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a72bb-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="a72bb-126">Odabir entiteta uređujete tek nakon što stvorite izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="a72bb-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="a72bb-127">Na primjer, ako su platformi Common Data Service dodani dodatni entiteti, a i njih također želite uvesti.</span><span class="sxs-lookup"><span data-stu-id="a72bb-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="a72bb-128">Da biste povezali drugi Common Data Service, [stvorite novi izvor podataka](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="a72bb-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="a72bb-129">U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="a72bb-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="a72bb-130">Pored izvora podataka koji želite ažurirati odaberite elipsu.</span><span class="sxs-lookup"><span data-stu-id="a72bb-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="a72bb-131">S popisa odaberite mogućnost **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="a72bb-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="a72bb-132">Odaberite dodatne entitete s dostupnog popisa entiteta i odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="a72bb-132">Select additional entities from the available list of entities and select **Save**.</span></span>
