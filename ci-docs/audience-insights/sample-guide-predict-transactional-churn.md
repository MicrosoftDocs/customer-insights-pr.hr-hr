---
title: Vodič uzorka za predviđanje transakcijskog gubitka
description: Upotrijebite ovaj uzorak vodiča da biste isprobali gotov model predviđanja transakcijskog gubitka,
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 251bc26246cee16952e8e4cb08e2ed7aa4d18488
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595417"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="86302-103">Vodič uzorka za predviđanje transakcijskog gubitka (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="86302-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="86302-104">Ovaj će vam vodič objasniti kroz primjer predviđanje transakcijskog gubitka u usluzi Customer Insights s pomoću podataka uzorka navedenih u nastavku.</span><span class="sxs-lookup"><span data-stu-id="86302-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="86302-105">Svi podaci koji se koriste u ovom vodiču nisu stvarni podaci o klijentu i dio su skupa podataka Contoso koji se nalazi u okruženju *Demo* unutar pretplate na Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="86302-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="86302-106">Scenarij</span><span class="sxs-lookup"><span data-stu-id="86302-106">Scenario</span></span>

<span data-ttu-id="86302-107">Contoso je tvrtka koja proizvodi visokokvalitetnu kavu i aparate za kavu koje prodaju putem svoje web-stranice Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="86302-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="86302-108">Cilj im je znati koji će klijenti koji obično redovito kupuju njihove proizvode prestati biti aktivni kupci u sljedećih 60 dana.</span><span class="sxs-lookup"><span data-stu-id="86302-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="86302-109">Znajući tko će od njihovih klijenata **vjerojatno prekinuti**, može im pomoći uštedjeti na marketinškim aktivnostima usredotočujući se na njihovo zadržavanje.</span><span class="sxs-lookup"><span data-stu-id="86302-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="86302-110">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="86302-110">Prerequisites</span></span>

- <span data-ttu-id="86302-111">Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="86302-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="86302-112">Preporučujemo da primijenite sljedeće korake [u novom okruženju](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="86302-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="86302-113">Zadatak 1 – Podaci za unos</span><span class="sxs-lookup"><span data-stu-id="86302-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="86302-114">Pregledajte članke [o unosu podataka](data-sources.md) i posebice o [uvozu izvora podataka pomoću konektora Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="86302-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="86302-115">Sljedeće informacije pretpostavljaju da ste se upoznali s unosom podataka općenito.</span><span class="sxs-lookup"><span data-stu-id="86302-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="86302-116">Unesite podatke o klijentima s platforme eCommerce</span><span class="sxs-lookup"><span data-stu-id="86302-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="86302-117">Stvorite izvor podataka pod nazivom **E-trgovina**, odaberite opciju uvoza i odaberite poveznik **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="86302-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="86302-118">Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="86302-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="86302-119">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="86302-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="86302-120">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="86302-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="86302-121">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="86302-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="86302-122">**Datum izrade**: datum/vrijeme/vremenska zona</span><span class="sxs-lookup"><span data-stu-id="86302-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="86302-123">![Promijenite DoB u Datum](media/ecommerce-dob-date.PNG "pretvori datum rođenja u datum")</span><span class="sxs-lookup"><span data-stu-id="86302-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="86302-124">U polju **Naziv** u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="86302-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="86302-125">Spremite izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="86302-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="86302-126">Unesite podatke o internetskoj kupnji</span><span class="sxs-lookup"><span data-stu-id="86302-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="86302-127">Dodajte još jedan skup podataka na isti izvor podataka **E-trgovina**.</span><span class="sxs-lookup"><span data-stu-id="86302-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="86302-128">Ponovno odaberite konektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="86302-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="86302-129">Unesite URL za podatke za **Internetske kupnje** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="86302-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="86302-130">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="86302-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="86302-131">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="86302-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="86302-132">**PurchasedOn**: datum/vrijeme</span><span class="sxs-lookup"><span data-stu-id="86302-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="86302-133">**Ukupna cijena**: valuta</span><span class="sxs-lookup"><span data-stu-id="86302-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="86302-134">U polju **Naziv** u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="86302-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="86302-135">Spremite izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="86302-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="86302-136">Unesite podatke o klijentima iz sheme vjernosti</span><span class="sxs-lookup"><span data-stu-id="86302-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="86302-137">Stvorite izvor podataka pod nazivom **LoyaltyScheme**, odaberite opciju uvoza i odaberite poveznik **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="86302-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="86302-138">Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="86302-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="86302-139">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="86302-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="86302-140">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="86302-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="86302-141">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="86302-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="86302-142">**Nagradni bodovi**: cijeli broj</span><span class="sxs-lookup"><span data-stu-id="86302-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="86302-143">**Datum stvaranja**: datum/vrijeme</span><span class="sxs-lookup"><span data-stu-id="86302-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="86302-144">U polju **Naziv** u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Odanost klijenata**.</span><span class="sxs-lookup"><span data-stu-id="86302-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="86302-145">Spremite izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="86302-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="86302-146">Zadatak 2 - Objedinjavanje podataka</span><span class="sxs-lookup"><span data-stu-id="86302-146">Task 2 - Data unification</span></span>

<span data-ttu-id="86302-147">Nakon unosa podataka, sada započinjemo postupak **Karta, podudaranje, spajanje** za stvaranje objedinjenog profila kupca.</span><span class="sxs-lookup"><span data-stu-id="86302-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="86302-148">Dodatne informacije potražite u odjeljku [Objedinjavanje podataka](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="86302-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="86302-149">Mapa</span><span class="sxs-lookup"><span data-stu-id="86302-149">Map</span></span>

1. <span data-ttu-id="86302-150">Nakon unosa podataka, mapirajte kontakte iz e-trgovine i podataka o vjernosti u uobičajene vrste podataka.</span><span class="sxs-lookup"><span data-stu-id="86302-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="86302-151">Idite na **Podaci** > **Objedini** > **Mapiraj**.</span><span class="sxs-lookup"><span data-stu-id="86302-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="86302-152">Odaberite entitete koji predstavljaju profil klijenta – **Kontakti e-trgovine** i **Odani kupci**.</span><span class="sxs-lookup"><span data-stu-id="86302-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="objedinite izvore podataka o e-trgovini i vjernosti.":::

1. <span data-ttu-id="86302-154">Odaberite **ContactId** kao primarni ključ za **eCommerceContacts** i **LoyaltyID** kao primarni ključ za **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="86302-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Objedinite LoyaltyId kao primarni ključ.":::

### <a name="match"></a><span data-ttu-id="86302-156">Usklađivanje</span><span class="sxs-lookup"><span data-stu-id="86302-156">Match</span></span>

1. <span data-ttu-id="86302-157">Idite na karticu **Usklađivanje** i odaberite **Naruči**.</span><span class="sxs-lookup"><span data-stu-id="86302-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="86302-158">Na padajućem popisu **Primarni** odaberite **Kontakti e-trgovine: etrgovina** kao primarni izvor i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="86302-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="86302-159">Na padajućem popisu **Entitet 2** odaberite **Odani klijenti: Shema odanosti** i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="86302-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="objedinite usklađivanje e-trgovine i odanost.":::

1. <span data-ttu-id="86302-161">Odaberite **Stvaranje novog pravila**</span><span class="sxs-lookup"><span data-stu-id="86302-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="86302-162">Dodajte svoj prvi uvjet pomoću programa FullName.</span><span class="sxs-lookup"><span data-stu-id="86302-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="86302-163">Za eCommerceContacts u padajućem izborniku odaberite **Puni naziv**.</span><span class="sxs-lookup"><span data-stu-id="86302-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="86302-164">Za loyCustomers u padajućem izborniku odaberite **Puni naziv**.</span><span class="sxs-lookup"><span data-stu-id="86302-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="86302-165">Odaberite padajući izbornik **Normaliziraj** i odaberite **Vrsta (telefon, ime, adresa, ...)**.</span><span class="sxs-lookup"><span data-stu-id="86302-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="86302-166">Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="86302-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="86302-167">Unesite naziv **Puno ime, e-pošta** za novo pravilo.</span><span class="sxs-lookup"><span data-stu-id="86302-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="86302-168">Odaberite drugi uvjet za adresu e-pošte tako da odaberete **Dodaj uvjet**</span><span class="sxs-lookup"><span data-stu-id="86302-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="86302-169">Za entitet eCommerceContacts u padajućem izborniku odaberite **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="86302-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="86302-170">Za entitet loyCustomers u padajućem izborniku odaberite **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="86302-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="86302-171">Ostavite praznim polje Normaliziraj.</span><span class="sxs-lookup"><span data-stu-id="86302-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="86302-172">Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="86302-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="objedinite pravilo podudaranja za naziv i e-poštu.":::

7. <span data-ttu-id="86302-174">Odaberite **Spremi** i **Pokreni**.</span><span class="sxs-lookup"><span data-stu-id="86302-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="86302-175">Spoji</span><span class="sxs-lookup"><span data-stu-id="86302-175">Merge</span></span>

1. <span data-ttu-id="86302-176">Idite na karticu **Spoji**.</span><span class="sxs-lookup"><span data-stu-id="86302-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="86302-177">U dijelu **ContactId** za entitet **loyCustomers** promijenite zaslonsko ime u **ContactIdLOYALTY** kako bi se razlikovao od ostalih unesenih identifikacijskih oznaka.</span><span class="sxs-lookup"><span data-stu-id="86302-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="preimenujte ID kontakta iz oznake ID za vjernost.":::

1. <span data-ttu-id="86302-179">Odaberi **Spremi** i **Pokreni** da biste započeli postupak spajanja.</span><span class="sxs-lookup"><span data-stu-id="86302-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="86302-180">Zadatak 3 - Konfigurirajte predviđanje transakcijskog gubitka</span><span class="sxs-lookup"><span data-stu-id="86302-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="86302-181">S uspostavljenim objedinjenim profilima klijenata, sada možemo pokrenuti predviđanje gubitka pretplate.</span><span class="sxs-lookup"><span data-stu-id="86302-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="86302-182">Detaljne korake pogledajte u članku [Predviđanje odbijanja pretplate (pregled)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="86302-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="86302-183">Idite na **Obavještavanje** > **Otkrij** i odaberite **Model gubitka klijenta**.</span><span class="sxs-lookup"><span data-stu-id="86302-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="86302-184">Odaberite opciju **Transakcijski** i odaberite **Započni**.</span><span class="sxs-lookup"><span data-stu-id="86302-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="86302-185">Imenujte model **Predviđanje transakcijskog gubitka OOB e-trgovine** i izlazni entitet **Predviđanje gubitka OOB e-trgovine**.</span><span class="sxs-lookup"><span data-stu-id="86302-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="86302-186">Odredite dva uvjeta za model gubitka:</span><span class="sxs-lookup"><span data-stu-id="86302-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="86302-187">**Prozor predviđanja**: **najmanje 60** dana.</span><span class="sxs-lookup"><span data-stu-id="86302-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="86302-188">Ova postavka definira za koje razdoblje u budućnosti želimo predvidjeti gubitak klijenta.</span><span class="sxs-lookup"><span data-stu-id="86302-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="86302-189">**Definicija gubitka**: **najmanje 60** dana.</span><span class="sxs-lookup"><span data-stu-id="86302-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="86302-190">Trajanje bez kupnje nakon kojeg se kupac smatra odbačenim.</span><span class="sxs-lookup"><span data-stu-id="86302-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Odaberite poluge modela Prozor predviđanja i definicija gubitka.":::

1. <span data-ttu-id="86302-192">Odaberite **Povijest kupnje (obavezno)** i odaberite **Dodaj podatke** za povijest kupnje.</span><span class="sxs-lookup"><span data-stu-id="86302-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="86302-193">Dodajte entitet **Kupovine e-trgovine: e-trgovina** i mapirajte polja iz e-trgovine u odgovarajuća polja koja model zahtijeva.</span><span class="sxs-lookup"><span data-stu-id="86302-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="86302-194">Pridružite entitet **Kupovine e-trgovine: e-trgovina** entitetu **Kontakti e-trgovine: e-trgovina**.</span><span class="sxs-lookup"><span data-stu-id="86302-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pridružite entitetima e-trgovine.":::

1. <span data-ttu-id="86302-196">Odaberite **Sljedeće** za postavljanje rasporeda modela.</span><span class="sxs-lookup"><span data-stu-id="86302-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="86302-197">Model je potrebno redovito obučavati da bi naučio nove obrasce kada se unose novi podaci.</span><span class="sxs-lookup"><span data-stu-id="86302-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="86302-198">Za ovaj primjer odaberite **Mjesečno**.</span><span class="sxs-lookup"><span data-stu-id="86302-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="86302-199">Nakon pregleda svih detalja odaberite **Spremi i pokreni**.</span><span class="sxs-lookup"><span data-stu-id="86302-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="86302-200">Zadatak 4 – Pregled rezultata modela i objašnjenja</span><span class="sxs-lookup"><span data-stu-id="86302-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="86302-201">Neka model dovrši obuku i bodovanje podataka.</span><span class="sxs-lookup"><span data-stu-id="86302-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="86302-202">Sada možete pregledati objašnjenja modela gubitka pretplate.</span><span class="sxs-lookup"><span data-stu-id="86302-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="86302-203">Više informacija pogledajte u [Pregledaj stanje i rezultate predviđanje](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="86302-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="86302-204">Zadatak 5 – Stvaranje segmenta klijenta s visokim rizikom gubitka</span><span class="sxs-lookup"><span data-stu-id="86302-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="86302-205">Pokretanje proizvodnog modela stvara novi entitet u kojem možete vidjeti **Podaci** > **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="86302-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="86302-206">Možete stvoriti novi segment na temelju entiteta stvorenog prema modelu.</span><span class="sxs-lookup"><span data-stu-id="86302-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="86302-207">Idite na **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="86302-207">Go to **Segments**.</span></span> <span data-ttu-id="86302-208">Odaberite **Novo** i odaberite **Stvori iz** > **Obavještavanje**.</span><span class="sxs-lookup"><span data-stu-id="86302-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Stvaranje segmenta s izlazom modela.":::

1. <span data-ttu-id="86302-210">Odaberite krajnju točku **Predviđanje gubitka pretplate OOB** i definirajte segment:</span><span class="sxs-lookup"><span data-stu-id="86302-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="86302-211">Polje: rezultat odbijanja</span><span class="sxs-lookup"><span data-stu-id="86302-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="86302-212">Operator: veće je od</span><span class="sxs-lookup"><span data-stu-id="86302-212">Operator: greater than</span></span>
   - <span data-ttu-id="86302-213">Vrijednost: 0,6</span><span class="sxs-lookup"><span data-stu-id="86302-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Postavite segment gubitka pretplate.":::

<span data-ttu-id="86302-215">Sada imate segment koji se dinamički ažurira i koji identificira kupce s visokim rizikom za ovu pretplatu.</span><span class="sxs-lookup"><span data-stu-id="86302-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="86302-216">Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).</span><span class="sxs-lookup"><span data-stu-id="86302-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]