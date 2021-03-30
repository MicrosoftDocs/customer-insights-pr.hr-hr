---
title: Izvoz podataka usluge Customer Insights u Dynamics 365 Sales
description: Saznajte kako konfigurirati vezu s uslugom Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598100"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="b3fee-103">Poveznik za Dynamics 365 Sales (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="b3fee-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b3fee-104">Upotrijebite podatke o klijentima za izradu popisa zainteresiranih, daljnje praćenje tijekova rada i slanje promocija pomoću aplikacije Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b3fee-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="b3fee-105">Preduvjet</span><span class="sxs-lookup"><span data-stu-id="b3fee-105">Prerequisite</span></span>

1. <span data-ttu-id="b3fee-106">Zapisi o kontaktima moraju biti prisutni u sustavu Dynamics 365 Sales prije nego što možete izvesti segment iz Customer Insights u Sales.</span><span class="sxs-lookup"><span data-stu-id="b3fee-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="b3fee-107">Pročitajte više o tome kako preuzeti kontakte u [Dynamics 365 Sales pomoću Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b3fee-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="b3fee-108">Izvoz segmenata iz uvida u ciljnu skupinnu u Sales neće stvoriti nove zapise o kontaktima u instancama programa Sales.</span><span class="sxs-lookup"><span data-stu-id="b3fee-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="b3fee-109">Zapisi o kontaktima iz programa Sales moraju se preuzeti u uvide u ciljnu skupinu i koristiti kao izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="b3fee-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="b3fee-110">Trebaju se uključiti i u objedinjeni entitet Klijent da bi mapirali ID-jeve klijenta u ID-jeve kontakta prije nego što se segmenti mogu izvesti.</span><span class="sxs-lookup"><span data-stu-id="b3fee-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="b3fee-111">Konfiguracija poveznika za Sales</span><span class="sxs-lookup"><span data-stu-id="b3fee-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="b3fee-112">U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.</span><span class="sxs-lookup"><span data-stu-id="b3fee-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b3fee-113">U odjeljku **Dynamics 365 Sales** odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="b3fee-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="b3fee-114">Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="b3fee-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b3fee-115">Unesite URL za Sales vaše tvrtke ili ustanove u polje **Adresa poslužitelja**.</span><span class="sxs-lookup"><span data-stu-id="b3fee-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="b3fee-116">U odjeljku **Račun administratora poslužitelja** odaberite **Prijava** i odaberite račun usluge Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b3fee-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="b3fee-117">Mapirajte polje ID-a klijenta na ID kontakta sustava Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b3fee-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="b3fee-118">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="b3fee-118">Select **Next**.</span></span>

1. <span data-ttu-id="b3fee-119">Odaberite jedan segment ili više njih.</span><span class="sxs-lookup"><span data-stu-id="b3fee-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="b3fee-120">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="b3fee-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b3fee-121">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="b3fee-121">Export the data</span></span>

<span data-ttu-id="b3fee-122">Možete [izvesti podatke na zahtjev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b3fee-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b3fee-123">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b3fee-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]