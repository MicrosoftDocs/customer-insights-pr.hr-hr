---
title: Stvaranje i upravljanje segmentima
description: Izradite segmente klijenata da biste ih grupirali na temelju različitih atributa.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597042"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="233ed-103">Stvaranje i upravljanje segmentima</span><span class="sxs-lookup"><span data-stu-id="233ed-103">Create and manage segments</span></span>

<span data-ttu-id="233ed-104">Segmenti vam omogućuju grupiranje klijenata na temelju demografskih, transakcijskih ili bihevioralnih atributa.</span><span class="sxs-lookup"><span data-stu-id="233ed-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="233ed-105">Možete koristiti segmente za ciljanje promotivnih kampanja, prodajnih aktivnosti i radnji za korisničku podršku kako biste postigli svoje poslovne ciljeve.</span><span class="sxs-lookup"><span data-stu-id="233ed-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="233ed-106">Složene filtre možete definirati oko entiteta Profil klijenta i povezanih entiteta.</span><span class="sxs-lookup"><span data-stu-id="233ed-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="233ed-107">Nakon obrade, svaki segment stvara skup zapisa o klijentima koji možete izvesti i koristiti za rad.</span><span class="sxs-lookup"><span data-stu-id="233ed-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="233ed-108">Primjenjuju se neka [ograničenja usluge](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="233ed-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="233ed-109">Ako nije drugačije navedeno, svi segmenti jesu **Dinamički segmenti** koji se redovito osvježavaju.</span><span class="sxs-lookup"><span data-stu-id="233ed-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="233ed-110">Sljedeći primjer prikazuje način upotrebe segmentacije.</span><span class="sxs-lookup"><span data-stu-id="233ed-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="233ed-111">Definirali smo segment za klijente koji su naručili najmanje $500 robe u posljednjih 90 dana *i* koji su bili uključeni u poziv službe za korisnike koji je eskalirao.</span><span class="sxs-lookup"><span data-stu-id="233ed-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="233ed-112">![Više grupa](media/segmentation-group1-2.png "Više grupa")</span><span class="sxs-lookup"><span data-stu-id="233ed-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="233ed-113">Izrada novog segmenta</span><span class="sxs-lookup"><span data-stu-id="233ed-113">Create a new segment</span></span>

<span data-ttu-id="233ed-114">Segmentima se upravlja na stranici **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="233ed-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="233ed-115">U uvidima u ciljnu skupinu idite na stranicu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="233ed-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="233ed-116">Odaberite **Novo** > **Prazni segment**.</span><span class="sxs-lookup"><span data-stu-id="233ed-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="233ed-117">U oknu **Novi segment** odaberite vrstu segmenta i navedite **Naziv**.</span><span class="sxs-lookup"><span data-stu-id="233ed-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="233ed-118">Po želji navedite zaslonski naziv i opis koji pomaže u prepoznavanju segmenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="233ed-119">Odaberite **Dalje** da biste pristupili stranici **Alat za sastavljanje segmenata** na kojoj definirate grupu.</span><span class="sxs-lookup"><span data-stu-id="233ed-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="233ed-120">Grupa je skup klijenata.</span><span class="sxs-lookup"><span data-stu-id="233ed-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="233ed-121">Odaberite entitet koji uključuje atribut za koji želite segmentiranje.</span><span class="sxs-lookup"><span data-stu-id="233ed-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="233ed-122">Odaberite atribut za segmentaciju.</span><span class="sxs-lookup"><span data-stu-id="233ed-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="233ed-123">Ovaj atribut može imati jednu od četiri vrste vrijednosti: numeričku, niz, datum ili Booleov izraz.</span><span class="sxs-lookup"><span data-stu-id="233ed-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="233ed-124">Odaberite operatora i vrijednost za odabrani atribut.</span><span class="sxs-lookup"><span data-stu-id="233ed-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="233ed-125">![Prilagođeni filtar grupe](media/customer-group-numbers.png "Filtar grupe klijenata")</span><span class="sxs-lookup"><span data-stu-id="233ed-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="233ed-126">Broj</span><span class="sxs-lookup"><span data-stu-id="233ed-126">Number</span></span> |<span data-ttu-id="233ed-127">Definicija</span><span class="sxs-lookup"><span data-stu-id="233ed-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="233ed-128">1</span><span class="sxs-lookup"><span data-stu-id="233ed-128">1</span></span>     |<span data-ttu-id="233ed-129">Entity</span><span class="sxs-lookup"><span data-stu-id="233ed-129">Entity</span></span>          |
   |<span data-ttu-id="233ed-130">2</span><span class="sxs-lookup"><span data-stu-id="233ed-130">2</span></span>     |<span data-ttu-id="233ed-131">Atribut</span><span class="sxs-lookup"><span data-stu-id="233ed-131">Attribute</span></span>          |
   |<span data-ttu-id="233ed-132">3</span><span class="sxs-lookup"><span data-stu-id="233ed-132">3</span></span>    |<span data-ttu-id="233ed-133">Operater</span><span class="sxs-lookup"><span data-stu-id="233ed-133">Operator</span></span>         |
   |<span data-ttu-id="233ed-134">4</span><span class="sxs-lookup"><span data-stu-id="233ed-134">4</span></span>    |<span data-ttu-id="233ed-135">Value</span><span class="sxs-lookup"><span data-stu-id="233ed-135">Value</span></span>         |

8. <span data-ttu-id="233ed-136">Ako je entitet povezan s objedinjenim entitetom klijenta putem [odnosa](relationships.md), morate definirati putanju odnosa za stvaranje valjanog segmenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="233ed-137">Dodajte entitete s putanje odnosa sve dok ne možete odabrati entitet **Klijent: CustomerInsights** s padajućeg izbornika.</span><span class="sxs-lookup"><span data-stu-id="233ed-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="233ed-138">Zatim odaberite **Svi zapisi** za svaki uvjet.</span><span class="sxs-lookup"><span data-stu-id="233ed-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="233ed-139">![Putanja odnosa tijekom stvaranja segmenta](media/segments-multiple-relationships.png "Putanja odnosa tijekom stvaranja segmenta")</span><span class="sxs-lookup"><span data-stu-id="233ed-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="233ed-140">Prema zadanim postavkama, segmenti generiraju izlazni entitet koji sadrži sve atribute profila klijenata koji odgovaraju definiranim filtrima.</span><span class="sxs-lookup"><span data-stu-id="233ed-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="233ed-141">Ako se segment temelji na drugim entitetima osim na entitetu *Klijent*, izlaznom entitetu možete dodati više atributa iz tih entiteta.</span><span class="sxs-lookup"><span data-stu-id="233ed-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="233ed-142">Odaberite stavku **Atributi projekta** za odabir atributa koji će se dodati izlaznom entitetu.</span><span class="sxs-lookup"><span data-stu-id="233ed-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="233ed-143">Primjer: Segment se temelji na entitetu koji sadrži podatke o aktivnostima klijenta koji su povezani s entitetom *Klijent*.</span><span class="sxs-lookup"><span data-stu-id="233ed-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="233ed-144">Segment traži sve klijente koji su nazvali službu za pomoć u posljednjih 60 dana.</span><span class="sxs-lookup"><span data-stu-id="233ed-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="233ed-145">Možete odabrati dodavanje trajanja poziva i broja poziva svim odgovarajućim zapisima klijenata u izlaznom entitetu.</span><span class="sxs-lookup"><span data-stu-id="233ed-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="233ed-146">Ove bi informacije mogle biti korisne za slanje e-pošte s korisnim vezama do članaka za pomoć na mreži i najčešćih pitanja klijentima koji su često zvali.</span><span class="sxs-lookup"><span data-stu-id="233ed-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="233ed-147">Odaberite **Spremi** da biste spremili segment.</span><span class="sxs-lookup"><span data-stu-id="233ed-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="233ed-148">Segment će se spremiti i obraditi ako su potvrđeni svi zahtjevi.</span><span class="sxs-lookup"><span data-stu-id="233ed-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="233ed-149">U protivnom će se spremiti kao skica.</span><span class="sxs-lookup"><span data-stu-id="233ed-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="233ed-150">Odaberite **Natrag na segmente** za povratak na stranicu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="233ed-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="233ed-151">Upravljanje postojećim segmentima</span><span class="sxs-lookup"><span data-stu-id="233ed-151">Manage existing segments</span></span>

<span data-ttu-id="233ed-152">Na stranici **Segmenti** možete pregledati sve spremljene segmente i upravljati njima.</span><span class="sxs-lookup"><span data-stu-id="233ed-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="233ed-153">Svaki segment predstavljen je retkom koji sadrži dodatne informacije o segmentu.</span><span class="sxs-lookup"><span data-stu-id="233ed-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="233ed-154">Segmente možete sortirati u stupcu odabirom zaglavlja stupca.</span><span class="sxs-lookup"><span data-stu-id="233ed-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="233ed-155">Za filtriranje segmenata koristite okvir **Traži** u gornjem desnom kutu.</span><span class="sxs-lookup"><span data-stu-id="233ed-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="233ed-156">![Mogućnosti za upravljanje postojećim segmentom](media/segments-selected-segment.png "Mogućnosti za upravljanje postojećim segmentom")</span><span class="sxs-lookup"><span data-stu-id="233ed-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="233ed-157">Sljedeća je radnja dostupna kada odaberete segment:</span><span class="sxs-lookup"><span data-stu-id="233ed-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="233ed-158">**Prikaz** pojedinosti o segmentu, uključujući trend broja članova, pretpregled članova segmenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="233ed-159">**Uredi** segment da promijeni svoja svojstva.</span><span class="sxs-lookup"><span data-stu-id="233ed-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="233ed-160">**Stvorite duplikat** segmenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="233ed-161">Možete odmah urediti njegova svojstva ili jednostavno spremiti duplikat.</span><span class="sxs-lookup"><span data-stu-id="233ed-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="233ed-162">**Osvježi** segment tako da uključuje najnovije podatke.</span><span class="sxs-lookup"><span data-stu-id="233ed-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="233ed-163">**Aktiviraj** ili **Deaktiviraj** segment.</span><span class="sxs-lookup"><span data-stu-id="233ed-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="233ed-164">Segmenti imaju dva moguća stanja – aktivno ili neaktivno.</span><span class="sxs-lookup"><span data-stu-id="233ed-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="233ed-165">Ta su stanja praktična tijekom uređivanja segmenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="233ed-166">Za neaktivne segmente definicija segmenta postoji, ali još ne sadrži korisnike.</span><span class="sxs-lookup"><span data-stu-id="233ed-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="233ed-167">Kada aktivirate segment, njegovo se stanje mijenja iz „neaktivan” u „aktivan” i on počinje tražiti klijente koji pristaju definiciji segmenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="233ed-168">Ako je konfigurirano [planirano osvježavanje](system.md#schedule-tab), neaktivni segmenti imaju **Status** naveden kao **Preskočen**, što ukazuje da osvježenje nije ni pokušano.</span><span class="sxs-lookup"><span data-stu-id="233ed-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="233ed-169">Kad se aktivira neaktivni segment, osvježit će se i uključiti u planirana osvježavanja.</span><span class="sxs-lookup"><span data-stu-id="233ed-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="233ed-170">Umjesto toga, možete koristiti funkcionalnost **Zakaži kasnije** u padajućem izborniku **Aktiviraj/deaktiviraj** kako biste odredili budući datum i vrijeme aktivacije i deaktivacije određenog segmenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="233ed-171">**Preimenuj** segment.</span><span class="sxs-lookup"><span data-stu-id="233ed-171">**Rename** the segment.</span></span>
- <span data-ttu-id="233ed-172">**Preuzmi** popis članova kao .CSV datoteku.</span><span class="sxs-lookup"><span data-stu-id="233ed-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="233ed-173">Mogućnost **Dodaj u** šalje popis korisničkih ID-a u segmentu na obradu u drugu aplikaciju.</span><span class="sxs-lookup"><span data-stu-id="233ed-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="233ed-174">**Izbriši** segment.</span><span class="sxs-lookup"><span data-stu-id="233ed-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="233ed-175">Osvježavanje segmenata</span><span class="sxs-lookup"><span data-stu-id="233ed-175">Refresh segments</span></span>

<span data-ttu-id="233ed-176">Možete osvježiti sve segmente odjednom odabirom mogućenosti **Osvježi sve** na stranici **Segmenti** ili možete osvježiti jedan ili više segmenata kada ih odaberete i zatim među opcijama odaberete **Osvježi**.</span><span class="sxs-lookup"><span data-stu-id="233ed-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="233ed-177">Možete i konfigurirati ponavljajuće osvježavanje na **Admin** > **Sustav** > **Raspored**.</span><span class="sxs-lookup"><span data-stu-id="233ed-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="233ed-178">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="233ed-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="233ed-179">Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="233ed-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="233ed-180">Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla.</span><span class="sxs-lookup"><span data-stu-id="233ed-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="233ed-181">Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="233ed-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="233ed-182">Preuzimanje i izvoz segmenata</span><span class="sxs-lookup"><span data-stu-id="233ed-182">Download and export segments</span></span>

<span data-ttu-id="233ed-183">Možete preuzeti segmente u CSV datoteku ili ih izvesti u sustav Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="233ed-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="233ed-184">Preuzimanje segmenata u CSV datoteku</span><span class="sxs-lookup"><span data-stu-id="233ed-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="233ed-185">U uvidima u ciljnu skupinu idite na stranicu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="233ed-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="233ed-186">Odaberite trotočku na pločici određenog segmenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="233ed-187">Odaberite **Preuzmi kao CSV** s padajućeg popisa akcija.</span><span class="sxs-lookup"><span data-stu-id="233ed-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="233ed-188">Izvoz segmenata u sustav Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="233ed-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="233ed-189">Prije izvoza segmenata u sustav Dynamics 365 Sales administrator treba [stvoriti odredište za izvoz](export-destinations.md) za Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="233ed-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="233ed-190">U uvidima u ciljnu skupinu idite na stranicu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="233ed-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="233ed-191">Odaberite trotočku na pločici određenog segmenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="233ed-192">Odaberite **Dodaj u** s padajućeg popisa radnji i odaberite odredište za izvoz na koje želite poslati podatke.</span><span class="sxs-lookup"><span data-stu-id="233ed-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="233ed-193">Način skice za segmente</span><span class="sxs-lookup"><span data-stu-id="233ed-193">Draft mode for segments</span></span>

<span data-ttu-id="233ed-194">Ako nisu ispunjeni svi zahtjevi za obradu segmenta, segment možete spremiti kao skicu i pristupiti mu sa stranice **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="233ed-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="233ed-195">Spremit će se kao neaktivni segment i neće ga biti moguće aktivirati dok nije valjan.</span><span class="sxs-lookup"><span data-stu-id="233ed-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="233ed-196">Dodavanje dodatnih uvjeta grupi</span><span class="sxs-lookup"><span data-stu-id="233ed-196">Add more conditions to a group</span></span>

<span data-ttu-id="233ed-197">Da biste grupi dodali više uvjeta, možete upotrijebiti dva logička operatora:</span><span class="sxs-lookup"><span data-stu-id="233ed-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="233ed-198">Operator **I**: oba uvjeta moraju biti ispunjena kao dio postupka segmentacije.</span><span class="sxs-lookup"><span data-stu-id="233ed-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="233ed-199">Ova je mogućnost najkorisnija kada definirate uvjete u različitim entitetima.</span><span class="sxs-lookup"><span data-stu-id="233ed-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="233ed-200">Operator **ILI**: jedan od uvjeta mora biti ispunjen kao dio postupka segmentacije.</span><span class="sxs-lookup"><span data-stu-id="233ed-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="233ed-201">Ova je mogućnost najkorisnija kada definirate više uvjeta za isti entitet.</span><span class="sxs-lookup"><span data-stu-id="233ed-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="233ed-202">![Operator ILI ako je potrebno ispuniti bilo koji uvjet](media/segmentation-either-condition.png "Operator ILI ako je potrebno ispuniti bilo koji uvjet")</span><span class="sxs-lookup"><span data-stu-id="233ed-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="233ed-203">Trenutačno je moguće ugnijezditi operator **ILI** pod operatorom **I**, ali ne i obratno.</span><span class="sxs-lookup"><span data-stu-id="233ed-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="233ed-204">Kombiniranje više grupa</span><span class="sxs-lookup"><span data-stu-id="233ed-204">Combine multiple groups</span></span>

<span data-ttu-id="233ed-205">Svaka grupa proizvodi određeni skup klijenata.</span><span class="sxs-lookup"><span data-stu-id="233ed-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="233ed-206">Te grupe možete kombinirati da biste uključili klijente koji su potrebni za vaš poslovni slučaj.</span><span class="sxs-lookup"><span data-stu-id="233ed-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="233ed-207">U uvidima u ciljnu skupinu idite na stranicu **Segmenti** i odaberite segment.</span><span class="sxs-lookup"><span data-stu-id="233ed-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="233ed-208">Odaberite **Dodaj grupu**.</span><span class="sxs-lookup"><span data-stu-id="233ed-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="233ed-209">![Grupa za dodavanje grupe klijenata](media/customer-group-add-group.png "Grupa za dodavanje grupe klijenata")</span><span class="sxs-lookup"><span data-stu-id="233ed-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="233ed-210">Odaberite jedan od sljedećih operatora skupa: **Unija**, **Sjecište** ili **Osim**.</span><span class="sxs-lookup"><span data-stu-id="233ed-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="233ed-211">![Unija za dodavanje grupe klijenata](media/customer-group-union.png "Unija za dodavanje grupe klijenata")</span><span class="sxs-lookup"><span data-stu-id="233ed-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="233ed-212">Odaberite skup operatora za definiranje nove grupe.</span><span class="sxs-lookup"><span data-stu-id="233ed-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="233ed-213">Spremite različite grupe da bi se odredilo koji će se podaci zadržati:</span><span class="sxs-lookup"><span data-stu-id="233ed-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="233ed-214">**Unija** objedinjuje dvije grupe.</span><span class="sxs-lookup"><span data-stu-id="233ed-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="233ed-215">**Unakrsno** preklapa dvije grupe.</span><span class="sxs-lookup"><span data-stu-id="233ed-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="233ed-216">Samo podaci koji su *zajednički* u obje grupe zadržavaju se u objedinjenoj grupi.</span><span class="sxs-lookup"><span data-stu-id="233ed-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="233ed-217">**Izuzmi** kombinira dvije grupe.</span><span class="sxs-lookup"><span data-stu-id="233ed-217">**Except** combines the two groups.</span></span> <span data-ttu-id="233ed-218">Zadržavaju se samo podaci u grupi A koji *nisu zajednički* s podacima grupe B.</span><span class="sxs-lookup"><span data-stu-id="233ed-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="233ed-219">Prikaz povijesti obrade i članova segmenta</span><span class="sxs-lookup"><span data-stu-id="233ed-219">View processing history and segment members</span></span>

<span data-ttu-id="233ed-220">Konsolidirane podatke o segmentu možete vidjeti prikazom njegovih pojedinosti.</span><span class="sxs-lookup"><span data-stu-id="233ed-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="233ed-221">Na stranici **Segmenti** odaberite segment koji želite pregledati.</span><span class="sxs-lookup"><span data-stu-id="233ed-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="233ed-222">Gornji dio stranice sadrži grafikon trenda koji prikazuje promjene u broju članova.</span><span class="sxs-lookup"><span data-stu-id="233ed-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="233ed-223">Zadržite pokazivač iznad podataka da biste vidjeli broj članova na određeni datum.</span><span class="sxs-lookup"><span data-stu-id="233ed-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="233ed-224">Možete ažurirati vremenski okvir vizualizacije.</span><span class="sxs-lookup"><span data-stu-id="233ed-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="233ed-225">![Vremenski raspon segmenta](media/segment-time-range.png "Vremenski raspon segmenta")</span><span class="sxs-lookup"><span data-stu-id="233ed-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="233ed-226">U donjem dijelu nalazi se popis članova segmenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="233ed-227">Polja koja se pojavljuju na tom popisu temelje se na atributima entiteta segmenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="233ed-228">Popis je pregled odgovarajućih članova segmenta i pokazuje prvih 100 zapisa vašeg segmenta tako da ga po potrebi možete brzo procijeniti i pregledati njegove definicije.</span><span class="sxs-lookup"><span data-stu-id="233ed-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="233ed-229">Da biste prikazali sve odgovarajuće zapise, morate [izvesti segment](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="233ed-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="233ed-230">Brzi segmenti</span><span class="sxs-lookup"><span data-stu-id="233ed-230">Quick segments</span></span>

<span data-ttu-id="233ed-231">Pored alata za stvaranje segmenata, postoji još jedan put za stvaranje segmenata.</span><span class="sxs-lookup"><span data-stu-id="233ed-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="233ed-232">Brzi segmenti omogućavaju vam brzu izradu jednostavnih segmenata s jednim operatorom uz trenutačne uvide.</span><span class="sxs-lookup"><span data-stu-id="233ed-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="233ed-233">Na stranici **Segmenti** odaberite **Novo** > **Brzo stvorite od**.</span><span class="sxs-lookup"><span data-stu-id="233ed-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="233ed-234">Odaberite opciju **Profili** za stvaranje segmenta koji se temelji na jedinstvenom entitetu klijenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="233ed-235">Odaberite opciju **Mjere** da biste stvorili segment oko svake vrste mjera atributa klijenta koje ste prethodno stvorili na stranici **Mjere**.</span><span class="sxs-lookup"><span data-stu-id="233ed-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="233ed-236">Odaberite mogućnost **Inteligencija** za izgradnju segmenta oko jednog od izlaznih entiteta koje ste generirali pomoću mogućnosti **Predviđanja** ili **Prilagođeni modeli**.</span><span class="sxs-lookup"><span data-stu-id="233ed-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="233ed-237">U dijaloškom okviru **Novi brzi segment** odaberite atribut iz padajućeg izbornika **Polje**.</span><span class="sxs-lookup"><span data-stu-id="233ed-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="233ed-238">Sustav će pružiti neke dodatne uvide koji će vam pomoći stvoriti bolje segmente svojih klijenata.</span><span class="sxs-lookup"><span data-stu-id="233ed-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="233ed-239">Za kategorijska polja prikazat ćemo 10 brojeva najboljih kupaca.</span><span class="sxs-lookup"><span data-stu-id="233ed-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="233ed-240">Odaberite **Vrijednost** te **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="233ed-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="233ed-241">Za numerički atribut sustav će pokazati koja vrijednost atributa spada pod svaki postotak klijenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="233ed-242">Odaberite **Operator** i **Vrijednost**, a zatim odaberite **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="233ed-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="233ed-243">Sustav će vam pružiti **Procijenjenu veličinu segmenta**.</span><span class="sxs-lookup"><span data-stu-id="233ed-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="233ed-244">Možete odabrati želite li generirati definirani segment ili ga prvo pregledati kako biste dobili drugu veličinu segmenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="233ed-245">![Naziv i procjena brzog segmenta](media/quick-segment-name.png "Naziv i procjena brzog segmenta")</span><span class="sxs-lookup"><span data-stu-id="233ed-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="233ed-246">Unesite **Naziv** segmenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="233ed-247">Po želji možete unijeti i **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="233ed-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="233ed-248">Odaberite **Spremi** kako biste stvorili segment.</span><span class="sxs-lookup"><span data-stu-id="233ed-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="233ed-249">Nakon dovršetka obrade segmenta možete ga pregledati kao i bilo koji drugi segment koji ste stvorili.</span><span class="sxs-lookup"><span data-stu-id="233ed-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="233ed-250">Za sljedeće scenarije savjetujemo upotrebu alata za stvaranje segmenata umjesto preporučenih mogućnosti segmentacije:</span><span class="sxs-lookup"><span data-stu-id="233ed-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="233ed-251">Stvaranje segmenata s filtrima na kategorijskim poljima gdje se operator razlikuje od operatora **Je**</span><span class="sxs-lookup"><span data-stu-id="233ed-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="233ed-252">Stvaranje segmenata s filtrima na numeričkim poljima gdje se operator razlikuje od operatora **Između**, **Više od** i **Manje od**</span><span class="sxs-lookup"><span data-stu-id="233ed-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="233ed-253">Stvaranje segmenata s filtrima na poljima vrste datuma</span><span class="sxs-lookup"><span data-stu-id="233ed-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="233ed-254">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="233ed-254">Next steps</span></span>

<span data-ttu-id="233ed-255">[Izvezite segment](export-destinations.md) i istražite [Korisničku karticu](customer-card-add-in.md) i [Poveznike](export-power-bi.md) da biste dobili uvide na razini klijenta.</span><span class="sxs-lookup"><span data-stu-id="233ed-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]