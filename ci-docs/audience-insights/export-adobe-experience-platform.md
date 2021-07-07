---
title: Izvoz podataka servisa Customer Insights u Adobe Experience Platform
description: Naučite kako koristiti segmente uvida publike na platformi Adobe Experience.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305515"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="1e6d3-103">Korištenje segmenata servisa Customer Insights u servisu Adobe Experience Platform (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="1e6d3-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="1e6d3-104">Kao korisnik uvida u publiku značajke Dynamics 365 Customer Insights možda ste stvorili segmente kako biste svoje marketinške kampanje učinili učinkovitijim ciljanjem relevantne publike.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="1e6d3-105">Da biste koristili segment iz uvida u ciljnu skupinu u servisu Adobe Experience Platform i aplikacijama kao što je Adobe Campaign Standard, morate slijediti nekoliko koraka navedenih u ovom članku.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a><span data-ttu-id="1e6d3-107">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="1e6d3-107">Prerequisites</span></span>

-   <span data-ttu-id="1e6d3-108">Licenca sustava Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="1e6d3-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="1e6d3-109">Licenca za Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="1e6d3-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="1e6d3-110">Licenca za Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1e6d3-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="1e6d3-111">Račun za Azure spremište blobova</span><span class="sxs-lookup"><span data-stu-id="1e6d3-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="1e6d3-112">Pregled kampanje</span><span class="sxs-lookup"><span data-stu-id="1e6d3-112">Campaign Overview</span></span>

<span data-ttu-id="1e6d3-113">Da biste bolje razumjeli kako možete koristiti segmente iz uvida u ciljnu skupinu u servisu Adobe Experience Platform, pogledajmo fiktivni primjer kampanje.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="1e6d3-114">Pretpostavimo da vaša tvrtka nudi mjesečnu uslugu zasnovanu na pretplati vašim klijentima u Sjedinjenim Državama.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="1e6d3-115">Želite identificirati klijente čije pretplate trebaju biti obnovljene u sljedećih osam dana, ali koji još nisu obnovili pretplatu.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="1e6d3-116">Da biste zadržali te klijente, želite im poslati promotivnu ponudu putem e-pošte koristeći Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="1e6d3-117">U ovom primjeru želimo jednom provesti promotivnu kampanju putem e-pošte.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="1e6d3-118">Ovaj članak ne pokriva slučaj upotrebe za provođenje kampanje više puta.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="1e6d3-119">Identificiranje ciljne skupine</span><span class="sxs-lookup"><span data-stu-id="1e6d3-119">Identify your target audience</span></span>

<span data-ttu-id="1e6d3-120">U našem scenariju pretpostavljamo da su adrese e-pošte klijenata dostupne u uvidima u ciljnu skupinu i analizirane su njihove promotivne preferencije kako bi se identificirali članovi segmenta.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="1e6d3-121">[Segment koji ste definirali u uvidima u ciljnu skupinu](segments.md) se zove **ChurnProneCustomers** i tim klijentima planirate poslati promotivnu e-poštu.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimka zaslona sa stranicom segmenata sa stvorenim segmentom ChurnProneCustomers.":::

<span data-ttu-id="1e6d3-123">E-pošta s ponudom koju želite poslati sadržavat će ime, prezime i datum završetka pretplate klijenta.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="1e6d3-124">Ona obavještava klijente o popustu koji će dobiti ako obnove pretplatu prije nego što završi.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="1e6d3-125">Izvoz ciljne skupine</span><span class="sxs-lookup"><span data-stu-id="1e6d3-125">Export your target audience</span></span>

<span data-ttu-id="1e6d3-126">Nakon što identificiramo našu ciljnu skupinu, možemo konfigurirati izvoz iz uvida u ciljnu skupinu na račun za Azure spremište blobova.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="1e6d3-127">Konfiguracija veze</span><span class="sxs-lookup"><span data-stu-id="1e6d3-127">Configure a connection</span></span>

1. <span data-ttu-id="1e6d3-128">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1e6d3-129">Odaberite **Dodaj vezu** pa odaberite **Azure Blob Storage** ili odaberite **Postavljanje** na pločici **Azure Blob Storage** radi konfiguriranja veze.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Pločica za konfiguraciju za Azure spremište blobova."::: 

1. <span data-ttu-id="1e6d3-131">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1e6d3-132">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1e6d3-133">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1e6d3-134">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-134">Choose who can use this connection.</span></span> <span data-ttu-id="1e6d3-135">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1e6d3-136">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1e6d3-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1e6d3-137">Unesite **Naziv računa**, **Ključ računa** i **Spremnik** za svoj račun spremnika za pohranu bloba na koji želite izvesti segment.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimka zaslona konfiguracije računa za pohranu. "::: 
   
    - <span data-ttu-id="1e6d3-139">Da biste saznali više o tome kako pronaći naziv računa apremnika za pohranu bloba i ključ računa, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="1e6d3-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="1e6d3-140">Pogledajte kako stvoriti spremnik [Stvaranje spremnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="1e6d3-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="1e6d3-141">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="1e6d3-142">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="1e6d3-142">Configure an export</span></span>

<span data-ttu-id="1e6d3-143">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1e6d3-144">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1e6d3-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1e6d3-145">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1e6d3-146">Da biste stvorili novi izvoz, ddaberite **Dodaj izvoz**.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="1e6d3-147">U polju **Veza za izvoz** odaberite vezu iz odjeljka Spremnik za pohranu bloba za Azure.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="1e6d3-148">Ako ne vidite naziv ovog odjeljka, tada vam nisu dostupne veze ove vrste.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="1e6d3-149">Odaberite segment koji želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="1e6d3-150">U ovom primjeru je to **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimka zaslona korisničkog sučelja za odabir segmenta s odabranim segmentom ChurnProneCustomers.":::

1. <span data-ttu-id="1e6d3-152">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-152">Select **Save**.</span></span>

<span data-ttu-id="1e6d3-153">Nakon spremanja izvoznog odredišta pronaći ćete ga na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="1e6d3-154">Sada možete [izvesti segment na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1e6d3-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="1e6d3-155">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md).</span><span class="sxs-lookup"><span data-stu-id="1e6d3-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1e6d3-156">Provjerite je li broj zapisa u izvezenom segmentu unutar dopuštenog ograničenja vaše licence za Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="1e6d3-157">Izvezeni podaci pohranjeni su u spremniku Azure spremište blobova koji ste ranije konfigurirali.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="1e6d3-158">Sljedeća putanja mape stvara se automatski u vašem spremniku:</span><span class="sxs-lookup"><span data-stu-id="1e6d3-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="1e6d3-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="1e6d3-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="1e6d3-160">Primjer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="1e6d3-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="1e6d3-161">*Model.json* za izvezene entitete nalazi se razini *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="1e6d3-162">Primjer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="1e6d3-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="1e6d3-163">Definiranje Podatkovnog modela iskustva (XDM) u servisu Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="1e6d3-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="1e6d3-164">Prije nego što se izvezeni podaci iz uvida u ciljnu skupinu mogu upotrijebiti u servisu Adobe Experience Platform, moramo definirati shemu Podatkovnog modela iskustva i [konfigurirati podatke za profil klijenta u stvarnom vremenu](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="1e6d3-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="1e6d3-165">Saznajte [što je XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) i usvojite [osnove sastavljanja sheme](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="1e6d3-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="1e6d3-166">Uvoz podataka u Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="1e6d3-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="1e6d3-167">Sad kad je sve na svom mjestu, trebamo uvesti pripremljene podatke o ciljnim skupinama iz uvida u ciljnu skupinu u Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="1e6d3-168">Najprije [stvorite izvornu vezu za Azure spremište blobova](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="1e6d3-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="1e6d3-169">Nakon definiranja izvorne veze, [konfigurirajte tok podataka](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) za skup veza za pohranu u oblaku za uvoz rezultata segmenta iz uvida u ciljnu skupinu u Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="1e6d3-170">Stvaranje ciljne skupine u servisu Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1e6d3-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="1e6d3-171">Da bismo slali e-poštu za ovu kampanju, upotrijebit ćemo Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="1e6d3-172">Nakon uvoza podataka u Adobe Experience Platform, trebamo [stvoriti ciljnu skupinu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) u servisu Adobe Campaign Standard koristeći podatke u servisu Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="1e6d3-173">Saznajte kako [koristiti sastavljač segmenata](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) u servisu Adobe Campaign Standard za definiranje ciljne skupine na temelju podataka u servisu Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="1e6d3-174">Stvaranje i slanje e-pošte pomoću servisa Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1e6d3-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="1e6d3-175">Stvorite sadržaj e-pošte, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoju poruku e-pošte.</span><span class="sxs-lookup"><span data-stu-id="1e6d3-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ogledna poruka e-pošte s ponudom za obnovu iz servisa Adobe Campaign Standard.":::
