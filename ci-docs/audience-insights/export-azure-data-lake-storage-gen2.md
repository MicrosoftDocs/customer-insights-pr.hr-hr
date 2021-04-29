---
title: Izvoz podataka usluge Customer Insights u Azure Data Lake Storage druge generacije
description: Saznajte kako konfigurirati vezu s uslugom Azure Data Lake Storage druge generacije.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760042"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="d437c-103">Postavljanje veze s Azure Data Lake Storage Gen2 (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="d437c-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="d437c-104">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="d437c-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d437c-105">Odaberite **Dodaj vezu** i odaberite **Azure Data Lake Gen 2** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="d437c-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="d437c-106">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="d437c-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d437c-107">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="d437c-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d437c-108">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="d437c-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d437c-109">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="d437c-109">Choose who can use this connection.</span></span> <span data-ttu-id="d437c-110">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="d437c-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d437c-111">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d437c-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d437c-112">Unesite **Naziv računa**, **Ključ računa** i **Spremnik** za svoj Azure Data Lake Storage druge generacije.</span><span class="sxs-lookup"><span data-stu-id="d437c-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="d437c-113">Da biste saznali kako stvoriti račun za pohranu za korištenje uz Azure Data Lake Storage druge generacije, pogledajte [Stvaranje računa za pohranu](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="d437c-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="d437c-114">Da biste saznali više o nazivu računa za pohranu i ključu računa za Azure Data Lake Gen2, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="d437c-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="d437c-115">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="d437c-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="d437c-116">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="d437c-116">Configure an export</span></span>

<span data-ttu-id="d437c-117">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="d437c-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d437c-118">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d437c-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d437c-119">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="d437c-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d437c-120">Da biste stvorili novi izvoz, ddaberite **Dodaj izvoz**.</span><span class="sxs-lookup"><span data-stu-id="d437c-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="d437c-121">U polju **Veza za izvoz** odaberite vezu iz odjeljka **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="d437c-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="d437c-122">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="d437c-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d437c-123">Označite okvir pokraj svakog entiteta koji želite izvesti na ovo odredište.</span><span class="sxs-lookup"><span data-stu-id="d437c-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="d437c-124">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="d437c-124">Select **Save**.</span></span>

<span data-ttu-id="d437c-125">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="d437c-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d437c-126">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d437c-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d437c-127">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d437c-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="d437c-128">Izvezeni podaci pohranjuju se u spremnik za pohranu za Azure Data Lake Gen 2 koji ste konfigurirali.</span><span class="sxs-lookup"><span data-stu-id="d437c-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
