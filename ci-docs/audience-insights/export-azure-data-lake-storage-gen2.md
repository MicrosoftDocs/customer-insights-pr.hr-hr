---
title: Izvoz podataka usluge Customer Insights u Azure Data Lake Storage druge generacije
description: Saznajte kako konfigurirati vezu s uslugom Azure Data Lake Storage druge generacije.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596628"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="c191e-103">Poveznik za Azure Data Lake Storage druge generacije (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="c191e-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="c191e-104">Pohranite podatke iz usluge Customer Insights na Azure Data Lake Storage druge generacije ili ih koristite za prijenos podataka u ostale aplikacije.</span><span class="sxs-lookup"><span data-stu-id="c191e-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="c191e-105">Konfiguriranje poveznika za Azure Data Lake Storage druge generacije</span><span class="sxs-lookup"><span data-stu-id="c191e-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="c191e-106">U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.</span><span class="sxs-lookup"><span data-stu-id="c191e-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c191e-107">Pod **Azure Data Lake Storage druge generacije** odaberite **Postavi**.</span><span class="sxs-lookup"><span data-stu-id="c191e-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="c191e-108">Dodijelite odredištu prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="c191e-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c191e-109">Unesite **Naziv računa**, **Ključ računa** i **Spremnik** za svoj Azure Data Lake Storage druge generacije.</span><span class="sxs-lookup"><span data-stu-id="c191e-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="c191e-110">Da biste saznali kako stvoriti račun za pohranu za korištenje uz Azure Data Lake Storage druge generacije, pogledajte [Stvaranje računa za pohranu](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="c191e-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="c191e-111">Da biste saznali više o tome kako pronaći naziv računa za pohranu Azure Data Lake druge generacije i ključ računa, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="c191e-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="c191e-112">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="c191e-112">Select **Next**.</span></span>

1. <span data-ttu-id="c191e-113">Označite okvir pokraj svakog entiteta koji želite izvesti na ovo odredište.</span><span class="sxs-lookup"><span data-stu-id="c191e-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="c191e-114">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="c191e-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c191e-115">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="c191e-115">Export the data</span></span>

<span data-ttu-id="c191e-116">Možete [izvesti podatke na zahtjev](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c191e-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="c191e-117">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c191e-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>