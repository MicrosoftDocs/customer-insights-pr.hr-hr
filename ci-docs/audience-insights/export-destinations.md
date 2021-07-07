---
title: Izvoz podataka iz Customer Insights
description: Upravljajte izvozima da biste dijelili podatke.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305469"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="c5c06-103">Pregled izvoza (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="c5c06-103">Exports (preview) overview</span></span>

<span data-ttu-id="c5c06-104">Stranica **Izvozi** prikazuje sve konfigurirane izvoze.</span><span class="sxs-lookup"><span data-stu-id="c5c06-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="c5c06-105">Izvozi dijele određene podatke s različitim aplikacijama.</span><span class="sxs-lookup"><span data-stu-id="c5c06-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="c5c06-106">Mogu uključivati profile ili entitete klijenata, sheme i pojedinosti mapiranja.</span><span class="sxs-lookup"><span data-stu-id="c5c06-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="c5c06-107">Svaki izvoz zahtijeva [vezu koju je postavio administrator za upravljanje provjerom autentičnosti i pristupom](connections.md).</span><span class="sxs-lookup"><span data-stu-id="c5c06-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="c5c06-108">Idite na **Podaci** > **Izvozi** za prikaz stranice izvoza.</span><span class="sxs-lookup"><span data-stu-id="c5c06-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="c5c06-109">Sve korisničke uloge mogu pregledavati konfigurirane izvoze.</span><span class="sxs-lookup"><span data-stu-id="c5c06-109">All user roles can view configured exports.</span></span> <span data-ttu-id="c5c06-110">Koristite polje za pretraživanje na naredbenoj traci da biste pronašli izvoze prema njihovu nazivu, nazivu veze ili vrsti veze.</span><span class="sxs-lookup"><span data-stu-id="c5c06-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="c5c06-111">Postavljanje novog izvoza</span><span class="sxs-lookup"><span data-stu-id="c5c06-111">Set up a new export</span></span>

<span data-ttu-id="c5c06-112">Da biste postavili ili uredili izvoz, trebate imati dostupne veze.</span><span class="sxs-lookup"><span data-stu-id="c5c06-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="c5c06-113">Veze ovise o vašoj [korisničkoj ulozi](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="c5c06-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="c5c06-114">Administratori imaju pristup svim vezama.</span><span class="sxs-lookup"><span data-stu-id="c5c06-114">Administrators have access to all connections.</span></span> <span data-ttu-id="c5c06-115">Također mogu stvoriti nove veze prilikom postavljanja izvoza.</span><span class="sxs-lookup"><span data-stu-id="c5c06-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="c5c06-116">Suradnici mogu imati pristup određenim vezama.</span><span class="sxs-lookup"><span data-stu-id="c5c06-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="c5c06-117">Ovise o administratorima za konfiguriranje i dijeljenje veza.</span><span class="sxs-lookup"><span data-stu-id="c5c06-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="c5c06-118">Popis izvoza pokazuje suradnicima mogu li uređivati ili samo pregledavati izvoz u stupcu **Vaše dozvole**.</span><span class="sxs-lookup"><span data-stu-id="c5c06-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="c5c06-119">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c5c06-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="c5c06-120">Gledatelji mogu samo pregledavati postojeće izvoze, ali ne mogu ih stvarati.</span><span class="sxs-lookup"><span data-stu-id="c5c06-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="c5c06-121">Definiranje novog izvoza</span><span class="sxs-lookup"><span data-stu-id="c5c06-121">Define a new export</span></span>

1. <span data-ttu-id="c5c06-122">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="c5c06-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c5c06-123">Odaberite **Dodaj izvoz** za stvaranje novog izvoza.</span><span class="sxs-lookup"><span data-stu-id="c5c06-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="c5c06-124">U oknu **Postavi izvoz** odaberite koju ćete vezu koristiti.</span><span class="sxs-lookup"><span data-stu-id="c5c06-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="c5c06-125">[Vezama](connections.md) upravljaju administratori.</span><span class="sxs-lookup"><span data-stu-id="c5c06-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="c5c06-126">Navedite potrebne pojedinosti i odaberite **Spremi** da biste stvorili izvoz.</span><span class="sxs-lookup"><span data-stu-id="c5c06-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="c5c06-127">Definiranje novog izvoza na temelju postojećeg</span><span class="sxs-lookup"><span data-stu-id="c5c06-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="c5c06-128">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="c5c06-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c5c06-129">Na popisu izvoza odaberite izvoz koji želite duplicirati.</span><span class="sxs-lookup"><span data-stu-id="c5c06-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="c5c06-130">Odaberite **Stvori duplikat** na naredbenoj traci za otvaranje okna **Postavi izvoz** s pojedinostima odabranog izvoza.</span><span class="sxs-lookup"><span data-stu-id="c5c06-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="c5c06-131">Pregledajte i prilagodite izvoz te odaberite **Spremi** za stvaranje novog izvoza.</span><span class="sxs-lookup"><span data-stu-id="c5c06-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="c5c06-132">Uređivanje izvoza</span><span class="sxs-lookup"><span data-stu-id="c5c06-132">Edit an export</span></span>

1. <span data-ttu-id="c5c06-133">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="c5c06-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c5c06-134">Na popisu izvoza odaberite izvoz koji želite urediti.</span><span class="sxs-lookup"><span data-stu-id="c5c06-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="c5c06-135">Odaberite **Uredi** na naredbenoj traci.</span><span class="sxs-lookup"><span data-stu-id="c5c06-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="c5c06-136">Promijenite vrijednosti koje želite ažurirati i odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="c5c06-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="c5c06-137">Prikaz izvoza i pojedinosti o izvozu</span><span class="sxs-lookup"><span data-stu-id="c5c06-137">View exports and export details</span></span>

<span data-ttu-id="c5c06-138">Nakon stvaranja izvoznih odredišta ona su navedena u odjeljku **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="c5c06-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="c5c06-139">Svi korisnici mogu vidjeti koji se podaci dijele i njihov najnoviji status.</span><span class="sxs-lookup"><span data-stu-id="c5c06-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="c5c06-140">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="c5c06-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c5c06-141">Korisnicie bez dozvole za uređivanje odabiru **Prikaži** umjesto **Uredi** kako bi vidjeli pojedinosti o izvozu.</span><span class="sxs-lookup"><span data-stu-id="c5c06-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="c5c06-142">Bočno okno prikazuje konfiguraciju izvoza.</span><span class="sxs-lookup"><span data-stu-id="c5c06-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="c5c06-143">Bez dozvola za uređivanje ne možete promijeniti vrijednosti.</span><span class="sxs-lookup"><span data-stu-id="c5c06-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="c5c06-144">Odaberite **Zatvori** za povratak na stranicu izvoza.</span><span class="sxs-lookup"><span data-stu-id="c5c06-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="c5c06-145">Zakazivanje i pokretanje izvoza</span><span class="sxs-lookup"><span data-stu-id="c5c06-145">Schedule and run exports</span></span>

<span data-ttu-id="c5c06-146">Svaki izvoz koji konfigurirate ima raspored osvježavanja.</span><span class="sxs-lookup"><span data-stu-id="c5c06-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="c5c06-147">Tijekom osvježavanja sustav traži nove ili ažurirane podatke koje će uključiti u izvoz.</span><span class="sxs-lookup"><span data-stu-id="c5c06-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="c5c06-148">Prema zadanim postavkama izvozi se izvode kao dio svakog [zakazanog osvježavanja sustava](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c5c06-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c5c06-149">Raspored osvježavanja možete prilagoditi ili ga isključiti za ručno pokretanje izvoza.</span><span class="sxs-lookup"><span data-stu-id="c5c06-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="c5c06-150">Rasporedi izvoza ovise o stanju vašeg okruženja.</span><span class="sxs-lookup"><span data-stu-id="c5c06-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="c5c06-151">Ako su u tijeku ažuriranja na [ovisnostima](system.md#refresh-policies) kada bi trebao započeti planirani izvoz, sustav će prvo dovršiti ažuriranja, a zatim pokrenuti izvoz.</span><span class="sxs-lookup"><span data-stu-id="c5c06-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="c5c06-152">U stupcu **Osvježeno** možete vidjeti kad je izvoz zadnji put bio osvježen.</span><span class="sxs-lookup"><span data-stu-id="c5c06-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="c5c06-153">Zakazivanje izvoza</span><span class="sxs-lookup"><span data-stu-id="c5c06-153">Schedule exports</span></span>

<span data-ttu-id="c5c06-154">Možete definirati prilagođene rasporede osvježavanja za pojedinačne izvoze ili više izvoza odjednom.</span><span class="sxs-lookup"><span data-stu-id="c5c06-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="c5c06-155">Trenutno definirani raspored naveden je u stupcu **Raspored** na popisu izvoza.</span><span class="sxs-lookup"><span data-stu-id="c5c06-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="c5c06-156">Dozvola za promjenu rasporeda je ista kao i za [uređivanje i definiranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c5c06-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="c5c06-157">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="c5c06-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c5c06-158">Odaberite izvoz koji želite zakazati.</span><span class="sxs-lookup"><span data-stu-id="c5c06-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="c5c06-159">Odaberite **Raspored** na naredbenoj traci.</span><span class="sxs-lookup"><span data-stu-id="c5c06-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="c5c06-160">U oknu **Zakazivanje izvoza** postavite **Pokretanje rasporeda** na **Uključeno** za automatsko pokretanje izvoza.</span><span class="sxs-lookup"><span data-stu-id="c5c06-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="c5c06-161">Postavite na **Isključeno** da ga osvježite ručno.</span><span class="sxs-lookup"><span data-stu-id="c5c06-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="c5c06-162">Za automatski osvježene izvoze odaberite vrijednost **Ponavljanje** i za nju navedite pojedinosti.</span><span class="sxs-lookup"><span data-stu-id="c5c06-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="c5c06-163">Definirano vrijeme odnosi se na sve slučajeve ponavljanja.</span><span class="sxs-lookup"><span data-stu-id="c5c06-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="c5c06-164">To je vrijeme kada bi se izvoz trebao početi osvježavati.</span><span class="sxs-lookup"><span data-stu-id="c5c06-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="c5c06-165">Primijenite i aktivirajte promjene odabirom mogućnosti **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="c5c06-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="c5c06-166">Pri uređivanju rasporeda za nekoliko izvoza, morate izvršiti odabir u odjeljku **Sačuvaj ili zamijeni rasporede**:</span><span class="sxs-lookup"><span data-stu-id="c5c06-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="c5c06-167">**Sačuvaj pojedinačne rasporede**: Zadržite prethodno definirani raspored za odabrane izvoze i samo ih onemogućite ili omogućite.</span><span class="sxs-lookup"><span data-stu-id="c5c06-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="c5c06-168">**Definiraj novi raspored za sve odabrane izvoze**: Zamijenite postojeće rasporede odabranih izvoza.</span><span class="sxs-lookup"><span data-stu-id="c5c06-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="c5c06-169">Pokretanje izvoza na zahtjev</span><span class="sxs-lookup"><span data-stu-id="c5c06-169">Run exports on demand</span></span>

<span data-ttu-id="c5c06-170">Da biste izvezli podatke bez čekanja na zakazano osvježavanje, idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="c5c06-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="c5c06-171">Da biste pokrenuli sve izvoze, odaberite **Pokreni sve** na naredbenoj traci.</span><span class="sxs-lookup"><span data-stu-id="c5c06-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="c5c06-172">Ovom akcijom pokrenut će se samo izvozi sa aktivnim rasporedom.</span><span class="sxs-lookup"><span data-stu-id="c5c06-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="c5c06-173">Da biste pokrenuli jedan izvoz, odaberite ga na popisu i odaberite **Pokreni** na naredbenoj traci.</span><span class="sxs-lookup"><span data-stu-id="c5c06-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="c5c06-174">Tako pokrećete izvoz bez aktivnog rasporeda.</span><span class="sxs-lookup"><span data-stu-id="c5c06-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="c5c06-175">Uklanjanje Izvoza</span><span class="sxs-lookup"><span data-stu-id="c5c06-175">Remove an Export</span></span>

1. <span data-ttu-id="c5c06-176">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="c5c06-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c5c06-177">Odaberite izvoz koji želite ukloniti.</span><span class="sxs-lookup"><span data-stu-id="c5c06-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="c5c06-178">Odaberite **Ukloni** na naredbenoj traci.</span><span class="sxs-lookup"><span data-stu-id="c5c06-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="c5c06-179">Potvrdite uklanjanje odabirom opcije **Ukloni** na zaslonu za potvrdu.</span><span class="sxs-lookup"><span data-stu-id="c5c06-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
