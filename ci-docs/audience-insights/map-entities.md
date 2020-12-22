---
title: Mapiranje entiteta za objedinjavanje podataka
description: Mapirajte podatke da biste stvorili objedinjene profile klijenata.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405331"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="61539-103">Entiteti i atributi karte</span><span class="sxs-lookup"><span data-stu-id="61539-103">Map entities and attributes</span></span>

<span data-ttu-id="61539-104">**Mapiranje** je prva faza u procesu objedinjavanja podataka uvida u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="61539-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="61539-105">Mapiranje se sastoji od tri faze:</span><span class="sxs-lookup"><span data-stu-id="61539-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="61539-106">*Odabir entiteta*: identificirajte entitete koji se mogu kombinirati koji vode do skupa podataka s više potpunih informacija o vašim klijentima.</span><span class="sxs-lookup"><span data-stu-id="61539-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="61539-107">*Odabir atributa*: za svaki entitet identificirajte stupce koje želite kombinirati i uskladiti u fazama *uspoređivanja* i *spajanja*.</span><span class="sxs-lookup"><span data-stu-id="61539-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="61539-108">Ti se stupci nazivaju *Atributi*.</span><span class="sxs-lookup"><span data-stu-id="61539-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="61539-109">*Odabir primarnog ključa i semantičkog tipa*: Za svaki entitet identificirajte atribut koji želite definirati kao primarni ključ za taj entitet, a za svaki atribut identificirajte semantički tip koji najbolje opisuje taj atribut.</span><span class="sxs-lookup"><span data-stu-id="61539-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="61539-110">Za više informacija o općenitom tijeku objedinjavanja podataka pogledajte dio [Objedinjavanje](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="61539-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="61539-111">Odabir prvog entiteta</span><span class="sxs-lookup"><span data-stu-id="61539-111">Select the first entities</span></span>

1. <span data-ttu-id="61539-112">U uvidima u ciljnu skupinu idite na **Podaci** > **Objedini** > **Mapiraj**.</span><span class="sxs-lookup"><span data-stu-id="61539-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="61539-113">Pokrenite fazu mapiranja odabirom stavke **Odaberi entitete**.</span><span class="sxs-lookup"><span data-stu-id="61539-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="61539-114">Odaberite entitete i atribute koje želite koristiti u fazama *uskladi* i *spoji*.</span><span class="sxs-lookup"><span data-stu-id="61539-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="61539-115">Možete pojedinačno odabrati potrebne atribute iz entiteta ili uključiti sve atribute iz entiteta odabirom potvrdnog okvira **Uključi sva polja** na razini entiteta.</span><span class="sxs-lookup"><span data-stu-id="61539-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="61539-116">Preporučujemo vam da odaberete barem dva entiteta kako biste imali koristi od postupka objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="61539-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="61539-117">![Dodavanje primjera entiteta](media/data-manager-configure-map-add-entities-example.png "Dodavanje primjera entiteta")</span><span class="sxs-lookup"><span data-stu-id="61539-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="61539-118">U ovom primjeru dodajemo entitete **eCommerceContacts** i **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="61539-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="61539-119">Odabirom ovih entiteta možete steći uvid u to koji su od internetskih poslovnih klijenata članovi programa vjernosti.</span><span class="sxs-lookup"><span data-stu-id="61539-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="61539-120">Ključne riječi možete pretraživati po svim atributima i entitetima kako biste odabrali potrebne atribute koje želite mapirati.</span><span class="sxs-lookup"><span data-stu-id="61539-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="61539-121">![Primjer polja za pretraživanje](media/data-manager-configure-map-search-fields-example.png "Primjer polja za pretraživanje")</span><span class="sxs-lookup"><span data-stu-id="61539-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="61539-122">Odaberite **Primijeni** za potvrdu odabira.</span><span class="sxs-lookup"><span data-stu-id="61539-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="61539-123">Odaberite primarni ključ i semantičku vrstu za atribute</span><span class="sxs-lookup"><span data-stu-id="61539-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="61539-124">Nakon odabira entiteta, stranica **Mapiraj** navodi odabrane entitete za pregled.</span><span class="sxs-lookup"><span data-stu-id="61539-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="61539-125">Definirajte primarni ključ za entitet i identificirajte semantički tip za atribut u entitetu.</span><span class="sxs-lookup"><span data-stu-id="61539-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="61539-126">**Primarni ključ**: odaberite jedan atribut kao primarni ključ za svaki vaš entitet.</span><span class="sxs-lookup"><span data-stu-id="61539-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="61539-127">Da bi atribut bio važeći primarni ključ, on ne bi trebao uključivati dvostruke vrijednosti, vrijednosti koje nedostaju ili vrijednosti nula.</span><span class="sxs-lookup"><span data-stu-id="61539-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="61539-128">Atributi vrste podataka niza, cijelog broja i GUID-a podržani su kao primarni ključevi i bit će prikazani u polju za odabir.</span><span class="sxs-lookup"><span data-stu-id="61539-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="61539-129">**Semantički tip atributa**: kategorije vaših atributa, kao što su adresa e-pošte ili ime.</span><span class="sxs-lookup"><span data-stu-id="61539-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="61539-130">Kako biste upotrebljavali modele umjetne inteligencije za pametno predviđanje semantike, uštedjeli vrijeme i poboljšali točnost, postavite mogućnost **Inteligentno mapiranje** na **UKLJUČENO**.</span><span class="sxs-lookup"><span data-stu-id="61539-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="61539-131">Inteligentno mapiranje ističe preporuke o semantici koje se temelje na umjetnoj iteligenciji u polju **Vrsta**.</span><span class="sxs-lookup"><span data-stu-id="61539-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="61539-132">Ako ga postavite na **ISKLJUČENO**, vidjet ćete naše redovne preporuke za mapiranje.</span><span class="sxs-lookup"><span data-stu-id="61539-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="61539-133">Možete odabrati bilo koju vrstu semantike s dostupnog popisa mogućnnosti i prebrisati predloženi odabir.</span><span class="sxs-lookup"><span data-stu-id="61539-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="61539-134">![Vrsta atributa i predviđanje semantike](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Vrsta atributa i predviđanje semantike")</span><span class="sxs-lookup"><span data-stu-id="61539-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="61539-135">Također je moguće dodati i prilagođeni semantički tip.</span><span class="sxs-lookup"><span data-stu-id="61539-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="61539-136">Odaberite polje tipa za atribut i unesite naziv prilagođenog semantičkog tipa.</span><span class="sxs-lookup"><span data-stu-id="61539-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="61539-137">Tim putem također možete promijeniti vrste atributa koje je automatski identificirao sustav.</span><span class="sxs-lookup"><span data-stu-id="61539-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="61539-138">Svi atributi za koje se semantički tip automatski identificira grupirani su u odjeljku **Pregledaj mapirana polja**.</span><span class="sxs-lookup"><span data-stu-id="61539-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="61539-139">Pregledajte ove atribute i njihove semantičke tipove jer će se koristiti za kombiniranje vaših entiteta u koraku spajanja kod objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="61539-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="61539-140">Atributi koji nisu automatski mapirani u semantički tip grupirani su u odjeljku **Definiraj podatke u nemapiranim poljima**.</span><span class="sxs-lookup"><span data-stu-id="61539-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="61539-141">Odaberite polje semantičkog tipa za nemapirane atribute ili unesite naziv prilagođenog tipa atributa.</span><span class="sxs-lookup"><span data-stu-id="61539-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="61539-142">![Primarni ključ i vrsta atributa](media/data-manager-configure-map-add-attributes.png "Primarni ključ i vrsta atributa")</span><span class="sxs-lookup"><span data-stu-id="61539-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="61539-143">Jedno polje treba se mapirati na semantički tip Person.FullName da bi se ime klijenta popunilo u kartici klijenta.</span><span class="sxs-lookup"><span data-stu-id="61539-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="61539-144">U suprotnom će se kartice klijenta prikazati bez naziva.</span><span class="sxs-lookup"><span data-stu-id="61539-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="61539-145">Dodavanje i uklanjanje atributa i entiteta</span><span class="sxs-lookup"><span data-stu-id="61539-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="61539-146">Na **Ujedini** > **Mapiraj**, odaberite **Uredi polja**.</span><span class="sxs-lookup"><span data-stu-id="61539-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="61539-147">U oknu **Uredi polja**, dodajte ili uklonite atribute i entitete.</span><span class="sxs-lookup"><span data-stu-id="61539-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="61539-148">S pomoću pretraživanja ili pomicanja pronađite i odaberite svoje atribute i entitete od interesa.</span><span class="sxs-lookup"><span data-stu-id="61539-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="61539-149">Ne možete ukloniti atribut ili entitet ako su već usklađeni.</span><span class="sxs-lookup"><span data-stu-id="61539-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="61539-150">![Dodavanje ili uklanjanje atributa](media/configure-data-map-edit.png "Dodavanje ili uklanjanje atributa")</span><span class="sxs-lookup"><span data-stu-id="61539-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="61539-151">Odaberite **Primijeni**.</span><span class="sxs-lookup"><span data-stu-id="61539-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="61539-152">Dodavanje slika profilima</span><span class="sxs-lookup"><span data-stu-id="61539-152">Add images to profiles</span></span>

<span data-ttu-id="61539-153">Ako entitet sadrži URL-ove javno dostupnih slika ili logotipa profila, možete ih dodati u objedinjeni profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="61539-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="61539-154">Odaberite entitet i pronađite polje koje sadrži URL slike profila.</span><span class="sxs-lookup"><span data-stu-id="61539-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="61539-155">U polje za unos **Tip**, ručno unesite sljedeću vrijednost:</span><span class="sxs-lookup"><span data-stu-id="61539-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="61539-156">Za osobu: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="61539-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="61539-157">Za tvrtku ili ustanovu: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="61539-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="61539-158">Nastavite s koracima ujedinjavanja i osigurajte da je atribut koji sadrži URL slike također dodan u koraku [Spoji](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="61539-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="61539-159">Postavljanje atributa za organizacije</span><span class="sxs-lookup"><span data-stu-id="61539-159">Set attributes for organizations</span></span>

<span data-ttu-id="61539-160">Za organizacije (Pregled), tip atributa trebao bi se mapirati u "Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="61539-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="61539-161">![Primarni ključ i vrsta atributa B2B](media/configure-data-map-edit-b2b.png "Primarni ključ i vrsta atributa B2B")</span><span class="sxs-lookup"><span data-stu-id="61539-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="61539-162">Sljedeći korak</span><span class="sxs-lookup"><span data-stu-id="61539-162">Next step</span></span>

<span data-ttu-id="61539-163">Kao dio postupka objedinjavanja podataka idite na stranicu **Podudaranje**.</span><span class="sxs-lookup"><span data-stu-id="61539-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="61539-164">Otvorite dio [**Podudaranje**](match-entities.md) kako biste saznali više o ovoj fazi.</span><span class="sxs-lookup"><span data-stu-id="61539-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="61539-165">Provjerite sljedeći videozapis: [Prvi koraci: izrada jedinstvenog profila klijenta](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="61539-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>
