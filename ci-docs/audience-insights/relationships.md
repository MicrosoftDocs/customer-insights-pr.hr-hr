---
title: Odnosi među entitetima i putanjama entiteta
description: Stvorite i upravljajte odnosima između entiteta iz više izvora podataka.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171155"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="90a1b-103">Odnosi među entitetima</span><span class="sxs-lookup"><span data-stu-id="90a1b-103">Relationships between entities</span></span>

<span data-ttu-id="90a1b-104">Odnosi povezuju entitete i definiraju grafikon vaših podataka kada entiteti dijele zajednički identifikator, vanjski ključ.</span><span class="sxs-lookup"><span data-stu-id="90a1b-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="90a1b-105">Ovaj se vanjski ključ može referencirati s jednog entiteta na drugi.</span><span class="sxs-lookup"><span data-stu-id="90a1b-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="90a1b-106">Povezani entiteti omogućuju definiciju segmenata i mjera na temelju više izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="90a1b-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="90a1b-107">Postoje tri vrste odnosa:</span><span class="sxs-lookup"><span data-stu-id="90a1b-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="90a1b-108">Odnosi sustava koji se ne mogu uređivati, stvara ih sustav kao dio postupka objedinjavanja podataka</span><span class="sxs-lookup"><span data-stu-id="90a1b-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="90a1b-109">Naslijeđeni odnosi koji se ne mogu uređivati, a koji se automatski stvaraju iz unosa izvora podataka</span><span class="sxs-lookup"><span data-stu-id="90a1b-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="90a1b-110">Prilagođeni odnosi koji se mogu uređivati i koje stvaraju i konfiguriraju korisnici</span><span class="sxs-lookup"><span data-stu-id="90a1b-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="90a1b-111">Odnosi sustava koji se ne mogu uređivati</span><span class="sxs-lookup"><span data-stu-id="90a1b-111">Non-editable system relationships</span></span>

<span data-ttu-id="90a1b-112">Tijekom objedinjavanja podataka, odnosi sustava stvaraju se automatski na temelju inteligentnog podudaranja.</span><span class="sxs-lookup"><span data-stu-id="90a1b-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="90a1b-113">Ovi odnosi pomažu pri povezivanju zapisa profila klijenta s odgovarajućim zapisima.</span><span class="sxs-lookup"><span data-stu-id="90a1b-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="90a1b-114">Sljedeći dijagram ilustrira stvaranje tri odnosa na temelju sustava.</span><span class="sxs-lookup"><span data-stu-id="90a1b-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="90a1b-115">Entitet klijenta uparuje se s drugim entitetima kako bi se dobio objedinjeni entitet *Klijent*.</span><span class="sxs-lookup"><span data-stu-id="90a1b-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Dijagram s putovima odnosa za entitet klijenta s tri 1-n odnosa.":::

- <span data-ttu-id="90a1b-117">***CustomerToContact* odnos** izrađen je između entiteta *Klijent* i entiteta *Kontakt*.</span><span class="sxs-lookup"><span data-stu-id="90a1b-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="90a1b-118">Entitet *Klijent* dobiva polje ključa **Contact_contactID** za povezivanje s poljem ključa **contactID** entiteta *Kontakt*.</span><span class="sxs-lookup"><span data-stu-id="90a1b-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="90a1b-119">***CustomerToAccount* odnos** izrađen je između entiteta *Klijent* i entiteta *Račun*.</span><span class="sxs-lookup"><span data-stu-id="90a1b-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="90a1b-120">Entitet *Klijent* dobiva polje ključa **Account_accountID** za povezivanje s poljem ključa **accountID** entiteta *Račun*.</span><span class="sxs-lookup"><span data-stu-id="90a1b-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="90a1b-121">***CustomerToWebAccount* odnos** izrađen je između entiteta *Klijent* i entiteta *Web-račun*.</span><span class="sxs-lookup"><span data-stu-id="90a1b-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="90a1b-122">Entitet *Klijent* dobiva polje ključa **WebAccount_webaccountID** za povezivanje s poljem ključa **webaccountID** entiteta *Web-račun*.</span><span class="sxs-lookup"><span data-stu-id="90a1b-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="90a1b-123">Naslijeđeni odnosi koji se ne mogu uređivati</span><span class="sxs-lookup"><span data-stu-id="90a1b-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="90a1b-124">Tijekom postupka unosa podataka, sustav provjerava izvore podataka za postojeće odnose.</span><span class="sxs-lookup"><span data-stu-id="90a1b-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="90a1b-125">Ako ne postoje odnosi, sustav ih automatski stvara.</span><span class="sxs-lookup"><span data-stu-id="90a1b-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="90a1b-126">Ovi se odnosi također koriste u nizvodnim procesima.</span><span class="sxs-lookup"><span data-stu-id="90a1b-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="90a1b-127">Stvaranje prilagođenog odnosa</span><span class="sxs-lookup"><span data-stu-id="90a1b-127">Create a custom relationship</span></span>

<span data-ttu-id="90a1b-128">Odnos se sastoji od *izvornog entiteta* koji sadrži vanjski ključ i *ciljnog entiteta* na koji ukazuje vanjski ključ izvornog entiteta.</span><span class="sxs-lookup"><span data-stu-id="90a1b-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="90a1b-129">U uvidima u ciljnu skupinu idite na **Podaci** > **Odnosi**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="90a1b-130">Odaberite **Novi odnos**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="90a1b-131">U oknu **Novi odnos** navedite sljedeće informacije:</span><span class="sxs-lookup"><span data-stu-id="90a1b-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Bočno okno novog odnosa s praznim poljima za unos.":::

   - <span data-ttu-id="90a1b-133">**Naziv odnosa**: naziv koji odražava svrhu odnosa.</span><span class="sxs-lookup"><span data-stu-id="90a1b-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="90a1b-134">Primjer: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="90a1b-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="90a1b-135">**Opis**: Opis odnosa.</span><span class="sxs-lookup"><span data-stu-id="90a1b-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="90a1b-136">**Izvorni entitet**: entitet koji se koristi kao izvor u odnosu.</span><span class="sxs-lookup"><span data-stu-id="90a1b-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="90a1b-137">Primjer: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="90a1b-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="90a1b-138">**Ciljni entitet**: entitet koji se koristi kao cilj u odnosu.</span><span class="sxs-lookup"><span data-stu-id="90a1b-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="90a1b-139">Primjer: Klijent.</span><span class="sxs-lookup"><span data-stu-id="90a1b-139">Example: Customer.</span></span>
   - <span data-ttu-id="90a1b-140">**Izvorna kardinalnost**: određuje kardinalnost izvornog entiteta.</span><span class="sxs-lookup"><span data-stu-id="90a1b-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="90a1b-141">Kardinalnost opisuje broj mogućih elemenata u skupu.</span><span class="sxs-lookup"><span data-stu-id="90a1b-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="90a1b-142">Uvijek se odnosi na ciljnu kardinalnost.</span><span class="sxs-lookup"><span data-stu-id="90a1b-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="90a1b-143">Možete birati između **Jedan** i **Više**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="90a1b-144">Podržani su samo odnosi mnogi na jedan i jedan na jedan.</span><span class="sxs-lookup"><span data-stu-id="90a1b-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="90a1b-145">Više na jedan: više izvornih zapisa može se odnositi na jedan ciljni zapis.</span><span class="sxs-lookup"><span data-stu-id="90a1b-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="90a1b-146">Primjer: više slučajeva podrške od jednog klijenta.</span><span class="sxs-lookup"><span data-stu-id="90a1b-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="90a1b-147">Jedan na jedan: jedan izvorni zapis odnosi se na jedan ciljni zapis.</span><span class="sxs-lookup"><span data-stu-id="90a1b-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="90a1b-148">Primjer: jedan ID odanosti za jednog klijenta.</span><span class="sxs-lookup"><span data-stu-id="90a1b-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="90a1b-149">Odnosi jedan na više mogu se stvoriti pomoću dva odnosa više na jedan i povezujućeg entiteta koji povezuje izvorni entitet i ciljni entitet.</span><span class="sxs-lookup"><span data-stu-id="90a1b-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="90a1b-150">**Kardinalnost cilja**: Odaberite kardinalnost zapisa entiteta cilja.</span><span class="sxs-lookup"><span data-stu-id="90a1b-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="90a1b-151">**Polje izvornog ključa**: polje vanjskog ključa u izvornom entitetu.</span><span class="sxs-lookup"><span data-stu-id="90a1b-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="90a1b-152">Primjer: SupportCase bi mogao koristiti CaseID kao polje vanjskog ključa.</span><span class="sxs-lookup"><span data-stu-id="90a1b-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="90a1b-153">**Polje ciljnog ključa**: polje ključa ciljnog entiteta.</span><span class="sxs-lookup"><span data-stu-id="90a1b-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="90a1b-154">Primjer Klijent bi mogao koristiti polje ključa **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="90a1b-155">Odaberite **Spremi** za stvaranje prilagođenog odnosa.</span><span class="sxs-lookup"><span data-stu-id="90a1b-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="90a1b-156">Prikaz odnosa</span><span class="sxs-lookup"><span data-stu-id="90a1b-156">View relationships</span></span>

<span data-ttu-id="90a1b-157">Na stranici Odnosi navedeni su svi stvoreni odnosi.</span><span class="sxs-lookup"><span data-stu-id="90a1b-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="90a1b-158">Svaki redak predstavlja odnos, koji također uključuje pojedinosti o izvornom entitetu, ciljnom entitetu i kardinalnosti.</span><span class="sxs-lookup"><span data-stu-id="90a1b-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Popis odnosa i mogućnosti na traci radnji stranice Odnosi.":::

<span data-ttu-id="90a1b-160">Ova stranica nudi skup mogućnosti za postojeće i nove odnose:</span><span class="sxs-lookup"><span data-stu-id="90a1b-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="90a1b-161">**Novi odnos**: [Stvaranje prilagođenog odnosa](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="90a1b-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="90a1b-162">**Vizualizator**: [Istražite vizualizator odnosa](#explore-the-relationship-visualizer) da biste vidjeli mrežni dijagram postojećih odnosa i njihovu kardinalnost.</span><span class="sxs-lookup"><span data-stu-id="90a1b-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="90a1b-163">**Filtrirati po**: Odaberite vrstu odnosa koja će se prikazivati na popisu.</span><span class="sxs-lookup"><span data-stu-id="90a1b-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="90a1b-164">**Pretraživanje odnosa**: Upotrijebite tekstualno pretraživanje svojstava odnosa.</span><span class="sxs-lookup"><span data-stu-id="90a1b-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="90a1b-165">Istražite vizualizator odnosa</span><span class="sxs-lookup"><span data-stu-id="90a1b-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="90a1b-166">Vizualizator odnosa prikazuje mrežni dijagram postojećih odnosa među povezanim entitetima i njihovu kardinalnost.</span><span class="sxs-lookup"><span data-stu-id="90a1b-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="90a1b-167">Da biste prilagodili prikaz, možete promijeniti položaj okvira povlačenjem po radnom području.</span><span class="sxs-lookup"><span data-stu-id="90a1b-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Snimka zaslona s mrežnim dijagramom vizualizatora odnosa s vezama među povezanim entitetima.":::

<span data-ttu-id="90a1b-169">Dostupne mogućnosti:</span><span class="sxs-lookup"><span data-stu-id="90a1b-169">Available options:</span></span> 
- <span data-ttu-id="90a1b-170">**Izvezi kao sliku**: Spremite trenutni prikaz kao slikovnu datoteku.</span><span class="sxs-lookup"><span data-stu-id="90a1b-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="90a1b-171">**Promjena na vodoravni/okomiti raspored**: Promijenite poravnanje entiteta i odnosa.</span><span class="sxs-lookup"><span data-stu-id="90a1b-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="90a1b-172">**Uređivanje**: Ažurirajte svojstva prilagođenih odnosa u oknu za uređivanje i spremite promjene.</span><span class="sxs-lookup"><span data-stu-id="90a1b-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="90a1b-173">Upravljanje postojećim odnosima</span><span class="sxs-lookup"><span data-stu-id="90a1b-173">Manage existing relationships</span></span> 

<span data-ttu-id="90a1b-174">Na stranici Odnosi svaki je odnos predstavljen retkom.</span><span class="sxs-lookup"><span data-stu-id="90a1b-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="90a1b-175">Odaberite odnos i odaberite jednu od sljedećih mogućnosti:</span><span class="sxs-lookup"><span data-stu-id="90a1b-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="90a1b-176">**Uređivanje**: Ažurirajte svojstva prilagođenih odnosa u oknu za uređivanje i spremite promjene.</span><span class="sxs-lookup"><span data-stu-id="90a1b-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="90a1b-177">**Brisanje**: Izbrišite prilagođene odnose.</span><span class="sxs-lookup"><span data-stu-id="90a1b-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="90a1b-178">**Prikaz**: Prikažite odnose koje je stvorio sustav i naslijeđene odnose.</span><span class="sxs-lookup"><span data-stu-id="90a1b-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="90a1b-179">Sljedeći korak</span><span class="sxs-lookup"><span data-stu-id="90a1b-179">Next step</span></span>

<span data-ttu-id="90a1b-180">Odnosi sustava i prilagođeni odnosi koriste se za [izradu segmenata](segments.md) na temelju više izvora podataka koji se više ne biraju.</span><span class="sxs-lookup"><span data-stu-id="90a1b-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
