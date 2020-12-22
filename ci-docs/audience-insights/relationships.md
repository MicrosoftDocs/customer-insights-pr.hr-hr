---
title: Odnosi među entitetima i putanjama entiteta
description: Stvorite i upravljajte odnosima između entiteta iz više izvora podataka.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405340"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="60354-103">Odnosi među entitetima</span><span class="sxs-lookup"><span data-stu-id="60354-103">Relationships between entities</span></span>

<span data-ttu-id="60354-104">Odnosi pomažu pri povezivanju entiteta i generiranju grafikona vaših podataka kada entiteti dijele zajednički identifikator (strani ključ) koji se može uputiti iz jednog entiteta u drugi.</span><span class="sxs-lookup"><span data-stu-id="60354-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="60354-105">Povezani entiteti omogućuju vam definiranje segmenata i mjera na temelju više izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="60354-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="60354-106">Postoje dvije vrste odnosa.</span><span class="sxs-lookup"><span data-stu-id="60354-106">There are two types of relationships.</span></span> <span data-ttu-id="60354-107">Sistemski odnosi koji se ne mogu uređivati, a koji se izrađuju automatski i prilagođeni odnosi koje izrađuju i konfiguriraju korisnici.</span><span class="sxs-lookup"><span data-stu-id="60354-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="60354-108">Tijekom procesa uparivanja i spajanja, sistemski odnosi izrađuju se iza scene na temelju inteligentnog uparivanja.</span><span class="sxs-lookup"><span data-stu-id="60354-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="60354-109">Ovi odnosi pomažu pri povezivanju zapisa profila klijenta s ostalim odgovarajućim zapisima entiteta.</span><span class="sxs-lookup"><span data-stu-id="60354-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="60354-110">Sljedeći dijagram ilustrira izradu triju sistemskih odnosa kada se entitet klijenta uparuje s dodatnim entitetima radi izrade konačnog entiteta Profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="60354-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="60354-111">![Izrada odnosa](media/relationships-entities-merge.png "Izrada odnosa")</span><span class="sxs-lookup"><span data-stu-id="60354-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="60354-112">***CustomerToContact* odnos** izrađen je između entiteta Klijent i entiteta Kontakt.</span><span class="sxs-lookup"><span data-stu-id="60354-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="60354-113">Entitet Klijent dobiva polje ključa **Contact_contactId** za povezivanje s poljem ključa **contactId** entiteta Kontakt.</span><span class="sxs-lookup"><span data-stu-id="60354-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="60354-114">**_CustomerToAccount_ odnos** izrađen je između entiteta Klijent i entiteta Račun.</span><span class="sxs-lookup"><span data-stu-id="60354-114">**_CustomerToAccount_ relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="60354-115">Entitet Klijent dobiva polje ključa **Account_accountId** za povezivanje s poljem ključa **accountId** entiteta Račun.</span><span class="sxs-lookup"><span data-stu-id="60354-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="60354-116">**_CustomerToWebAccount_ odnos** izrađen je između entiteta Klijent i entiteta Web-račun.</span><span class="sxs-lookup"><span data-stu-id="60354-116">**_CustomerToWebAccount_ relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="60354-117">Entitet Klijent dobiva polje ključa **WebAccount_webaccountId** za povezivanje s poljem ključa **webaccountId** entiteta Web-račun.</span><span class="sxs-lookup"><span data-stu-id="60354-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="60354-118">Izrada odnosa</span><span class="sxs-lookup"><span data-stu-id="60354-118">Create a relationship</span></span>

<span data-ttu-id="60354-119">Definirajte prilagođene odnose na stranici **Odnosi**.</span><span class="sxs-lookup"><span data-stu-id="60354-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="60354-120">Svaki se odnos sastoji od entiteta izvora (entitet koji drži vanjski ključ) i entiteta cilja (entitet na koji ukazuje vanjski ključ entiteta izvora).</span><span class="sxs-lookup"><span data-stu-id="60354-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="60354-121">U uvidima u ciljnu skupinu idite na **Podaci** > **Odnosi**.</span><span class="sxs-lookup"><span data-stu-id="60354-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="60354-122">Odaberite **Novi odnos**.</span><span class="sxs-lookup"><span data-stu-id="60354-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="60354-123">U oknu **Dodaj odnos** navedite sljedeće informacije:</span><span class="sxs-lookup"><span data-stu-id="60354-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="60354-124">![Unos pojedinosti o odnosu](media/relationships-add.png "Unos pojedinosti o odnosu")</span><span class="sxs-lookup"><span data-stu-id="60354-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="60354-125">**Naziv odnosa**: Naziv koji odražava svrhu odnosa (na primjer, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="60354-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="60354-126">**Opis**: Opis odnosa.</span><span class="sxs-lookup"><span data-stu-id="60354-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="60354-127">**Entitet Izvor** : Odaberite entitet koji se koristi kao izvor u odnosu (na primjer, WebLog).</span><span class="sxs-lookup"><span data-stu-id="60354-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="60354-128">**Kardinalnost**: Odaberite kardinalnost zapisa entiteta izvor.</span><span class="sxs-lookup"><span data-stu-id="60354-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="60354-129">Na primjer, „mnogo” znači da je više zapisa web-zapisnika povezano s jednim web-računom.</span><span class="sxs-lookup"><span data-stu-id="60354-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="60354-130">**Polje ključa izvora**: Ovo predstavlja polje stranog ključa u entitetu izvor.</span><span class="sxs-lookup"><span data-stu-id="60354-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="60354-131">Na primjer, WebLog ima **accountId** polje stranog ključa.</span><span class="sxs-lookup"><span data-stu-id="60354-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="60354-132">**Entitet Cilj** : Odaberite entitet koji se koristi kao cilj u odnosu (na primjer, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="60354-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="60354-133">**Kardinalnost cilja**: Odaberite kardinalnost zapisa entiteta cilja.</span><span class="sxs-lookup"><span data-stu-id="60354-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="60354-134">Na primjer, „jedan” znači da je više zapisa web-zapisnika povezano s jednim web-računom.</span><span class="sxs-lookup"><span data-stu-id="60354-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="60354-135">**Polje ključa cilja**: Ovo polje predstavlja polje ključa entiteta cilj.</span><span class="sxs-lookup"><span data-stu-id="60354-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="60354-136">Na primjer, WebAccount ima **accountId** polje ključa.</span><span class="sxs-lookup"><span data-stu-id="60354-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="60354-137">Podržani su samo odnosi mnogi na jedan i jedan na jedan.</span><span class="sxs-lookup"><span data-stu-id="60354-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="60354-138">Odnosi mnogi na mnogi mogu se izraditi s pomoću dva odnosa mnogi na jedan i entiteta veze (entitet koji se koristi za povezivanje entiteta izvor i entiteta cilj).</span><span class="sxs-lookup"><span data-stu-id="60354-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="60354-139">Brisanje odnosa</span><span class="sxs-lookup"><span data-stu-id="60354-139">Delete a relationship</span></span>

1. <span data-ttu-id="60354-140">U uvidima u ciljnu skupinu idite na **Podaci** > **Odnosi**.</span><span class="sxs-lookup"><span data-stu-id="60354-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="60354-141">Potvrdite okvire za odnose koje želite izbrisati.</span><span class="sxs-lookup"><span data-stu-id="60354-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="60354-142">Odaberite **Izbriši** na vrhu tablice **Odnosi**.</span><span class="sxs-lookup"><span data-stu-id="60354-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="60354-143">Potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="60354-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="60354-144">Sljedeći korak</span><span class="sxs-lookup"><span data-stu-id="60354-144">Next step</span></span>

<span data-ttu-id="60354-145">Sistemski i prilagođeni odnosi koriste se za izradu segmenata na temelju više izvora podataka koji se više ne biraju.</span><span class="sxs-lookup"><span data-stu-id="60354-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="60354-146">Dodatne informacije potražite u dijelu [Segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="60354-146">For more information, see [Segments](segments.md).</span></span>
