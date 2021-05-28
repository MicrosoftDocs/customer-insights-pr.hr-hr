---
title: Izvoz podataka usluge Customer Insights u Dynamics 365 Sales
description: Saznajte kako konfigurirati vezu i izvesti u Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976217"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="bcd2b-103">Korištenje segmenata u Dynamics 365 Sales (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="bcd2b-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bcd2b-104">Upotrijebite podatke o klijentima za izradu popisa zainteresiranih, daljnje praćenje tijekova rada i slanje promocija pomoću aplikacije Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="bcd2b-105">Preduvjet za vezu</span><span class="sxs-lookup"><span data-stu-id="bcd2b-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="bcd2b-106">Zapisi o kontaktima moraju biti prisutni u sustavu Dynamics 365 Sales prije nego što možete izvesti segment iz Customer Insights u Sales.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="bcd2b-107">Pročitajte više o tome kako preuzeti kontakte u [Dynamics 365 Sales pomoću Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="bcd2b-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="bcd2b-108">Izvoz segmenata iz uvida u ciljnu skupinnu u Sales neće stvoriti nove zapise o kontaktima u instancama programa Sales.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="bcd2b-109">Zapisi o kontaktima iz programa Sales moraju se preuzeti u uvide u ciljnu skupinu i koristiti kao izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="bcd2b-110">Trebaju se uključiti i u objedinjeni entitet Klijent da bi mapirali ID-jeve klijenta u ID-jeve kontakta prije nego što se segmenti mogu izvesti.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="bcd2b-111">Postavite vezu sa Sales</span><span class="sxs-lookup"><span data-stu-id="bcd2b-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="bcd2b-112">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bcd2b-113">Odaberite **Dodaj vezu** i odaberite **Dynamics 365 Sales** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="bcd2b-114">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bcd2b-115">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bcd2b-116">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bcd2b-117">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-117">Choose who can use this connection.</span></span> <span data-ttu-id="bcd2b-118">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bcd2b-119">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bcd2b-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bcd2b-120">Unesite URL za Sales vaše tvrtke ili ustanove u polje **Adresa poslužitelja**.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="bcd2b-121">U odjeljku **Račun administratora poslužitelja** odaberite **Prijava** i odaberite račun usluge Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="bcd2b-122">Mapirajte polje ID-a klijenta na ID kontakta sustava Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="bcd2b-123">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="bcd2b-124">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="bcd2b-124">Configure an export</span></span>

<span data-ttu-id="bcd2b-125">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bcd2b-126">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bcd2b-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bcd2b-127">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bcd2b-128">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bcd2b-129">U polju **Veza za izvoz** odaberite vezu iz odjeljka Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="bcd2b-130">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bcd2b-131">Odaberite jedan segment ili više njih.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="bcd2b-132">Odaberite **Spremi**</span><span class="sxs-lookup"><span data-stu-id="bcd2b-132">Select **Save**</span></span>

<span data-ttu-id="bcd2b-133">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="bcd2b-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bcd2b-134">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bcd2b-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bcd2b-135">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bcd2b-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
