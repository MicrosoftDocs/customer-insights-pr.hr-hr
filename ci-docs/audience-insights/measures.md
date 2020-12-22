---
title: Stvaranje i uređivanje mjera
description: Definirajte mjere povezane s klijentima kako biste analizirali i odrazili performanse određenih poslovnih područja.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405337"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="7249a-103">Definiranje i upravljanje mjerama</span><span class="sxs-lookup"><span data-stu-id="7249a-103">Define and manage measures</span></span>

<span data-ttu-id="7249a-104">**Mjere** predstavljaju ključne pokazatelje uspješnosti (KPI-jeve) koji odražavaju performanse i stanje specifičnog poslovnog područja.</span><span class="sxs-lookup"><span data-stu-id="7249a-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="7249a-105">Uvidi u ciljnu skupinu pružaju intuitivno iskustvo za izgradnju različitih vrsta mjera pomoću sastavljača upita koji ne zahtijeva ručno kodiranje ili provjeru valjanosti mjera.</span><span class="sxs-lookup"><span data-stu-id="7249a-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="7249a-106">Poslovne mjere možete pratiti na stranici **Početna**, pregledati mjere za određene klijente na stavci **Kartica klijenta** i koristiti mjere za definiranje segmenata klijenata na stranici **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="7249a-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="7249a-107">Izrada mjere</span><span class="sxs-lookup"><span data-stu-id="7249a-107">Create a measure</span></span>

<span data-ttu-id="7249a-108">Ovaj vas dio vodi kroz izradu mjere od početka.</span><span class="sxs-lookup"><span data-stu-id="7249a-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="7249a-109">Možete izraditi mjere s podacima iz više izvora podataka koji su povezani putem entiteta Klijent.</span><span class="sxs-lookup"><span data-stu-id="7249a-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="7249a-110">Primjenjuju se neka [ograničenja usluge](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="7249a-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="7249a-111">U uvidima u ciljnu skupinu idite na **Mjere**.</span><span class="sxs-lookup"><span data-stu-id="7249a-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="7249a-112">Odaberite **Nova mjera**.</span><span class="sxs-lookup"><span data-stu-id="7249a-112">Select **New measure**.</span></span>

3. <span data-ttu-id="7249a-113">Odaberite mjeru **Vrsta**:</span><span class="sxs-lookup"><span data-stu-id="7249a-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="7249a-114">**Atribut klijenta**: jedno polje po klijentu koje odražava ocjenu, vrijednost ili stanje za klijenta.</span><span class="sxs-lookup"><span data-stu-id="7249a-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="7249a-115">Atributi klijenta izrađeni su kao atributi u novom entitetu koji generira sustav naziva **Mjera klijenta**.</span><span class="sxs-lookup"><span data-stu-id="7249a-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="7249a-116">**Mjera klijenta**: uvidi o klijentu o ponašanju klijenta s raščlambom odabranih dimenzija.</span><span class="sxs-lookup"><span data-stu-id="7249a-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="7249a-117">Novi se entitet generira za svaku mjeru, potencijalno s više zapisa po klijentu.</span><span class="sxs-lookup"><span data-stu-id="7249a-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="7249a-118">**Poslovna mjera**: prati poslovanje vaše tvrtke i stanje poslovnog odnosa.</span><span class="sxs-lookup"><span data-stu-id="7249a-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="7249a-119">Poslovne mjere mogu imati dva različita rezultata: numerički rezultat koji se prikazuje na stranici **Početna** ili novi entitet koji možete pronaći na stranici **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="7249a-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="7249a-120">Navedite **Naziv** i opcionalni **Zaslonski naziv** i zatim odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="7249a-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="7249a-121">U odjeljku **Entiteti** odaberite prvi entitet na padajućem izborniku.</span><span class="sxs-lookup"><span data-stu-id="7249a-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="7249a-122">Ovdje biste trebali odlučiti jesu li dodatni entiteti potrebni kao dio definicije mjerenja.</span><span class="sxs-lookup"><span data-stu-id="7249a-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7249a-123">![Definicija mjerila](media/measure-definition.png "Definicija mjerila")</span><span class="sxs-lookup"><span data-stu-id="7249a-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="7249a-124">Za dodavanje više entiteta odaberite **Dodaj entitet** i odaberite entitete koje želite koristiti za mjerenje.</span><span class="sxs-lookup"><span data-stu-id="7249a-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7249a-125">Možete odabrati samo entitete koji su u odnosu s vašim početnim entitetom.</span><span class="sxs-lookup"><span data-stu-id="7249a-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="7249a-126">Za više informacija o definiranju odnosa pogledajte dio [Odnosi](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="7249a-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="7249a-127">Opcionalno možete konfigurirati varijable.</span><span class="sxs-lookup"><span data-stu-id="7249a-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="7249a-128">U odjeljku **Varijable** odaberite **Nova varijabla**.</span><span class="sxs-lookup"><span data-stu-id="7249a-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="7249a-129">Varijable su izračuni koji se izvode za svaki vaš odabrani zapis.</span><span class="sxs-lookup"><span data-stu-id="7249a-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="7249a-130">Na primjer, zbrajanje prodajnog mjesta (POS) i internetskih prodaja za svaki zapis vašeg klijenta.</span><span class="sxs-lookup"><span data-stu-id="7249a-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="7249a-131">Navedite **Naziv** za varijablu.</span><span class="sxs-lookup"><span data-stu-id="7249a-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="7249a-132">U dijelu **Izraz** odaberite polje s kojim čete započeti izračun.</span><span class="sxs-lookup"><span data-stu-id="7249a-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="7249a-133">Upišite izraz u polje **Izraz** i pritom odaberite više polja koja će se uključiti u vaš izračun.</span><span class="sxs-lookup"><span data-stu-id="7249a-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7249a-134">Trenutno su podržani samo aritmetički izrazi.</span><span class="sxs-lookup"><span data-stu-id="7249a-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="7249a-135">Osim toga, izračun varijabli nije podržan za entitete s različitih [putova entiteta](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="7249a-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="7249a-136">Odaberite **Gotovo**.</span><span class="sxs-lookup"><span data-stu-id="7249a-136">Select **Done**.</span></span>

11. <span data-ttu-id="7249a-137">U odjeljku **Definicija mjere** definirat ćete kako se vaši odabrani entiteti i izračunate varijable agregiraju u novi entitet ili atribut mjere.</span><span class="sxs-lookup"><span data-stu-id="7249a-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="7249a-138">Odaberite **Nova dimenzija**.</span><span class="sxs-lookup"><span data-stu-id="7249a-138">Select **New dimension**.</span></span> <span data-ttu-id="7249a-139">Dimenzije možete shvatiti kao funkciju *grupiraj kao*.</span><span class="sxs-lookup"><span data-stu-id="7249a-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="7249a-140">Rezultat podataka vašeg entiteta ili atributa Mjera bit će grupiran prema svim vašim definiranim dimenzijama.</span><span class="sxs-lookup"><span data-stu-id="7249a-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7249a-141">![Odaberite skupni ciklus](media/measures-businessreport-measure-definition2.png "Odaberite skupni ciklus")</span><span class="sxs-lookup"><span data-stu-id="7249a-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="7249a-142">Odaberite ili unesite sljedeće informacija kao dio definicije dimenzije:</span><span class="sxs-lookup"><span data-stu-id="7249a-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="7249a-143">**EntitetEntity**: ako definirate entitet Mjera, on bi trebao uključivati barem jedan atribut.</span><span class="sxs-lookup"><span data-stu-id="7249a-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="7249a-144">Ako definirate atribut Mjera, on će uključivati samo jedan atribut prema zadanim postavkama.</span><span class="sxs-lookup"><span data-stu-id="7249a-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="7249a-145">Pri ovom se odabiru radi o odabiru entiteta koji uključuje taj atribut.</span><span class="sxs-lookup"><span data-stu-id="7249a-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="7249a-146">**Polje**: odaberite specifični atribut koji će se uključiti u vaš entitet ili atribut Mjera.</span><span class="sxs-lookup"><span data-stu-id="7249a-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="7249a-147">**Grupa**: odaberite želite li agregirati podatke na dnevnoj, mjesečnoj ili godišnjoj osnovi.</span><span class="sxs-lookup"><span data-stu-id="7249a-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="7249a-148">To je obavezan odabir samo ako ste odabrali atribut vrste Datum.</span><span class="sxs-lookup"><span data-stu-id="7249a-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="7249a-149">**Kao**: definira naziv vašeg novog polja.</span><span class="sxs-lookup"><span data-stu-id="7249a-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="7249a-150">**Zaslonski naziv**: definira zaslonski naziv vašeg polja.</span><span class="sxs-lookup"><span data-stu-id="7249a-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7249a-151">Vaša poslovna mjera bit će spremljena kao entitet s jednim brojem i prikazat će se na stranici **Početna**, osim ako ne dodate više dimenzija za svoju mjeru.</span><span class="sxs-lookup"><span data-stu-id="7249a-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="7249a-152">Nakon što dodate više dimenzija, mjera se *neće* prikazati na stranici **Početna**.</span><span class="sxs-lookup"><span data-stu-id="7249a-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="7249a-153">Izborno možete dodati funkcije agregacije.</span><span class="sxs-lookup"><span data-stu-id="7249a-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="7249a-154">Svaka agregacija koje izradite može rezultirati novom vrijednosti unutar entiteta ili atributa Mjera.</span><span class="sxs-lookup"><span data-stu-id="7249a-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="7249a-155">Podržane funkcije agregacije su: **Min**, **Maks**, **Prosjek**, **Medijan**, **Zbroj**, **Jedinstveni broj**, **Prvo** (uzima prvi zapis vrijednosti dimenzije) i **Posljednje** (uzima posljednji zapis dodan za vrijednost dimenzije).</span><span class="sxs-lookup"><span data-stu-id="7249a-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="7249a-156">Odaberite **Spremi** kako biste spremili izmjene mjere.</span><span class="sxs-lookup"><span data-stu-id="7249a-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="7249a-157">Upravljanje mjerama</span><span class="sxs-lookup"><span data-stu-id="7249a-157">Manage your measures</span></span>

<span data-ttu-id="7249a-158">Nakon što stvorite barem jednu mjeru, vidjet ćete popis mjera na stranici **Mjere**.</span><span class="sxs-lookup"><span data-stu-id="7249a-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="7249a-159">Tu možete pronaći informacije o vrsti mjere, autoru, datumu i vremenu izrade, datumu i vremenu posljednjeg ažuriranja, statusu (je li mjera aktivna, neaktivna ili nije uspjela) i posljednjem datumu i vremenu osvježavanja.</span><span class="sxs-lookup"><span data-stu-id="7249a-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="7249a-160">Kada s popisa odaberete mjeru, možete vidjeti pretpregled njezina izlaza.</span><span class="sxs-lookup"><span data-stu-id="7249a-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="7249a-161">Da biste istovremeno osvježili sve svoje mjere, odaberite **Osvježi sve** bez odabiranja određene mjere.</span><span class="sxs-lookup"><span data-stu-id="7249a-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7249a-162">![Radnje za upravljanje jedinstvenim mjerama](media/measure-actions.png "Radnje za upravljanje jedinstvenim mjerama")</span><span class="sxs-lookup"><span data-stu-id="7249a-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="7249a-163">Ili odaberite mjeru s popisa i izvršite jednu od sljedećih radnji:</span><span class="sxs-lookup"><span data-stu-id="7249a-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="7249a-164">Odaberite naziv mjere da biste vidjeli njezine pojedinosti.</span><span class="sxs-lookup"><span data-stu-id="7249a-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="7249a-165">Odaberite **Uredi** konfiguraciju mjere.</span><span class="sxs-lookup"><span data-stu-id="7249a-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="7249a-166">Odaberite **Preimenuj** mjeru.</span><span class="sxs-lookup"><span data-stu-id="7249a-166">**Rename** the measure.</span></span>
- <span data-ttu-id="7249a-167">Odaberite **Izbriši** mjeru.</span><span class="sxs-lookup"><span data-stu-id="7249a-167">**Delete** the measure.</span></span>
- <span data-ttu-id="7249a-168">Odaberite trotočku (...) i zatim **Osvježi** da biste započeli postupak osvježavanja mjere.</span><span class="sxs-lookup"><span data-stu-id="7249a-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="7249a-169">Odaberite trotočku (...) i zatim **Preuzmi** da biste dobili .CSV datoteku mjere.</span><span class="sxs-lookup"><span data-stu-id="7249a-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="7249a-170">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="7249a-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="7249a-171">Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="7249a-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="7249a-172">Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla.</span><span class="sxs-lookup"><span data-stu-id="7249a-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="7249a-173">Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="7249a-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="7249a-174">Sljedeći korak</span><span class="sxs-lookup"><span data-stu-id="7249a-174">Next step</span></span>

<span data-ttu-id="7249a-175">Možete upotrebljavati postojeće mjere za izradu prvog segmenta klijenta na stranici **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="7249a-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="7249a-176">Dodatne informacije potražite u dijelu [Segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="7249a-176">For more information, see [Segments](segments.md).</span></span>
