---
title: Aktivnosti klijenta
description: Definirajte aktivnosti kupaca i pregledajte ih na vremenskoj traci klijenta.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667220"
---
# <a name="customer-activities"></a><span data-ttu-id="e480f-103">Aktivnosti klijenta</span><span class="sxs-lookup"><span data-stu-id="e480f-103">Customer activities</span></span>

<span data-ttu-id="e480f-104">Kombinirajte aktivnosti klijenata iz [raznih izvora podataka](data-sources.md) u značajci Dynamics 365 Customer Insights kako biste stvorili vremensku crtu klijenta koja navodi aktivnosti kronološkim redoslijedom.</span><span class="sxs-lookup"><span data-stu-id="e480f-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="e480f-105">Vremensku traku možete dodati u aplikacije Customer Engagement u sustavu Dynamics 365 putem [dodatka za korisničku karticu](customer-card-add-in.md) ili na nadzornoj ploči usluge Power BI.</span><span class="sxs-lookup"><span data-stu-id="e480f-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="e480f-106">Definiranje aktivnosti</span><span class="sxs-lookup"><span data-stu-id="e480f-106">Define an activity</span></span>

<span data-ttu-id="e480f-107">Vaši izvori podataka uključuju entitete s podacima o transakcijama i aktivnostima iz više izvora.</span><span class="sxs-lookup"><span data-stu-id="e480f-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="e480f-108">Identificirajte te entitete i odaberite aktivnosti koje želite prikazati na vremenskoj traci klijenta.</span><span class="sxs-lookup"><span data-stu-id="e480f-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="e480f-109">Odaberite entitet koji uključuje vašu ciljanu aktivnost ili aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="e480f-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="e480f-110">U uvidima u ciljnu skupinu idite na **Podaci** > **Aktivnosti**.</span><span class="sxs-lookup"><span data-stu-id="e480f-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="e480f-111">Odaberite **Dodaj aktivnost**.</span><span class="sxs-lookup"><span data-stu-id="e480f-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e480f-112">Entitet mora imati najmanje jedan atribut vrste **Datum** da bi se uključio u vremensku traku klijenta i ne možete dodavati entitete bez polja **Datum**.</span><span class="sxs-lookup"><span data-stu-id="e480f-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="e480f-113">Kontrola **Dodaj aktivnost** onemogućena je ako nije pronađen takav entitet.</span><span class="sxs-lookup"><span data-stu-id="e480f-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="e480f-114">U oknu **Dodavanje aktivnosti** okno postavite vrijednosti za sljedeća polja:</span><span class="sxs-lookup"><span data-stu-id="e480f-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="e480f-115">**Entitet**: odaberite entitet koji uključuje podatke o transakcijama ili aktivnostima.</span><span class="sxs-lookup"><span data-stu-id="e480f-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="e480f-116">**Primarni ključ**: odaberite polje koje jedinstveno identificira zapis.</span><span class="sxs-lookup"><span data-stu-id="e480f-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="e480f-117">Ne smije sadržavati duplicirane vrijednosti, prazne vrijednosti ili vrijednosti koje nedostaju.</span><span class="sxs-lookup"><span data-stu-id="e480f-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="e480f-118">**Vremenska oznaka**: odaberite polje koje predstavlja vrijeme početka vaše aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="e480f-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="e480f-119">**Događaj**: odaberite polje koje je događaj za aktivnost.</span><span class="sxs-lookup"><span data-stu-id="e480f-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="e480f-120">**Web-adresa**: Odaberite polje koje predstavlja URL koji pruža dodatne informacije o ovoj aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="e480f-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="e480f-121">Na primjer, transakcijski sustav iz kojega je potekla ova aktivnost.</span><span class="sxs-lookup"><span data-stu-id="e480f-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="e480f-122">Ovaj URL može biti bilo koje polje iz izvora podataka ili se može konstruirati kao novo polje s pomoću transformacije Power Query.</span><span class="sxs-lookup"><span data-stu-id="e480f-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="e480f-123">Podaci ovog URL-a bit će pohranjeni u entitetu Jedinstvena aktivnost, koji se može koristiti nizvodno pomoću API-ja.</span><span class="sxs-lookup"><span data-stu-id="e480f-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="e480f-124">**Pojedinosti**: prema želji odaberite polje koje se dodaje za dodatne pojedinosti.</span><span class="sxs-lookup"><span data-stu-id="e480f-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="e480f-125">**Ikona**: prema želji odaberite ikonu koja predstavlja navedenu aktivnost.</span><span class="sxs-lookup"><span data-stu-id="e480f-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="e480f-126">**Vrsta aktivnosti**: Definirajte referencu vrste aktivnosti prema modelu Common Data Model koji najbolje opisuje semantičku definiciju aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="e480f-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="e480f-127">U odjeljku **Postavi odnos** konfigurirajte pojedinosti da biste povezali podatke o aktivnosti s odgovarajućim klijentom.</span><span class="sxs-lookup"><span data-stu-id="e480f-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e480f-128">![Definiranje odnosa entiteta](media/activities-entities-define.png "Definiranje odnosa entiteta")</span><span class="sxs-lookup"><span data-stu-id="e480f-128">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

    - <span data-ttu-id="e480f-129">**Polje entiteta aktivnosti**: odaberite polje u svojem entitetu aktivnosti koje će se koristiti za uspostavljanje odnosa s drugim entitetom.</span><span class="sxs-lookup"><span data-stu-id="e480f-129">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="e480f-130">**Entitet klijenta**: odaberite odgovarajući izvorni entitet klijenta s kojim će entitet aktivnosti biti u odnosu.</span><span class="sxs-lookup"><span data-stu-id="e480f-130">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="e480f-131">Možete se povezati samo s onim izvornim entitetima klijenta koji se koriste u postupku objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="e480f-131">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="e480f-132">**Polje entiteta klijenta**: ovo polje pokazuje primarni ključ izvornog entiteta klijenta kao odabranog u postupku mapiranja.</span><span class="sxs-lookup"><span data-stu-id="e480f-132">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="e480f-133">Ovo polje primarnog ključa u izvornom entitetu klijenta koristi se za uspostavljanje odnosa s entitetom aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="e480f-133">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="e480f-134">**Naziv**: ako odnos između ovog entiteta aktivnosti i odabranog izvornog entiteta klijenta već postoji, naziv odnosa bit će u načinu rada samo za čitanje.</span><span class="sxs-lookup"><span data-stu-id="e480f-134">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="e480f-135">Ako takav odnos ne postoji, stvorit će se novi odnos s ovdje navedenim nazivom.</span><span class="sxs-lookup"><span data-stu-id="e480f-135">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>

1. <span data-ttu-id="e480f-136">Odaberite **Spremi** za primjenu izmjena.</span><span class="sxs-lookup"><span data-stu-id="e480f-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="e480f-137">Na stranici **Aktivnosti** odaberite **Pokreni**.</span><span class="sxs-lookup"><span data-stu-id="e480f-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="e480f-138">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="e480f-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e480f-139">Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e480f-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e480f-140">Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla.</span><span class="sxs-lookup"><span data-stu-id="e480f-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e480f-141">Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="e480f-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="e480f-142">Uređivanje aktivnosti</span><span class="sxs-lookup"><span data-stu-id="e480f-142">Edit an activity</span></span>

1. <span data-ttu-id="e480f-143">U uvidima u ciljnu skupinu idite na **Podaci** > **Aktivnosti**.</span><span class="sxs-lookup"><span data-stu-id="e480f-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="e480f-144">Odaberite entitet aktivnosti koji želite urediti i odaberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="e480f-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="e480f-145">Ili možete držati pokazivač iznad retka entiteta i odabrati ikonu **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="e480f-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="e480f-146">Kliknite na ikonu **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="e480f-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="e480f-147">U oknu **Uređivanje aktivnosti** ažurirajte vrijednosti i odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="e480f-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="e480f-148">Na stranici **Aktivnosti** odaberite **Pokreni**.</span><span class="sxs-lookup"><span data-stu-id="e480f-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="e480f-149">Brisanje aktivnosti</span><span class="sxs-lookup"><span data-stu-id="e480f-149">Delete an activity</span></span>

1. <span data-ttu-id="e480f-150">U uvidima u ciljnu skupinu idite na **Podaci** > **Aktivnosti**.</span><span class="sxs-lookup"><span data-stu-id="e480f-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="e480f-151">Odaberite entitet aktivnosti koji želite ukloniti i odaberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="e480f-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="e480f-152">Ili možete držati pokazivač iznad retka entiteta i odabrati ikonu **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="e480f-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="e480f-153">Usto možete odabrati više entiteta aktivnosti koje ćete istovremeno izbrisati.</span><span class="sxs-lookup"><span data-stu-id="e480f-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e480f-154">![Uređivanje ili brisanje odnosa među entitetima](media/activities-entities-edit-delete.png "Uređivanje ili brisanje odnosa među entitetima")</span><span class="sxs-lookup"><span data-stu-id="e480f-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="e480f-155">Odaberite ikonu **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="e480f-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="e480f-156">Potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="e480f-156">Confirm your deletion.</span></span>
