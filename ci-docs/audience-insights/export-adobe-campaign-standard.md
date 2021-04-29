---
title: Izvoz podataka servisa Customer Insights u Adobe Campaign Standard
description: Saznajte kako koristiti segmente uvida u ciljnu skupinu u servisu Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760272"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="2469b-103">Korištenje segmenata servisa Customer Insights u servisu Adobe Campaign Standard (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="2469b-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="2469b-104">Možda ste kao korisnik uvida u ciljnu skupinu za Dynamics 365 Customer Insights stvorili segmente kako biste svoje marketinške kampanje učinili učinkovitijim ciljanjem relevantnih ciljnih skupina.</span><span class="sxs-lookup"><span data-stu-id="2469b-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="2469b-105">Da biste koristili segment iz uvida u ciljnu skupinu u servisu Adobe Experience Platform i aplikacijama kao što je Adobe Campaign Standard, morate slijediti nekoliko koraka navedenih u ovom članku.</span><span class="sxs-lookup"><span data-stu-id="2469b-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a><span data-ttu-id="2469b-107">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="2469b-107">Prerequisites</span></span>

-   <span data-ttu-id="2469b-108">Licenca sustava Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="2469b-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="2469b-109">Licenca za Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="2469b-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="2469b-110">Račun za Azure spremište blobova</span><span class="sxs-lookup"><span data-stu-id="2469b-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="2469b-111">Pregled kampanje</span><span class="sxs-lookup"><span data-stu-id="2469b-111">Campaign Overview</span></span>

<span data-ttu-id="2469b-112">Da biste bolje razumjeli kako možete koristiti segmente iz uvida u ciljnu skupinu u servisu Adobe Experience Platform, pogledajmo fiktivni primjer kampanje.</span><span class="sxs-lookup"><span data-stu-id="2469b-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="2469b-113">Pretpostavimo da vaša tvrtka nudi mjesečnu uslugu zasnovanu na pretplati vašim klijentima u Sjedinjenim Državama.</span><span class="sxs-lookup"><span data-stu-id="2469b-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="2469b-114">Želite identificirati klijente čije pretplate trebaju biti obnovljene u sljedećih osam dana, ali koji još nisu obnovili pretplatu.</span><span class="sxs-lookup"><span data-stu-id="2469b-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="2469b-115">Da biste zadržali te klijente, želite im poslati promotivnu ponudu putem e-pošte koristeći Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="2469b-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="2469b-116">U ovom primjeru želimo jednom provesti promotivnu kampanju putem e-pošte.</span><span class="sxs-lookup"><span data-stu-id="2469b-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="2469b-117">Ovaj članak ne pokriva slučaj upotrebe za provođenje kampanje više puta.</span><span class="sxs-lookup"><span data-stu-id="2469b-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="2469b-118">Međutim, uvidi u ciljnu skupinu i Adobe Campaign Standard mogu se konfigurirati i za rad s ponovljenim scenarijem kampanje.</span><span class="sxs-lookup"><span data-stu-id="2469b-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="2469b-119">Identificiranje ciljne skupine</span><span class="sxs-lookup"><span data-stu-id="2469b-119">Identify your target audience</span></span>

<span data-ttu-id="2469b-120">U našem scenariju pretpostavljamo da su adrese e-pošte klijenata dostupne u uvidima u ciljnu skupinu i analizirane su njihove promotivne preferencije kako bi se identificirali članovi segmenta.</span><span class="sxs-lookup"><span data-stu-id="2469b-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="2469b-121">[Segment koji ste definirali u uvidima u ciljnu skupinu](segments.md) se zove **ChurnProneCustomers** i tim klijentima planirate poslati promotivnu e-poštu.</span><span class="sxs-lookup"><span data-stu-id="2469b-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimka zaslona sa stranicom segmenata sa stvorenim segmentom ChurnProneCustomers.":::

<span data-ttu-id="2469b-123">E-pošta s ponudom koju želite poslati sadržavat će ime, prezime i datum završetka pretplate klijenta.</span><span class="sxs-lookup"><span data-stu-id="2469b-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="2469b-124">Ona obavještava klijente o popustu koji će dobiti ako obnove pretplatu prije nego što završi.</span><span class="sxs-lookup"><span data-stu-id="2469b-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="2469b-125">Izvoz ciljne skupine</span><span class="sxs-lookup"><span data-stu-id="2469b-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="2469b-126">Konfiguracija veze</span><span class="sxs-lookup"><span data-stu-id="2469b-126">Configure a connection</span></span>

<span data-ttu-id="2469b-127">Nakon što identificiramo našu ciljnu skupinu, možemo konfigurirati izvoz iz uvida u ciljnu skupinu na račun za Azure spremište blobova.</span><span class="sxs-lookup"><span data-stu-id="2469b-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="2469b-128">U uvidima u ciljnu skupinu idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="2469b-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2469b-129">Odaberite **Dodaj vezu** i odaberite **Adobe Campaign** za konfiguriranje veze ili odaberite **Postavi** na pločici **Adobe Campaign**</span><span class="sxs-lookup"><span data-stu-id="2469b-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Pločica za konfiguraciju za Adobe Campaign Standard.":::

1. <span data-ttu-id="2469b-131">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="2469b-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2469b-132">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="2469b-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2469b-133">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="2469b-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2469b-134">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="2469b-134">Choose who can use this connection.</span></span> <span data-ttu-id="2469b-135">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="2469b-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2469b-136">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2469b-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2469b-137">Unesite **Naziv računa**, **Ključ računa** i **Spremnik** računa spremnika za pohranu bloba za Azure na koji želite izvesti segment.</span><span class="sxs-lookup"><span data-stu-id="2469b-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimka zaslona konfiguracije računa za pohranu. "::: 

   - <span data-ttu-id="2469b-139">Da biste saznali više o pronalaženju imena i ključa računa spremišta blobova platforme Azure, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="2469b-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="2469b-140">Pogledajte kako stvoriti spremnik [Stvaranje spremnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="2469b-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="2469b-141">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="2469b-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="2469b-142">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="2469b-142">Configure an export</span></span>

<span data-ttu-id="2469b-143">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="2469b-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2469b-144">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2469b-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2469b-145">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="2469b-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2469b-146">Da biste stvorili novi izvoz, ddaberite **Dodaj izvoz**.</span><span class="sxs-lookup"><span data-stu-id="2469b-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="2469b-147">U polju **Veza za izvoz** odaberite vezu iz odjeljka Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="2469b-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="2469b-148">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="2469b-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2469b-149">Odaberite segment koji želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="2469b-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="2469b-150">U ovom primjeru je to **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="2469b-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimka zaslona korisničkog sučelja za odabir segmenta s odabranim segmentom ChurnProneCustomers.":::

1. <span data-ttu-id="2469b-152">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="2469b-152">Select **Next**.</span></span>

1. <span data-ttu-id="2469b-153">Sada mapiramo polja **Izvor** od segmenta uvida u ciljnu skupinu do naziva polja **Cilj** u shemi profila servisa Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="2469b-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapiranje polja za poveznik Adobe Campaign Standard.":::

   <span data-ttu-id="2469b-155">Ako želite dodati još atributa, odaberite **Dodaj atribut**.</span><span class="sxs-lookup"><span data-stu-id="2469b-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="2469b-156">Naziv cilja može se razlikovati od naziva izvornog polja, tako da i dalje možete mapirati izlaz segmenta iz uvida u ciljnu skupinu u Adobe Campaign Standard ako polja nemaju isti naziv u dva sustava.</span><span class="sxs-lookup"><span data-stu-id="2469b-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2469b-157">Adresa e-pošte koristi se kao polje identiteta, ali možete upotrijebiti bilo koji drugi identifikator iz vašeg profila klijenta uvida u ciljnu skupinu za mapiranje podataka u Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="2469b-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="2469b-158">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="2469b-158">Select **Save**.</span></span>

<span data-ttu-id="2469b-159">Nakon spremanja izvoznog odredišta pronaći ćete ga na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="2469b-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="2469b-160">Sada možete [izvesti segment na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2469b-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="2469b-161">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md).</span><span class="sxs-lookup"><span data-stu-id="2469b-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2469b-162">Provjerite je li broj zapisa u izvezenom segmentu unutar dopuštenog ograničenja vaše licence za Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="2469b-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="2469b-163">Izvezeni podaci pohranjeni su u spremniku Azure spremište blobova koji ste ranije konfigurirali.</span><span class="sxs-lookup"><span data-stu-id="2469b-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="2469b-164">Sljedeća putanja mape stvara se automatski u vašem spremniku:</span><span class="sxs-lookup"><span data-stu-id="2469b-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="2469b-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="2469b-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="2469b-166">Primjer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="2469b-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="2469b-167">Konfiguracija servisa Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="2469b-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="2469b-168">Kada se segment izveze iz uvida u ciljnu skupinu, on sadrži stupce koje ste odabrali prilikom definiranja odredišta izvoza u prethodnom koraku.</span><span class="sxs-lookup"><span data-stu-id="2469b-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="2469b-169">Ti se podaci mogu koristiti za [stvaranje profila u servisu Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="2469b-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="2469b-170">Da bismo koristili segment u servisu Adobe Campaign Standard, moramo proširiti shemu profila u servisu Adobe Campaign Standard tako da uključuje dva dodatna polja.</span><span class="sxs-lookup"><span data-stu-id="2469b-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="2469b-171">Saznajte kako [proširiti resurs profila](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) s novim poljima u servisu Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="2469b-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="2469b-172">U našem primjeru ta su polja *Naziv segmenta i Datum segmenta (neobavezno).*</span><span class="sxs-lookup"><span data-stu-id="2469b-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="2469b-173">Pomoću ovih polja identificirat ćemo profile u servisu Adobe Campaign Standard koje želimo ciljati za ovu kampanju.</span><span class="sxs-lookup"><span data-stu-id="2469b-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="2469b-174">Ako u servisu Adobe Campaign Standard ne postoje drugi zapisi, osim onoga što ćete uvoziti, možete preskočiti ovaj korak.</span><span class="sxs-lookup"><span data-stu-id="2469b-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="2469b-175">Uvoz podataka u Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="2469b-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="2469b-176">Sad kad je sve na svom mjestu, trebamo uvesti pripremljene podatke o ciljnim skupinama iz uvida u ciljnu skupinu u Adobe Campaign Standard radi stvaranja profila.</span><span class="sxs-lookup"><span data-stu-id="2469b-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="2469b-177">Saznajte [kako uvesti profile u Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) koristeći tijek rada.</span><span class="sxs-lookup"><span data-stu-id="2469b-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="2469b-178">Tijek rada uvoza na slici ispod konfiguriran je za pokretanje svakih 8 sati i traži izvezene segmente uvida u ciljnu skupinu (.csv datoteka u Azure spremištu blobova).</span><span class="sxs-lookup"><span data-stu-id="2469b-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="2469b-179">Tijek rada izdvaja sadržaj .csv datoteke u navedenom redoslijedu stupaca.</span><span class="sxs-lookup"><span data-stu-id="2469b-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="2469b-180">Ovaj je tijek rada napravljen za izvođenje osnovne obrade pogreški i osigurava da svaki zapis ima adresu e-pošte prije popunjavanja podacima u servisu Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="2469b-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="2469b-181">Tijek rada također izdvaja naziv segmenta iz naziva datoteke prije dodavanja u podatke ACS profila.</span><span class="sxs-lookup"><span data-stu-id="2469b-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Snimka zaslona tijeka rada uvoza u korisničkom sučelju servisa Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="2469b-183">Dohvaćanje ciljne skupine u servisu Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="2469b-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="2469b-184">Nakon što se podaci uvezu u Adobe Campaign Standard, [možete stvoriti tijek rada](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [upitati](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) klijente na temelju polja *Naziv segmenta* i *Datum segmenta* da odaberu profile koji su identificirani za našu oglednu kampanju.</span><span class="sxs-lookup"><span data-stu-id="2469b-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="2469b-185">Stvaranje i slanje e-pošte pomoću servisa Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="2469b-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="2469b-186">Stvorite sadržaj e-pošte, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoju poruku e-pošte.</span><span class="sxs-lookup"><span data-stu-id="2469b-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ogledna poruka e-pošte s ponudom za obnovu iz servisa Adobe Campaign Standard.":::
