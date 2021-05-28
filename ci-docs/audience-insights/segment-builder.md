---
title: Stvaranje i upravljanje segmentima
description: Izradite segmente klijenata da biste ih grupirali na temelju različitih atributa.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064928"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="82233-103">Stvaranje i upravljanje segmentima</span><span class="sxs-lookup"><span data-stu-id="82233-103">Create and manage segments</span></span>

<span data-ttu-id="82233-104">Definirajte složene filtre oko objedinjenog entiteta klijenta i s njime povezanih entiteta.</span><span class="sxs-lookup"><span data-stu-id="82233-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="82233-105">Nakon obrade, svaki segment stvara skup zapisa o klijentima koji možete izvesti i koristiti za rad.</span><span class="sxs-lookup"><span data-stu-id="82233-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="82233-106">Segmentima se upravlja na stranici **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="82233-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="82233-107">Sljedeći primjer prikazuje način upotrebe segmentacije.</span><span class="sxs-lookup"><span data-stu-id="82233-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="82233-108">Definirali smo segment za klijente koji su naručili najmanje $500 robe u posljednjih 90 dana *i* koji su bili uključeni u poziv službe za korisnike koji je eskalirao.</span><span class="sxs-lookup"><span data-stu-id="82233-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Snimka zaslona korisničkog sučelja sastavljača segmenata s dvije grupe koje određuju segment klijenta.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="82233-110">Izrada novog segmenta</span><span class="sxs-lookup"><span data-stu-id="82233-110">Create a new segment</span></span>

<span data-ttu-id="82233-111">Postoji više načina za stvaranje novog segmenta.</span><span class="sxs-lookup"><span data-stu-id="82233-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="82233-112">U ovom odjeljku je opisano kako stvoriti *prazan segment* od početka.</span><span class="sxs-lookup"><span data-stu-id="82233-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="82233-113">Također možete stvoriti *brzi segment* na temelju postojećih entiteta ili iskoristiti modele strojnog učenja da biste dobili *predložene segmente*.</span><span class="sxs-lookup"><span data-stu-id="82233-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="82233-114">Dodatne informacije: [Pregled segmenata](segments.md).</span><span class="sxs-lookup"><span data-stu-id="82233-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="82233-115">Tijekom izrade segmenta možete spremiti skicu.</span><span class="sxs-lookup"><span data-stu-id="82233-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="82233-116">Spremit će se kao neaktivni segment i ne može se aktivirati, završava valjanom konfiguracijom.</span><span class="sxs-lookup"><span data-stu-id="82233-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="82233-117">Idite na stranicu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="82233-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="82233-118">Odaberite **Novo** > **Prazni segment**.</span><span class="sxs-lookup"><span data-stu-id="82233-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="82233-119">U oknu **Novi segment** odaberite vrstu segmenta:</span><span class="sxs-lookup"><span data-stu-id="82233-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="82233-120">**Dinamički segmenti** [osvježavaju se](segments.md#refresh-segments) prema ponavljajućem rasporedu.</span><span class="sxs-lookup"><span data-stu-id="82233-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="82233-121">**Statički segmenti** pokreću se jednom kad ih stvorite.</span><span class="sxs-lookup"><span data-stu-id="82233-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="82233-122">Navedite **Naziv izlaznog entiteta** za segment.</span><span class="sxs-lookup"><span data-stu-id="82233-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="82233-123">Po želji navedite zaslonski naziv i opis koji pomaže u prepoznavanju segmenta.</span><span class="sxs-lookup"><span data-stu-id="82233-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="82233-124">Odaberite **Dalje** da biste pristupili stranici **Alat za sastavljanje segmenata** na kojoj definirate grupu.</span><span class="sxs-lookup"><span data-stu-id="82233-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="82233-125">Grupa je skup klijenata.</span><span class="sxs-lookup"><span data-stu-id="82233-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="82233-126">Odaberite entitet koji uključuje atribut za koji želite segmentiranje.</span><span class="sxs-lookup"><span data-stu-id="82233-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="82233-127">Odaberite atribut za segmentaciju.</span><span class="sxs-lookup"><span data-stu-id="82233-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="82233-128">Ovaj atribut može imati jednu od četiri vrste vrijednosti: numeričku, niz, datum ili Booleov izraz.</span><span class="sxs-lookup"><span data-stu-id="82233-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="82233-129">Odaberite operatora i vrijednost za odabrani atribut.</span><span class="sxs-lookup"><span data-stu-id="82233-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="82233-130">![Prilagođeni filtar grupe](media/customer-group-numbers.png "Filtar grupe klijenata")</span><span class="sxs-lookup"><span data-stu-id="82233-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="82233-131">Broj</span><span class="sxs-lookup"><span data-stu-id="82233-131">Number</span></span> |<span data-ttu-id="82233-132">Definicija</span><span class="sxs-lookup"><span data-stu-id="82233-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="82233-133">1</span><span class="sxs-lookup"><span data-stu-id="82233-133">1</span></span>     |<span data-ttu-id="82233-134">Entity</span><span class="sxs-lookup"><span data-stu-id="82233-134">Entity</span></span>          |
   |<span data-ttu-id="82233-135">2</span><span class="sxs-lookup"><span data-stu-id="82233-135">2</span></span>     |<span data-ttu-id="82233-136">Atribut</span><span class="sxs-lookup"><span data-stu-id="82233-136">Attribute</span></span>          |
   |<span data-ttu-id="82233-137">3</span><span class="sxs-lookup"><span data-stu-id="82233-137">3</span></span>    |<span data-ttu-id="82233-138">Operater</span><span class="sxs-lookup"><span data-stu-id="82233-138">Operator</span></span>         |
   |<span data-ttu-id="82233-139">4</span><span class="sxs-lookup"><span data-stu-id="82233-139">4</span></span>    |<span data-ttu-id="82233-140">Value</span><span class="sxs-lookup"><span data-stu-id="82233-140">Value</span></span>         |

   1. <span data-ttu-id="82233-141">Da biste grupi dodali više uvjeta, možete upotrijebiti dva logička operatora:</span><span class="sxs-lookup"><span data-stu-id="82233-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="82233-142">Operator **I**: oba uvjeta moraju biti ispunjena kao dio postupka segmentacije.</span><span class="sxs-lookup"><span data-stu-id="82233-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="82233-143">Ova je mogućnost najkorisnija kada definirate uvjete u različitim entitetima.</span><span class="sxs-lookup"><span data-stu-id="82233-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="82233-144">Operator **ILI**: jedan od uvjeta mora biti ispunjen kao dio postupka segmentacije.</span><span class="sxs-lookup"><span data-stu-id="82233-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="82233-145">Ova je mogućnost najkorisnija kada definirate više uvjeta za isti entitet.</span><span class="sxs-lookup"><span data-stu-id="82233-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="82233-146">![Operator ILI ako je potrebno ispuniti bilo koji uvjet](media/segmentation-either-condition.png "Operator ILI ako je potrebno ispuniti bilo koji uvjet")</span><span class="sxs-lookup"><span data-stu-id="82233-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="82233-147">Trenutačno je moguće ugnijezditi operator **ILI** pod operatorom **I**, ali ne i obratno.</span><span class="sxs-lookup"><span data-stu-id="82233-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="82233-148">Svaka grupa odgovara skupu klijenata.</span><span class="sxs-lookup"><span data-stu-id="82233-148">Each group matches set of customers.</span></span> <span data-ttu-id="82233-149">Možete kombinirati grupe da biste uključili klijente potrebne za vaš poslovni slučaj.</span><span class="sxs-lookup"><span data-stu-id="82233-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="82233-150">Odaberite **Dodaj grupu**.</span><span class="sxs-lookup"><span data-stu-id="82233-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="82233-151">![Grupa za dodavanje grupe klijenata](media/customer-group-add-group.png "Grupa za dodavanje grupe klijenata")</span><span class="sxs-lookup"><span data-stu-id="82233-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="82233-152">Odaberite jednog od postavljenih operatora: **Unija**, **Unakrsno** ili **Izuzmi**.</span><span class="sxs-lookup"><span data-stu-id="82233-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="82233-153">![Unija za dodavanje grupe klijenata](media/customer-group-union.png "Unija za dodavanje grupe klijenata")</span><span class="sxs-lookup"><span data-stu-id="82233-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="82233-154">**Unija** objedinjuje dvije grupe.</span><span class="sxs-lookup"><span data-stu-id="82233-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="82233-155">**Unakrsno** preklapa dvije grupe.</span><span class="sxs-lookup"><span data-stu-id="82233-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="82233-156">Samo podaci koji su *zajednički* u obje grupe zadržavaju se u objedinjenoj grupi.</span><span class="sxs-lookup"><span data-stu-id="82233-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="82233-157">**Izuzmi** kombinira dvije grupe.</span><span class="sxs-lookup"><span data-stu-id="82233-157">**Except** combines the two groups.</span></span> <span data-ttu-id="82233-158">Zadržavaju se samo podaci u grupi A koji *nisu zajednički* s podacima grupe B.</span><span class="sxs-lookup"><span data-stu-id="82233-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="82233-159">Ako je entitet povezan s objedinjenim entitetom klijenta putem [odnosa](relationships.md), morate definirati putanju odnosa za stvaranje valjanog segmenta.</span><span class="sxs-lookup"><span data-stu-id="82233-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="82233-160">Dodajte entitete s putanje odnosa sve dok ne možete odabrati entitet **Klijent: CustomerInsights** s padajućeg izbornika.</span><span class="sxs-lookup"><span data-stu-id="82233-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="82233-161">Zatim odaberite **Svi zapisi** za svaki korak.</span><span class="sxs-lookup"><span data-stu-id="82233-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="82233-162">![Putanja odnosa tijekom stvaranja segmenta](media/segments-multiple-relationships.png "Putanja odnosa tijekom stvaranja segmenta")</span><span class="sxs-lookup"><span data-stu-id="82233-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="82233-163">Prema zadanim postavkama, segmenti generiraju izlazni entitet koji sadrži sve atribute profila klijenata koji odgovaraju definiranim filtrima.</span><span class="sxs-lookup"><span data-stu-id="82233-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="82233-164">Ako se segment temelji na drugim entitetima osim na entitetu *Klijent*, izlaznom entitetu možete dodati više atributa iz tih entiteta.</span><span class="sxs-lookup"><span data-stu-id="82233-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="82233-165">Odaberite stavku **Atributi projekta** za odabir atributa koji će se dodati izlaznom entitetu.</span><span class="sxs-lookup"><span data-stu-id="82233-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="82233-166">Primjer: Segment se temelji na entitetu koji sadrži podatke o aktivnostima klijenta koji su povezani s entitetom *Klijent*.</span><span class="sxs-lookup"><span data-stu-id="82233-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="82233-167">Segment traži sve klijente koji su nazvali službu za pomoć u posljednjih 60 dana.</span><span class="sxs-lookup"><span data-stu-id="82233-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="82233-168">Možete odabrati dodavanje trajanja poziva i broja poziva svim odgovarajućim zapisima klijenata u izlaznom entitetu.</span><span class="sxs-lookup"><span data-stu-id="82233-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="82233-169">Ove bi informacije mogle biti korisne za slanje e-pošte s korisnim vezama do članaka za pomoć na mreži i najčešćih pitanja klijentima koji su često zvali.</span><span class="sxs-lookup"><span data-stu-id="82233-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="82233-170">Projicirani atributi funkcioniraju samo za entitete koji imaju odnos jedan-prema-više s entitetom klijenta.</span><span class="sxs-lookup"><span data-stu-id="82233-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="82233-171">Na primjer, jedan klijent može imati više pretplata.</span><span class="sxs-lookup"><span data-stu-id="82233-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="82233-172">Atribute možete projicirati samo iz entiteta koji se koristi u svakoj grupi upita segmenta koji gradite.</span><span class="sxs-lookup"><span data-stu-id="82233-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="82233-173">Projicirani atributi uzimaju se u obzir pri korištenju postavljenih operatora.</span><span class="sxs-lookup"><span data-stu-id="82233-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="82233-174">Odaberite **Spremi** da biste spremili segment.</span><span class="sxs-lookup"><span data-stu-id="82233-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="82233-175">Segment će se spremiti i obraditi ako su potvrđeni svi zahtjevi.</span><span class="sxs-lookup"><span data-stu-id="82233-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="82233-176">U protivnom će se spremiti kao skica.</span><span class="sxs-lookup"><span data-stu-id="82233-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="82233-177">Odaberite **Natrag na segmente** za povratak na stranicu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="82233-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="82233-178">Brzi segmenti</span><span class="sxs-lookup"><span data-stu-id="82233-178">Quick segments</span></span>

<span data-ttu-id="82233-179">Brzi segmenti omogućuju vam brzu izgradnju jednostavnih segmenata s jednim operatorom za brži uvid.</span><span class="sxs-lookup"><span data-stu-id="82233-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="82233-180">Na stranici **Segmenti** odaberite **Novo** > **Stvori iz**.</span><span class="sxs-lookup"><span data-stu-id="82233-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="82233-181">Odaberite mogućnost **Profili** za stvaranje segmenta koji se temelji na entitetu *jedinstvenog klijenta*.</span><span class="sxs-lookup"><span data-stu-id="82233-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="82233-182">Odaberite mogućnost **Mjere** za stvaranje segmenta prema mjerama koje ste prethodno stvorili.</span><span class="sxs-lookup"><span data-stu-id="82233-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="82233-183">Odaberite mogućnost **Inteligencija** za izgradnju segmenta oko jednog od izlaznih entiteta koje ste generirali pomoću mogućnosti **Predviđanja** ili **Prilagođeni modeli**.</span><span class="sxs-lookup"><span data-stu-id="82233-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="82233-184">U dijaloškom okviru **Novi brzi segment** odaberite atribut iz padajućeg izbornika **Polje**.</span><span class="sxs-lookup"><span data-stu-id="82233-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="82233-185">Sustav će pružiti neke dodatne uvide koji će vam pomoći stvoriti bolje segmente svojih klijenata.</span><span class="sxs-lookup"><span data-stu-id="82233-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="82233-186">Za kategorijska polja prikazat ćemo 10 brojeva najboljih kupaca.</span><span class="sxs-lookup"><span data-stu-id="82233-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="82233-187">Odaberite **Vrijednost** te **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="82233-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="82233-188">Za numerički atribut sustav će pokazati koja vrijednost atributa spada pod svaki postotak klijenta.</span><span class="sxs-lookup"><span data-stu-id="82233-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="82233-189">Odaberite **Operator** i **Vrijednost**, a zatim odaberite **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="82233-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="82233-190">Sustav će vam pružiti **Procijenjenu veličinu segmenta**.</span><span class="sxs-lookup"><span data-stu-id="82233-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="82233-191">Možete odabrati želite li generirati definirani segment ili ga prvo pregledati kako biste dobili drugu veličinu segmenta.</span><span class="sxs-lookup"><span data-stu-id="82233-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="82233-192">![Naziv i procjena brzog segmenta](media/quick-segment-name.png "Naziv i procjena brzog segmenta")</span><span class="sxs-lookup"><span data-stu-id="82233-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="82233-193">Unesite **Naziv** segmenta.</span><span class="sxs-lookup"><span data-stu-id="82233-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="82233-194">Po želji možete unijeti i **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="82233-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="82233-195">Odaberite **Spremi** kako biste stvorili segment.</span><span class="sxs-lookup"><span data-stu-id="82233-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="82233-196">Nakon dovršetka obrade segmenta možete ga pregledati kao i bilo koji drugi segment koji ste stvorili.</span><span class="sxs-lookup"><span data-stu-id="82233-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="82233-197">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="82233-197">Next steps</span></span>

<span data-ttu-id="82233-198">[Izvezite segment](export-destinations.md) i istražite [Korisničku karticu](customer-card-add-in.md) i [Poveznike](export-power-bi.md) da biste dobili uvide na razini klijenta.</span><span class="sxs-lookup"><span data-stu-id="82233-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
