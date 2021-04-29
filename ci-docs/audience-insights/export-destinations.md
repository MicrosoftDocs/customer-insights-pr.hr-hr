---
title: Izvoz podataka iz Customer Insights
description: Upravljajte izvozima da biste dijelili podatke.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896134"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="d705f-103">Pregled izvoza (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="d705f-103">Exports (preview) overview</span></span>

<span data-ttu-id="d705f-104">Stranica **Izvozi** prikazuje sve konfigurirane izvoze.</span><span class="sxs-lookup"><span data-stu-id="d705f-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="d705f-105">Izvozi dijele određene podatke s različitim aplikacijama.</span><span class="sxs-lookup"><span data-stu-id="d705f-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="d705f-106">Mogu uključivati profile ili entitete klijenata, sheme i pojedinosti mapiranja.</span><span class="sxs-lookup"><span data-stu-id="d705f-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="d705f-107">Svaki izvoz zahtijeva [vezu koju je postavio administrator za upravljanje provjerom autentičnosti i pristupom](connections.md).</span><span class="sxs-lookup"><span data-stu-id="d705f-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d705f-108">Do ožujka 2021. izvozi su automatski stvarali vezu s odgovarajućom uslugom.</span><span class="sxs-lookup"><span data-stu-id="d705f-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="d705f-109">Izvozi sada zahtijevaju [vezu koju je stvorio i podijelio administrator](connections.md) prije nego što ih možete stvoriti.</span><span class="sxs-lookup"><span data-stu-id="d705f-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="d705f-110">Idite na **Podaci** > **Izvozi** za prikaz stranice izvoza.</span><span class="sxs-lookup"><span data-stu-id="d705f-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="d705f-111">Sve korisničke uloge imaju pristup za prikaz konfiguriranih izvoza.</span><span class="sxs-lookup"><span data-stu-id="d705f-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="d705f-112">Korištenje polja za pretraživanje na naredbenoj traci za pronalaženje izvoza prema njihovu nazivu, nazivu veze ili vrsti veze.</span><span class="sxs-lookup"><span data-stu-id="d705f-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="d705f-113">Postavljanje novog izvoza</span><span class="sxs-lookup"><span data-stu-id="d705f-113">Set up a new export</span></span>

<span data-ttu-id="d705f-114">Da biste postavili ili uredili izvoz, trebate imati dostupne veze.</span><span class="sxs-lookup"><span data-stu-id="d705f-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="d705f-115">Veze ovise o vašoj [korisničkoj ulozi](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="d705f-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="d705f-116">Administratori imaju pristup svim vezama.</span><span class="sxs-lookup"><span data-stu-id="d705f-116">Administrators have access to all connections.</span></span> <span data-ttu-id="d705f-117">Također mogu stvoriti nove veze prilikom postavljanja izvoza.</span><span class="sxs-lookup"><span data-stu-id="d705f-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="d705f-118">Suradnici mogu imati pristup određenim vezama.</span><span class="sxs-lookup"><span data-stu-id="d705f-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="d705f-119">Ovise o administratorima za konfiguriranje i dijeljenje veza.</span><span class="sxs-lookup"><span data-stu-id="d705f-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="d705f-120">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d705f-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="d705f-121">Gledatelji mogu samo pregledavati postojeće izvoze, ali ne mogu ih stvarati.</span><span class="sxs-lookup"><span data-stu-id="d705f-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="d705f-122">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="d705f-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d705f-123">Odaberite **Dodaj izvoz** da biste stvorili novo izvozno odredište.</span><span class="sxs-lookup"><span data-stu-id="d705f-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="d705f-124">U oknu **Postavi izvoz** odaberite koju ćete vezu koristiti.</span><span class="sxs-lookup"><span data-stu-id="d705f-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="d705f-125">[Vezama](connections.md) upravljaju administratori.</span><span class="sxs-lookup"><span data-stu-id="d705f-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="d705f-126">Navedite potrebne pojedinosti i odaberite **Spremi** da biste stvorili izvoz.</span><span class="sxs-lookup"><span data-stu-id="d705f-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="d705f-127">Uređivanje izvoza</span><span class="sxs-lookup"><span data-stu-id="d705f-127">Edit an export</span></span>

1. <span data-ttu-id="d705f-128">Odaberite okomitu elipsu za izvozno odredište koje želite urediti.</span><span class="sxs-lookup"><span data-stu-id="d705f-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="d705f-129">Odaberite **Uredi** na padajućem izborniku.</span><span class="sxs-lookup"><span data-stu-id="d705f-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="d705f-130">Promijenite vrijednosti koje želite ažurirati i odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="d705f-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="d705f-131">Prikaz Izvoza i pojedinosti o izvozu</span><span class="sxs-lookup"><span data-stu-id="d705f-131">View Exports and export details</span></span>

<span data-ttu-id="d705f-132">Nakon stvaranja izvoznih odredišta ona se navode na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="d705f-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="d705f-133">Svi korisnici mogu vidjeti koji se podaci dijele i njihov najnoviji status.</span><span class="sxs-lookup"><span data-stu-id="d705f-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="d705f-134">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="d705f-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d705f-135">Korisnici bez dozvola za uređivanje odabiru **Prikaz** umjesto **Uredi** da bi vidjeli pojedinosti o izvozu.</span><span class="sxs-lookup"><span data-stu-id="d705f-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="d705f-136">To bočno okno prikazuje postavku tog izvoza.</span><span class="sxs-lookup"><span data-stu-id="d705f-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="d705f-137">Bez dozvola za uređivanje ne možete promijeniti vrijednosti.</span><span class="sxs-lookup"><span data-stu-id="d705f-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="d705f-138">Odaberite **Zatvori** za povratak na stranicu izvoza.</span><span class="sxs-lookup"><span data-stu-id="d705f-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="d705f-139">Pokretanje izvoza na zahtjev</span><span class="sxs-lookup"><span data-stu-id="d705f-139">Run exports on demand</span></span>

<span data-ttu-id="d705f-140">Nakon konfiguriranja izvoza pokrenut će se sa svakim [zakazanim osvježavanjem](system.md#schedule-tab) sve dok ima funkcionalnu vezu.</span><span class="sxs-lookup"><span data-stu-id="d705f-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="d705f-141">Da biste izvezli podatke bez čekanja na zakazano osvježavanje, idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="d705f-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="d705f-142">Postoje dvije mogućnosti:</span><span class="sxs-lookup"><span data-stu-id="d705f-142">You have two options:</span></span>

- <span data-ttu-id="d705f-143">Da biste pokrenuli sve izvoze, odaberite **Pokreni sve** na naredbenoj traci.</span><span class="sxs-lookup"><span data-stu-id="d705f-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="d705f-144">Da biste pokrenuli pojedinačni izvoz, odaberite elipsu (...) na stavci popisa, a zatim odaberite **Pokreni**.</span><span class="sxs-lookup"><span data-stu-id="d705f-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="d705f-145">Uklanjanje Izvoza</span><span class="sxs-lookup"><span data-stu-id="d705f-145">Remove an Export</span></span>

1. <span data-ttu-id="d705f-146">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="d705f-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d705f-147">Odaberite okomitu elipsu za Izvoz koji želite ukloniti.</span><span class="sxs-lookup"><span data-stu-id="d705f-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="d705f-148">Na padajućem popisu odaberite **Ukloni**.</span><span class="sxs-lookup"><span data-stu-id="d705f-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="d705f-149">Potvrdite uklanjanje odabirom opcije **Ukloni** na zaslonu za potvrdu.</span><span class="sxs-lookup"><span data-stu-id="d705f-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
