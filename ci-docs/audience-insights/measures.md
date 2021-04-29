---
title: Stvaranje i upravljanje mjerama
description: Definirajte mjere za analizu i odražavanje uspješnosti svojeg poslovanja.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a94a32a04f2a8beb661c27271fe96f23d998722
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887931"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="9744f-103">Definiranje i upravljanje mjerama</span><span class="sxs-lookup"><span data-stu-id="9744f-103">Define and manage measures</span></span>

<span data-ttu-id="9744f-104">Mjere vam pomažu da bolje razumijete ponašanja klijenata i poslovne performanse.</span><span class="sxs-lookup"><span data-stu-id="9744f-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="9744f-105">Gledaju na relevantne vrijednosti iz [objedinjenih profila](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="9744f-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="9744f-106">Na primjer, tvrtka želi vidjeti *ukupnu potrošnju po klijentu* kako bi razumjela povijest kupnje pojedinog klijenta ili mjeri *ukupnu prodaju tvrtke* kako bi razumjela ukupnu razinu prihoda u cijelom poslovanju.</span><span class="sxs-lookup"><span data-stu-id="9744f-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="9744f-107">Mjere se stvaraju pomoću alata za izradu mjera, platforme za upite podataka s različitim operatorima i jednostavnim mogućnostima mapiranja.</span><span class="sxs-lookup"><span data-stu-id="9744f-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="9744f-108">Omogućuje vam filtriranje podataka, grupiranje rezultata, otkrivanje [putanja odnosa entiteta](relationships.md) i pretpregled izlazne vrijednosti.</span><span class="sxs-lookup"><span data-stu-id="9744f-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="9744f-109">Koristite alat za izradu mjera za planiranje poslovnih aktivnosti ispitivanjem podataka o klijentima i izvozom uvida.</span><span class="sxs-lookup"><span data-stu-id="9744f-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="9744f-110">Na primjer, stvaranje mjere *ukupna potrošnja po klijentu* i *ukupan povrat po klijentu* pomaže identificirati grupu klijenata s visokom potrošnjom, ali i visokim povratom.</span><span class="sxs-lookup"><span data-stu-id="9744f-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="9744f-111">Možete [stvoriti segment](segments.md) za pokretanje sljedećih najboljih radnji.</span><span class="sxs-lookup"><span data-stu-id="9744f-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="9744f-112">Izrada vlastitih mjera od nule</span><span class="sxs-lookup"><span data-stu-id="9744f-112">Build your own measure from scratch</span></span>

<span data-ttu-id="9744f-113">Ovaj vas odjeljak vodi kroz stvaranje nove mjere od početka.</span><span class="sxs-lookup"><span data-stu-id="9744f-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="9744f-114">Možete izraditi mjeru s atributima podataka iz podatkovnih entiteta koji imaju uspostavljen odnos za povezivanje s entitetom Klijent.</span><span class="sxs-lookup"><span data-stu-id="9744f-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="9744f-115">U uvidima u ciljnu skupinu idite na **Mjere**.</span><span class="sxs-lookup"><span data-stu-id="9744f-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="9744f-116">Odaberite **Novo** i odaberite **Izradi vlastiti**.</span><span class="sxs-lookup"><span data-stu-id="9744f-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="9744f-117">Odaberite **Uredi naziv** i navedite **Naziv** za mjeru.</span><span class="sxs-lookup"><span data-stu-id="9744f-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="9744f-118">Ako vaša nova konfiguracija mjere ima samo dva polja, za primjer, CustomerID i jedan izračun, izlazna će se vrijednost dodati kao novi stupac entitetu koji je generirao sustav pod nazivom Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="9744f-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="9744f-119">Vrijednost mjere moći ćete vidjeti u objedinjenom profilu klijenta.</span><span class="sxs-lookup"><span data-stu-id="9744f-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="9744f-120">Ostale će mjere generirati vlastite entitete.</span><span class="sxs-lookup"><span data-stu-id="9744f-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="9744f-121">U području konfiguracije odaberite funkciju skupljanja u padajućem izborniku **Odabir funkcije**.</span><span class="sxs-lookup"><span data-stu-id="9744f-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="9744f-122">Funkcije skupljanja uključuju:</span><span class="sxs-lookup"><span data-stu-id="9744f-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="9744f-123">**Zbroj**</span><span class="sxs-lookup"><span data-stu-id="9744f-123">**Sum**</span></span>
   - <span data-ttu-id="9744f-124">**Prosječno**</span><span class="sxs-lookup"><span data-stu-id="9744f-124">**Average**</span></span>
   - <span data-ttu-id="9744f-125">**Brojanje**</span><span class="sxs-lookup"><span data-stu-id="9744f-125">**Count**</span></span>
   - <span data-ttu-id="9744f-126">**Jedinstveni broj**</span><span class="sxs-lookup"><span data-stu-id="9744f-126">**Count Unique**</span></span>
   - <span data-ttu-id="9744f-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="9744f-127">**Max**</span></span>
   - <span data-ttu-id="9744f-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="9744f-128">**Min**</span></span>
   - <span data-ttu-id="9744f-129">**Prvi**: uzima prvu vrijednost zapisa podataka</span><span class="sxs-lookup"><span data-stu-id="9744f-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="9744f-130">**Posljednji**: uzima posljednju vrijednost koja je dodana u zapis podataka</span><span class="sxs-lookup"><span data-stu-id="9744f-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatori za izračun mjera.":::

1. <span data-ttu-id="9744f-132">Odaberite **Dodaj atribut** za odabir podataka koji su vam potrebni za stvaranje ove mjere.</span><span class="sxs-lookup"><span data-stu-id="9744f-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="9744f-133">Odaberite karticu **Atributi**.</span><span class="sxs-lookup"><span data-stu-id="9744f-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="9744f-134">Entitet podataka: odaberite entitet koji uključuje atribut koji želite mjeriti.</span><span class="sxs-lookup"><span data-stu-id="9744f-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="9744f-135">Atribut podataka: Odaberite atribut koji želite koristiti u funkciji skupljanja za izračunavanje mjere.</span><span class="sxs-lookup"><span data-stu-id="9744f-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="9744f-136">Odjednom možete odabrati samo jedan atribut.</span><span class="sxs-lookup"><span data-stu-id="9744f-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="9744f-137">Možete odabrati i atribut podataka iz postojeće mjere odabirom kartice **Mjere**. Ili možete tražiti naziv entiteta ili mjere.</span><span class="sxs-lookup"><span data-stu-id="9744f-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="9744f-138">Odaberite **Dodaj** za dodavanje odabranog atributa mjeri.</span><span class="sxs-lookup"><span data-stu-id="9744f-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Odaberite atribut koji ćete koristiti u izračunima.":::

1. <span data-ttu-id="9744f-140">Da biste izradili složenije mjere, možete dodati više atributa ili koristiti matematičke operatore u svojoj funkciji mjere.</span><span class="sxs-lookup"><span data-stu-id="9744f-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Stvorite složenu mjeru s matematičkim operatorima.":::

1. <span data-ttu-id="9744f-142">Da biste dodali filtre, odaberite **Filtar** u području konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="9744f-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="9744f-143">U odjeljku **Dodaj atribut** okna **Filtri** odaberite atribut koji želite koristiti za stvaranje filtara.</span><span class="sxs-lookup"><span data-stu-id="9744f-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="9744f-144">Postavite operatore filtra da definiraju filtar za svaki odabrani atribut.</span><span class="sxs-lookup"><span data-stu-id="9744f-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="9744f-145">Odaberite **Primijeni** za dodavanje filtara mjeri.</span><span class="sxs-lookup"><span data-stu-id="9744f-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="9744f-146">Da biste dodali dimenzije, odaberite **Dimenzija** u području konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="9744f-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="9744f-147">Dimenzije će se prikazati kao stupci u entitetu izlazne vrijednosti mjere.</span><span class="sxs-lookup"><span data-stu-id="9744f-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="9744f-148">Odaberite **Uredi dimenzije** za dodavanje atributa podataka po kojima želite grupirati vrijednosti mjere.</span><span class="sxs-lookup"><span data-stu-id="9744f-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="9744f-149">Na primjer, grad ili spol.</span><span class="sxs-lookup"><span data-stu-id="9744f-149">For example, city or gender.</span></span> <span data-ttu-id="9744f-150">Prema zadanim postavkama dimenzija *CustomerID* odabrana je za stvaranje *mjera na razini klijenta*.</span><span class="sxs-lookup"><span data-stu-id="9744f-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="9744f-151">Možete ukloniti zadanu dimenziju ako želite stvoriti *mjere na poslovnoj razini*.</span><span class="sxs-lookup"><span data-stu-id="9744f-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="9744f-152">Odaberite **Gotovo** za dodavanje dimenzija mjeri.</span><span class="sxs-lookup"><span data-stu-id="9744f-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="9744f-153">Ako u vašim podacima postoje vrijednosti koje trebate zamijeniti cijelim brojem, na primjer, zamijeniti *null* s *0*, odaberite **Pravila**.</span><span class="sxs-lookup"><span data-stu-id="9744f-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="9744f-154">Konfigurirajte pravilo i obavezno odaberite samo cijele brojeve kao zamjene.</span><span class="sxs-lookup"><span data-stu-id="9744f-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="9744f-155">Ako postoji više putanja između entiteta podataka koji ste mapirali i entiteta *Klijent*, morate odabrati jednu od identificiranih [putanja odnosa entiteta](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="9744f-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="9744f-156">Rezultati mjerenja mogu se razlikovati ovisno o odabranoj putanji.</span><span class="sxs-lookup"><span data-stu-id="9744f-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="9744f-157">Odaberite **Preference podataka** i odaberite putanju entiteta koju treba koristiti za identificiranje vaše mjere.</span><span class="sxs-lookup"><span data-stu-id="9744f-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="9744f-158">Ako postoji samo jedna putanja do entiteta *Klijent*, ova se kontrola neće prikazati.</span><span class="sxs-lookup"><span data-stu-id="9744f-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="9744f-159">Odaberite **Gotovo** da biste primijenili svoj odabir.</span><span class="sxs-lookup"><span data-stu-id="9744f-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Odaberite putanju entiteta za mjeru.":::

1. <span data-ttu-id="9744f-161">Da biste dodali više izračuna za mjeru, odaberite **Novi izračun**.</span><span class="sxs-lookup"><span data-stu-id="9744f-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="9744f-162">Za nove izračune možete koristiti samo entitete na istoj putanji entiteta.</span><span class="sxs-lookup"><span data-stu-id="9744f-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="9744f-163">Više će se izračuna prikazati kao novi stupci u entitetu izlazne vrijednosti mjere.</span><span class="sxs-lookup"><span data-stu-id="9744f-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="9744f-164">Odaberite **...** na izračunu da biste proveli **Dupliciraj**, **Preimenuj** ili **Ukloni** izračun iz mjere.</span><span class="sxs-lookup"><span data-stu-id="9744f-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="9744f-165">U području **Pretpregled** vidjet ćete shemu podataka entiteta izlazne vrijednosti mjere, uključujući filtre i dimenzije.</span><span class="sxs-lookup"><span data-stu-id="9744f-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="9744f-166">Pretpregled dinamički reagira na promjene u konfiguraciji.</span><span class="sxs-lookup"><span data-stu-id="9744f-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="9744f-167">Odaberite **Pokreni** za izračunavanje rezultata za konfiguriranu mjeru.</span><span class="sxs-lookup"><span data-stu-id="9744f-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="9744f-168">Odaberite **Spremi i zatvori** ako želite zadržati trenutnu konfiguraciju i kasnije pokrenuti mjeru.</span><span class="sxs-lookup"><span data-stu-id="9744f-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="9744f-169">Idite na **Mjere** da biste na popisu vidjeli novostvorenu mjeru.</span><span class="sxs-lookup"><span data-stu-id="9744f-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="9744f-170">Korištenje predloška za izradu mjera</span><span class="sxs-lookup"><span data-stu-id="9744f-170">Use a template to build a measure</span></span>

<span data-ttu-id="9744f-171">Za njihovo stvaranje možete koristiti unaprijed definirane predloške najčešće korištenih mjera.</span><span class="sxs-lookup"><span data-stu-id="9744f-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="9744f-172">Detaljni opisi predložaka i vođeno iskustvo pomažu vam u učinkovitom stvaranju mjera.</span><span class="sxs-lookup"><span data-stu-id="9744f-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="9744f-173">Predlošci se nadovezuju na mapirane podatke iz entiteta *Objedinjena aktivnost*.</span><span class="sxs-lookup"><span data-stu-id="9744f-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="9744f-174">Stoga provjerite jeste li konfigurirali [aktivnosti klijenata](activities.md) prije nego što stvorite mjeru iz predloška.</span><span class="sxs-lookup"><span data-stu-id="9744f-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="9744f-175">Dostupni predlošci mjera:</span><span class="sxs-lookup"><span data-stu-id="9744f-175">Available measure templates:</span></span> 
- <span data-ttu-id="9744f-176">Prosječna vrijednost transakcije (ATV)</span><span class="sxs-lookup"><span data-stu-id="9744f-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="9744f-177">Ukupna vrijednost transakcije</span><span class="sxs-lookup"><span data-stu-id="9744f-177">Total transaction value</span></span>
- <span data-ttu-id="9744f-178">Prosječni dnevni prihod</span><span class="sxs-lookup"><span data-stu-id="9744f-178">Average daily revenue</span></span>
- <span data-ttu-id="9744f-179">Prosječni godišnji prihod</span><span class="sxs-lookup"><span data-stu-id="9744f-179">Average yearly revenue</span></span>
- <span data-ttu-id="9744f-180">Broj transakcija</span><span class="sxs-lookup"><span data-stu-id="9744f-180">Transaction count</span></span>
- <span data-ttu-id="9744f-181">Zarađeni bodovi vjernosti</span><span class="sxs-lookup"><span data-stu-id="9744f-181">Loyalty points earned</span></span>
- <span data-ttu-id="9744f-182">Iskorišteni bodovi vjernosti</span><span class="sxs-lookup"><span data-stu-id="9744f-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="9744f-183">Bilanca stanja bodova vjernosti</span><span class="sxs-lookup"><span data-stu-id="9744f-183">Loyalty points balance</span></span>
- <span data-ttu-id="9744f-184">Životni vijek aktivnog klijenta</span><span class="sxs-lookup"><span data-stu-id="9744f-184">Active customer lifespan</span></span>
- <span data-ttu-id="9744f-185">Trajanje članstva u programu vjernosti</span><span class="sxs-lookup"><span data-stu-id="9744f-185">Loyalty membership duration</span></span>
- <span data-ttu-id="9744f-186">Vrijeme od zadnje kupnje</span><span class="sxs-lookup"><span data-stu-id="9744f-186">Time since last purchase</span></span>

<span data-ttu-id="9744f-187">Sljedeći postupak opisuje korake za izradu nove mjere pomoću predloška.</span><span class="sxs-lookup"><span data-stu-id="9744f-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="9744f-188">U uvidima u ciljnu skupinu idite na **Mjere**.</span><span class="sxs-lookup"><span data-stu-id="9744f-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="9744f-189">Odaberite **Novo**, a zatim odaberite **Odaberi predložak**.</span><span class="sxs-lookup"><span data-stu-id="9744f-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Snimka zaslona padajućeg izbornika prilikom stvaranja nove mjere s naglaskom na predložak.":::

1. <span data-ttu-id="9744f-191">Pronađite predložak koji odgovara vašim potrebama i odaberite **Odaberi predložak**.</span><span class="sxs-lookup"><span data-stu-id="9744f-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="9744f-192">Pregledajte potrebne podatke i odaberite **Započni** ako imate sve podatke na mjestu.</span><span class="sxs-lookup"><span data-stu-id="9744f-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="9744f-193">U oknu **Uredi naziv** postavite naziv mjere i izlazni entitet.</span><span class="sxs-lookup"><span data-stu-id="9744f-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="9744f-194">Odaberite **Gotovo**.</span><span class="sxs-lookup"><span data-stu-id="9744f-194">Select **Done**.</span></span>

1. <span data-ttu-id="9744f-195">U odjeljku **Postavi vremensko razdoblje** definirajte vremenski okvir podataka koji će se koristiti.</span><span class="sxs-lookup"><span data-stu-id="9744f-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="9744f-196">Odaberite želite li da nova mjera pokriva cijeli skup podataka odabirom **Cijelo vrijeme**.</span><span class="sxs-lookup"><span data-stu-id="9744f-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="9744f-197">Ili želite li da se mjera usredotoči na **Određeno vremensko razdoblje**.</span><span class="sxs-lookup"><span data-stu-id="9744f-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Snimka zaslona koja prikazuje odjeljak vremenskog razdoblja prilikom konfiguriranja mjere iz predloška.":::

1. <span data-ttu-id="9744f-199">U sljedećem odjeljku odaberite **Dodaj podatke** za odabir aktivnosti i mapiranje odgovarajućih podataka iz vašeg entiteta *Objedinjena aktivnost*.</span><span class="sxs-lookup"><span data-stu-id="9744f-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="9744f-200">Korak 1 od 2: Pod **Vrsta aktivnosti** odaberite vrstu entiteta koju želite koristiti.</span><span class="sxs-lookup"><span data-stu-id="9744f-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="9744f-201">Za **Aktivnosti** odaberite entitete koje želite mapirati.</span><span class="sxs-lookup"><span data-stu-id="9744f-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="9744f-202">Korak 2 od 2: Odaberite atribut iz entiteta *Objedinjena aktivnost* za komponentu koju zahtijeva formula.</span><span class="sxs-lookup"><span data-stu-id="9744f-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="9744f-203">Na primjer, za Prosječna vrijednost transakcije to je atribut koji predstavlja vrijednost Transakcije.</span><span class="sxs-lookup"><span data-stu-id="9744f-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="9744f-204">Za **Vremenska oznaka aktivnosti** odaberite atribut iz entiteta Objedinjena aktivnost koji predstavlja datum i vrijeme aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="9744f-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="9744f-205">Nakon što mapiranje podataka bude uspješno, možete vidjeti status kao **Dovršeno** te naziv mapiranih aktivnosti i atributa.</span><span class="sxs-lookup"><span data-stu-id="9744f-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Snimka zaslona dovršene konfiguracije predloška mjere.":::

1. <span data-ttu-id="9744f-207">Sada možete odabrati **Pokreni** za izračunavanje rezultata mjere.</span><span class="sxs-lookup"><span data-stu-id="9744f-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="9744f-208">Da biste je kasnije pročistili, odaberite **Spremi nacrt**.</span><span class="sxs-lookup"><span data-stu-id="9744f-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="9744f-209">Upravljanje mjerama</span><span class="sxs-lookup"><span data-stu-id="9744f-209">Manage your measures</span></span>

<span data-ttu-id="9744f-210">Popis mjera možete pronaći na stranici **Mjere**.</span><span class="sxs-lookup"><span data-stu-id="9744f-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="9744f-211">Pronaći ćete informacije o vrsti mjere, autoru, datumu stvaranja, statusu i stanju.</span><span class="sxs-lookup"><span data-stu-id="9744f-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="9744f-212">Kada odaberete mjeru s popisa, možete pretpregledati izlaznu vrijednost i preuzeti .CSV datoteku.</span><span class="sxs-lookup"><span data-stu-id="9744f-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="9744f-213">Da biste istovremeno osvježili sve svoje mjere, odaberite **Osvježi sve** bez odabiranja određene mjere.</span><span class="sxs-lookup"><span data-stu-id="9744f-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9744f-214">![Radnje za upravljanje jedinstvenim mjerama](media/measure-actions.png "Radnje za upravljanje jedinstvenim mjerama")</span><span class="sxs-lookup"><span data-stu-id="9744f-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="9744f-215">Odaberite mjeru s popisa za sljedeće mogućnosti:</span><span class="sxs-lookup"><span data-stu-id="9744f-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="9744f-216">Odaberite naziv mjere da biste vidjeli njezine pojedinosti.</span><span class="sxs-lookup"><span data-stu-id="9744f-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="9744f-217">Odaberite **Uredi** konfiguraciju mjere.</span><span class="sxs-lookup"><span data-stu-id="9744f-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="9744f-218">**Osvježi** mjeru na temelju najnovijih podataka.</span><span class="sxs-lookup"><span data-stu-id="9744f-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="9744f-219">Odaberite **Preimenuj** mjeru.</span><span class="sxs-lookup"><span data-stu-id="9744f-219">**Rename** the measure.</span></span>
- <span data-ttu-id="9744f-220">Odaberite **Izbriši** mjeru.</span><span class="sxs-lookup"><span data-stu-id="9744f-220">**Delete** the measure.</span></span>
- <span data-ttu-id="9744f-221">**Aktiviraj** ili **Deaktiviraj**.</span><span class="sxs-lookup"><span data-stu-id="9744f-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="9744f-222">Neaktivne mjere neće se osvježavati tijekom [zakazanog osvježavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9744f-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="9744f-223">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="9744f-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="9744f-224">Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="9744f-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="9744f-225">Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla.</span><span class="sxs-lookup"><span data-stu-id="9744f-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="9744f-226">Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="9744f-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="9744f-227">Sljedeći korak</span><span class="sxs-lookup"><span data-stu-id="9744f-227">Next step</span></span>

<span data-ttu-id="9744f-228">Možete koristit postojeće mjere da biste stvorili [segment klijenta](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9744f-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]