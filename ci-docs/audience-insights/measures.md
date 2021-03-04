---
title: Stvaranje i upravljanje mjerama
description: Definirajte mjere za analizu i odražavanje uspješnosti svojeg poslovanja.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269919"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="de2be-103">Definiranje i upravljanje mjerama</span><span class="sxs-lookup"><span data-stu-id="de2be-103">Define and manage measures</span></span>

<span data-ttu-id="de2be-104">Mjere vam pomažu da bolje razumijete ponašanje klijenata i poslovne performanse dohvaćanjem relevantnih vrijednosti iz [objedinjenih profila](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="de2be-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="de2be-105">Na primjer, tvrtka želi vidjeti *ukupnu potrošnju po klijentu* da bi razumjela povijest kupnje pojedinog klijenta.</span><span class="sxs-lookup"><span data-stu-id="de2be-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="de2be-106">Ili izmjeriti *ukupnu prodaju tvrtke* da bi razumjela ukupnu razinu prihoda u cijelom poslovanju.</span><span class="sxs-lookup"><span data-stu-id="de2be-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="de2be-107">Mjere se stvaraju pomoću alata za izradu mjera, platforme za upite podataka s različitim operatorima i jednostavnim mogućnostima mapiranja.</span><span class="sxs-lookup"><span data-stu-id="de2be-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="de2be-108">Omogućuje vam filtriranje podataka, grupiranje rezultata, otkrivanje [putanja odnosa entiteta](relationships.md) i pretpregled izlazne vrijednosti.</span><span class="sxs-lookup"><span data-stu-id="de2be-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="de2be-109">Koristite alat za izradu mjera za planiranje poslovnih aktivnosti ispitivanjem podataka o klijentima i izvozom uvida.</span><span class="sxs-lookup"><span data-stu-id="de2be-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="de2be-110">Na primjer, stvaranje mjere *ukupna potrošnja po klijentu* i *ukupan povrat po klijentu* pomaže identificirati grupu klijenata s visokom potrošnjom, ali i visokim povratom.</span><span class="sxs-lookup"><span data-stu-id="de2be-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="de2be-111">Možete [stvoriti segment](segments.md) za pokretanje sljedećih najboljih radnji.</span><span class="sxs-lookup"><span data-stu-id="de2be-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="de2be-112">Izrada mjere</span><span class="sxs-lookup"><span data-stu-id="de2be-112">Create a measure</span></span>

<span data-ttu-id="de2be-113">Ovaj vas odjeljak vodi kroz stvaranje nove mjere od početka.</span><span class="sxs-lookup"><span data-stu-id="de2be-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="de2be-114">Možete izraditi mjeru s atributima podataka iz podatkovnih entiteta koji imaju uspostavljen odnos za povezivanje s entitetom Klijent.</span><span class="sxs-lookup"><span data-stu-id="de2be-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="de2be-115">U uvidima u ciljnu skupinu idite na **Mjere**.</span><span class="sxs-lookup"><span data-stu-id="de2be-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="de2be-116">Odaberite **Novo**.</span><span class="sxs-lookup"><span data-stu-id="de2be-116">Select **New**.</span></span>

1. <span data-ttu-id="de2be-117">Odaberite **Uredi naziv** i navedite **Naziv** za mjeru.</span><span class="sxs-lookup"><span data-stu-id="de2be-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="de2be-118">Ako vaša nova konfiguracija mjere ima samo dva polja, za primjer, CustomerID i jedan izračun, izlazna će se vrijednost dodati kao novi stupac entitetu koji je generirao sustav pod nazivom Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="de2be-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="de2be-119">Vrijednost mjere moći ćete vidjeti u objedinjenom profilu klijenta.</span><span class="sxs-lookup"><span data-stu-id="de2be-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="de2be-120">Ostale će mjere generirati vlastite entitete.</span><span class="sxs-lookup"><span data-stu-id="de2be-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="de2be-121">U području konfiguracije odaberite funkciju skupljanja u padajućem izborniku **Odabir funkcije**.</span><span class="sxs-lookup"><span data-stu-id="de2be-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="de2be-122">Funkcije skupljanja uključuju:</span><span class="sxs-lookup"><span data-stu-id="de2be-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="de2be-123">**Zbroj**</span><span class="sxs-lookup"><span data-stu-id="de2be-123">**Sum**</span></span>
   - <span data-ttu-id="de2be-124">**Prosječno**</span><span class="sxs-lookup"><span data-stu-id="de2be-124">**Average**</span></span>
   - <span data-ttu-id="de2be-125">**Brojanje**</span><span class="sxs-lookup"><span data-stu-id="de2be-125">**Count**</span></span>
   - <span data-ttu-id="de2be-126">**Jedinstveni broj**</span><span class="sxs-lookup"><span data-stu-id="de2be-126">**Count Unique**</span></span>
   - <span data-ttu-id="de2be-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="de2be-127">**Max**</span></span>
   - <span data-ttu-id="de2be-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="de2be-128">**Min**</span></span>
   - <span data-ttu-id="de2be-129">**Prvi**: uzima prvu vrijednost zapisa podataka</span><span class="sxs-lookup"><span data-stu-id="de2be-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="de2be-130">**Posljednji**: uzima posljednju vrijednost koja je dodana u zapis podataka</span><span class="sxs-lookup"><span data-stu-id="de2be-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatori za izračun mjera.":::

1. <span data-ttu-id="de2be-132">Odaberite **Dodaj atribut** za odabir podataka koji su vam potrebni za stvaranje ove mjere.</span><span class="sxs-lookup"><span data-stu-id="de2be-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="de2be-133">Odaberite karticu **Atributi**.</span><span class="sxs-lookup"><span data-stu-id="de2be-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="de2be-134">Entitet podataka: odaberite entitet koji uključuje atribut koji želite mjeriti.</span><span class="sxs-lookup"><span data-stu-id="de2be-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="de2be-135">Atribut podataka: Odaberite atribut koji želite koristiti u funkciji skupljanja za izračunavanje mjere.</span><span class="sxs-lookup"><span data-stu-id="de2be-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="de2be-136">Odjednom možete odabrati samo jedan atribut.</span><span class="sxs-lookup"><span data-stu-id="de2be-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="de2be-137">Možete odabrati i atribut podataka iz postojeće mjere odabirom kartice **Mjere**. Ili možete tražiti naziv entiteta ili mjere.</span><span class="sxs-lookup"><span data-stu-id="de2be-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="de2be-138">Odaberite **Dodaj** za dodavanje odabranog atributa mjeri.</span><span class="sxs-lookup"><span data-stu-id="de2be-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Odaberite atribut koji ćete koristiti u izračunima.":::

1. <span data-ttu-id="de2be-140">Da biste izradili složenije mjere, možete dodati više atributa ili koristiti matematičke operatore u svojoj funkciji mjere.</span><span class="sxs-lookup"><span data-stu-id="de2be-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Stvorite složenu mjeru s matematičkim operatorima.":::

1. <span data-ttu-id="de2be-142">Da biste dodali filtre, odaberite **Filtar** u području konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="de2be-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="de2be-143">U odjeljku **Dodaj atribut** okna **Filtri** odaberite atribut koji želite koristiti za stvaranje filtara.</span><span class="sxs-lookup"><span data-stu-id="de2be-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="de2be-144">Postavite operatore filtra da definiraju filtar za svaki odabrani atribut.</span><span class="sxs-lookup"><span data-stu-id="de2be-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="de2be-145">Odaberite **Primijeni** za dodavanje filtara mjeri.</span><span class="sxs-lookup"><span data-stu-id="de2be-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="de2be-146">Da biste dodali dimenzije, odaberite **Dimenzija** u području konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="de2be-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="de2be-147">Dimenzije će se prikazati kao stupci u entitetu izlazne vrijednosti mjere.</span><span class="sxs-lookup"><span data-stu-id="de2be-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="de2be-148">Odaberite **Uredi dimenzije** za dodavanje atributa podataka po kojima želite grupirati vrijednosti mjere.</span><span class="sxs-lookup"><span data-stu-id="de2be-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="de2be-149">Na primjer, grad ili spol.</span><span class="sxs-lookup"><span data-stu-id="de2be-149">For example, city or gender.</span></span> <span data-ttu-id="de2be-150">Prema zadanim postavkama dimenzija *CustomerID* odabrana je za stvaranje *mjera na razini klijenta*.</span><span class="sxs-lookup"><span data-stu-id="de2be-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="de2be-151">Možete ukloniti zadanu dimenziju ako želite stvoriti *mjere na poslovnoj razini*.</span><span class="sxs-lookup"><span data-stu-id="de2be-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="de2be-152">Odaberite **Gotovo** za dodavanje dimenzija mjeri.</span><span class="sxs-lookup"><span data-stu-id="de2be-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="de2be-153">Ako postoji više putanja između entiteta podataka koji ste mapirali i entiteta Klijent, morate odabrati jednu od identificiranih [putanja odnosa entiteta](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="de2be-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="de2be-154">Rezultati mjerenja mogu se razlikovati ovisno o odabranoj putanji.</span><span class="sxs-lookup"><span data-stu-id="de2be-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="de2be-155">Odaberite **Preference podataka** i odaberite putanju entiteta koju treba koristiti za identificiranje vaše mjere.</span><span class="sxs-lookup"><span data-stu-id="de2be-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="de2be-156">Odaberite **Gotovo** da biste primijenili svoj odabir.</span><span class="sxs-lookup"><span data-stu-id="de2be-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Odaberite putanju entiteta za mjeru.":::

1. <span data-ttu-id="de2be-158">Da biste dodali više izračuna za mjeru, odaberite **Novi izračun**.</span><span class="sxs-lookup"><span data-stu-id="de2be-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="de2be-159">Za nove izračune možete koristiti samo entitete na istoj putanji entiteta.</span><span class="sxs-lookup"><span data-stu-id="de2be-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="de2be-160">Više će se izračuna prikazati kao novi stupci u entitetu izlazne vrijednosti mjere.</span><span class="sxs-lookup"><span data-stu-id="de2be-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="de2be-161">Odaberite **...** na izračunu da biste proveli **Dupliciraj**, **Preimenuj** ili **Ukloni** izračun iz mjere.</span><span class="sxs-lookup"><span data-stu-id="de2be-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="de2be-162">U području **Pretpregled** vidjet ćete shemu podataka entiteta izlazne vrijednosti mjere, uključujući filtre i dimenzije.</span><span class="sxs-lookup"><span data-stu-id="de2be-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="de2be-163">Pretpregled dinamički reagira na promjene u konfiguraciji.</span><span class="sxs-lookup"><span data-stu-id="de2be-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="de2be-164">Odaberite **Pokreni** za izračunavanje rezultata za konfiguriranu mjeru.</span><span class="sxs-lookup"><span data-stu-id="de2be-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="de2be-165">Odaberite **Spremi i zatvori** ako želite zadržati trenutnu konfiguraciju i kasnije pokrenuti mjeru.</span><span class="sxs-lookup"><span data-stu-id="de2be-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="de2be-166">Idite na **Mjere** da biste na popisu vidjeli novostvorenu mjeru.</span><span class="sxs-lookup"><span data-stu-id="de2be-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="de2be-167">Upravljanje mjerama</span><span class="sxs-lookup"><span data-stu-id="de2be-167">Manage your measures</span></span>

<span data-ttu-id="de2be-168">Nakon [stvaranja mjere](#create-a-measure) vidjet ćete popis mjera na stranici **Mjere**.</span><span class="sxs-lookup"><span data-stu-id="de2be-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="de2be-169">Pronaći ćete informacije o vrsti mjere, autoru, datumu stvaranja, statusu i stanju.</span><span class="sxs-lookup"><span data-stu-id="de2be-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="de2be-170">Kada odaberete mjeru s popisa, možete pretpregledati izlaznu vrijednost i preuzeti .CSV datoteku.</span><span class="sxs-lookup"><span data-stu-id="de2be-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="de2be-171">Da biste istovremeno osvježili sve svoje mjere, odaberite **Osvježi sve** bez odabiranja određene mjere.</span><span class="sxs-lookup"><span data-stu-id="de2be-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="de2be-172">![Radnje za upravljanje jedinstvenim mjerama](media/measure-actions.png "Radnje za upravljanje jedinstvenim mjerama")</span><span class="sxs-lookup"><span data-stu-id="de2be-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="de2be-173">Odaberite mjeru s popisa za sljedeće mogućnosti:</span><span class="sxs-lookup"><span data-stu-id="de2be-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="de2be-174">Odaberite naziv mjere da biste vidjeli njezine pojedinosti.</span><span class="sxs-lookup"><span data-stu-id="de2be-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="de2be-175">Odaberite **Uredi** konfiguraciju mjere.</span><span class="sxs-lookup"><span data-stu-id="de2be-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="de2be-176">**Osvježi** mjeru na temelju najnovijih podataka.</span><span class="sxs-lookup"><span data-stu-id="de2be-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="de2be-177">Odaberite **Preimenuj** mjeru.</span><span class="sxs-lookup"><span data-stu-id="de2be-177">**Rename** the measure.</span></span>
- <span data-ttu-id="de2be-178">Odaberite **Izbriši** mjeru.</span><span class="sxs-lookup"><span data-stu-id="de2be-178">**Delete** the measure.</span></span>
- <span data-ttu-id="de2be-179">**Aktiviraj** ili **Deaktiviraj**.</span><span class="sxs-lookup"><span data-stu-id="de2be-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="de2be-180">Neaktivne mjere neće se osvježavati tijekom [zakazanog osvježavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="de2be-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="de2be-181">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="de2be-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="de2be-182">Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="de2be-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="de2be-183">Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla.</span><span class="sxs-lookup"><span data-stu-id="de2be-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="de2be-184">Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="de2be-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="de2be-185">Sljedeći korak</span><span class="sxs-lookup"><span data-stu-id="de2be-185">Next step</span></span>

<span data-ttu-id="de2be-186">Možete koristit postojeće mjere da biste stvorili [segment klijenta](segments.md).</span><span class="sxs-lookup"><span data-stu-id="de2be-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]