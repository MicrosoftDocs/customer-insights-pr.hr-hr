---
title: Spajanje entiteta u objedinjavanju podataka
description: Spojite entitete da biste stvorili objedinjene profile klijenata.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597824"
---
# <a name="merge-entities"></a><span data-ttu-id="8363f-103">Spajanje entiteta</span><span class="sxs-lookup"><span data-stu-id="8363f-103">Merge entities</span></span>

<span data-ttu-id="8363f-104">Faza spajanja zadnja je faza u procesu objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="8363f-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="8363f-105">Njezina je svrha usklađivanje zbunjujućih podataka.</span><span class="sxs-lookup"><span data-stu-id="8363f-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="8363f-106">Primjeri sukobljenih podataka mogu uključivati ime klijenta koje se nalazi u dvama skupovima podataka, ali se malo drugačije prikazuje u svakome od njih („Grant Marshall” u odnosu na „Grant Marshal”) ili telefonski broj koji se razlikuje u obliku (617-803-091X u odnosu na 617803091X).</span><span class="sxs-lookup"><span data-stu-id="8363f-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="8363f-107">Spajanje tih zbunjujućih podatkovnih točaka vrši se na osnovi atribut prema atributu.</span><span class="sxs-lookup"><span data-stu-id="8363f-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="8363f-108">Nakon dovršetka [faze uparivanja](match-entities.md) fazu spajanja možete započeti odabirom pločice **Spajanje** na stranici **Objedinjavanje**.</span><span class="sxs-lookup"><span data-stu-id="8363f-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="8363f-109">Pregled preporuka sustava</span><span class="sxs-lookup"><span data-stu-id="8363f-109">Review system recommendations</span></span>

<span data-ttu-id="8363f-110">Na stranici **Spajanje** možete odabrati i isključiti atribute koji će se spajati unutar vašeg objedinjenog entiteta profila klijenta (rezultat procesa konfiguracije).</span><span class="sxs-lookup"><span data-stu-id="8363f-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="8363f-111">Sustav automatski spaja neke atribute.</span><span class="sxs-lookup"><span data-stu-id="8363f-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="8363f-112">Prikaz spojenih atributa</span><span class="sxs-lookup"><span data-stu-id="8363f-112">View merged attributes</span></span>

<span data-ttu-id="8363f-113">Da biste prikazali atribute koji su uključeni u jedan od vaših automatski spojenih atributa, odaberite taj spojeni atribut.</span><span class="sxs-lookup"><span data-stu-id="8363f-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="8363f-114">Dva atributa koja čine taj spojeni atribut prikazat će se u dva nova reda ispod spojenog atributa.</span><span class="sxs-lookup"><span data-stu-id="8363f-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8363f-115">![Odabir spojenog atributa](media/configure-data-merge-profile-attributes.png "Odabir spojenog atributa")</span><span class="sxs-lookup"><span data-stu-id="8363f-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="8363f-116">Odvajanje spojenih atributa</span><span class="sxs-lookup"><span data-stu-id="8363f-116">Separate merged attributes</span></span>

<span data-ttu-id="8363f-117">Da biste odvojili ili odspojili bilo koji od automatski spojenih atributa, pronađite atribut u tablici **Atributi profila**.</span><span class="sxs-lookup"><span data-stu-id="8363f-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="8363f-118">Odaberite gumb trotočke (...).</span><span class="sxs-lookup"><span data-stu-id="8363f-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="8363f-119">Na padajućem popisu odaberite **Odvoji polja**.</span><span class="sxs-lookup"><span data-stu-id="8363f-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="8363f-120">Uklanjanje spojenih atributa</span><span class="sxs-lookup"><span data-stu-id="8363f-120">Remove merged attributes</span></span>

<span data-ttu-id="8363f-121">Da biste atribut isključili iz konačnog entiteta profila klijenta, pronađite ga u tablici **Atributi profila**.</span><span class="sxs-lookup"><span data-stu-id="8363f-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="8363f-122">Odaberite gumb trotočke (...).</span><span class="sxs-lookup"><span data-stu-id="8363f-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="8363f-123">Na padajućem popisu odaberite **Nemoj spojiti**.</span><span class="sxs-lookup"><span data-stu-id="8363f-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="8363f-124">Atribut je premješten u odjeljak **Uklonjeno iz zapisa klijenta**.</span><span class="sxs-lookup"><span data-stu-id="8363f-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="8363f-125">Ručno dodavanje spojenog atributa</span><span class="sxs-lookup"><span data-stu-id="8363f-125">Manually add a merged attribute</span></span>

<span data-ttu-id="8363f-126">Da biste dodali spojeni atribut, idite na stranicu **Spoji**.</span><span class="sxs-lookup"><span data-stu-id="8363f-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="8363f-127">Odaberite **Dodaj spojeni atribut**.</span><span class="sxs-lookup"><span data-stu-id="8363f-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="8363f-128">Unesite **Naziv** da biste ga kasnije identificirali na stranici **Spoji**.</span><span class="sxs-lookup"><span data-stu-id="8363f-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="8363f-129">Ako želite, unesite **Zaslonski naziv** koji će se pojaviti u objedinjenom entitetu profila klijenta.</span><span class="sxs-lookup"><span data-stu-id="8363f-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="8363f-130">Konfigurirajte **Odaberi duplicirane atribute** da biste odabrali atribute koje želite spojiti iz uparenih entiteta.</span><span class="sxs-lookup"><span data-stu-id="8363f-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="8363f-131">Također možete tražiti atribute.</span><span class="sxs-lookup"><span data-stu-id="8363f-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="8363f-132">Postavite **Poredak po značaju** da biste dali prednost jednom atributu iznad ostalih.</span><span class="sxs-lookup"><span data-stu-id="8363f-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="8363f-133">Na primjer, ako *WebAccountCSV* entitet uključuje najtočnije podatke o atributu *Puni nazivi*, možete dati prednost ovom entitetu iznad *ContactCSV* odabirom *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="8363f-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="8363f-134">Kao rezultat, *WebAccountCSV* prelazi na prvi prioritet, dok *ContactCSV* prelazi na drugi prioritet pri povlačenju vrijednosti za atribut *Puni naziv*.</span><span class="sxs-lookup"><span data-stu-id="8363f-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="8363f-135">Pokretanje spajanja</span><span class="sxs-lookup"><span data-stu-id="8363f-135">Run your merge</span></span>

<span data-ttu-id="8363f-136">Bilo da ručno spajate atribute ili da ih spaja sustav, uvijek možete pokrenuti spajanje.</span><span class="sxs-lookup"><span data-stu-id="8363f-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="8363f-137">Odaberite **Pokreni** na stranici **Spoji** da biste pokrenuli proces.</span><span class="sxs-lookup"><span data-stu-id="8363f-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8363f-138">![Spremi i pokreni spajanje podataka](media/configure-data-merge-save-run.png "Spremi i pokreni spajanje podataka")</span><span class="sxs-lookup"><span data-stu-id="8363f-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="8363f-139">Da biste napravili dodatne promjene i ponovo pokrenuli korak, možete otkazati slaganje u tijeku.</span><span class="sxs-lookup"><span data-stu-id="8363f-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="8363f-140">Odaberite **Osvježavanje...** i odaberite **Otkaži posao**  na bočnom oknu koje se pojavljuje.</span><span class="sxs-lookup"><span data-stu-id="8363f-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="8363f-141">Nakon što se tekst **Osvježavanje...** promijeni u **Uspješno**, spajanje se dovršilo i riješilo kontradikcije u podacima prema pravilima koje ste definirali.</span><span class="sxs-lookup"><span data-stu-id="8363f-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="8363f-142">Spojeni i nespojeni atributi uključeni su u objedinjeni entitet profila.</span><span class="sxs-lookup"><span data-stu-id="8363f-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="8363f-143">Isključeni atributi nisu uključeni u objedinjeni entitet profila.</span><span class="sxs-lookup"><span data-stu-id="8363f-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="8363f-144">Ako nije prvi put da ste uspješno pokrenuli spajanje, svi postupci, uključujući obogaćivanje, segmentaciju i mjere, automatski će se ponovno pokrenuti.</span><span class="sxs-lookup"><span data-stu-id="8363f-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="8363f-145">Nakon što su se svi postupci ponovno pokrenuli, profili klijenta odražavaju sve promjene.</span><span class="sxs-lookup"><span data-stu-id="8363f-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="8363f-146">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="8363f-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="8363f-147">Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="8363f-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="8363f-148">Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla.</span><span class="sxs-lookup"><span data-stu-id="8363f-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="8363f-149">Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="8363f-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="8363f-150">Sljedeći korak</span><span class="sxs-lookup"><span data-stu-id="8363f-150">Next Step</span></span>

<span data-ttu-id="8363f-151">Konfigurirajte [aktivnosti](activities.md), [obogaćivanje](enrichment-microsoft-graph.md) ili [odnose](relationships.md) za više uvida u svoje klijente.</span><span class="sxs-lookup"><span data-stu-id="8363f-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="8363f-152">Ako ste već konfigurirali aktivnosti, obogaćivanje ili odnose ili ako ste definirali segmente, oni će se automatski obraditi kako bi se upotrijebili najnoviji podaci o klijentima.</span><span class="sxs-lookup"><span data-stu-id="8363f-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]