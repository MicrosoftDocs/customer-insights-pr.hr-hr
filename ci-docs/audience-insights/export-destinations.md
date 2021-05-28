---
title: Izvoz podataka iz Customer Insights
description: Upravljajte izvozima da biste dijelili podatke.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016605"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="2d295-103">Pregled izvoza (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="2d295-103">Exports (preview) overview</span></span>

<span data-ttu-id="2d295-104">Stranica **Izvozi** prikazuje sve konfigurirane izvoze.</span><span class="sxs-lookup"><span data-stu-id="2d295-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="2d295-105">Izvozi dijele određene podatke s različitim aplikacijama.</span><span class="sxs-lookup"><span data-stu-id="2d295-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="2d295-106">Mogu uključivati profile ili entitete klijenata, sheme i pojedinosti mapiranja.</span><span class="sxs-lookup"><span data-stu-id="2d295-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="2d295-107">Svaki izvoz zahtijeva [vezu koju je postavio administrator za upravljanje provjerom autentičnosti i pristupom](connections.md).</span><span class="sxs-lookup"><span data-stu-id="2d295-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="2d295-108">Idite na **Podaci** > **Izvozi** za prikaz stranice izvoza.</span><span class="sxs-lookup"><span data-stu-id="2d295-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="2d295-109">Sve korisničke uloge imaju pristup za prikaz konfiguriranih izvoza.</span><span class="sxs-lookup"><span data-stu-id="2d295-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="2d295-110">Korištenje polja za pretraživanje na naredbenoj traci za pronalaženje izvoza prema njihovu nazivu, nazivu veze ili vrsti veze.</span><span class="sxs-lookup"><span data-stu-id="2d295-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="2d295-111">Postavljanje novog izvoza</span><span class="sxs-lookup"><span data-stu-id="2d295-111">Set up a new export</span></span>

<span data-ttu-id="2d295-112">Da biste postavili ili uredili izvoz, trebate imati dostupne veze.</span><span class="sxs-lookup"><span data-stu-id="2d295-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="2d295-113">Veze ovise o vašoj [korisničkoj ulozi](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="2d295-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="2d295-114">Administratori imaju pristup svim vezama.</span><span class="sxs-lookup"><span data-stu-id="2d295-114">Administrators have access to all connections.</span></span> <span data-ttu-id="2d295-115">Također mogu stvoriti nove veze prilikom postavljanja izvoza.</span><span class="sxs-lookup"><span data-stu-id="2d295-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="2d295-116">Suradnici mogu imati pristup određenim vezama.</span><span class="sxs-lookup"><span data-stu-id="2d295-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="2d295-117">Ovise o administratorima za konfiguriranje i dijeljenje veza.</span><span class="sxs-lookup"><span data-stu-id="2d295-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="2d295-118">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2d295-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="2d295-119">Gledatelji mogu samo pregledavati postojeće izvoze, ali ne mogu ih stvarati.</span><span class="sxs-lookup"><span data-stu-id="2d295-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="2d295-120">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="2d295-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2d295-121">Odaberite **Dodaj izvoz** da biste stvorili novo izvozno odredište.</span><span class="sxs-lookup"><span data-stu-id="2d295-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="2d295-122">U oknu **Postavi izvoz** odaberite koju ćete vezu koristiti.</span><span class="sxs-lookup"><span data-stu-id="2d295-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="2d295-123">[Vezama](connections.md) upravljaju administratori.</span><span class="sxs-lookup"><span data-stu-id="2d295-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="2d295-124">Navedite potrebne pojedinosti i odaberite **Spremi** da biste stvorili izvoz.</span><span class="sxs-lookup"><span data-stu-id="2d295-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="2d295-125">Uređivanje izvoza</span><span class="sxs-lookup"><span data-stu-id="2d295-125">Edit an export</span></span>

1. <span data-ttu-id="2d295-126">Odaberite okomitu elipsu za izvozno odredište koje želite urediti.</span><span class="sxs-lookup"><span data-stu-id="2d295-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="2d295-127">Odaberite **Uredi** na padajućem izborniku.</span><span class="sxs-lookup"><span data-stu-id="2d295-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="2d295-128">Promijenite vrijednosti koje želite ažurirati i odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="2d295-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="2d295-129">Prikaz Izvoza i pojedinosti o izvozu</span><span class="sxs-lookup"><span data-stu-id="2d295-129">View Exports and export details</span></span>

<span data-ttu-id="2d295-130">Nakon stvaranja izvoznih odredišta ona se navode na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="2d295-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="2d295-131">Svi korisnici mogu vidjeti koji se podaci dijele i njihov najnoviji status.</span><span class="sxs-lookup"><span data-stu-id="2d295-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="2d295-132">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="2d295-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2d295-133">Korisnici bez dozvola za uređivanje odabiru **Prikaz** umjesto **Uredi** da bi vidjeli pojedinosti o izvozu.</span><span class="sxs-lookup"><span data-stu-id="2d295-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="2d295-134">To bočno okno prikazuje postavku tog izvoza.</span><span class="sxs-lookup"><span data-stu-id="2d295-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="2d295-135">Bez dozvola za uređivanje ne možete promijeniti vrijednosti.</span><span class="sxs-lookup"><span data-stu-id="2d295-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="2d295-136">Odaberite **Zatvori** za povratak na stranicu izvoza.</span><span class="sxs-lookup"><span data-stu-id="2d295-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="2d295-137">Pokretanje izvoza na zahtjev</span><span class="sxs-lookup"><span data-stu-id="2d295-137">Run exports on demand</span></span>

<span data-ttu-id="2d295-138">Nakon konfiguriranja izvoza pokrenut će se sa svakim [zakazanim osvježavanjem](system.md#schedule-tab) sve dok ima funkcionalnu vezu.</span><span class="sxs-lookup"><span data-stu-id="2d295-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="2d295-139">Da biste izvezli podatke bez čekanja na zakazano osvježavanje, idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="2d295-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="2d295-140">Postoje dvije mogućnosti:</span><span class="sxs-lookup"><span data-stu-id="2d295-140">You have two options:</span></span>

- <span data-ttu-id="2d295-141">Da biste pokrenuli sve izvoze, odaberite **Pokreni sve** na naredbenoj traci.</span><span class="sxs-lookup"><span data-stu-id="2d295-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="2d295-142">Da biste pokrenuli pojedinačni izvoz, odaberite elipsu (...) na stavci popisa, a zatim odaberite **Pokreni**.</span><span class="sxs-lookup"><span data-stu-id="2d295-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="2d295-143">Uklanjanje Izvoza</span><span class="sxs-lookup"><span data-stu-id="2d295-143">Remove an Export</span></span>

1. <span data-ttu-id="2d295-144">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="2d295-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2d295-145">Odaberite okomitu elipsu za Izvoz koji želite ukloniti.</span><span class="sxs-lookup"><span data-stu-id="2d295-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="2d295-146">Na padajućem popisu odaberite **Ukloni**.</span><span class="sxs-lookup"><span data-stu-id="2d295-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="2d295-147">Potvrdite uklanjanje odabirom opcije **Ukloni** na zaslonu za potvrdu.</span><span class="sxs-lookup"><span data-stu-id="2d295-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
