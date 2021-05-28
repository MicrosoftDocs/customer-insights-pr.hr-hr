---
title: Spajanje entiteta u objedinjavanju podataka
description: Spojite entitete da biste stvorili objedinjene profile klijenata.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085567"
---
# <a name="merge-entities"></a><span data-ttu-id="a6061-103">Spajanje entiteta</span><span class="sxs-lookup"><span data-stu-id="a6061-103">Merge entities</span></span>

<span data-ttu-id="a6061-104">Faza spajanja zadnja je faza u procesu objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="a6061-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="a6061-105">Njezina je svrha usklađivanje zbunjujućih podataka.</span><span class="sxs-lookup"><span data-stu-id="a6061-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="a6061-106">Primjeri sukobljenih podataka mogu uključivati ime klijenta koje se nalazi u dvama skupovima podataka, ali se malo drugačije prikazuje u svakome od njih („Grant Marshall” u odnosu na „Grant Marshal”) ili telefonski broj koji se razlikuje u obliku (617-803-091X u odnosu na 617803091X).</span><span class="sxs-lookup"><span data-stu-id="a6061-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="a6061-107">Spajanje tih zbunjujućih podatkovnih točaka vrši se na osnovi atribut prema atributu.</span><span class="sxs-lookup"><span data-stu-id="a6061-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Stranica spajanja u postupku objedinjavanja podataka koja prikazuje tablicu sa spojenim poljima koja definiraju objedinjeni profil klijenta.":::

<span data-ttu-id="a6061-109">Nakon dovršetka [faze uparivanja](match-entities.md) fazu spajanja možete započeti odabirom pločice **Spajanje** na stranici **Objedinjavanje**.</span><span class="sxs-lookup"><span data-stu-id="a6061-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="a6061-110">Pregled preporuka sustava</span><span class="sxs-lookup"><span data-stu-id="a6061-110">Review system recommendations</span></span>

<span data-ttu-id="a6061-111">U odjeljku **Podaci** > **Objedini** > **Spoji** odabirete i isključujete atribute za spajanje unutar vašeg entiteta objedinjenog profila klijenta.</span><span class="sxs-lookup"><span data-stu-id="a6061-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="a6061-112">Objedinjeni profil klijenta rezultat je postupka objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="a6061-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="a6061-113">Sustav automatski spaja neke atribute.</span><span class="sxs-lookup"><span data-stu-id="a6061-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="a6061-114">Da biste pregledali atribute koji su uključeni u jedan od vaših automatski spojenih atributa, odaberite taj spojeni atribut na kartici **Polja klijenata** za tablicu.</span><span class="sxs-lookup"><span data-stu-id="a6061-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="a6061-115">Atributi koji čine taj spojeni atribut prikazuju se u dva nova retka ispod spojenog atributa.</span><span class="sxs-lookup"><span data-stu-id="a6061-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="a6061-116">Razdvajanje, preimenovanje, isključivanje i uređivanje spojenih polja</span><span class="sxs-lookup"><span data-stu-id="a6061-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="a6061-117">Možete promijeniti način na koji sustav obrađuje spojene atribute kako bi stvorio objedinjeni profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="a6061-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="a6061-118">Odaberite **Prikaži više** i odaberite što želite promijeniti.</span><span class="sxs-lookup"><span data-stu-id="a6061-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Mogućnosti u padajućem izborniku Prikaži više za upravljanje spojenim atributima.":::

<span data-ttu-id="a6061-120">Dodatne informacije potražite u sljedećim odjeljcima.</span><span class="sxs-lookup"><span data-stu-id="a6061-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="a6061-121">Razdvajanje spojenih polja</span><span class="sxs-lookup"><span data-stu-id="a6061-121">Separate merged fields</span></span>

<span data-ttu-id="a6061-122">Da biste razdvojili spojena polja, pronađite atribut u tablici.</span><span class="sxs-lookup"><span data-stu-id="a6061-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="a6061-123">Razdvojena polja prikazuju se kao pojedinačne podatkovne točke na objedinjenom profilu klijenta.</span><span class="sxs-lookup"><span data-stu-id="a6061-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="a6061-124">Odaberite spojeno polje.</span><span class="sxs-lookup"><span data-stu-id="a6061-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="a6061-125">Odaberite **Prikaži više** pa odaberite **Razdvoji polja**.</span><span class="sxs-lookup"><span data-stu-id="a6061-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="a6061-126">Potvrdite razdvajanje.</span><span class="sxs-lookup"><span data-stu-id="a6061-126">Confirm the separation.</span></span>

1. <span data-ttu-id="a6061-127">Odaberite **Spremi** i **Pokreni** za obradu promjena.</span><span class="sxs-lookup"><span data-stu-id="a6061-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="a6061-128">Preimenovanje spojenih polja</span><span class="sxs-lookup"><span data-stu-id="a6061-128">Rename merged fields</span></span>

<span data-ttu-id="a6061-129">Promijenite zaslonski naziv spojenih atributa.</span><span class="sxs-lookup"><span data-stu-id="a6061-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="a6061-130">Ne možete promijeniti naziv izlaznog entiteta.</span><span class="sxs-lookup"><span data-stu-id="a6061-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="a6061-131">Odaberite spojeno polje.</span><span class="sxs-lookup"><span data-stu-id="a6061-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="a6061-132">Odaberite **Prikaži više** pa odaberite **Preimenuj**.</span><span class="sxs-lookup"><span data-stu-id="a6061-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="a6061-133">Potvrdite promijenjeni zaslonski naziv.</span><span class="sxs-lookup"><span data-stu-id="a6061-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="a6061-134">Odaberite **Spremi** i **Pokreni** za obradu promjena.</span><span class="sxs-lookup"><span data-stu-id="a6061-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="a6061-135">Isključivanje spojenih polja</span><span class="sxs-lookup"><span data-stu-id="a6061-135">Exclude merged fields</span></span>

<span data-ttu-id="a6061-136">Isključite atribut iz objedinjenog profila klijenta.</span><span class="sxs-lookup"><span data-stu-id="a6061-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="a6061-137">Ako se polje koristi u drugim postupcima, npr. u segmentu, uklonite ga iz tih postupaka prije nego što ga isključite iz profila klijenta.</span><span class="sxs-lookup"><span data-stu-id="a6061-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="a6061-138">Odaberite spojeno polje.</span><span class="sxs-lookup"><span data-stu-id="a6061-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="a6061-139">Odaberite **Prikaži više** pa odaberite **Isključi**.</span><span class="sxs-lookup"><span data-stu-id="a6061-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="a6061-140">Potvrdite isključivanje.</span><span class="sxs-lookup"><span data-stu-id="a6061-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="a6061-141">Odaberite **Spremi** i **Pokreni** za obradu promjena.</span><span class="sxs-lookup"><span data-stu-id="a6061-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="a6061-142">Na stranici **Spajanje** odaberite **Isključena polja** da biste vidjeli popis svih isključenih polja.</span><span class="sxs-lookup"><span data-stu-id="a6061-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="a6061-143">Ovo okno omogućuje vraćanje isključenih polja.</span><span class="sxs-lookup"><span data-stu-id="a6061-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="a6061-144">Ručno kombiniranje polja</span><span class="sxs-lookup"><span data-stu-id="a6061-144">Manually combine fields</span></span>

<span data-ttu-id="a6061-145">Ručno navedite spojeni atribut.</span><span class="sxs-lookup"><span data-stu-id="a6061-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="a6061-146">Na stranici **Spajanje** odaberite **Kombiniraj polja**.</span><span class="sxs-lookup"><span data-stu-id="a6061-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="a6061-147">Navedite **Naziv** i **Naziv polja rezultata**.</span><span class="sxs-lookup"><span data-stu-id="a6061-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="a6061-148">Odaberite polje za dodavanje.</span><span class="sxs-lookup"><span data-stu-id="a6061-148">Choose a field to add.</span></span> <span data-ttu-id="a6061-149">Odaberite **Dodaj polja** za kombiniranje više polja.</span><span class="sxs-lookup"><span data-stu-id="a6061-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="a6061-150">Potvrdite isključivanje.</span><span class="sxs-lookup"><span data-stu-id="a6061-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="a6061-151">Odaberite **Spremi** i **Pokreni** za obradu promjena.</span><span class="sxs-lookup"><span data-stu-id="a6061-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="a6061-152">Promjena redoslijeda polja</span><span class="sxs-lookup"><span data-stu-id="a6061-152">Change the order of fields</span></span>

<span data-ttu-id="a6061-153">Neki entiteti sadrže više pojedinosti od drugih.</span><span class="sxs-lookup"><span data-stu-id="a6061-153">Some entities contain more details than others.</span></span> <span data-ttu-id="a6061-154">Ako entitet uključuje najnovije podatke o polju, možete mu dati prednost nad drugim entitetima pri spajanju vrijednosti.</span><span class="sxs-lookup"><span data-stu-id="a6061-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="a6061-155">Odaberite spojeno polje.</span><span class="sxs-lookup"><span data-stu-id="a6061-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="a6061-156">Odaberite **Prikaži više** pa odaberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="a6061-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="a6061-157">U oknu **Kombiniraj polja** odaberite **Pomakni gore/dolje** za postavljanje redoslijeda ili ih povucite i ispustite u željeni položaj.</span><span class="sxs-lookup"><span data-stu-id="a6061-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="a6061-158">Potvrdite promjenu.</span><span class="sxs-lookup"><span data-stu-id="a6061-158">Confirm the change.</span></span>

1. <span data-ttu-id="a6061-159">Odaberite **Spremi** i **Pokreni** za obradu promjena.</span><span class="sxs-lookup"><span data-stu-id="a6061-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="a6061-160">Pokretanje spajanja</span><span class="sxs-lookup"><span data-stu-id="a6061-160">Run your merge</span></span>

<span data-ttu-id="a6061-161">Bilo da ručno spajate atribute ili da ih spaja sustav, uvijek možete pokrenuti spajanje.</span><span class="sxs-lookup"><span data-stu-id="a6061-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="a6061-162">Odaberite **Pokreni** na stranici **Spoji** da biste pokrenuli proces.</span><span class="sxs-lookup"><span data-stu-id="a6061-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6061-163">![Spremi i pokreni spajanje podataka](media/configure-data-merge-save-run.png "Spremi i pokreni spajanje podataka")</span><span class="sxs-lookup"><span data-stu-id="a6061-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="a6061-164">Odaberite **Pokreni samo spajanje** ako želite vidjeti samo rezultat koji se odražava u objedinjenom entitetu klijenta.</span><span class="sxs-lookup"><span data-stu-id="a6061-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="a6061-165">Nizvodni procesi bit će osvježeni kako je [definirano u rasporedu osvježavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a6061-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="a6061-166">Odaberite **Pokreni spajanje i nizvodne procese** kako biste sustav osvježili svojim promjenama.</span><span class="sxs-lookup"><span data-stu-id="a6061-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="a6061-167">Svi procesi, uključujući obogaćivanje, segmente i mjere automatski će se ponovno pokrenuti.</span><span class="sxs-lookup"><span data-stu-id="a6061-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="a6061-168">Nakon završetka svih nizvodnih procesa, profili klijenata odražavaju sve promjene koje ste napravili.</span><span class="sxs-lookup"><span data-stu-id="a6061-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="a6061-169">Da biste izvršili više promjena i ponovno pokrenuli korak, možete otkazati spajanje u tijeku.</span><span class="sxs-lookup"><span data-stu-id="a6061-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="a6061-170">Odaberite **Osvježavanje...** i odaberite **Otkaži posao**  na bočnom oknu koje se pojavljuje.</span><span class="sxs-lookup"><span data-stu-id="a6061-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="a6061-171">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="a6061-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a6061-172">Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a6061-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a6061-173">Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla.</span><span class="sxs-lookup"><span data-stu-id="a6061-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a6061-174">Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="a6061-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="a6061-175">Sljedeći korak</span><span class="sxs-lookup"><span data-stu-id="a6061-175">Next Step</span></span>

<span data-ttu-id="a6061-176">Konfigurirajte [aktivnosti](activities.md), [obogaćivanje](enrichment-hub.md) ili [odnose](relationships.md) za više uvida u svoje klijente.</span><span class="sxs-lookup"><span data-stu-id="a6061-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="a6061-177">Ako ste već konfigurirali aktivnosti, obogaćivanje ili segmente, obrađivat će se automatski kako bi se upotrijebili najnoviji podaci o klijentu.</span><span class="sxs-lookup"><span data-stu-id="a6061-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
