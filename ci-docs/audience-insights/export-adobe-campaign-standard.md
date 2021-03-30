---
title: Izvoz podataka servisa Customer Insights u Adobe Campaign Standard
description: Saznajte kako koristiti segmente uvida u ciljnu skupinu u servisu Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596306"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="7d3c7-103">Korištenje segmenata servisa Customer Insights u servisu Adobe Campaign Standard (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="7d3c7-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="7d3c7-104">Možda ste kao korisnik uvida u ciljnu skupinu za Dynamics 365 Customer Insights stvorili segmente kako biste svoje marketinške kampanje učinili učinkovitijim ciljanjem relevantnih ciljnih skupina.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="7d3c7-105">Da biste koristili segment iz uvida u ciljnu skupinu u servisu Adobe Experience Platform i aplikacijama kao što je Adobe Campaign Standard, morate slijediti nekoliko koraka navedenih u ovom članku.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a><span data-ttu-id="7d3c7-107">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="7d3c7-107">Prerequisites</span></span>

-   <span data-ttu-id="7d3c7-108">Licenca sustava Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="7d3c7-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="7d3c7-109">Licenca za Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="7d3c7-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="7d3c7-110">Račun za Azure spremište blobova</span><span class="sxs-lookup"><span data-stu-id="7d3c7-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="7d3c7-111">Pregled kampanje</span><span class="sxs-lookup"><span data-stu-id="7d3c7-111">Campaign Overview</span></span>

<span data-ttu-id="7d3c7-112">Da biste bolje razumjeli kako možete koristiti segmente iz uvida u ciljnu skupinu u servisu Adobe Experience Platform, pogledajmo fiktivni primjer kampanje.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="7d3c7-113">Pretpostavimo da vaša tvrtka nudi mjesečnu uslugu zasnovanu na pretplati vašim klijentima u Sjedinjenim Državama.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="7d3c7-114">Želite identificirati klijente čije pretplate trebaju biti obnovljene u sljedećih osam dana, ali koji još nisu obnovili pretplatu.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="7d3c7-115">Da biste zadržali te klijente, želite im poslati promotivnu ponudu putem e-pošte koristeći Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="7d3c7-116">U ovom primjeru želimo jednom provesti promotivnu kampanju putem e-pošte.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="7d3c7-117">Ovaj članak ne pokriva slučaj upotrebe za provođenje kampanje više puta.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="7d3c7-118">Međutim, uvidi u ciljnu skupinu i Adobe Campaign Standard mogu se konfigurirati i za rad s ponovljenim scenarijem kampanje.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="7d3c7-119">Identificiranje ciljne skupine</span><span class="sxs-lookup"><span data-stu-id="7d3c7-119">Identify your target audience</span></span>

<span data-ttu-id="7d3c7-120">U našem scenariju pretpostavljamo da su adrese e-pošte klijenata dostupne u uvidima u ciljnu skupinu i analizirane su njihove promotivne preferencije kako bi se identificirali članovi segmenta.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="7d3c7-121">[Segment koji ste definirali u uvidima u ciljnu skupinu](segments.md) se zove **ChurnProneCustomers** i tim klijentima planirate poslati promotivnu e-poštu.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimka zaslona sa stranicom segmenata sa stvorenim segmentom ChurnProneCustomers.":::

<span data-ttu-id="7d3c7-123">E-pošta s ponudom koju želite poslati sadržavat će ime, prezime i datum završetka pretplate klijenta.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="7d3c7-124">Ona obavještava klijente o popustu koji će dobiti ako obnove pretplatu prije nego što završi.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="7d3c7-125">Izvoz ciljne skupine</span><span class="sxs-lookup"><span data-stu-id="7d3c7-125">Export your target audience</span></span>

<span data-ttu-id="7d3c7-126">Nakon što identificiramo našu ciljnu skupinu, možemo konfigurirati izvoz iz uvida u ciljnu skupinu na račun za Azure spremište blobova.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="7d3c7-127">U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7d3c7-128">Na pločici **Adobe Campaign** odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Pločica za konfiguraciju za Adobe Campaign Standard.":::

1. <span data-ttu-id="7d3c7-130">Navedite **zaslonski naziv** za ovo novo odredište izvoza, a zatim unesite **Naziv računa**, **Ključ računa** i **Spremnik** računa za Azure spremište blobova na koji želite izvesti segment.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimka zaslona konfiguracije računa za pohranu. "::: 

   - <span data-ttu-id="7d3c7-132">Da biste saznali više o pronalaženju imena i ključa računa spremišta blobova platforme Azure, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="7d3c7-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="7d3c7-133">Pogledajte kako stvoriti spremnik [Stvaranje spremnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="7d3c7-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="7d3c7-134">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-134">Select **Next**.</span></span>

1. <span data-ttu-id="7d3c7-135">Odaberite segment koji želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="7d3c7-136">U ovom primjeru je to **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimka zaslona korisničkog sučelja za odabir segmenta s odabranim segmentom ChurnProneCustomers.":::

1. <span data-ttu-id="7d3c7-138">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-138">Select **Next**.</span></span>

1. <span data-ttu-id="7d3c7-139">Sada mapiramo polja **Izvor** od segmenta uvida u ciljnu skupinu do naziva polja **Cilj** u shemi profila servisa Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapiranje polja za poveznik Adobe Campaign Standard.":::

   <span data-ttu-id="7d3c7-141">Ako želite dodati još atributa, odaberite **Dodaj atribut**.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="7d3c7-142">Naziv cilja može se razlikovati od naziva izvornog polja, tako da i dalje možete mapirati izlaz segmenta iz uvida u ciljnu skupinu u Adobe Campaign Standard ako polja nemaju isti naziv u dva sustava.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7d3c7-143">Adresa e-pošte koristi se kao polje identiteta, ali možete upotrijebiti bilo koji drugi identifikator iz vašeg profila klijenta uvida u ciljnu skupinu za mapiranje podataka u Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="7d3c7-144">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-144">Select **Save**.</span></span>

<span data-ttu-id="7d3c7-145">Nakon spremanja odredišta izvoza, pronaći ćete ga u odjeljku **Administrator** > **Izvozi** > **Moja odredišta izvoza**.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Snimka zaslona s istaknutim popisom izvoza i uzorkom segmenta.":::

<span data-ttu-id="7d3c7-147">Sada možete [izvesti segment na zahtjev](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7d3c7-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="7d3c7-148">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md).</span><span class="sxs-lookup"><span data-stu-id="7d3c7-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7d3c7-149">Provjerite je li broj zapisa u izvezenom segmentu unutar dopuštenog ograničenja vaše licence za Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="7d3c7-150">Izvezeni podaci pohranjeni su u spremniku Azure spremište blobova koji ste ranije konfigurirali.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="7d3c7-151">Sljedeća putanja mape stvara se automatski u vašem spremniku:</span><span class="sxs-lookup"><span data-stu-id="7d3c7-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="7d3c7-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="7d3c7-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="7d3c7-153">Primjer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="7d3c7-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="7d3c7-154">Konfiguracija servisa Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="7d3c7-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="7d3c7-155">Kada se segment izveze iz uvida u ciljnu skupinu, on sadrži stupce koje ste odabrali prilikom definiranja odredišta izvoza u prethodnom koraku.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="7d3c7-156">Ti se podaci mogu koristiti za [stvaranje profila u servisu Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="7d3c7-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="7d3c7-157">Da bismo koristili segment u servisu Adobe Campaign Standard, moramo proširiti shemu profila u servisu Adobe Campaign Standard tako da uključuje dva dodatna polja.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="7d3c7-158">Saznajte kako [proširiti resurs profila](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) s novim poljima u servisu Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="7d3c7-159">U našem primjeru ta su polja *Naziv segmenta i Datum segmenta (neobavezno).*</span><span class="sxs-lookup"><span data-stu-id="7d3c7-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="7d3c7-160">Pomoću ovih polja identificirat ćemo profile u servisu Adobe Campaign Standard koje želimo ciljati za ovu kampanju.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="7d3c7-161">Ako u servisu Adobe Campaign Standard ne postoje drugi zapisi, osim onoga što ćete uvoziti, možete preskočiti ovaj korak.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="7d3c7-162">Uvoz podataka u Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="7d3c7-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="7d3c7-163">Sad kad je sve na svom mjestu, trebamo uvesti pripremljene podatke o ciljnim skupinama iz uvida u ciljnu skupinu u Adobe Campaign Standard radi stvaranja profila.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="7d3c7-164">Saznajte [kako uvesti profile u Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) koristeći tijek rada.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="7d3c7-165">Tijek rada uvoza na slici ispod konfiguriran je za pokretanje svakih 8 sati i traži izvezene segmente uvida u ciljnu skupinu (.csv datoteka u Azure spremištu blobova).</span><span class="sxs-lookup"><span data-stu-id="7d3c7-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="7d3c7-166">Tijek rada izdvaja sadržaj .csv datoteke u navedenom redoslijedu stupaca.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="7d3c7-167">Ovaj je tijek rada napravljen za izvođenje osnovne obrade pogreški i osigurava da svaki zapis ima adresu e-pošte prije popunjavanja podacima u servisu Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="7d3c7-168">Tijek rada također izdvaja naziv segmenta iz naziva datoteke prije dodavanja u podatke ACS profila.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Snimka zaslona tijeka rada uvoza u korisničkom sučelju servisa Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="7d3c7-170">Dohvaćanje ciljne skupine u servisu Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="7d3c7-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="7d3c7-171">Nakon što se podaci uvezu u Adobe Campaign Standard, [možete stvoriti tijek rada](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [upitati](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) klijente na temelju polja *Naziv segmenta* i *Datum segmenta* da odaberu profile koji su identificirani za našu oglednu kampanju.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="7d3c7-172">Stvaranje i slanje e-pošte pomoću servisa Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="7d3c7-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="7d3c7-173">Stvorite sadržaj e-pošte, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoju poruku e-pošte.</span><span class="sxs-lookup"><span data-stu-id="7d3c7-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ogledna poruka e-pošte s ponudom za obnovu iz servisa Adobe Campaign Standard.":::