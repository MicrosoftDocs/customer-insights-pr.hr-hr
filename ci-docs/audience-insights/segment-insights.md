---
title: Uvidi u segmente za postojeće segmente
description: Steknite uvid u postojeće segmente da biste vidjeli razlike i zajedničke karakteristike.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 92e1b05dd08588a5da446af5b17b2d6ce57490ce
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405339"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="a1181-103">Uvidi u segmente (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="a1181-103">Segment insights (preview)</span></span>

<span data-ttu-id="a1181-104">Otkrijte dodatne informacije i uvide o svojim postojećim segmentima.</span><span class="sxs-lookup"><span data-stu-id="a1181-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="a1181-105">Otkrijte što razlikuje dva segmenta ili što imaju zajedničko.</span><span class="sxs-lookup"><span data-stu-id="a1181-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="a1181-106">Preklapanje segmenata</span><span class="sxs-lookup"><span data-stu-id="a1181-106">Segment overlap</span></span>

<span data-ttu-id="a1181-107">Analiza preklapanja segmenata pokazuje tko su i koliko ima klijenata zajedničkih za dva ili više segmenta.</span><span class="sxs-lookup"><span data-stu-id="a1181-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="a1181-108">Na primjer, kako se neki segment čestih klijenata preklapa sa segmentom koji sadrži klijente koji su zadovoljni vašom uslugom ili proizvodom.</span><span class="sxs-lookup"><span data-stu-id="a1181-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="a1181-109">Također, možete analizirati kako se preklapanje mijenja za određene atribute.</span><span class="sxs-lookup"><span data-stu-id="a1181-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="a1181-110">Pokretanje analize preklapanja</span><span class="sxs-lookup"><span data-stu-id="a1181-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="a1181-111">Idite na **Segmenti** i odaberite karticu **Uvidi (pretpregled)**.</span><span class="sxs-lookup"><span data-stu-id="a1181-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="a1181-112">Odaberite **Novo** i odaberite opciju **Preklapanje** u oknu **Odabir vrste uvida**.</span><span class="sxs-lookup"><span data-stu-id="a1181-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="a1181-113">Odaberite segmente koji vas zanimaju i odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="a1181-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="a1181-114">Također, možete odabrati jedno ili više polja koja vas zanimaju kako biste analizirali preklapanja za svaku moguću vrijednost polja i zatim odabrati **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="a1181-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="a1181-115">Navedite naziv za analizu preklapanja, neobvezni zaslonski naziv i opis.</span><span class="sxs-lookup"><span data-stu-id="a1181-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="a1181-116">Odaberite **Spremi** kako biste započeli analizu.</span><span class="sxs-lookup"><span data-stu-id="a1181-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="a1181-117">Analiza preklapanja bit će spremna kada se status promijeni s Osvježavanje na Uspješno.</span><span class="sxs-lookup"><span data-stu-id="a1181-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="a1181-118">Prikaz i optimiziranje analize preklapanja</span><span class="sxs-lookup"><span data-stu-id="a1181-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="a1181-119">Nakon dovršetka analize, pronađite detalje o ovom uvidu u **Segmenti** > **Uvidi (pretpregled)**.</span><span class="sxs-lookup"><span data-stu-id="a1181-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Pojedinosti uvida o preklapanju segmenta":::

<span data-ttu-id="a1181-121">Odaberite uvid da biste vidjeli rezultate analize:</span><span class="sxs-lookup"><span data-stu-id="a1181-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="a1181-122">Broj članova kod kojih se preklapaju segmenti odabrani za analizu.</span><span class="sxs-lookup"><span data-stu-id="a1181-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="a1181-123">Broj članova koji su uključeni u jedan od segmenata, ali ne i u ostale segmente.</span><span class="sxs-lookup"><span data-stu-id="a1181-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="a1181-124">Ako ste tijekom konfiguriranja analize preklapanja odabrali polja, naći ćete ih na odgovarajućim karticama.</span><span class="sxs-lookup"><span data-stu-id="a1181-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="a1181-125">Pomoću padajućeg izbornika filtra možete odabrati bilo koju razinu atributa koja vas zanima, a tablica pri dnu prikazat će odgovarajuće podatke.</span><span class="sxs-lookup"><span data-stu-id="a1181-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="a1181-126">Diferencijatori segmenta</span><span class="sxs-lookup"><span data-stu-id="a1181-126">Segment differentiators</span></span>

<span data-ttu-id="a1181-127">Elementi razlikovanja segmenata pomažu vam otkriti po čemu se neki segment razlikuje od ostalih klijenata ili nekog drugog segmenta.</span><span class="sxs-lookup"><span data-stu-id="a1181-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="a1181-128">Trebate samo odabrati segment i sustav će prepoznati atribute profila i mjere koje razlikuju odabrani segment.</span><span class="sxs-lookup"><span data-stu-id="a1181-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="a1181-129">Pokretanje analize elemenata razlikovanja</span><span class="sxs-lookup"><span data-stu-id="a1181-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="a1181-130">Idite na **Segmenti** i odaberite karticu **Uvidi (pretpregled)**.</span><span class="sxs-lookup"><span data-stu-id="a1181-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="a1181-131">Odaberite **Novo** i odaberite opciju **Preklapanje** u oknu **Odabir vrste uvida**.</span><span class="sxs-lookup"><span data-stu-id="a1181-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="a1181-132">Odaberite segment koji želite analizirati kao **Primarni segment** i odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="a1181-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="a1181-133">Odaberite **Svi klijenti** ili **Sekundarni segment** za usporedbu vašeg primarnog segmenta i zatim odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="a1181-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="a1181-134">Također, možete odabrati jedno ili više polja koja vas zanimaju da biste analizu usredotočili na određene atribute i zatim odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="a1181-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="a1181-135">Navedite naziv za analizu preklapanja, neobvezni zaslonski naziv i opis.</span><span class="sxs-lookup"><span data-stu-id="a1181-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="a1181-136">Odaberite **Spremi** kako biste započeli analizu.</span><span class="sxs-lookup"><span data-stu-id="a1181-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="a1181-137">Analiza preklapanja bit će spremna kada se status promijeni s Osvježavanje na Uspješno.</span><span class="sxs-lookup"><span data-stu-id="a1181-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="a1181-138">Prikaz i optimiziranje analize elemenata razlikovanja</span><span class="sxs-lookup"><span data-stu-id="a1181-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="a1181-139">Nakon dovršetka analize, pronađite detalje o ovom uvidu u **Segmenti** > **Uvidi (pretpregled)**.</span><span class="sxs-lookup"><span data-stu-id="a1181-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Pojedinosti uvida u elemente razlikovanja segmenta":::

<span data-ttu-id="a1181-141">Odaberite uvid da biste vidjeli rezultate analize.</span><span class="sxs-lookup"><span data-stu-id="a1181-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="a1181-142">Analiza elemenata razlikovanja uključuje dvije kartice.</span><span class="sxs-lookup"><span data-stu-id="a1181-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="a1181-143">Na kartici **Atributi** nalaze se atributi profila koji se smatraju elementima razlikovanja.</span><span class="sxs-lookup"><span data-stu-id="a1181-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="a1181-144">Na kartici **Mjere** nalaze se elementi razlikovanja.</span><span class="sxs-lookup"><span data-stu-id="a1181-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="a1181-145">Svaka kartica sadrži sljedeće detalje:</span><span class="sxs-lookup"><span data-stu-id="a1181-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="a1181-146">Rangirani popis elemenata razlikovanja, poredan po ocjeni razlike.</span><span class="sxs-lookup"><span data-stu-id="a1181-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="a1181-147">**Ocjena razlike** za svaki element razlikovanja.</span><span class="sxs-lookup"><span data-stu-id="a1181-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="a1181-148">Ocjena razlike predstavlja stupanj razlike atributa između dva segmenta.</span><span class="sxs-lookup"><span data-stu-id="a1181-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="a1181-149">Što je veća ocjena razlike, to se više atributi razlikuju između dva segmenta.</span><span class="sxs-lookup"><span data-stu-id="a1181-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="a1181-150">Odaberite ocjenu kako bi se otvorilo okno **Ocjena razlike** s raspodjelom vrijednosti za taj atribut.</span><span class="sxs-lookup"><span data-stu-id="a1181-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="a1181-151">Upravljanje uvidima u segmente</span><span class="sxs-lookup"><span data-stu-id="a1181-151">Manage segment insights</span></span>

<span data-ttu-id="a1181-152">Sljedeće opcije s naredbene trake možete koristiti za svoje uvide:</span><span class="sxs-lookup"><span data-stu-id="a1181-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="a1181-153">**Natrag** za vraćanje popisa uvida</span><span class="sxs-lookup"><span data-stu-id="a1181-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="a1181-154">**Osvježi** za ponovno pokretanje analize</span><span class="sxs-lookup"><span data-stu-id="a1181-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="a1181-155">**Izbriši** za uklanjanje ovog uvida</span><span class="sxs-lookup"><span data-stu-id="a1181-155">**Delete** to remove this insight</span></span>
