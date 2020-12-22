---
title: Vodič uzorka za predviđanje gubitka pretplate
description: Upotrijebite ovaj uzorak vodiča da biste isprobali gotov model predviđanja gubitka pretplate.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653971"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="949e2-103">Vodič uzorka za predviđanje gubitka pretplate (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="949e2-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="949e2-104">Objasnit ćemo vam kroz primjer predviđanje odbijanja pretplate pomoću podataka uzorka navedenih u nastavku.</span><span class="sxs-lookup"><span data-stu-id="949e2-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="949e2-105">Scenarij</span><span class="sxs-lookup"><span data-stu-id="949e2-105">Scenario</span></span>

<span data-ttu-id="949e2-106">Contoso je tvrtka koja proizvodi visokokvalitetnu kavu i aparate za kavu koje prodaju putem svoje web-stranice Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="949e2-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="949e2-107">Nedavno su pokrenuli pretplatu za svoje kupce kako bi redovito dobivali kavu.</span><span class="sxs-lookup"><span data-stu-id="949e2-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="949e2-108">Cilj im je razumjeti koji bi pretplaćeni kupci mogli otkazati pretplatu u sljedećih nekoliko mjeseci.</span><span class="sxs-lookup"><span data-stu-id="949e2-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="949e2-109">Znajući tko će od njihovih klijenata **vjerojatno prekinuti**, može im pomoći uštedjeti na marketinškim aktivnostima usredotočujući se na njihovo zadržavanje.</span><span class="sxs-lookup"><span data-stu-id="949e2-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="949e2-110">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="949e2-110">Prerequisites</span></span>

- <span data-ttu-id="949e2-111">Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="949e2-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="949e2-112">Preporučujemo da primijenite sljedeće korake [u novom okruženju](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="949e2-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="949e2-113">Zadatak 1 – Podaci za unos</span><span class="sxs-lookup"><span data-stu-id="949e2-113">Task 1 - Ingest Data</span></span>

<span data-ttu-id="949e2-114">Pregledajte članke [o unosu podataka](data-sources.md) i posebice o [uvozu izvora podataka pomoću konektora Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="949e2-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="949e2-115">Sljedeće informacije pretpostavljaju da ste se upoznali s unosom podataka općenito.</span><span class="sxs-lookup"><span data-stu-id="949e2-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="949e2-116">Unesite podatke o klijentima s platforme eCommerce</span><span class="sxs-lookup"><span data-stu-id="949e2-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="949e2-117">Stvorite izvor podataka pod nazivom **E-trgovina**, odaberite opciju uvoza i odaberite poveznik **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="949e2-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="949e2-118">Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="949e2-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="949e2-119">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="949e2-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="949e2-120">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="949e2-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="949e2-121">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="949e2-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="949e2-122">**Datum izrade**: datum/vrijeme/vremenska zona</span><span class="sxs-lookup"><span data-stu-id="949e2-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="949e2-123">![Promijenite DoB u Datum](media/ecommerce-dob-date.PNG "pretvori datum rođenja u datum")</span><span class="sxs-lookup"><span data-stu-id="949e2-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="949e2-124">U polju „Naziv” u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Kontakti e-trgovine**</span><span class="sxs-lookup"><span data-stu-id="949e2-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="949e2-125">Spremite izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="949e2-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="949e2-126">Unesite podatke o klijentima iz sheme vjernosti</span><span class="sxs-lookup"><span data-stu-id="949e2-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="949e2-127">Stvorite izvor podataka pod nazivom **LoyaltyScheme**, odaberite opciju uvoza i odaberite poveznik **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="949e2-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="949e2-128">Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="949e2-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="949e2-129">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="949e2-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="949e2-130">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="949e2-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="949e2-131">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="949e2-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="949e2-132">**Nagradni bodovi**: cijeli broj</span><span class="sxs-lookup"><span data-stu-id="949e2-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="949e2-133">**Datum stvaranja**: datum/vrijeme</span><span class="sxs-lookup"><span data-stu-id="949e2-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="949e2-134">U polju „Naziv” u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Odanost klijenata**.</span><span class="sxs-lookup"><span data-stu-id="949e2-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="949e2-135">Spremite izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="949e2-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="949e2-136">Informacije o unosu pretplate</span><span class="sxs-lookup"><span data-stu-id="949e2-136">Ingest subscription information</span></span>

1. <span data-ttu-id="949e2-137">Stvorite izvor podataka pod nazivom **Povijest pretplate**, odaberite opciju uvoza i odaberite poveznik **Tekst / CSV**.</span><span class="sxs-lookup"><span data-stu-id="949e2-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="949e2-138">Unesite URL za kontakte e-trgovine https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="949e2-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="949e2-139">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="949e2-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="949e2-140">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="949e2-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="949e2-141">**ID pretplate**: cijeli broj</span><span class="sxs-lookup"><span data-stu-id="949e2-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="949e2-142">**Iznos pretplate**: valuta</span><span class="sxs-lookup"><span data-stu-id="949e2-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="949e2-143">**Datum završetka pretplate**: datum/vrijeme</span><span class="sxs-lookup"><span data-stu-id="949e2-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="949e2-144">**Datum početka pretplate**: datum/vrijeme</span><span class="sxs-lookup"><span data-stu-id="949e2-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="949e2-145">**Datum transakcije**: datum/vrijeme</span><span class="sxs-lookup"><span data-stu-id="949e2-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="949e2-146">**IsRecurring**: točno/netočno</span><span class="sxs-lookup"><span data-stu-id="949e2-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="949e2-147">**Is_auto_renew**: točno/netočno</span><span class="sxs-lookup"><span data-stu-id="949e2-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="949e2-148">**Ponavljajuća frekvencija u mjesecima**: cijeli broj</span><span class="sxs-lookup"><span data-stu-id="949e2-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="949e2-149">U polju „Naziv” u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Povijest pretplate**.</span><span class="sxs-lookup"><span data-stu-id="949e2-149">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="949e2-150">Spremite izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="949e2-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="949e2-151">Unesite podatke o kupcima iz recenzija web-stranice</span><span class="sxs-lookup"><span data-stu-id="949e2-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="949e2-152">Stvorite izvor podataka pod nazivom **Web-stranica**, odaberite opciju uvoza i odaberite poveznik **Tekst / CSV**.</span><span class="sxs-lookup"><span data-stu-id="949e2-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="949e2-153">Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="949e2-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="949e2-154">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="949e2-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="949e2-155">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="949e2-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="949e2-156">**Ocjena pregleda**: cijeli broj</span><span class="sxs-lookup"><span data-stu-id="949e2-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="949e2-157">**Datum pregleda**: datum</span><span class="sxs-lookup"><span data-stu-id="949e2-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="949e2-158">U polju „Naziv” u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Recenzije web-stranice**.</span><span class="sxs-lookup"><span data-stu-id="949e2-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="949e2-159">Zadatak 2 - Objedinjavanje podataka</span><span class="sxs-lookup"><span data-stu-id="949e2-159">Task 2 - Data unification</span></span>

<span data-ttu-id="949e2-160">Nakon unosa podataka, sada započinjemo postupak **Karta, podudaranje, spajanje** za stvaranje objedinjenog profila kupca.</span><span class="sxs-lookup"><span data-stu-id="949e2-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="949e2-161">Dodatne informacije potražite u odjeljku [Objedinjavanje podataka](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="949e2-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="949e2-162">Mapa</span><span class="sxs-lookup"><span data-stu-id="949e2-162">Map</span></span>

1. <span data-ttu-id="949e2-163">Nakon unosa podataka, mapirajte kontakte iz e-trgovine i podataka o vjernosti u uobičajene vrste podataka.</span><span class="sxs-lookup"><span data-stu-id="949e2-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="949e2-164">Idite na **Podaci** > **Objedini** > **Mapiraj**.</span><span class="sxs-lookup"><span data-stu-id="949e2-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="949e2-165">Odaberite entitete koji predstavljaju profil klijenta – **Kontakti e-trgovine** i **Odani kupci**.</span><span class="sxs-lookup"><span data-stu-id="949e2-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="objedinite izvore podataka o e-trgovini i vjernosti.":::

1. <span data-ttu-id="949e2-167">Odaberite **ContactId** kao primarni ključ za **eCommerceContacts** i **LoyaltyID** kao primarni ključ za **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="949e2-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Objedinite LoyaltyId kao primarni ključ.":::

### <a name="match"></a><span data-ttu-id="949e2-169">Usklađivanje</span><span class="sxs-lookup"><span data-stu-id="949e2-169">Match</span></span>

1. <span data-ttu-id="949e2-170">Idite na karticu **Usklađivanje** i odaberite **Naruči**.</span><span class="sxs-lookup"><span data-stu-id="949e2-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="949e2-171">Na padajućem popisu **Primarni** odaberite **Kontakti e-trgovine: etrgovina** kao primarni izvor i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="949e2-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="949e2-172">Na padajućem popisu **Entitet 2** odaberite **Odani klijenti: Shema odanosti** i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="949e2-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="objedinite usklađivanje e-trgovine i odanost.":::

1. <span data-ttu-id="949e2-174">Odaberite **Stvaranje novog pravila**</span><span class="sxs-lookup"><span data-stu-id="949e2-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="949e2-175">Dodajte svoj prvi uvjet pomoću programa FullName.</span><span class="sxs-lookup"><span data-stu-id="949e2-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="949e2-176">Za eCommerceContacts u padajućem izborniku odaberite **Puni naziv**.</span><span class="sxs-lookup"><span data-stu-id="949e2-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="949e2-177">Za loyCustomers u padajućem izborniku odaberite **Puni naziv**.</span><span class="sxs-lookup"><span data-stu-id="949e2-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="949e2-178">Odaberite padajući izbornik **Normaliziraj** i odaberite **Vrsta (telefon, ime, adresa, ...)**.</span><span class="sxs-lookup"><span data-stu-id="949e2-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="949e2-179">Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="949e2-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="949e2-180">Unesite naziv **Puno ime, e-pošta** za novo pravilo.</span><span class="sxs-lookup"><span data-stu-id="949e2-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="949e2-181">Odaberite drugi uvjet za adresu e-pošte tako da odaberete **Dodaj uvjet**</span><span class="sxs-lookup"><span data-stu-id="949e2-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="949e2-182">Za entitet eCommerceContacts u padajućem izborniku odaberite **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="949e2-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="949e2-183">Za entitet loyCustomers u padajućem izborniku odaberite **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="949e2-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="949e2-184">Ostavite praznim polje Normaliziraj.</span><span class="sxs-lookup"><span data-stu-id="949e2-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="949e2-185">Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="949e2-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="objedinite pravilo podudaranja za naziv i e-poštu.":::

7. <span data-ttu-id="949e2-187">Odaberite **Spremi** i **Pokreni**.</span><span class="sxs-lookup"><span data-stu-id="949e2-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="949e2-188">Spoji</span><span class="sxs-lookup"><span data-stu-id="949e2-188">Merge</span></span>

1. <span data-ttu-id="949e2-189">Idite na karticu **Spoji**.</span><span class="sxs-lookup"><span data-stu-id="949e2-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="949e2-190">U dijelu **ContactId** za entitet **loyCustomers** promijenite zaslonsko ime u **ContactIdLOYALTY** kako bi se razlikovao od ostalih unesenih identifikacijskih oznaka.</span><span class="sxs-lookup"><span data-stu-id="949e2-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="preimenujte ID kontakta iz oznake ID za vjernost.":::

1. <span data-ttu-id="949e2-192">Odaberi **Spremi** i **Pokreni** da biste započeli postupak spajanja.</span><span class="sxs-lookup"><span data-stu-id="949e2-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="949e2-193">Zadatak 3 - Konfigurirajte predviđanje gubitka pretplate</span><span class="sxs-lookup"><span data-stu-id="949e2-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="949e2-194">S uspostavljenim objedinjenim profilima klijenata, sada možemo pokrenuti predviđanje gubitka pretplate.</span><span class="sxs-lookup"><span data-stu-id="949e2-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="949e2-195">Detaljne korake pogledajte u članku [Predviđanje odbijanja pretplate (pregled)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="949e2-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="949e2-196">Idite na **Obavještavanje** > **Otkrij** i odaberite **Model gubitka klijenta**.</span><span class="sxs-lookup"><span data-stu-id="949e2-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="949e2-197">Odaberite opciju **Pretplata** i odaberite **Započni**.</span><span class="sxs-lookup"><span data-stu-id="949e2-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="949e2-198">Imenujte model **Predviđanje gubitka pretplate OOB** i izlazni entitet **Predviđanje gubitka pretplate OOB**.</span><span class="sxs-lookup"><span data-stu-id="949e2-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="949e2-199">Odredite dva uvjeta za model gubitka:</span><span class="sxs-lookup"><span data-stu-id="949e2-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="949e2-200">**Dana od završetka pretplate**: **najmanje 60** dana.</span><span class="sxs-lookup"><span data-stu-id="949e2-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="949e2-201">Ako klijent ne obnovi svoju pretplatu tijekom ovog razdoblja nakon njezinog isteka, smatra se izgubljenom.</span><span class="sxs-lookup"><span data-stu-id="949e2-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="949e2-202">**Definicija gubitka**: **najmanje 93** dana.</span><span class="sxs-lookup"><span data-stu-id="949e2-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="949e2-203">Trajanje koje model predviđa za odbijanje klijenta.</span><span class="sxs-lookup"><span data-stu-id="949e2-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="949e2-204">Što dalje gledate u budućnost, bit će manja preciznost rezultata.</span><span class="sxs-lookup"><span data-stu-id="949e2-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Odaberite poluge modela Prozor predviđanja i definicija gubitka.":::

1. <span data-ttu-id="949e2-206">Odaberite **Dodajte potrebne podatke** i odaberite **Dodajte podatke** za povijest pretplate.</span><span class="sxs-lookup"><span data-stu-id="949e2-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="949e2-207">Dodajte entitet **Pretplata: SubscriptionHistory** i mapirajte polja iz e-trgovine u odgovarajuća polja koja model zahtijeva.</span><span class="sxs-lookup"><span data-stu-id="949e2-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="949e2-208">Pridružite **Pretplata: SubscriptionHistory** s **eCommerceContacts: eCommerce**, imenujte odnos **Pretplata na e-trgovinu**.</span><span class="sxs-lookup"><span data-stu-id="949e2-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Pridružite entitetima e-trgovine.":::

1. <span data-ttu-id="949e2-210">U odjeljku Aktivnosti klijenta dodajte entitet **webReviews: Web-stranica** i mapirajte polja iz recenzije web-stranice u odgovarajuća polja koja zahtijeva model.</span><span class="sxs-lookup"><span data-stu-id="949e2-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="949e2-211">Primarni ključ: Id pregleda</span><span class="sxs-lookup"><span data-stu-id="949e2-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="949e2-212">Vremenska oznaka: datum pregleda</span><span class="sxs-lookup"><span data-stu-id="949e2-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="949e2-213">Događaj: ocjena pregleda</span><span class="sxs-lookup"><span data-stu-id="949e2-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="949e2-214">Konfigurirajte aktivnost za recenzije web-stranice.</span><span class="sxs-lookup"><span data-stu-id="949e2-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="949e2-215">Odaberite aktivnost **Pregled** i pridružite entitet **webReviews: web-stranica** entitetu **eCommerceContacts: e-trgovina**.</span><span class="sxs-lookup"><span data-stu-id="949e2-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="949e2-216">Odaberite **Sljedeće** za postavljanje rasporeda modela.</span><span class="sxs-lookup"><span data-stu-id="949e2-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="949e2-217">Model je potrebno redovito obučavati da bi naučio nove obrasce kada se unose novi podaci.</span><span class="sxs-lookup"><span data-stu-id="949e2-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="949e2-218">Za ovaj primjer odaberite **Mjesečno**.</span><span class="sxs-lookup"><span data-stu-id="949e2-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="949e2-219">Nakon pregleda svih detalja odaberite **Spremi i pokreni**.</span><span class="sxs-lookup"><span data-stu-id="949e2-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="949e2-220">Zadatak 4 – Pregled rezultata modela i objašnjenja</span><span class="sxs-lookup"><span data-stu-id="949e2-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="949e2-221">Neka model dovrši obuku i bodovanje podataka.</span><span class="sxs-lookup"><span data-stu-id="949e2-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="949e2-222">Sada možete pregledati objašnjenja modela gubitka pretplate.</span><span class="sxs-lookup"><span data-stu-id="949e2-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="949e2-223">Više informacija pogledajte u [Pregledaj stanje i rezultate predviđanje](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="949e2-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="949e2-224">Zadatak 5 – Stvaranje segmenta klijenta s visokim rizikom gubitka</span><span class="sxs-lookup"><span data-stu-id="949e2-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="949e2-225">Pokretanje proizvodnog modela stvara novi entitet u kojem možete vidjeti **Podaci** > **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="949e2-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="949e2-226">Možete stvoriti novi segment na temelju entiteta stvorenog prema modelu.</span><span class="sxs-lookup"><span data-stu-id="949e2-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="949e2-227">Idite na **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="949e2-227">Go to **Segments**.</span></span> <span data-ttu-id="949e2-228">Odaberite **Novo** i odaberite **Stvori iz** > **Obavještavanje**.</span><span class="sxs-lookup"><span data-stu-id="949e2-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Stvaranje segmenta s izlazom modela.":::

1. <span data-ttu-id="949e2-230">Odaberite krajnju točku **Predviđanje gubitka pretplate OOB** i definirajte segment:</span><span class="sxs-lookup"><span data-stu-id="949e2-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="949e2-231">Polje: rezultat odbijanja</span><span class="sxs-lookup"><span data-stu-id="949e2-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="949e2-232">Operator: veće je od</span><span class="sxs-lookup"><span data-stu-id="949e2-232">Operator: greater than</span></span>
   - <span data-ttu-id="949e2-233">Vrijednost: 0,6</span><span class="sxs-lookup"><span data-stu-id="949e2-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Postavite segment gubitka pretplate.":::

<span data-ttu-id="949e2-235">Sada imate segment koji se dinamički ažurira i koji identificira kupce s visokim rizikom za ovu pretplatu.</span><span class="sxs-lookup"><span data-stu-id="949e2-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="949e2-236">Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).</span><span class="sxs-lookup"><span data-stu-id="949e2-236">For more information, see [Create and manage segments](segments.md).</span></span>
