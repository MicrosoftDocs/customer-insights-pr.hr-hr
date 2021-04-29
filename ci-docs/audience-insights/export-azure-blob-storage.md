---
title: Izvoz podataka usluge Customer Insights u Spremnik za pohranu bloba za Azure
description: Saznajte kako konfigurirati vezu i izvesti u Spremnik za pohranu bloba.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760180"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="f4b74-103">Izvoz popisa segmenata i ostalih podataka u Spremnik za pohranu bloba za Azure (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="f4b74-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="f4b74-104">Pohranite podatke usluge Customer Insights na Spremnik za pohranu bloba ili ih koristite za prijenos svojih podataka u ostale aplikacije.</span><span class="sxs-lookup"><span data-stu-id="f4b74-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="f4b74-105">Postavite vezu sa Spremnikom za pohranu bloba</span><span class="sxs-lookup"><span data-stu-id="f4b74-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="f4b74-106">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="f4b74-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f4b74-107">Odaberite **Dodaj vezu** i odaberite **Spremnik za pohranu bloba za Azure** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="f4b74-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="f4b74-108">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="f4b74-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f4b74-109">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="f4b74-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f4b74-110">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="f4b74-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f4b74-111">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="f4b74-111">Choose who can use this connection.</span></span> <span data-ttu-id="f4b74-112">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="f4b74-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f4b74-113">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f4b74-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f4b74-114">Unesite **Naziv računa**, **Ključ računa** i **Spremnik** za svoj račun za Spremnik za pohranu bloba.</span><span class="sxs-lookup"><span data-stu-id="f4b74-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="f4b74-115">Da biste saznali više o tome kako pronaći naziv računa apremnika za pohranu bloba i ključ računa, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="f4b74-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="f4b74-116">Pogledajte kako stvoriti spremnik [Stvaranje spremnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="f4b74-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="f4b74-117">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="f4b74-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="f4b74-118">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="f4b74-118">Configure an export</span></span>

<span data-ttu-id="f4b74-119">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="f4b74-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f4b74-120">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f4b74-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f4b74-121">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="f4b74-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f4b74-122">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="f4b74-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f4b74-123">U polju **Veza za izvoz** odaberite vezu iz odjeljka Spremnik za pohranu bloba za Azure.</span><span class="sxs-lookup"><span data-stu-id="f4b74-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="f4b74-124">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="f4b74-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f4b74-125">Označite okvir pokraj svakog entiteta koji želite izvesti na ovo odredište.</span><span class="sxs-lookup"><span data-stu-id="f4b74-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="f4b74-126">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="f4b74-126">Select **Save**.</span></span>

<span data-ttu-id="f4b74-127">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="f4b74-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f4b74-128">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f4b74-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="f4b74-129">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f4b74-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="f4b74-130">Izvezeni podaci pohranjuju se u spremnik za pohranu bloba koji ste konfigurirali.</span><span class="sxs-lookup"><span data-stu-id="f4b74-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="f4b74-131">Sljedeći se putovi mapa automatski stvaraju u vašem spremniku:</span><span class="sxs-lookup"><span data-stu-id="f4b74-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="f4b74-132">Za izvorne entitete i entitete koje generira sustav: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="f4b74-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="f4b74-133">Primjer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="f4b74-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="f4b74-134">Model.json za izvezene entitete bit će na razini %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="f4b74-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="f4b74-135">Primjer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="f4b74-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
