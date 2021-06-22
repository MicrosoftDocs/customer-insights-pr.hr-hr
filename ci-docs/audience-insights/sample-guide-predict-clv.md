---
title: Uzorak vodiča za predviđanje cjeloživotne vrijednosti klijenta
description: Koristite ovaj uzorak vodiča da biste isprobali model predviđanja cjeloživotne vrijednosti klijenta.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129936"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="85773-103">Uzorak vodiča za predviđanje cjeloživotne vrijednosti klijenta (CLV)</span><span class="sxs-lookup"><span data-stu-id="85773-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="85773-104">Ovaj vodič će vam detaljno objasniti primjer predviđanja cjeloživotne vrijednosti klijenta (CLV) u rješenju Customer Insights koristeći uzorke podataka.</span><span class="sxs-lookup"><span data-stu-id="85773-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="85773-105">Scenarij</span><span class="sxs-lookup"><span data-stu-id="85773-105">Scenario</span></span>

<span data-ttu-id="85773-106">Contoso je tvrtka koja proizvodi visokokvalitetnu kavu i aparate za kavu.</span><span class="sxs-lookup"><span data-stu-id="85773-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="85773-107">Proizvode prodaju putem svog web-mjesta Kava Contoso.</span><span class="sxs-lookup"><span data-stu-id="85773-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="85773-108">Tvrtka želi razumjeti vrijednost (prihod) koju njihovi klijenti mogu stvoriti u sljedećih 12 mjeseci.</span><span class="sxs-lookup"><span data-stu-id="85773-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="85773-109">Poznavanje očekivane vrijednosti njihovih klijenata u sljedećih 12 mjeseci pomoći će im da usmjere svoje marketinške napore na visokovrijedne klijente.</span><span class="sxs-lookup"><span data-stu-id="85773-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85773-110">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="85773-110">Prerequisites</span></span>

- <span data-ttu-id="85773-111">Barem [dozvole suradnika](permissions.md) u uvidima u ciljne skupine.</span><span class="sxs-lookup"><span data-stu-id="85773-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="85773-112">Preporučujemo da primijenite sljedeće korake [u novom okruženju](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="85773-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="85773-113">Zadatak 1 – Podaci za unos</span><span class="sxs-lookup"><span data-stu-id="85773-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="85773-114">Pregledajte članke [o unosu podataka](data-sources.md) i [uvozu izvora podataka pomoću poveznika Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="85773-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="85773-115">Sljedeće informacije pretpostavljaju da ste se upoznali s unosom podataka općenito.</span><span class="sxs-lookup"><span data-stu-id="85773-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="85773-116">Unesite podatke o klijentima s platforme eCommerce</span><span class="sxs-lookup"><span data-stu-id="85773-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="85773-117">Stvorite izvor podataka pod nazivom **E-trgovina**, odaberite mogućnost uvoza i odaberite poveznik **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="85773-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="85773-118">Unesite URL za kontakte e-trgovine [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="85773-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="85773-119">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog retka kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="85773-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="85773-120">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="85773-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="85773-121">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="85773-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="85773-122">**Datum izrade**: datum/vrijeme/vremenska zona</span><span class="sxs-lookup"><span data-stu-id="85773-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rođenja u datum.":::

1. <span data-ttu-id="85773-124">U polju „Naziv” u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Kontakti e-trgovine**</span><span class="sxs-lookup"><span data-stu-id="85773-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="85773-125">**Spremi** izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="85773-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="85773-126">Unesite podatke o internetskoj kupnji</span><span class="sxs-lookup"><span data-stu-id="85773-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="85773-127">Dodajte još jedan skup podataka na isti izvor podataka **E-trgovina**.</span><span class="sxs-lookup"><span data-stu-id="85773-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="85773-128">Ponovno odaberite konektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="85773-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="85773-129">Unesite URL za podatke za **Internetske kupnje** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="85773-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="85773-130">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="85773-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="85773-131">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="85773-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="85773-132">**PurchasedOn**: datum/vrijeme</span><span class="sxs-lookup"><span data-stu-id="85773-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="85773-133">**Ukupna cijena**: valuta</span><span class="sxs-lookup"><span data-stu-id="85773-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="85773-134">U polju **Naziv** u bočnom oknu preimenujte svoj izvor podataka iz **Upit** u **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="85773-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="85773-135">**Spremi** izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="85773-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="85773-136">Unesite podatke o klijentima iz sheme vjernosti</span><span class="sxs-lookup"><span data-stu-id="85773-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="85773-137">Stvorite izvor podataka pod nazivom **LoyaltyScheme**, odaberite opciju uvoza i odaberite poveznik **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="85773-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="85773-138">Unesite URL za kontakte e-trgovine https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="85773-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="85773-139">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="85773-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="85773-140">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="85773-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="85773-141">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="85773-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="85773-142">**Nagradni bodovi**: cijeli broj</span><span class="sxs-lookup"><span data-stu-id="85773-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="85773-143">**Datum stvaranja**: datum/vrijeme</span><span class="sxs-lookup"><span data-stu-id="85773-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="85773-144">U polju **Naziv** u desnom oknu preimenujte svoj izvor podataka iz **Upit** u **Odanost klijenata**.</span><span class="sxs-lookup"><span data-stu-id="85773-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="85773-145">**Spremi** izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="85773-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="85773-146">Unesite podatke o kupcima iz recenzija web-stranice</span><span class="sxs-lookup"><span data-stu-id="85773-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="85773-147">Stvorite izvor podataka pod nazivom **Web-stranica**, odaberite opciju uvoza i odaberite poveznik **Tekst / CSV**.</span><span class="sxs-lookup"><span data-stu-id="85773-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="85773-148">Unesite URL za kontakte e-trgovine https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="85773-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="85773-149">Tijekom uređivanja podataka odaberite **Transformiranje** i zatim **Upotreba prvog reda kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="85773-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="85773-150">Ažurirajte vrstu podataka za stupce navedene u nastavku:</span><span class="sxs-lookup"><span data-stu-id="85773-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="85773-151">**ReviewRating**: decimalni broj</span><span class="sxs-lookup"><span data-stu-id="85773-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="85773-152">**Datum pregleda**: datum</span><span class="sxs-lookup"><span data-stu-id="85773-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="85773-153">U polju "Naziv", u desnom oknu, preimenujte svoj izvor podataka sa **Upit** na **Pregledi**.</span><span class="sxs-lookup"><span data-stu-id="85773-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="85773-154">**Spremi** izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="85773-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="85773-155">Zadatak 2 - Objedinjavanje podataka</span><span class="sxs-lookup"><span data-stu-id="85773-155">Task 2 - Data unification</span></span>

<span data-ttu-id="85773-156">Nakon unosa podataka, započinjemo postupak objedinjavanja podataka kako bismo stvorili objedinjeni profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="85773-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="85773-157">Dodatne informacije potražite u odjeljku [Objedinjavanje podataka](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="85773-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="85773-158">Mapa</span><span class="sxs-lookup"><span data-stu-id="85773-158">Map</span></span>

1. <span data-ttu-id="85773-159">Nakon unosa podataka, mapirajte kontakte iz e-trgovine i podataka o vjernosti u uobičajene vrste podataka.</span><span class="sxs-lookup"><span data-stu-id="85773-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="85773-160">Idite na **Podaci** > **Objedini** > **Mapiraj**.</span><span class="sxs-lookup"><span data-stu-id="85773-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="85773-161">Odaberite entitete koji predstavljaju profil klijenta – **Kontakti e-trgovine** i **Odani kupci**.</span><span class="sxs-lookup"><span data-stu-id="85773-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="85773-162">Zatim odaberite **Primijeni**.</span><span class="sxs-lookup"><span data-stu-id="85773-162">Then, select **Apply**.</span></span>

   ![objedinite izvore podataka o e-trgovini i vjernosti.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="85773-164">Odaberite **ContactId** kao primarni ključ za **eCommerceContacts** i **LoyaltyID** kao primarni ključ za **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="85773-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Objedinite LoyaltyId kao primarni ključ.](media/unify-loyaltyid.png)

1. <span data-ttu-id="85773-166">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="85773-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="85773-167">Usklađivanje</span><span class="sxs-lookup"><span data-stu-id="85773-167">Match</span></span>

1. <span data-ttu-id="85773-168">Idite na karticu **Usklađivanje** i odaberite **Naruči**.</span><span class="sxs-lookup"><span data-stu-id="85773-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="85773-169">Na padajućem popisu **Primarni** odaberite **Kontakti e-trgovine: etrgovina** kao primarni izvor i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="85773-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="85773-170">Na padajućem popisu **Entitet 2** odaberite **Odani klijenti: Shema odanosti** i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="85773-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![objedinite usklađivanje e-trgovine i odanost.](media/unify-match-order.png)

1. <span data-ttu-id="85773-172">Odaberite **Dodavanje pravila**</span><span class="sxs-lookup"><span data-stu-id="85773-172">Select **Add rule**</span></span>

1. <span data-ttu-id="85773-173">Dodajte svoj prvi uvjet pomoću programa FullName.</span><span class="sxs-lookup"><span data-stu-id="85773-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="85773-174">Za eCommerceContacts u padajućem izborniku odaberite **Puni naziv**.</span><span class="sxs-lookup"><span data-stu-id="85773-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="85773-175">Za loyCustomers u padajućem izborniku odaberite **Puni naziv**.</span><span class="sxs-lookup"><span data-stu-id="85773-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="85773-176">Odaberite padajući izbornik **Normaliziraj** i odaberite **Vrsta (telefon, ime, adresa, ...)**.</span><span class="sxs-lookup"><span data-stu-id="85773-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="85773-177">Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="85773-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="85773-178">Unesite naziv **Puno ime, e-pošta** za novo pravilo.</span><span class="sxs-lookup"><span data-stu-id="85773-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="85773-179">Odaberite drugi uvjet za adresu e-pošte tako da odaberete **Dodaj uvjet**</span><span class="sxs-lookup"><span data-stu-id="85773-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="85773-180">Za entitet eCommerceContacts u padajućem izborniku odaberite **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="85773-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="85773-181">Za entitet loyCustomers u padajućem izborniku odaberite **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="85773-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="85773-182">Ostavite praznim polje Normaliziraj.</span><span class="sxs-lookup"><span data-stu-id="85773-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="85773-183">Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="85773-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![objedinite pravilo podudaranja za naziv i e-poštu.](media/unify-match-rule.png)

1. <span data-ttu-id="85773-185">Odaberite **Gotovo**.</span><span class="sxs-lookup"><span data-stu-id="85773-185">Select **Done**.</span></span>

1. <span data-ttu-id="85773-186">Odaberite **Spremi** i **Pokreni**.</span><span class="sxs-lookup"><span data-stu-id="85773-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="85773-187">Spoji</span><span class="sxs-lookup"><span data-stu-id="85773-187">Merge</span></span>

1. <span data-ttu-id="85773-188">Idite na karticu **Spoji**.</span><span class="sxs-lookup"><span data-stu-id="85773-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="85773-189">U dijelu **ContactId** za entitet **loyCustomers** promijenite zaslonsko ime u **ContactIdLOYALTY** kako bi se razlikovao od ostalih unesenih identifikacijskih oznaka.</span><span class="sxs-lookup"><span data-stu-id="85773-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![preimenujte ID kontakta iz oznake ID za vjernost.](media/unify-merge-contactid.png)

1. <span data-ttu-id="85773-191">Odaberite **Spremi** i **Pokreni spajanje i nizvodne procese**.</span><span class="sxs-lookup"><span data-stu-id="85773-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="85773-192">Zadatak 3 - Konfiguracija predviđanja cjeloživotne vrijednosti klijenta</span><span class="sxs-lookup"><span data-stu-id="85773-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="85773-193">S postavljenim objedinjenim profilima klijenata, sada možemo pokrenuti predviđanje cjeloživotne vrijednosti klijenta.</span><span class="sxs-lookup"><span data-stu-id="85773-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="85773-194">Detaljne korake potražite u odjeljku [Predviđanje cjeloživotne vrijednosti klijenta (pretpregled)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="85773-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="85773-195">Idite u odjeljak **Inteligencija**  > **Predviđanja** i odaberite **Model cjeloživotne vrijednosti klijenta**.</span><span class="sxs-lookup"><span data-stu-id="85773-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="85773-196">Pregledajte informacije u bočnom oknu i odaberite **Početak**.</span><span class="sxs-lookup"><span data-stu-id="85773-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="85773-197">Dajte modelu naziv **CLV predviđanje e-trgovine OOB-a**, a izlaznom entitetu **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="85773-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="85773-198">Definirajte preferencije modela za CLV model:</span><span class="sxs-lookup"><span data-stu-id="85773-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="85773-199">**Vremensko razdoblje predviđanja**: **12 mjeseci ili 1 godina**.</span><span class="sxs-lookup"><span data-stu-id="85773-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="85773-200">Ova postavka definira koliko daleko u budućnosti treba predvidjeti cjeloživotnu vrijednost klijenta.</span><span class="sxs-lookup"><span data-stu-id="85773-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="85773-201">**Aktivni klijenti**: Navedite što aktivni klijenti znače za vaše poslovanje.</span><span class="sxs-lookup"><span data-stu-id="85773-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="85773-202">Postavite povijesni vremenski okvir u kojem je klijent morao imati barem jednu transakciju da bi se smatrao aktivnim.</span><span class="sxs-lookup"><span data-stu-id="85773-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="85773-203">Model će predvidjeti CLV samo za aktivne klijente.</span><span class="sxs-lookup"><span data-stu-id="85773-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="85773-204">Odaberite između dopuštanja modelu da izračuna vremensko razdoblje na temelju povijesnih podataka o transakciji ili navedite određeni vremenski okvir.</span><span class="sxs-lookup"><span data-stu-id="85773-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="85773-205">U ovom uzorku vodiča mi **dopuštamo modelu da izračuna interval kupnje**, što je zadana mogućnost.</span><span class="sxs-lookup"><span data-stu-id="85773-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="85773-206">**Visokovrijedni klijenti**: Visokovrijedne klijente definirajte kao percentil klijenata koji najviše plaćaju.</span><span class="sxs-lookup"><span data-stu-id="85773-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="85773-207">Model ovaj unos koristi za pružanje rezultata koji odgovaraju vašoj poslovnoj definiciji visokovrijednih klijenata.</span><span class="sxs-lookup"><span data-stu-id="85773-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="85773-208">Možete odabrati da dopustite modelu da definira visokovrijedne klijente.</span><span class="sxs-lookup"><span data-stu-id="85773-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="85773-209">On koristi heurističko pravilo koje izvodi percentil.</span><span class="sxs-lookup"><span data-stu-id="85773-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="85773-210">Visokovrijedne klijente možete definirati i kao percentil klijenata koji će najviše plaćati u budućnosti.</span><span class="sxs-lookup"><span data-stu-id="85773-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="85773-211">U ovom uzorku vodiča ćemo ručno definirati visokovrijedne klijente kao **30% najaktivnih klijenata koji najviše plaćaju** i odabrati **Sljedeće**.</span><span class="sxs-lookup"><span data-stu-id="85773-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Korak preferencija u vođenom iskustvu za CLV model.":::

1. <span data-ttu-id="85773-213">U koraku **Potrebni podaci** odaberite **Dodaj podatke** za pružanje podataka o povijesti transakcija.</span><span class="sxs-lookup"><span data-stu-id="85773-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="85773-214">Dodajte entitet **eCommercePurchases : eCommerce** i preslikajte atribute koji su potrebni modelu:</span><span class="sxs-lookup"><span data-stu-id="85773-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="85773-215">ID transakcije: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="85773-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="85773-216">Datum transakcije: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="85773-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="85773-217">Iznos transakcije: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="85773-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="85773-218">ID proizvoda: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="85773-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="85773-219">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="85773-219">Select **Next**.</span></span>

1. <span data-ttu-id="85773-220">Postavite odnos između entiteta **eCommercePurchases : eCommerce** i **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="85773-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="85773-221">Korak **Dodatni podaci (neobavezno)** vam omogućuje dodavanje više podataka o aktivnostima klijenata.</span><span class="sxs-lookup"><span data-stu-id="85773-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="85773-222">Ovi podaci mogu vam pomoći da dobijete više uvida o interakciji klijenata s vašom tvrtkom, što može pridonijeti CLV-u.</span><span class="sxs-lookup"><span data-stu-id="85773-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="85773-223">Dodavanje ključnih interakcija s klijentima, poput web-zapisnika, zapisnika službe za korisnike ili povijesti programa nagrađivanja, može poboljšati točnost predviđanja.</span><span class="sxs-lookup"><span data-stu-id="85773-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="85773-224">Odaberite **Dodaj podatke** za uključivanje više podataka o aktivnostima klijenata.</span><span class="sxs-lookup"><span data-stu-id="85773-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="85773-225">Dodajte entitet aktivnosti klijenta i preslikajte nazive njegovih polja u odgovarajuća polja koja zahtijeva model:</span><span class="sxs-lookup"><span data-stu-id="85773-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="85773-226">Entitet aktivnosti klijenta: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="85773-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="85773-227">Primarni ključ: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="85773-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="85773-228">Vremenska oznaka: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="85773-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="85773-229">Događaj (naziv aktivnosti): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="85773-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="85773-230">Pojedinosti (iznos ili vrijednost): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="85773-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="85773-231">Odaberite **Sljedeće** i konfigurirajte aktivnost i odnos između podataka o transakciji i podataka o klijentu:</span><span class="sxs-lookup"><span data-stu-id="85773-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="85773-232">Vrsta aktivnosti: odaberite postojeće</span><span class="sxs-lookup"><span data-stu-id="85773-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="85773-233">Oznaka aktivnosti: recenzija</span><span class="sxs-lookup"><span data-stu-id="85773-233">Activity label: Review</span></span>
   - <span data-ttu-id="85773-234">Odgovarajuća oznaka: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="85773-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="85773-235">Entitet klijenta: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="85773-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="85773-236">Odnos: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="85773-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="85773-237">Odaberite **Sljedeće** za postavljanje rasporeda modela.</span><span class="sxs-lookup"><span data-stu-id="85773-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="85773-238">Model treba redovito obučavati kako bi naučio nove obrasce kada se unose novi podaci.</span><span class="sxs-lookup"><span data-stu-id="85773-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="85773-239">Za ovaj primjer odaberite **Mjesečno**.</span><span class="sxs-lookup"><span data-stu-id="85773-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="85773-240">Nakon pregleda svih pojedinosti odaberite **Spremi i pokreni**.</span><span class="sxs-lookup"><span data-stu-id="85773-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="85773-241">Zadatak 4 – Pregled rezultata modela i objašnjenja</span><span class="sxs-lookup"><span data-stu-id="85773-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="85773-242">Neka model dovrši obuku i bodovanje podataka.</span><span class="sxs-lookup"><span data-stu-id="85773-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="85773-243">Zatim možete pregledati rezultate i objašnjenja CLV modela.</span><span class="sxs-lookup"><span data-stu-id="85773-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="85773-244">Više informacija pogledajte u [Pregledaj stanje i rezultate predviđanje](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="85773-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="85773-245">Zadatak 5 - Stvaranje segmenta visokovrijednih klijenata</span><span class="sxs-lookup"><span data-stu-id="85773-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="85773-246">Pokretanje modela stvara novi entitet koji je naveden u odjeljku **Podaci** > **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="85773-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="85773-247">Novi segment klijenta možete stvoriti na temelju entiteta koji je stvorio model.</span><span class="sxs-lookup"><span data-stu-id="85773-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="85773-248">Idite na **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="85773-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="85773-249">Odaberite **Novo** i odaberite **Stvori iz** > **Obavještavanje**.</span><span class="sxs-lookup"><span data-stu-id="85773-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Stvaranje segmenta s izlazom modela.](media/segment-intelligence.png)

1. <span data-ttu-id="85773-251">Odaberite entitet **OOBeCommerceCLVPrediction** i definirajte segment:</span><span class="sxs-lookup"><span data-stu-id="85773-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="85773-252">Polje: CLVScore</span><span class="sxs-lookup"><span data-stu-id="85773-252">Field: CLVScore</span></span>
  - <span data-ttu-id="85773-253">Operator: veće je od</span><span class="sxs-lookup"><span data-stu-id="85773-253">Operator: greater than</span></span>
  - <span data-ttu-id="85773-254">Vrijednost: 1500</span><span class="sxs-lookup"><span data-stu-id="85773-254">Value: 1500</span></span>

1. <span data-ttu-id="85773-255">Odaberite **Recenzija** i **Spremite** segment.</span><span class="sxs-lookup"><span data-stu-id="85773-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="85773-256">Sada imate segment koji identificira klijente za koje se predviđa da će u sljedećih 12 mjeseci donijeti više od $1500 prihoda.</span><span class="sxs-lookup"><span data-stu-id="85773-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="85773-257">Ovaj se segment dinamički ažurira ako se unese više podataka.</span><span class="sxs-lookup"><span data-stu-id="85773-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="85773-258">Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).</span><span class="sxs-lookup"><span data-stu-id="85773-258">For more information, see [Create and manage segments](segments.md).</span></span>
