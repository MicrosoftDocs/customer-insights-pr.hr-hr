---
title: Uzorak vodiča za predviđanje preporuka proizvoda
description: Koristite ovaj uzorak vodiča da biste isprobali gotove model predviđanja preporuka proizvoda.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595264"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="54f8a-103">Uzorak vodiča za predviđanje preporuka proizvoda (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="54f8a-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="54f8a-104">Preko primjera ćemo vas provesti kroz predviđanje preporuka proizvoda pomoću uzorka podataka navedenih u nastavku.</span><span class="sxs-lookup"><span data-stu-id="54f8a-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="54f8a-105">Scenarij</span><span class="sxs-lookup"><span data-stu-id="54f8a-105">Scenario</span></span>

<span data-ttu-id="54f8a-106">Contoso je tvrtka koja proizvodi visokokvalitetnu kavu i aparate za kavu koje prodaju putem svoje web-stranice Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="54f8a-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="54f8a-107">Cilj im je razumjeti koje proizvode trebaju preporučiti svojim redovnim klijentima.</span><span class="sxs-lookup"><span data-stu-id="54f8a-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="54f8a-108">Znanje o tome što će klijenti **vjerojatnije kupiti** može im pomoći sačuvati marketinške napore usredotočujući se na određene stavke.</span><span class="sxs-lookup"><span data-stu-id="54f8a-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="54f8a-109">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="54f8a-109">Prerequisites</span></span>

- <span data-ttu-id="54f8a-110">Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="54f8a-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="54f8a-111">Preporučujemo da primijenite sljedeće korake [u novom okruženju](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="54f8a-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="54f8a-112">Zadatak 1 – Podaci za unos</span><span class="sxs-lookup"><span data-stu-id="54f8a-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="54f8a-113">Pregledajte članke [o unosu podataka](data-sources.md) i posebice o [uvozu izvora podataka pomoću konektora Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="54f8a-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="54f8a-114">Sljedeće informacije pretpostavljaju da ste se upoznali s unosom podataka općenito.</span><span class="sxs-lookup"><span data-stu-id="54f8a-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="54f8a-115">Unesite podatke o klijentima s platforme eCommerce</span><span class="sxs-lookup"><span data-stu-id="54f8a-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="54f8a-116">Stvorite izvor podataka pod nazivom **E-trgovina**, odaberite opciju uvoza i odaberite poveznik **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="54f8a-117">Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="54f8a-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="54f8a-118">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="54f8a-119">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="54f8a-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="54f8a-120">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="54f8a-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="54f8a-121">**Datum izrade**: datum/vrijeme/vremenska zona</span><span class="sxs-lookup"><span data-stu-id="54f8a-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rođenja u datum.":::

5. <span data-ttu-id="54f8a-123">U polju „Naziv” u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Kontakti e-trgovine**</span><span class="sxs-lookup"><span data-stu-id="54f8a-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="54f8a-124">**Spremi** izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="54f8a-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="54f8a-125">Unesite podatke o internetskoj kupnji</span><span class="sxs-lookup"><span data-stu-id="54f8a-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="54f8a-126">Dodajte još jedan skup podataka na isti izvor podataka **E-trgovina**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="54f8a-127">Ponovno odaberite konektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="54f8a-128">Unesite URL za podatke za **Internetske kupnje** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="54f8a-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="54f8a-129">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="54f8a-130">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="54f8a-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="54f8a-131">**PurchasedOn**: datum/vrijeme</span><span class="sxs-lookup"><span data-stu-id="54f8a-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="54f8a-132">**Ukupna cijena**: valuta</span><span class="sxs-lookup"><span data-stu-id="54f8a-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="54f8a-133">U polju **Naziv** u bočnom oknu preimenujte svoj izvor podataka iz **Upit** u **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="54f8a-134">Spremite izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="54f8a-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="54f8a-135">Unesite podatke o klijentima iz sheme vjernosti</span><span class="sxs-lookup"><span data-stu-id="54f8a-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="54f8a-136">Stvorite izvor podataka pod nazivom **LoyaltyScheme**, odaberite opciju uvoza i odaberite poveznik **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="54f8a-137">Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="54f8a-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="54f8a-138">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="54f8a-139">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="54f8a-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="54f8a-140">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="54f8a-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="54f8a-141">**Nagradni bodovi**: cijeli broj</span><span class="sxs-lookup"><span data-stu-id="54f8a-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="54f8a-142">**Datum stvaranja**: datum/vrijeme</span><span class="sxs-lookup"><span data-stu-id="54f8a-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="54f8a-143">U polju **Naziv** u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Odanost klijenata**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="54f8a-144">Spremite izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="54f8a-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="54f8a-145">Zadatak 2 - Objedinjavanje podataka</span><span class="sxs-lookup"><span data-stu-id="54f8a-145">Task 2 - Data unification</span></span>

<span data-ttu-id="54f8a-146">Nakon unosa podataka, sada započinjemo postupak **Karta, podudaranje, spajanje** za stvaranje objedinjenog profila kupca.</span><span class="sxs-lookup"><span data-stu-id="54f8a-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="54f8a-147">Dodatne informacije potražite u odjeljku [Objedinjavanje podataka](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="54f8a-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="54f8a-148">Mapa</span><span class="sxs-lookup"><span data-stu-id="54f8a-148">Map</span></span>

1. <span data-ttu-id="54f8a-149">Nakon unosa podataka, mapirajte kontakte iz e-trgovine i podataka o vjernosti u uobičajene vrste podataka.</span><span class="sxs-lookup"><span data-stu-id="54f8a-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="54f8a-150">Idite na **Podaci** > **Objedini** > **Mapiraj**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="54f8a-151">Odaberite entitete koji predstavljaju profil klijenta – **Kontakti e-trgovine** i **Odani kupci**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![objedinite izvore podataka o e-trgovini i vjernosti.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="54f8a-153">Odaberite **ContactId** kao primarni ključ za **eCommerceContacts** i **LoyaltyID** kao primarni ključ za **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Objedinite LoyaltyId kao primarni ključ.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="54f8a-155">Usklađivanje</span><span class="sxs-lookup"><span data-stu-id="54f8a-155">Match</span></span>

1. <span data-ttu-id="54f8a-156">Idite na karticu **Usklađivanje** i odaberite **Naruči**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="54f8a-157">Na padajućem popisu **Primarni** odaberite **Kontakti e-trgovine: etrgovina** kao primarni izvor i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="54f8a-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="54f8a-158">Na padajućem popisu **Entitet 2** odaberite **Odani klijenti: Shema odanosti** i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="54f8a-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![objedinite usklađivanje e-trgovine i odanost.](media/unify-match-order.png)

4. <span data-ttu-id="54f8a-160">Odaberite **Stvaranje novog pravila**</span><span class="sxs-lookup"><span data-stu-id="54f8a-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="54f8a-161">Dodajte svoj prvi uvjet pomoću programa FullName.</span><span class="sxs-lookup"><span data-stu-id="54f8a-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="54f8a-162">Za eCommerceContacts u padajućem izborniku odaberite **Puni naziv**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="54f8a-163">Za loyCustomers u padajućem izborniku odaberite **Puni naziv**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="54f8a-164">Odaberite padajući izbornik **Normaliziraj** i odaberite **Vrsta (telefon, ime, adresa, ...)**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="54f8a-165">Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="54f8a-166">Unesite naziv **Puno ime, e-pošta** za novo pravilo.</span><span class="sxs-lookup"><span data-stu-id="54f8a-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="54f8a-167">Odaberite drugi uvjet za adresu e-pošte tako da odaberete **Dodaj uvjet**</span><span class="sxs-lookup"><span data-stu-id="54f8a-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="54f8a-168">Za entitet eCommerceContacts u padajućem izborniku odaberite **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="54f8a-169">Za entitet loyCustomers u padajućem izborniku odaberite **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="54f8a-170">Ostavite praznim polje Normaliziraj.</span><span class="sxs-lookup"><span data-stu-id="54f8a-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="54f8a-171">Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![objedinite pravilo podudaranja za naziv i e-poštu.](media/unify-match-rule.png)

7. <span data-ttu-id="54f8a-173">Odaberite **Spremi** i **Pokreni**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="54f8a-174">Spoji</span><span class="sxs-lookup"><span data-stu-id="54f8a-174">Merge</span></span>

1. <span data-ttu-id="54f8a-175">Idite na karticu **Spoji**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="54f8a-176">U dijelu **ContactId** za entitet **loyCustomers** promijenite zaslonsko ime u **ContactIdLOYALTY** kako bi se razlikovao od ostalih unesenih identifikacijskih oznaka.</span><span class="sxs-lookup"><span data-stu-id="54f8a-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![preimenujte ID kontakta iz oznake ID za vjernost.](media/unify-merge-contactid.png)

1. <span data-ttu-id="54f8a-178">Odaberi **Spremi** i **Pokreni** da biste započeli postupak spajanja.</span><span class="sxs-lookup"><span data-stu-id="54f8a-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="54f8a-179">Zadatak 3 - Konfiguracija predviđanja preporuka proizvoda</span><span class="sxs-lookup"><span data-stu-id="54f8a-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="54f8a-180">S uspostavljenim objedinjenim profilima klijenata, sada možemo pokrenuti predviđanje gubitka pretplate.</span><span class="sxs-lookup"><span data-stu-id="54f8a-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="54f8a-181">Idite na **Inteligencija** > **Predviđanje** i odaberite **Preporuka proizvoda**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="54f8a-182">Odaberite **Početak rada**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-182">Select **Get started**.</span></span>

1. <span data-ttu-id="54f8a-183">Nazovite model **Previđanje modela preporuka proizvoda za OOB**, a izlazni entitet **Predviđanje modela preporuka proizvoda za OOB**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="54f8a-184">Definirajte tri uvjeta za model:</span><span class="sxs-lookup"><span data-stu-id="54f8a-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="54f8a-185">**Broj proizvoda**: Postavite ovu vrijednost na **5**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="54f8a-186">Ova postavka definira koliko proizvoda želite preporučiti svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="54f8a-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="54f8a-187">**Predložiti proizvode koje su klijenti nedavno kupili?**: Odaberite **Da** da biste naznačili da u preporuku želite uključiti proizvode koje su vaši klijenti ranije kupili.</span><span class="sxs-lookup"><span data-stu-id="54f8a-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="54f8a-188">**Pogled unatrag:** Odaberite barem **365 dana**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="54f8a-189">Ova postavka definira koliko će unatrag model pregledavati aktivnosti klijenata da bi to iskoristio kao ulazne vrijednosti za preporuke.</span><span class="sxs-lookup"><span data-stu-id="54f8a-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preference modela za model preporuke proizvoda.":::

1. <span data-ttu-id="54f8a-191">Odaberite **Potrebni podaci** i odaberite **Dodaj podatke** za povijest kupnje.</span><span class="sxs-lookup"><span data-stu-id="54f8a-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="54f8a-192">Dodajte entitet **Kupovine e-trgovine: e-trgovina** i mapirajte polja iz e-trgovine u odgovarajuća polja koja model zahtijeva.</span><span class="sxs-lookup"><span data-stu-id="54f8a-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="54f8a-193">Pridružite entitet **Kupovine e-trgovine: e-trgovina** entitetu **Kontakti e-trgovine: e-trgovina**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Pridružite entitetima e-trgovine.](media/model-purchase-join.png)

1. <span data-ttu-id="54f8a-195">Odaberite **Sljedeće** za postavljanje rasporeda modela.</span><span class="sxs-lookup"><span data-stu-id="54f8a-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="54f8a-196">Model je potrebno redovito obučavati da bi naučio nove obrasce kada se unose novi podaci.</span><span class="sxs-lookup"><span data-stu-id="54f8a-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="54f8a-197">Za ovaj primjer odaberite **Mjesečno**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="54f8a-198">Nakon pregleda svih detalja odaberite **Spremi i pokreni**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="54f8a-199">Zadatak 4 – Pregled rezultata modela i objašnjenja</span><span class="sxs-lookup"><span data-stu-id="54f8a-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="54f8a-200">Neka model dovrši obuku i bodovanje podataka.</span><span class="sxs-lookup"><span data-stu-id="54f8a-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="54f8a-201">Sada možete pregledati objašnjenja modela preporuka proizvoda.</span><span class="sxs-lookup"><span data-stu-id="54f8a-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="54f8a-202">Više informacija pogledajte u [Pregledaj stanje i rezultate predviđanje](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="54f8a-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="54f8a-203">Zadatak 5 - Stvaranje segmenta najčešće kupljenih proizvoda</span><span class="sxs-lookup"><span data-stu-id="54f8a-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="54f8a-204">Pokretanje proizvodnog modela stvara novi entitet u kojem možete vidjeti **Podaci** > **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="54f8a-205">Možete stvoriti novi segment na temelju entiteta stvorenog prema modelu.</span><span class="sxs-lookup"><span data-stu-id="54f8a-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="54f8a-206">Idite na **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-206">Go to **Segments**.</span></span> <span data-ttu-id="54f8a-207">Odaberite **Novo** i odaberite **Stvori iz** > **Obavještavanje**.</span><span class="sxs-lookup"><span data-stu-id="54f8a-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Stvaranje segmenta s izlazom modela.](media/segment-intelligence.png)

1. <span data-ttu-id="54f8a-209">Odaberite krajnju točku **OOBProductRecommendationModelPrediction** i definirajte segment:</span><span class="sxs-lookup"><span data-stu-id="54f8a-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="54f8a-210">Polje: ProductID</span><span class="sxs-lookup"><span data-stu-id="54f8a-210">Field: ProductID</span></span>
   - <span data-ttu-id="54f8a-211">Operator: Vrijednost</span><span class="sxs-lookup"><span data-stu-id="54f8a-211">Operator: Value</span></span>
   - <span data-ttu-id="54f8a-212">Vrijednost: Odaberite prva tri ID-ja proizvoda</span><span class="sxs-lookup"><span data-stu-id="54f8a-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Stvorite segment iz rezultata modela.":::

<span data-ttu-id="54f8a-214">Sada imate segment koji se dinamički ažurira, a koji identificira klijente koji su spremniji kupiti tri najčešće preporučena proizvoda</span><span class="sxs-lookup"><span data-stu-id="54f8a-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="54f8a-215">Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).</span><span class="sxs-lookup"><span data-stu-id="54f8a-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]