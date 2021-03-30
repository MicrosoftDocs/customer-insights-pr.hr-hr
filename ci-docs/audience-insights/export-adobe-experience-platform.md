---
title: Izvoz podataka servisa Customer Insights u Adobe Experience Platform
description: Saznajte kako koristiti segmente uvida u ciljnu skupinu u servisu Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596260"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="e865d-103">Korištenje segmenata servisa Customer Insights u servisu Adobe Experience Platform (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="e865d-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="e865d-104">Možda ste kao korisnik uvida u ciljnu skupinu za Dynamics 365 Customer Insights stvorili segmente kako biste svoje marketinške kampanje učinili učinkovitijim ciljanjem relevantnih ciljnih skupina.</span><span class="sxs-lookup"><span data-stu-id="e865d-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="e865d-105">Da biste koristili segment iz uvida u ciljnu skupinu u servisu Adobe Experience Platform i aplikacijama kao što je Adobe Campaign Standard, morate slijediti nekoliko koraka navedenih u ovom članku.</span><span class="sxs-lookup"><span data-stu-id="e865d-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a><span data-ttu-id="e865d-107">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="e865d-107">Prerequisites</span></span>

-   <span data-ttu-id="e865d-108">Licenca sustava Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e865d-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="e865d-109">Licenca za Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="e865d-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="e865d-110">Licenca za Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e865d-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="e865d-111">Račun za Azure spremište blobova</span><span class="sxs-lookup"><span data-stu-id="e865d-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="e865d-112">Pregled kampanje</span><span class="sxs-lookup"><span data-stu-id="e865d-112">Campaign Overview</span></span>

<span data-ttu-id="e865d-113">Da biste bolje razumjeli kako možete koristiti segmente iz uvida u ciljnu skupinu u servisu Adobe Experience Platform, pogledajmo fiktivni primjer kampanje.</span><span class="sxs-lookup"><span data-stu-id="e865d-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="e865d-114">Pretpostavimo da vaša tvrtka nudi mjesečnu uslugu zasnovanu na pretplati vašim klijentima u Sjedinjenim Državama.</span><span class="sxs-lookup"><span data-stu-id="e865d-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="e865d-115">Želite identificirati klijente čije pretplate trebaju biti obnovljene u sljedećih osam dana, ali koji još nisu obnovili pretplatu.</span><span class="sxs-lookup"><span data-stu-id="e865d-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="e865d-116">Da biste zadržali te klijente, želite im poslati promotivnu ponudu putem e-pošte koristeći Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="e865d-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="e865d-117">U ovom primjeru želimo jednom provesti promotivnu kampanju putem e-pošte.</span><span class="sxs-lookup"><span data-stu-id="e865d-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="e865d-118">Ovaj članak ne pokriva slučaj upotrebe za provođenje kampanje više puta.</span><span class="sxs-lookup"><span data-stu-id="e865d-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="e865d-119">Identificiranje ciljne skupine</span><span class="sxs-lookup"><span data-stu-id="e865d-119">Identify your target audience</span></span>

<span data-ttu-id="e865d-120">U našem scenariju pretpostavljamo da su adrese e-pošte klijenata dostupne u uvidima u ciljnu skupinu i analizirane su njihove promotivne preferencije kako bi se identificirali članovi segmenta.</span><span class="sxs-lookup"><span data-stu-id="e865d-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="e865d-121">[Segment koji ste definirali u uvidima u ciljnu skupinu](segments.md) se zove **ChurnProneCustomers** i tim klijentima planirate poslati promotivnu e-poštu.</span><span class="sxs-lookup"><span data-stu-id="e865d-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimka zaslona sa stranicom segmenata sa stvorenim segmentom ChurnProneCustomers.":::

<span data-ttu-id="e865d-123">E-pošta s ponudom koju želite poslati sadržavat će ime, prezime i datum završetka pretplate klijenta.</span><span class="sxs-lookup"><span data-stu-id="e865d-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="e865d-124">Ona obavještava klijente o popustu koji će dobiti ako obnove pretplatu prije nego što završi.</span><span class="sxs-lookup"><span data-stu-id="e865d-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="e865d-125">Izvoz ciljne skupine</span><span class="sxs-lookup"><span data-stu-id="e865d-125">Export your target audience</span></span>

<span data-ttu-id="e865d-126">Nakon što identificiramo našu ciljnu skupinu, možemo konfigurirati izvoz iz uvida u ciljnu skupinu na račun za Azure spremište blobova.</span><span class="sxs-lookup"><span data-stu-id="e865d-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="e865d-127">U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.</span><span class="sxs-lookup"><span data-stu-id="e865d-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e865d-128">Na pločici **Azure spremište blobova** odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="e865d-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Pločica za konfiguraciju za Azure spremište blobova.":::

1. <span data-ttu-id="e865d-130">Navedite **zaslonski naziv** za ovo novo odredište izvoza, a zatim unesite **Naziv računa**, **Ključ računa** i **Spremnik** računa za Azure spremište blobova na koji želite izvesti segment.</span><span class="sxs-lookup"><span data-stu-id="e865d-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimka zaslona konfiguracije računa za pohranu. "::: 

   - <span data-ttu-id="e865d-132">Da biste saznali više o pronalaženju imena i ključa računa spremišta blobova platforme Azure, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="e865d-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="e865d-133">Pogledajte kako stvoriti spremnik [Stvaranje spremnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="e865d-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="e865d-134">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="e865d-134">Select **Next**.</span></span>

1. <span data-ttu-id="e865d-135">Odaberite segment koji želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="e865d-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="e865d-136">U ovom primjeru je to **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="e865d-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimka zaslona korisničkog sučelja za odabir segmenta s odabranim segmentom ChurnProneCustomers.":::

1. <span data-ttu-id="e865d-138">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="e865d-138">Select **Save**.</span></span>

<span data-ttu-id="e865d-139">Nakon spremanja odredišta izvoza, pronaći ćete ga u odjeljku **Administrator** > **Izvozi** > **Moja odredišta izvoza**.</span><span class="sxs-lookup"><span data-stu-id="e865d-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Snimka zaslona s istaknutim popisom izvoza i uzorkom segmenta.":::

<span data-ttu-id="e865d-141">Sada možete [izvesti segment na zahtjev](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e865d-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="e865d-142">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md).</span><span class="sxs-lookup"><span data-stu-id="e865d-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e865d-143">Provjerite je li broj zapisa u izvezenom segmentu unutar dopuštenog ograničenja vaše licence za Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e865d-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="e865d-144">Izvezeni podaci pohranjeni su u spremniku Azure spremište blobova koji ste ranije konfigurirali.</span><span class="sxs-lookup"><span data-stu-id="e865d-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="e865d-145">Sljedeća putanja mape stvara se automatski u vašem spremniku:</span><span class="sxs-lookup"><span data-stu-id="e865d-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="e865d-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="e865d-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="e865d-147">Primjer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="e865d-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="e865d-148">*Model.json* za izvezene entitete nalazi se razini *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="e865d-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="e865d-149">Primjer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="e865d-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="e865d-150">Definiranje Podatkovnog modela iskustva (XDM) u servisu Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="e865d-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="e865d-151">Prije nego što se izvezeni podaci iz uvida u ciljnu skupinu mogu upotrijebiti u servisu Adobe Experience Platform, moramo definirati shemu Podatkovnog modela iskustva i [konfigurirati podatke za profil klijenta u stvarnom vremenu](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="e865d-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="e865d-152">Saznajte [što je XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) i usvojite [osnove sastavljanja sheme](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="e865d-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="e865d-153">Uvoz podataka u Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="e865d-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="e865d-154">Sad kad je sve na svom mjestu, trebamo uvesti pripremljene podatke o ciljnim skupinama iz uvida u ciljnu skupinu u Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="e865d-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="e865d-155">Najprije [stvorite izvornu vezu za Azure spremište blobova](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="e865d-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="e865d-156">Nakon definiranja izvorne veze, [konfigurirajte tok podataka](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) za skup veza za pohranu u oblaku za uvoz rezultata segmenta iz uvida u ciljnu skupinu u Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="e865d-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="e865d-157">Stvaranje ciljne skupine u servisu Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e865d-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="e865d-158">Za slanje e-pošte za ovu kampanju koristit ćemo Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e865d-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="e865d-159">Nakon uvoza podataka u Adobe Experience Platform, trebamo [stvoriti ciljnu skupinu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) u servisu Adobe Campaign Standard koristeći podatke u servisu Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="e865d-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="e865d-160">Saznajte kako [koristiti sastavljač segmenata](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) u servisu Adobe Campaign Standard za definiranje ciljne skupine na temelju podataka u servisu Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="e865d-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="e865d-161">Stvaranje i slanje e-pošte pomoću servisa Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e865d-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="e865d-162">Stvorite sadržaj e-pošte, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoju poruku e-pošte.</span><span class="sxs-lookup"><span data-stu-id="e865d-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ogledna poruka e-pošte s ponudom za obnovu iz servisa Adobe Campaign Standard.":::