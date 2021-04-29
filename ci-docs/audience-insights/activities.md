---
title: Aktivnosti klijenta
description: Definirajte aktivnosti kupaca i pregledajte ih na vremenskoj traci klijenta.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866398"
---
# <a name="customer-activities"></a><span data-ttu-id="227f9-103">Aktivnosti klijenta</span><span class="sxs-lookup"><span data-stu-id="227f9-103">Customer activities</span></span>

<span data-ttu-id="227f9-104">Kombinirajte aktivnosti klijenta iz [različitih izvora podataka](data-sources.md) u Dynamics 365 Customer Insights da biste stvorili vremensku traku koja kronološki navodi aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="227f9-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="227f9-105">Uključite vremensku traku u aplikacije sustava Dynamics 365 uz rješenje [Dodatak za karticu kupca](customer-card-add-in.md) ili u nadzornu ploču Power BI.</span><span class="sxs-lookup"><span data-stu-id="227f9-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="227f9-106">Definiranje aktivnosti</span><span class="sxs-lookup"><span data-stu-id="227f9-106">Define an activity</span></span>

<span data-ttu-id="227f9-107">Vaši izvori podataka mogu uključivati entitete s podacima o transakcijama i aktivnostima iz više izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="227f9-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="227f9-108">Identificirajte te entitete i odaberite aktivnosti koje želite prikazati na vremenskoj traci klijenta.</span><span class="sxs-lookup"><span data-stu-id="227f9-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="227f9-109">Odaberite entitet koji uključuje vašu ciljanu aktivnost ili aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="227f9-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="227f9-110">Entitet mora imati najmanje jedan atribut vrste **Datum** da bi se uključio u vremensku traku klijenta i ne možete dodavati entitete bez polja **Datum**.</span><span class="sxs-lookup"><span data-stu-id="227f9-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="227f9-111">Kontrola **Dodaj aktivnost** onemogućena je ako nije pronađen takav entitet.</span><span class="sxs-lookup"><span data-stu-id="227f9-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="227f9-112">U uvidima u ciljnu skupinu idite na **Podaci** > **Aktivnosti**.</span><span class="sxs-lookup"><span data-stu-id="227f9-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="227f9-113">Odaberite **Dodaj aktivnost** za pokretanje vođenog iskustva za postupak postavljanja aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="227f9-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="227f9-114">U koraku **Podaci o aktivnostima** postavite vrijednosti za sljedeća polja:</span><span class="sxs-lookup"><span data-stu-id="227f9-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="227f9-115">**Naziv aktivnosti**: Odaberite naziv za svoju aktivnost.</span><span class="sxs-lookup"><span data-stu-id="227f9-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="227f9-116">**Entitet**: odaberite entitet koji uključuje podatke o transakcijama ili aktivnostima.</span><span class="sxs-lookup"><span data-stu-id="227f9-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="227f9-117">**Primarni ključ**: odaberite polje koje jedinstveno identificira zapis.</span><span class="sxs-lookup"><span data-stu-id="227f9-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="227f9-118">Ne smije sadržavati duplicirane vrijednosti, prazne vrijednosti ili vrijednosti koje nedostaju.</span><span class="sxs-lookup"><span data-stu-id="227f9-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Postavite podatke o aktivnosti s nazivom, entitetom i primarnim ključem.":::

1. <span data-ttu-id="227f9-120">Odaberite **Sljedeće** da biste prešli na sljedeći korak.</span><span class="sxs-lookup"><span data-stu-id="227f9-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="227f9-121">U koraku **Odnos** konfigurirajte pojedinosti za povezivanje podataka o aktivnosti s odgovarajućim klijentom.</span><span class="sxs-lookup"><span data-stu-id="227f9-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="227f9-122">Ovaj korak vizualizira vezu među entitetima.</span><span class="sxs-lookup"><span data-stu-id="227f9-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="227f9-123">**Prvi**: Strano polje u vašem entitetu aktivnosti koje će se koristiti za uspostavljanje odnosa s drugim entitetom.</span><span class="sxs-lookup"><span data-stu-id="227f9-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="227f9-124">**Drugi**: Odgovarajući izvorni entitet klijenta s kojim će vaš entitet aktivnosti biti u odnosu.</span><span class="sxs-lookup"><span data-stu-id="227f9-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="227f9-125">Možete se odnositi samo na izvorne entitete klijenata koji se koriste u procesu objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="227f9-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="227f9-126">**Treći**: Ako odnos između ovog entiteta aktivnosti i odabranog izvornog entiteta klijenta već postoji, naziv odnosa bit će u načinu samo za čitanje.</span><span class="sxs-lookup"><span data-stu-id="227f9-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="227f9-127">Ako takav odnos ne postoji, stvorit će se novi odnos s nazivom koji navedete u ovom okviru.</span><span class="sxs-lookup"><span data-stu-id="227f9-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definirajte odnos entiteta.":::

1. <span data-ttu-id="227f9-129">Odaberite **Sljedeće** da biste prešli na sljedeći korak.</span><span class="sxs-lookup"><span data-stu-id="227f9-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="227f9-130">U koraku **Objedinjavanje aktivnosti** odaberite događaj aktivnosti i vrijeme početka svoje aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="227f9-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="227f9-131">**Obvezna polja**</span><span class="sxs-lookup"><span data-stu-id="227f9-131">**Required fields**</span></span>
      1. <span data-ttu-id="227f9-132">**Aktivnost događaja**: Polje koje je događaj za ovu aktivnost</span><span class="sxs-lookup"><span data-stu-id="227f9-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="227f9-133">**Vremenska oznaka**: Polje koje predstavlja vrijeme početka vaše aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="227f9-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="227f9-134">**Neobvezna polja**</span><span class="sxs-lookup"><span data-stu-id="227f9-134">**Optional fields**</span></span>
      1. <span data-ttu-id="227f9-135">**Dodatna pojedinost**: Polje s relevantnim informacijama za ovu aktivnost.</span><span class="sxs-lookup"><span data-stu-id="227f9-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="227f9-136">**Ikona**: Ikona koja najbolje predstavlja ovu vrstu aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="227f9-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="227f9-137">**Web-adresa**: Polje koje sadrži URL s informacijama o ovoj aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="227f9-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="227f9-138">Na primjer, transakcijski sustav iz kojega je potekla ova aktivnost.</span><span class="sxs-lookup"><span data-stu-id="227f9-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="227f9-139">Ovaj URL može biti bilo koje polje iz izvora podataka ili se može konstruirati kao novo polje s pomoću transformacije Power Query.</span><span class="sxs-lookup"><span data-stu-id="227f9-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="227f9-140">Podaci o URL-u bit će pohranjeni u entitetu *Objedinjena aktivnost* koji se može konzumirati prema dolje pomoću [API-ja](apis.md).</span><span class="sxs-lookup"><span data-stu-id="227f9-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Navedite podatke o aktivnostima klijenta u entitetu Objedinjene aktivnosti.":::

1. <span data-ttu-id="227f9-142">Odaberite **Sljedeće** da biste se pomaknuli na sljedeći korak.</span><span class="sxs-lookup"><span data-stu-id="227f9-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="227f9-143">Možete odabrati **Završi i pregledaj** da biste sada spremili aktivnost s vrstom aktivnosti postavljenom na **Ostalo**.</span><span class="sxs-lookup"><span data-stu-id="227f9-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="227f9-144">U koraku **Vrsta aktivnosti** odaberite vrstu aktivnosti i neobavezno odaberite želite li semantički mapirati neke od vrsta aktivnosti za korištenje u ostalim područjima Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="227f9-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="227f9-145">Trenutno se vrste aktivnosti *Pretplata* & *SalesOrderLine* mogu se semantički mapirati nakon dogovora o mapiranju polja.</span><span class="sxs-lookup"><span data-stu-id="227f9-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="227f9-146">Ako vrsta aktivnosti nije relevantna za novu aktivnost, možete odabrati *Ostalo* ili *Stvori novo* za prilagođenu vrstu aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="227f9-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="227f9-147">Odaberite **Sljedeće** da biste se pomaknuli na sljedeći korak.</span><span class="sxs-lookup"><span data-stu-id="227f9-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="227f9-148">U koraku **Pregled** provjerite svoje odabire.</span><span class="sxs-lookup"><span data-stu-id="227f9-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="227f9-149">Vratite se na bilo koji od prethodnih koraka i ažurirajte informacije ako je potrebno.</span><span class="sxs-lookup"><span data-stu-id="227f9-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Pregledajte navedena polja za aktivnost.":::
   
1. <span data-ttu-id="227f9-151">Odaberite **Spremi aktivnost** da biste primijenili promjene i odaberite **Gotovo** da biste se vratili na **Podaci** > **Aktivnosti**.</span><span class="sxs-lookup"><span data-stu-id="227f9-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="227f9-152">Ovdje možete vidjeti koje su aktivnosti postavljene za prikaz na vremenskoj traci.</span><span class="sxs-lookup"><span data-stu-id="227f9-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="227f9-153">Na stranici **Aktivnosti** odaberite **Pokreni** za obradu aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="227f9-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="227f9-154">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="227f9-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="227f9-155">Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="227f9-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="227f9-156">Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla.</span><span class="sxs-lookup"><span data-stu-id="227f9-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="227f9-157">Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="227f9-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="227f9-158">Upravljanje postojećim aktivnostima</span><span class="sxs-lookup"><span data-stu-id="227f9-158">Manage existing activities</span></span>

<span data-ttu-id="227f9-159">Na **Podaci** > **Aktivnosti** možete pregledati sve spremljene aktivnosti i upravljati njima.</span><span class="sxs-lookup"><span data-stu-id="227f9-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="227f9-160">Svaka je aktivnost predstavljena retkom koji također uključuje pojedinosti o izvoru, entitetu i vrsti aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="227f9-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="227f9-161">Sljedeće su radnje dostupne kada odaberete aktivnost.</span><span class="sxs-lookup"><span data-stu-id="227f9-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="227f9-162">**Uredi**: Otvara postavljanje aktivnosti u koraku pregleda.</span><span class="sxs-lookup"><span data-stu-id="227f9-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="227f9-163">U ovom koraku možete promijeniti bilo koju ili sve trenutne konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="227f9-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="227f9-164">Nakon promjene konfiguracije odaberite **Spremi aktivnost**, a zatim odaberite **Pokreni** za obradu promjena.</span><span class="sxs-lookup"><span data-stu-id="227f9-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="227f9-165">**Preimenuj**: Otvara dijaloški okvir u koji ćete unijeti drugi naziv za odabranu aktivnost.</span><span class="sxs-lookup"><span data-stu-id="227f9-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="227f9-166">Odaberite **Spremi** za primjenu izmjena.</span><span class="sxs-lookup"><span data-stu-id="227f9-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="227f9-167">**Izbriši**: Otvara dijaloški okvir za potvrdu brisanja odabrane aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="227f9-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="227f9-168">Možete i izbrisati više aktivnosti odjednom odabirom aktivnosti, a zatim odabirom ikone za brisanje.</span><span class="sxs-lookup"><span data-stu-id="227f9-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="227f9-169">Odaberite **Izbriši** da biste potvrdili brisanje.</span><span class="sxs-lookup"><span data-stu-id="227f9-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
