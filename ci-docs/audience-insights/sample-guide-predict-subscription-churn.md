---
title: Vodič uzorka za predviđanje gubitka pretplate
description: Upotrijebite ovaj uzorak vodiča da biste isprobali gotov model predviđanja gubitka pretplate.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: fa460fa5c79bc8a356ec5e90050ec85e05c55be8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306294"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="650b0-103">Vodič uzorka za predviđanje gubitka pretplate (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="650b0-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="650b0-104">Objasnit ćemo vam kroz primjer predviđanje odbijanja pretplate pomoću podataka uzorka navedenih u nastavku.</span><span class="sxs-lookup"><span data-stu-id="650b0-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="650b0-105">Scenarij</span><span class="sxs-lookup"><span data-stu-id="650b0-105">Scenario</span></span>

<span data-ttu-id="650b0-106">Contoso je tvrtka koja proizvodi visokokvalitetnu kavu i aparate za kavu, koje prodaju putem svog web-mjesta Kava Contoso.</span><span class="sxs-lookup"><span data-stu-id="650b0-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="650b0-107">Nedavno su pokrenuli pretplatu za svoje kupce kako bi redovito dobivali kavu.</span><span class="sxs-lookup"><span data-stu-id="650b0-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="650b0-108">Cilj im je razumjeti koji bi pretplaćeni kupci mogli otkazati pretplatu u sljedećih nekoliko mjeseci.</span><span class="sxs-lookup"><span data-stu-id="650b0-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="650b0-109">Znajući tko će od njihovih klijenata **vjerojatno prekinuti**, može im pomoći uštedjeti na marketinškim aktivnostima usredotočujući se na njihovo zadržavanje.</span><span class="sxs-lookup"><span data-stu-id="650b0-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="650b0-110">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="650b0-110">Prerequisites</span></span>

- <span data-ttu-id="650b0-111">Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="650b0-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="650b0-112">Preporučujemo da primijenite sljedeće korake [u novom okruženju](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="650b0-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="650b0-113">Zadatak 1 – Podaci za unos</span><span class="sxs-lookup"><span data-stu-id="650b0-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="650b0-114">Pregledajte članke [o unosu podataka](data-sources.md) i posebice o [uvozu izvora podataka pomoću konektora Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="650b0-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="650b0-115">Sljedeće informacije pretpostavljaju da ste se upoznali s unosom podataka općenito.</span><span class="sxs-lookup"><span data-stu-id="650b0-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="650b0-116">Unesite podatke o klijentima s platforme eCommerce</span><span class="sxs-lookup"><span data-stu-id="650b0-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="650b0-117">Stvorite izvor podataka pod nazivom **E-trgovina**, odaberite opciju uvoza i odaberite poveznik **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="650b0-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="650b0-118">Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="650b0-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="650b0-119">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="650b0-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="650b0-120">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="650b0-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="650b0-121">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="650b0-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="650b0-122">**Datum izrade**: datum/vrijeme/vremenska zona</span><span class="sxs-lookup"><span data-stu-id="650b0-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rođenja u datum.":::

1. <span data-ttu-id="650b0-124">U polju **Naziv** u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="650b0-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="650b0-125">Spremite izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="650b0-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="650b0-126">Unesite podatke o klijentima iz sheme vjernosti</span><span class="sxs-lookup"><span data-stu-id="650b0-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="650b0-127">Stvorite izvor podataka pod nazivom **LoyaltyScheme**, odaberite opciju uvoza i odaberite poveznik **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="650b0-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="650b0-128">Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="650b0-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="650b0-129">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="650b0-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="650b0-130">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="650b0-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="650b0-131">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="650b0-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="650b0-132">**Nagradni bodovi**: cijeli broj</span><span class="sxs-lookup"><span data-stu-id="650b0-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="650b0-133">**Datum stvaranja**: datum/vrijeme</span><span class="sxs-lookup"><span data-stu-id="650b0-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="650b0-134">U polju **Naziv** u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Odanost klijenata**.</span><span class="sxs-lookup"><span data-stu-id="650b0-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="650b0-135">Spremite izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="650b0-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="650b0-136">Informacije o unosu pretplate</span><span class="sxs-lookup"><span data-stu-id="650b0-136">Ingest subscription information</span></span>

1. <span data-ttu-id="650b0-137">Stvorite izvor podataka pod nazivom **Povijest pretplate**, odaberite opciju uvoza i odaberite poveznik **Tekst / CSV**.</span><span class="sxs-lookup"><span data-stu-id="650b0-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="650b0-138">Unesite URL za kontakte e-trgovine https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="650b0-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="650b0-139">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="650b0-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="650b0-140">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="650b0-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="650b0-141">**ID pretplate**: cijeli broj</span><span class="sxs-lookup"><span data-stu-id="650b0-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="650b0-142">**Iznos pretplate**: valuta</span><span class="sxs-lookup"><span data-stu-id="650b0-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="650b0-143">**Datum završetka pretplate**: datum/vrijeme</span><span class="sxs-lookup"><span data-stu-id="650b0-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="650b0-144">**Datum početka pretplate**: datum/vrijeme</span><span class="sxs-lookup"><span data-stu-id="650b0-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="650b0-145">**Datum transakcije**: datum/vrijeme</span><span class="sxs-lookup"><span data-stu-id="650b0-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="650b0-146">**IsRecurring**: točno/netočno</span><span class="sxs-lookup"><span data-stu-id="650b0-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="650b0-147">**Is_auto_renew**: točno/netočno</span><span class="sxs-lookup"><span data-stu-id="650b0-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="650b0-148">**Ponavljajuća frekvencija u mjesecima**: cijeli broj</span><span class="sxs-lookup"><span data-stu-id="650b0-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="650b0-149">U polju **Naziv** u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Povijest pretplate**.</span><span class="sxs-lookup"><span data-stu-id="650b0-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="650b0-150">Spremite izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="650b0-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="650b0-151">Unesite podatke o kupcima iz recenzija web-stranice</span><span class="sxs-lookup"><span data-stu-id="650b0-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="650b0-152">Stvorite izvor podataka pod nazivom **Web-stranica**, odaberite opciju uvoza i odaberite poveznik **Tekst / CSV**.</span><span class="sxs-lookup"><span data-stu-id="650b0-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="650b0-153">Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="650b0-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="650b0-154">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="650b0-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="650b0-155">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="650b0-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="650b0-156">**Ocjena pregleda**: cijeli broj</span><span class="sxs-lookup"><span data-stu-id="650b0-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="650b0-157">**Datum pregleda**: datum</span><span class="sxs-lookup"><span data-stu-id="650b0-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="650b0-158">U polju „Naziv” u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Recenzije web-stranice**.</span><span class="sxs-lookup"><span data-stu-id="650b0-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="650b0-159">Zadatak 2 - Objedinjavanje podataka</span><span class="sxs-lookup"><span data-stu-id="650b0-159">Task 2 - Data unification</span></span>

<span data-ttu-id="650b0-160">Nakon unosa podataka, sada započinjemo postupak **Karta, podudaranje, spajanje** za stvaranje objedinjenog profila kupca.</span><span class="sxs-lookup"><span data-stu-id="650b0-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="650b0-161">Dodatne informacije potražite u odjeljku [Objedinjavanje podataka](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="650b0-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="650b0-162">Mapa</span><span class="sxs-lookup"><span data-stu-id="650b0-162">Map</span></span>

1. <span data-ttu-id="650b0-163">Nakon unosa podataka, mapirajte kontakte iz e-trgovine i podataka o vjernosti u uobičajene vrste podataka.</span><span class="sxs-lookup"><span data-stu-id="650b0-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="650b0-164">Idite na **Podaci** > **Objedini** > **Mapiraj**.</span><span class="sxs-lookup"><span data-stu-id="650b0-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="650b0-165">Odaberite entitete koji predstavljaju profil klijenta – **Kontakti e-trgovine** i **Odani kupci**.</span><span class="sxs-lookup"><span data-stu-id="650b0-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="objedinite izvore podataka o e-trgovini i vjernosti.":::

1. <span data-ttu-id="650b0-167">Odaberite **ContactId** kao primarni ključ za **eCommerceContacts** i **LoyaltyID** kao primarni ključ za **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="650b0-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Objedinite LoyaltyId kao primarni ključ.":::

### <a name="match"></a><span data-ttu-id="650b0-169">Usklađivanje</span><span class="sxs-lookup"><span data-stu-id="650b0-169">Match</span></span>

1. <span data-ttu-id="650b0-170">Idite na karticu **Usklađivanje** i odaberite **Naruči**.</span><span class="sxs-lookup"><span data-stu-id="650b0-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="650b0-171">Na padajućem popisu **Primarni** odaberite **eCommerceContacts: eCommerce** kao primarni izvor i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="650b0-171">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="650b0-172">Na padajućem popisu **Entitet 2** odaberite **loyCustomers: LoyaltyScheme** i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="650b0-172">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="objedinite usklađivanje e-trgovine i odanost.":::

1. <span data-ttu-id="650b0-174">Odaberite **Stvaranje novog pravila**</span><span class="sxs-lookup"><span data-stu-id="650b0-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="650b0-175">Dodajte svoj prvi uvjet pomoću programa FullName.</span><span class="sxs-lookup"><span data-stu-id="650b0-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="650b0-176">Za eCommerceContacts odaberite **FullName** na padajućem popisu.</span><span class="sxs-lookup"><span data-stu-id="650b0-176">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="650b0-177">Za loyCustomers odaberite **FullName** na padajućem popisu.</span><span class="sxs-lookup"><span data-stu-id="650b0-177">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="650b0-178">Odaberite padajući izbornik **Normaliziraj** i odaberite **Vrsta (telefon, ime, adresa, ...)**.</span><span class="sxs-lookup"><span data-stu-id="650b0-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="650b0-179">Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="650b0-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="650b0-180">Unesite naziv **Puno ime, e-pošta** za novo pravilo.</span><span class="sxs-lookup"><span data-stu-id="650b0-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="650b0-181">Odaberite drugi uvjet za adresu e-pošte tako da odaberete **Dodaj uvjet**</span><span class="sxs-lookup"><span data-stu-id="650b0-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="650b0-182">Za entitet eCommerceContacts odaberite **E-pošta** na padajućem popisu.</span><span class="sxs-lookup"><span data-stu-id="650b0-182">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="650b0-183">Za entitet loyCustomers odaberite **E-pošta** na padajućem popisu.</span><span class="sxs-lookup"><span data-stu-id="650b0-183">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="650b0-184">Ostavite praznim polje Normaliziraj.</span><span class="sxs-lookup"><span data-stu-id="650b0-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="650b0-185">Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="650b0-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="objedinite pravilo podudaranja za naziv i e-poštu.":::

7. <span data-ttu-id="650b0-187">Odaberite **Spremi** i **Pokreni**.</span><span class="sxs-lookup"><span data-stu-id="650b0-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="650b0-188">Spoji</span><span class="sxs-lookup"><span data-stu-id="650b0-188">Merge</span></span>

1. <span data-ttu-id="650b0-189">Idite na karticu **Spoji**.</span><span class="sxs-lookup"><span data-stu-id="650b0-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="650b0-190">U dijelu **ContactId** za entitet **loyCustomers** promijenite zaslonsko ime u **ContactIdLOYALTY** kako bi se razlikovao od ostalih unesenih identifikacijskih oznaka.</span><span class="sxs-lookup"><span data-stu-id="650b0-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="preimenujte ID kontakta iz oznake ID za vjernost.":::

1. <span data-ttu-id="650b0-192">Odaberi **Spremi** i **Pokreni** da biste započeli postupak spajanja.</span><span class="sxs-lookup"><span data-stu-id="650b0-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="650b0-193">Zadatak 3 - Konfigurirajte predviđanje gubitka pretplate</span><span class="sxs-lookup"><span data-stu-id="650b0-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="650b0-194">S uspostavljenim objedinjenim profilima klijenata, sada možemo pokrenuti predviđanje gubitka pretplate.</span><span class="sxs-lookup"><span data-stu-id="650b0-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="650b0-195">Detaljne korake pogledajte u članku [Predviđanje odbijanja pretplate (pregled)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="650b0-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="650b0-196">Idite na **Obavještavanje** > **Otkrij** i odaberite **Model gubitka klijenta**.</span><span class="sxs-lookup"><span data-stu-id="650b0-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="650b0-197">Odaberite opciju **Pretplata** i odaberite **Započni**.</span><span class="sxs-lookup"><span data-stu-id="650b0-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="650b0-198">Imenujte model **Predviđanje gubitka pretplate OOB** i izlazni entitet **Predviđanje gubitka pretplate OOB**.</span><span class="sxs-lookup"><span data-stu-id="650b0-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="650b0-199">Odredite dva uvjeta za model gubitka:</span><span class="sxs-lookup"><span data-stu-id="650b0-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="650b0-200">**Dana od završetka pretplate**: **najmanje 60** dana.</span><span class="sxs-lookup"><span data-stu-id="650b0-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="650b0-201">Ako klijent ne obnovi svoju pretplatu tijekom ovog razdoblja nakon njezinog isteka, smatra se izgubljenom.</span><span class="sxs-lookup"><span data-stu-id="650b0-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="650b0-202">**Definicija gubitka**: **najmanje 93** dana.</span><span class="sxs-lookup"><span data-stu-id="650b0-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="650b0-203">Trajanje koje model predviđa za odbijanje klijenta.</span><span class="sxs-lookup"><span data-stu-id="650b0-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="650b0-204">Što dalje gledate u budućnost, bit će manja preciznost rezultata.</span><span class="sxs-lookup"><span data-stu-id="650b0-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Odaberite poluge modela Prozor predviđanja i definicija gubitka.":::

1. <span data-ttu-id="650b0-206">Odaberite **Dodajte potrebne podatke** i odaberite **Dodajte podatke** za povijest pretplate.</span><span class="sxs-lookup"><span data-stu-id="650b0-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="650b0-207">Dodajte entitet **Pretplata: SubscriptionHistory** i mapirajte polja iz e-trgovine u odgovarajuća polja koja model zahtijeva.</span><span class="sxs-lookup"><span data-stu-id="650b0-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="650b0-208">Pridružite **Pretplata: SubscriptionHistory** s **eCommerceContacts: eCommerce**, imenujte odnos **Pretplata na e-trgovinu**.</span><span class="sxs-lookup"><span data-stu-id="650b0-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Pridružite entitetima e-trgovine.":::

1. <span data-ttu-id="650b0-210">U odjeljku Aktivnosti klijenta dodajte entitet **webReviews: Web-stranica** i mapirajte polja iz recenzije web-stranice u odgovarajuća polja koja zahtijeva model.</span><span class="sxs-lookup"><span data-stu-id="650b0-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="650b0-211">Primarni ključ: Id pregleda</span><span class="sxs-lookup"><span data-stu-id="650b0-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="650b0-212">Vremenska oznaka: datum pregleda</span><span class="sxs-lookup"><span data-stu-id="650b0-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="650b0-213">Događaj: ocjena pregleda</span><span class="sxs-lookup"><span data-stu-id="650b0-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="650b0-214">Konfigurirajte aktivnost za recenzije web-stranice.</span><span class="sxs-lookup"><span data-stu-id="650b0-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="650b0-215">Odaberite aktivnost **Pregled** i pridružite entitet **webReviews: web-stranica** entitetu **eCommerceContacts: e-trgovina**.</span><span class="sxs-lookup"><span data-stu-id="650b0-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="650b0-216">Odaberite **Sljedeće** za postavljanje rasporeda modela.</span><span class="sxs-lookup"><span data-stu-id="650b0-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="650b0-217">Model je potrebno redovito obučavati da bi naučio nove obrasce kada se unose novi podaci.</span><span class="sxs-lookup"><span data-stu-id="650b0-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="650b0-218">Za ovaj primjer odaberite **Mjesečno**.</span><span class="sxs-lookup"><span data-stu-id="650b0-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="650b0-219">Nakon pregleda svih detalja odaberite **Spremi i pokreni**.</span><span class="sxs-lookup"><span data-stu-id="650b0-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="650b0-220">Zadatak 4 – Pregled rezultata modela i objašnjenja</span><span class="sxs-lookup"><span data-stu-id="650b0-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="650b0-221">Neka model dovrši obuku i bodovanje podataka.</span><span class="sxs-lookup"><span data-stu-id="650b0-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="650b0-222">Sada možete pregledati objašnjenja modela gubitka pretplate.</span><span class="sxs-lookup"><span data-stu-id="650b0-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="650b0-223">Više informacija pogledajte u [Pregledaj stanje i rezultate predviđanje](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="650b0-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="650b0-224">Zadatak 5 – Stvaranje segmenta klijenta s visokim rizikom gubitka</span><span class="sxs-lookup"><span data-stu-id="650b0-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="650b0-225">Pokretanje proizvodnog modela stvara novi entitet u kojem možete vidjeti **Podaci** > **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="650b0-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="650b0-226">Možete stvoriti novi segment na temelju entiteta stvorenog prema modelu.</span><span class="sxs-lookup"><span data-stu-id="650b0-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="650b0-227">Idite na **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="650b0-227">Go to **Segments**.</span></span> <span data-ttu-id="650b0-228">Odaberite **Novo** i odaberite **Stvori iz** > **Obavještavanje**.</span><span class="sxs-lookup"><span data-stu-id="650b0-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Stvaranje segmenta s izlazom modela.":::

1. <span data-ttu-id="650b0-230">Odaberite krajnju točku **Predviđanje gubitka pretplate OOB** i definirajte segment:</span><span class="sxs-lookup"><span data-stu-id="650b0-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="650b0-231">Polje: rezultat odbijanja</span><span class="sxs-lookup"><span data-stu-id="650b0-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="650b0-232">Operator: veće je od</span><span class="sxs-lookup"><span data-stu-id="650b0-232">Operator: greater than</span></span>
   - <span data-ttu-id="650b0-233">Vrijednost: 0,6</span><span class="sxs-lookup"><span data-stu-id="650b0-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Postavite segment gubitka pretplate.":::

<span data-ttu-id="650b0-235">Sada imate segment koji se dinamički ažurira i koji identificira kupce s visokim rizikom za ovu pretplatu.</span><span class="sxs-lookup"><span data-stu-id="650b0-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="650b0-236">Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).</span><span class="sxs-lookup"><span data-stu-id="650b0-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]