---
title: Prikaz profila klijenata
description: Dobijte kombinirani prikaz svojih objedinjenih podataka o klijentima.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596858"
---
# <a name="customer-profiles"></a><span data-ttu-id="5e56e-103">Profili klijenata</span><span class="sxs-lookup"><span data-stu-id="5e56e-103">Customer profiles</span></span>

<span data-ttu-id="5e56e-104">Na stranici **Klijenti** prikazuje se kombinirani prikaz vaših klijenata na temelju podataka profila prikupljenih iz [svih izvora podataka](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="5e56e-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="5e56e-105">Profili klijenata dostupni su nakon što [izradite objedinjeni entitet klijenta](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="5e56e-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="5e56e-106">Obavezno dovršite proces objedinjavanja podataka da biste stekli bogatije prikaze svojih klijenata.</span><span class="sxs-lookup"><span data-stu-id="5e56e-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="5e56e-107">Stranica vam također omogućuje pretraživanje klijenata.</span><span class="sxs-lookup"><span data-stu-id="5e56e-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="5e56e-108">Klijenti mogu biti pojedinci ili organizacije (pretpregled).</span><span class="sxs-lookup"><span data-stu-id="5e56e-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="5e56e-109">Svaki profil klijenta ili organizacije predstavljen je pločicom.</span><span class="sxs-lookup"><span data-stu-id="5e56e-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="5e56e-110">Odaberite pločicu da biste vidjeli dodatne informacije o tom određenom klijentu ili organizaciji.</span><span class="sxs-lookup"><span data-stu-id="5e56e-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="5e56e-111">Upotrijebite kontrole za postavljanje stranica na dnu stranice za prikaz dodatnih zapisa.</span><span class="sxs-lookup"><span data-stu-id="5e56e-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="5e56e-112">![B2C profili klijenata](media/profiles-customers.png "B2C profili klijenata")</span><span class="sxs-lookup"><span data-stu-id="5e56e-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="5e56e-113">Organizacije (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="5e56e-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="5e56e-114">![B2B profili klijenata](media/profile-customers-b2b.png "B2B profili klijenata")</span><span class="sxs-lookup"><span data-stu-id="5e56e-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="5e56e-115">Ako ne možete vidjeti pločice kada odaberete **Klijenti** na navigacijskoj traci, vaš administrator treba [definirati barem jedan atribut koji se može pretraživati](search-filter-index.md) na **Indeksu pretraživanja i filtriranja**.</span><span class="sxs-lookup"><span data-stu-id="5e56e-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="5e56e-116">Pretraživanje klijenata</span><span class="sxs-lookup"><span data-stu-id="5e56e-116">Search for customers</span></span>

<span data-ttu-id="5e56e-117">Potražite klijente unosom imena ili nekog drugog atributa u okvir za pretraživanje.</span><span class="sxs-lookup"><span data-stu-id="5e56e-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="5e56e-118">Pretraživanje funkcionira samo unutar entiteta Profil klijenta koji je izrađen tijekom procesa objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="5e56e-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="5e56e-119">Kao administrator, možete konfigurirati atribute pretraživanja s pomoću stranice **Indeks Pretraži i filtriraj**.</span><span class="sxs-lookup"><span data-stu-id="5e56e-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="5e56e-120">Za više informacija pogledajte [Upravljanje stranicom Indeks Pretraži i filtriraj](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="5e56e-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="5e56e-121">Filtriranje klijenata</span><span class="sxs-lookup"><span data-stu-id="5e56e-121">Filter customers</span></span>

<span data-ttu-id="5e56e-122">Možete filtrirati klijente prema poljima entiteta Profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="5e56e-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="5e56e-123">Slično pretraživanju, vaš administrator najprije će morati definirati polja kao filtrirajuća s pomoću stranice **Indeks Pretraži i filtriraj**.</span><span class="sxs-lookup"><span data-stu-id="5e56e-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="5e56e-124">Odaberite **Filtar** na stranici **Klijenti**.</span><span class="sxs-lookup"><span data-stu-id="5e56e-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="5e56e-125">Potvrdite okvire pored atributa prema kojima želite filtrirati klijente.</span><span class="sxs-lookup"><span data-stu-id="5e56e-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="5e56e-126">![Profili klijenata](media/profiles-customers3.png "Profili klijenata")</span><span class="sxs-lookup"><span data-stu-id="5e56e-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="5e56e-127">Uklonite filtre odabirom opcije **Obriši filtre** na stranici **Klijenti**.</span><span class="sxs-lookup"><span data-stu-id="5e56e-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="5e56e-128">Stranica s pojedinostima o klijentu</span><span class="sxs-lookup"><span data-stu-id="5e56e-128">Customer details page</span></span>

<span data-ttu-id="5e56e-129">Odaberite bilo koju pločicu klijenta da biste otvorili **Stranicu s pojedinostima o klijentu**.</span><span class="sxs-lookup"><span data-stu-id="5e56e-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="5e56e-130">Ovaj prikaz sadrži objedinjene podatke za odabranog klijenta.</span><span class="sxs-lookup"><span data-stu-id="5e56e-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="5e56e-131">Pojedinosti o klijentu uključuju sljedeće:</span><span class="sxs-lookup"><span data-stu-id="5e56e-131">Customer details include:</span></span>

-   <span data-ttu-id="5e56e-132">**Pločica profila klijenta:** Ova pločica prikazuje različite vrijednosti iz entiteta jedinstvenog profila kupca.</span><span class="sxs-lookup"><span data-stu-id="5e56e-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="5e56e-133">Te pojedinosti mogu uključivati adresu e-pošte, ime, grad itd.</span><span class="sxs-lookup"><span data-stu-id="5e56e-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="5e56e-134">**Potencijalni interesi, potencijalni brendovi:** Pokazuje jeste li konfigurirali obogaćivanje prve strane.</span><span class="sxs-lookup"><span data-stu-id="5e56e-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="5e56e-135">Predstavlja potencijalne interese i afinitete za brendove koje može imati klijent s profilom sličnim ovom klijentu.</span><span class="sxs-lookup"><span data-stu-id="5e56e-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="5e56e-136">Za više informacija pogledajte [Obogaćivanje profila klijenata afinitetima za robne marke i interese](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="5e56e-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="5e56e-137">**Mjerenja:** Pokazuje jeste li konfigurirali jedno ili više mjerenja određene vrste: mjerenja korisničkih atributa.</span><span class="sxs-lookup"><span data-stu-id="5e56e-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="5e56e-138">Uključuju izračunate KPI-jeve oko vaših klijenata na razini pojedinačnog klijenta.</span><span class="sxs-lookup"><span data-stu-id="5e56e-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="5e56e-139">Za više informacija pogledajte [Definiranje i upravljanje mjerama](measures.md).</span><span class="sxs-lookup"><span data-stu-id="5e56e-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="5e56e-140">**Vremenska traka aktivnosti:** Pokazuje jeste li konfigurirali aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="5e56e-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="5e56e-141">Prikaz vremenske trake sadrži kronološki poredane aktivnosti ovog klijenta, počevši od najnovije aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="5e56e-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="5e56e-142">Za dodatne informacije pogledajte [Aktivnosti klijenata](activities.md).</span><span class="sxs-lookup"><span data-stu-id="5e56e-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="5e56e-143">Odaberite **Natrag na stranicu Klijenti** za povratak na stranicu za pretraživanje klijenata.</span><span class="sxs-lookup"><span data-stu-id="5e56e-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5e56e-144">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="5e56e-144">Next steps</span></span>

<span data-ttu-id="5e56e-145">[Dodajte više izvora podataka](data-sources.md) ili [stvorite segmente klijenta](segments.md).</span><span class="sxs-lookup"><span data-stu-id="5e56e-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]