---
title: Izvoz podataka usluge Customer Insights u Dynamics 365 Marketing
description: Saznajte kako konfigurirati vezu i izvesti u Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759600"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="a1e89-103">Korištenje segmenata u Dynamics 365 Marketing (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="a1e89-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a1e89-104">Upotrijebite [segmente](segments.md) za stvaranje kampanja i kontaktiranje određenih grupa klijenata koristeći Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a1e89-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="a1e89-105">Za dodatne informacije pogledajte [Korištenje segmenata iz sustava Dynamics 365 Customer Insights s uslugom Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="a1e89-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="a1e89-106">Preduvjet za vezu</span><span class="sxs-lookup"><span data-stu-id="a1e89-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="a1e89-107">Zapisi o kontaktima moraju biti prisutni u sustavu Dynamics 365 Marketing prije nego što možete izvesti segment iz Customer Insights u Marketing.</span><span class="sxs-lookup"><span data-stu-id="a1e89-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="a1e89-108">Pročitajte više o tome kako preuzeti kontakte u [Dynamics 365 Marketing pomoću Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a1e89-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a1e89-109">Izvoz segmenata iz uvida u ciljnu skupinnu u Marketing neće stvoriti nove zapise o kontaktima u instancama programa Marketing.</span><span class="sxs-lookup"><span data-stu-id="a1e89-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="a1e89-110">Zapisi o kontaktima iz programa Marketing moraju se preuzeti u uvide u ciljnu skupinu i koristiti kao izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="a1e89-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="a1e89-111">Trebaju se uključiti i u objedinjeni entitet Klijent da bi mapirali ID-jeve klijenta u ID-jeve kontakta prije nego što se segmenti mogu izvesti.</span><span class="sxs-lookup"><span data-stu-id="a1e89-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="a1e89-112">Postavljanje veze s Marketing</span><span class="sxs-lookup"><span data-stu-id="a1e89-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="a1e89-113">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="a1e89-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a1e89-114">Odaberite **Dodaj vezu** i odaberite **Dynamics 365 Marketing** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="a1e89-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="a1e89-115">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="a1e89-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a1e89-116">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="a1e89-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a1e89-117">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="a1e89-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a1e89-118">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="a1e89-118">Choose who can use this connection.</span></span> <span data-ttu-id="a1e89-119">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="a1e89-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a1e89-120">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a1e89-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a1e89-121">Unesite URL za Marketing vaše tvrtke ili ustanove u polje **Adresa poslužitelja**.</span><span class="sxs-lookup"><span data-stu-id="a1e89-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a1e89-122">U odjeljku **Račun administratora poslužitelja** odaberite **Prijava** i odaberite račun usluge Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a1e89-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="a1e89-123">Mapirajte polje ID-a klijenta na ID kontakta sustava Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a1e89-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a1e89-124">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="a1e89-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="a1e89-125">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="a1e89-125">Configure an export</span></span>

<span data-ttu-id="a1e89-126">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="a1e89-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a1e89-127">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a1e89-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a1e89-128">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="a1e89-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a1e89-129">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="a1e89-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a1e89-130">U polju **Veza za izvoz** odaberite vezu iz odjeljka Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a1e89-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="a1e89-131">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="a1e89-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a1e89-132">Odaberite jedan segment ili više njih.</span><span class="sxs-lookup"><span data-stu-id="a1e89-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="a1e89-133">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="a1e89-133">Select **Save**.</span></span>

<span data-ttu-id="a1e89-134">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="a1e89-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a1e89-135">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a1e89-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a1e89-136">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a1e89-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
