---
title: Pretražite i filtrirajte profile klijenata
description: Pronađite brzo informacije o objedinjenim profilima klijenata i filtrirajte određene atribute.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597134"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="c850a-103">Profili klijenta: indeks pretraživanja i filtriranja</span><span class="sxs-lookup"><span data-stu-id="c850a-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="c850a-104">Rezultat objedinjavanja podataka vaših klijenata jest entitet Profil klijenta koji pruža objedinjeni pregled nad ukupnom bazom klijenata.</span><span class="sxs-lookup"><span data-stu-id="c850a-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="c850a-105">Da biste brzo [pronašli informacije o određenom klijentu ili grupi klijenata](customer-profiles.md) možete konfigurirati mogućnosti **Pretraži** i **Filtriraj** na stranici **Klijenti**.</span><span class="sxs-lookup"><span data-stu-id="c850a-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="c850a-106">Pročitajte više o tome kako administratori mogu uređivati atribute na stranici **Pretraži i filtriraj indeks**, koja je dostupna korisnicima za pretraživanje i filtriranje.</span><span class="sxs-lookup"><span data-stu-id="c850a-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c850a-107">![Pretraži filtar](media/search-filter.png "Pretraži filtar")</span><span class="sxs-lookup"><span data-stu-id="c850a-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="c850a-108">Dodajte polja i odredite atribute</span><span class="sxs-lookup"><span data-stu-id="c850a-108">Add fields and specify attributes</span></span>

<span data-ttu-id="c850a-109">Ako kao administrator po prvi put definirate atribute koje je moguće pretraživati, prvo trebate definirati indeksirana polja.</span><span class="sxs-lookup"><span data-stu-id="c850a-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="c850a-110">Preporučujemo da odaberete sve atribute po kojima korisnici mogu pretraživati i filtrirati klijente na stranici **Klijenti**.</span><span class="sxs-lookup"><span data-stu-id="c850a-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="c850a-111">Možete odrediti samo atribute koji postoje na entitetu Profil klijenta, koji ste izradili tijekom postupka objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="c850a-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="c850a-112">Otvorite stranicu **Kupci** i odaberite **Pretraži i filtriraj indeks**.</span><span class="sxs-lookup"><span data-stu-id="c850a-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="c850a-113">Odaberite **+ Dodaj** da biste odredili indeksirana polja.</span><span class="sxs-lookup"><span data-stu-id="c850a-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="c850a-114">Na popisu odaberite atribute koje želite dodati kao indeksirana polja.</span><span class="sxs-lookup"><span data-stu-id="c850a-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="c850a-115">Uvijek možete dodati više atributa odabirom mogućnosti **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="c850a-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="c850a-116">Također, možete ukloniti sve odabrane atribute odabirom simbola **Ukloni**.</span><span class="sxs-lookup"><span data-stu-id="c850a-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="c850a-117">Istraživanje tablice polja indeksiranih klijenata</span><span class="sxs-lookup"><span data-stu-id="c850a-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="c850a-118">U tablici su dostupne sljedeće informacije.</span><span class="sxs-lookup"><span data-stu-id="c850a-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="c850a-119">**Naziv**: predstavlja naziv atributa kako se pojavljuje u entitetu Profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="c850a-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="c850a-120">**Vrsta podataka**: određuje je li vrsta podataka niz, broj ili datum.</span><span class="sxs-lookup"><span data-stu-id="c850a-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="c850a-121">**Uključeno u pretraživanje**: određuje može li se taj atribut koristiti za pretraživanje klijenata na stranici **Klijenti** koristeći polje **Pretraživanje**.</span><span class="sxs-lookup"><span data-stu-id="c850a-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="c850a-122">**Dodavanje filtra**: kontrola za upravljanje načina na koji se taj atribut može koristiti za filtriranje na stranici **Klijenti**.</span><span class="sxs-lookup"><span data-stu-id="c850a-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="c850a-123">Uređivanje opcija filtriranja za određeni atribut</span><span class="sxs-lookup"><span data-stu-id="c850a-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="c850a-124">Izbornik **Filtar** na stranici **Klijenti** može uključivati različit broj razina atributa (na primjer, različite dobne skupine prema kojima se filtriraju klijenti).</span><span class="sxs-lookup"><span data-stu-id="c850a-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="c850a-125">Odaberite **Dodaj filtar** za određeni atribut na stranici **Pretraži i filtriraj indeks**.</span><span class="sxs-lookup"><span data-stu-id="c850a-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="c850a-126">Možete definirati broj rezultata i redoslijed po kojem će biti organizirani.</span><span class="sxs-lookup"><span data-stu-id="c850a-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="c850a-127">Ovisno o vrsti podataka atributa prikazat će se jedna od sljedećih ploča.</span><span class="sxs-lookup"><span data-stu-id="c850a-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="c850a-128">Atributi vrste niza: odredite broj željenih rezultata u oknu **Mogućnosti filtra niza** i pravila redoslijeda prema kojima će biti organizirani.</span><span class="sxs-lookup"><span data-stu-id="c850a-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="c850a-129">Atributi vrste broja: odredite uključene intervale u oknu **Mogućnosti filtra broja** i pravila redoslijeda prema kojima će biti organizirani.</span><span class="sxs-lookup"><span data-stu-id="c850a-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="c850a-130">Atributi vrste datuma: odredite uključene intervale u oknu **Mogućnosti filtra datuma** i pravila redoslijeda prema kojima će biti organizirani.</span><span class="sxs-lookup"><span data-stu-id="c850a-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="c850a-131">Odaberite **Spremi** za primjenu izmjena.</span><span class="sxs-lookup"><span data-stu-id="c850a-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="c850a-132">Odaberite **Pokreni** kad budete spremni primijeniti svoje postavke.</span><span class="sxs-lookup"><span data-stu-id="c850a-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c850a-133">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="c850a-133">Next steps</span></span>

<span data-ttu-id="c850a-134">Idite na stranicu **Klijenti** za pretraživanje korisničkih profila ili upotrijebite indeksirana polja za prikaz podskupa svih korisničkih profila.</span><span class="sxs-lookup"><span data-stu-id="c850a-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]