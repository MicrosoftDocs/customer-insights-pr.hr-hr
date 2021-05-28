---
title: Predloženi segmenti na temelju aktivnosti.
description: Neka vam strojno učenje pomogne da pronađete nove i zanimljive segmente na temelju aktivnosti klijenata.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034057"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="b461d-103">Predloženi segmenti na temelju podataka o aktivnostima (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="b461d-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="b461d-104">Otkrijte zanimljive segmente svojih klijenata na temelju podataka o aktivnostima klijenata koji se unose u Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b461d-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="b461d-105">Primjeri podataka o aktivnostima su transakcije, trajanje poziva za podršku, kupnje ili povrati.</span><span class="sxs-lookup"><span data-stu-id="b461d-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="b461d-106">Da bi se segmenti predložili, podaci o aktivnostima analiziraju se u odnosu na vrijeme, učestalost i novčanu vrijednost (ili trajanje).</span><span class="sxs-lookup"><span data-stu-id="b461d-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="b461d-107">Umjesto toga možete stvoriti [predložene segmente za poboljšanje mjere ili bolje razumijevanje utjecaja na atribut](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="b461d-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Kartica predloženih segmenata koja prikazuje prijedloge segmenata za segmente na temelju aktivnosti i atributa.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="b461d-109">Kategorizacija klijenata prema aktivnosti</span><span class="sxs-lookup"><span data-stu-id="b461d-109">Categorize customers by activity</span></span>

<span data-ttu-id="b461d-110">S [podacima o aktivnostima](activities.md) dostupnim u usluzi Customer Insights možemo stvoriti prijedloge koji predstavljaju grupe klijenata:</span><span class="sxs-lookup"><span data-stu-id="b461d-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="b461d-111">najaktivniji klijenti</span><span class="sxs-lookup"><span data-stu-id="b461d-111">most active customers</span></span> 
- <span data-ttu-id="b461d-112">klijenti koji su obavili najviše kupnji</span><span class="sxs-lookup"><span data-stu-id="b461d-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="b461d-113">klijenti koji su stvorili najviše prihoda</span><span class="sxs-lookup"><span data-stu-id="b461d-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="b461d-114">klijenti koji u posljednje vrijeme nisu aktivni</span><span class="sxs-lookup"><span data-stu-id="b461d-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="b461d-115">klijenti koji često komuniciraju s vašom tvrtkom</span><span class="sxs-lookup"><span data-stu-id="b461d-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="b461d-116">Ako imate maloprodajnu trgovinu, mogli biste saznati koji klijenti donose najveći prihod i nagraditi ih kuponom.</span><span class="sxs-lookup"><span data-stu-id="b461d-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="b461d-117">Ili možete identificirati povremene klijente i ponuditi im da se pridruže programu nagrađivanja kako bi češće posjećivali vašu tvrtku.</span><span class="sxs-lookup"><span data-stu-id="b461d-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="b461d-118">Ako se bavite zdravstvenom djelatnošću koja pruža javnu zdravstvenu zaštitu i vaš je cilj smanjiti troškove za pojedine pacijente.</span><span class="sxs-lookup"><span data-stu-id="b461d-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="b461d-119">Način da se to učini mogao bi biti smanjenje ponavljajućih posjeta pružanjem najbolje moguće skrbi u što manje posjeta.</span><span class="sxs-lookup"><span data-stu-id="b461d-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="b461d-120">U ovom je slučaju vaš cilj održati učestalost posjeta niskom i minimizirati ponavljajuće troškove za pacijente.</span><span class="sxs-lookup"><span data-stu-id="b461d-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="b461d-121">Ili možete identificirati segmente pacijenata koji imaju česte posjete i visoke troškove koji se ponavljaju i analizirati te slučajeve kako biste poboljšali liječenje pojedinca.</span><span class="sxs-lookup"><span data-stu-id="b461d-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="b461d-122">Obavezni podaci</span><span class="sxs-lookup"><span data-stu-id="b461d-122">Required data</span></span>

<span data-ttu-id="b461d-123">Prijedlozi se stvaraju na temelju odabranih ulaznih podataka.</span><span class="sxs-lookup"><span data-stu-id="b461d-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="b461d-124">Profili klijenata: svi klijenti ili članovi određenog segmenta.</span><span class="sxs-lookup"><span data-stu-id="b461d-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="b461d-125">Vremensko razdoblje: prošli mjesec, prošla godina ili bilo koji prilagođeni vremenski okvir.</span><span class="sxs-lookup"><span data-stu-id="b461d-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="b461d-126">Vrsta aktivnosti: kupnje, maloprodajne transakcije, mrežne transakcije, slučajevi korisničke podrške, pretplate itd.</span><span class="sxs-lookup"><span data-stu-id="b461d-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="b461d-127">Entitet u usluzi Customer Insights koji sadrži podatke o aktivnostima: entitet UnifiedActivity ili entitet za određenu aktivnost.</span><span class="sxs-lookup"><span data-stu-id="b461d-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="b461d-128">Dimenzije koje treba uključiti: vrijeme, učestalost ili novčanu dimenziju, ovisno o vašim poslovnim zahtjevima.</span><span class="sxs-lookup"><span data-stu-id="b461d-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="b461d-129">Stvaranje predloženih segmenata</span><span class="sxs-lookup"><span data-stu-id="b461d-129">Generate suggested segments</span></span>

1. <span data-ttu-id="b461d-130">Idite na **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="b461d-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="b461d-131">Odaberite karticu **Prijedlozi (pretpregled)**.</span><span class="sxs-lookup"><span data-stu-id="b461d-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="b461d-132">Odaberite **Pronađi nove prijedloge** i odaberite **Prati ili predvidi ponašanje klijenata**.</span><span class="sxs-lookup"><span data-stu-id="b461d-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="b461d-133">Odaberite **Pokreni** za pokretanje vođenog iskustva.</span><span class="sxs-lookup"><span data-stu-id="b461d-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Prvi korak čarobnjaka za konfiguraciju za predloženi segment na temelju aktivnosti.":::

1. <span data-ttu-id="b461d-135">Navedite potrebne ulazne podatke i odaberite **Sljedeće** za nastavak.</span><span class="sxs-lookup"><span data-stu-id="b461d-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="b461d-136">Odaberite klijente: uključite sve klijente ili određeni segment.</span><span class="sxs-lookup"><span data-stu-id="b461d-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="b461d-137">Odaberite aktivnost: odaberite vrstu aktivnosti i entitete koji opisuju aktivnost.</span><span class="sxs-lookup"><span data-stu-id="b461d-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="b461d-138">Postavke: postavite vremensko razdoblje koje treba uzeti u obzir, čimbenike za prijedloge i mapirajte atribute.</span><span class="sxs-lookup"><span data-stu-id="b461d-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="b461d-139">Pregledajte svoj unos i odaberite **Pokreni** za pokretanje modela i stvaranje prijedloga.</span><span class="sxs-lookup"><span data-stu-id="b461d-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="b461d-140">To može potrajati nekoliko minuta, ovisno o broju profila klijenata i odabranim aktivnostima.</span><span class="sxs-lookup"><span data-stu-id="b461d-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="b461d-141">Nakon stvaranja prijedloga možete ih filtrirati prema dimenziji ili vrijednosti koja vas najviše zanima.</span><span class="sxs-lookup"><span data-stu-id="b461d-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="b461d-142">Prikaz pojedinosti o predloženom segmentu</span><span class="sxs-lookup"><span data-stu-id="b461d-142">View details of a suggested segment</span></span>

<span data-ttu-id="b461d-143">Kada se stvore prijedlozi, pronaći ćete ih na popisu **Segmenti** > **Prijedlozi (pretpregled)** u odjeljku **Prijedlozi na temelju aktivnosti**.</span><span class="sxs-lookup"><span data-stu-id="b461d-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Prošireno bočno okno s detaljnim podacima predloženog segmenta.":::

<span data-ttu-id="b461d-145">Odaberite **Prikaži prijedlog** na predloženom segmentu za pregled pojedinosti tog segmenta.</span><span class="sxs-lookup"><span data-stu-id="b461d-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="b461d-146">Bočno okno pruža pojedinosti poput opsega svake dimenzije u usporedbi s ciljnom skupinom.</span><span class="sxs-lookup"><span data-stu-id="b461d-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="b461d-147">Također naglašava broj potencijalnih članova u segmentu i odgovarajući postotak ukupnog broja klijenata.</span><span class="sxs-lookup"><span data-stu-id="b461d-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="b461d-148">Ako želite zadržati prijedlog kao segment, odaberite **Stvori segment**.</span><span class="sxs-lookup"><span data-stu-id="b461d-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="b461d-149">Spremanje prijedloga kao segmenta</span><span class="sxs-lookup"><span data-stu-id="b461d-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="b461d-150">Idite u odjeljak **Segmenti** > **Prijedlozi (pretpregled)**.</span><span class="sxs-lookup"><span data-stu-id="b461d-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="b461d-151">Odaberite segment koji želite spremiti.</span><span class="sxs-lookup"><span data-stu-id="b461d-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="b461d-152">U bočnom oknu odaberite **Stvori segment**.</span><span class="sxs-lookup"><span data-stu-id="b461d-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="b461d-153">Nakon spremanja segmenta, prikazat će se na popisu segmenata na kartici **Svi segmenti**. Sad se može [osvježiti ili izbrisati kao i bilo koji drugi segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b461d-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="b461d-154">Ne možete uređivati pojedinosti segmenta.</span><span class="sxs-lookup"><span data-stu-id="b461d-154">You can't edit the segment details.</span></span> <span data-ttu-id="b461d-155">Međutim, možete promijeniti ulazne kriterije za prijedloge i stvarati različite prijedloge.</span><span class="sxs-lookup"><span data-stu-id="b461d-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="b461d-156">Osvježavanje ili uređivanje skupa prijedloga</span><span class="sxs-lookup"><span data-stu-id="b461d-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="b461d-157">Idite na **Segmenti** > **Prijedlozi (pretpregled)** i potražite segment u odjeljku **Prijedlozi na temelju aktivnosti**.</span><span class="sxs-lookup"><span data-stu-id="b461d-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="b461d-158">Odaberite **Osvježavanje prijedloga** za osvježavanje prijedloga uz zadržavanje konfiguriranih atributa.</span><span class="sxs-lookup"><span data-stu-id="b461d-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="b461d-159">Ili odaberite **Uredi prijedloge** za izmjenu konfiguriranih atributa.</span><span class="sxs-lookup"><span data-stu-id="b461d-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="b461d-160">Sustav će ponoviti postupak, stvoriti prijedloge segmenata na temelju najnovijih podataka i zamijeniti trenutne prijedloge.</span><span class="sxs-lookup"><span data-stu-id="b461d-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
