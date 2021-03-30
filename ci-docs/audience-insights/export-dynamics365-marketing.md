---
title: Izvoz podataka usluge Customer Insights u Dynamics 365 Marketing
description: Saznajte kako konfigurirati vezu s uslugom Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597594"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="263f6-103">Poveznik za Dynamics 365 Marketing (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="263f6-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="263f6-104">Upotrijebite [segmente](segments.md) za stvaranje kampanja i kontaktiranje određenih grupa klijenata koristeći Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="263f6-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="263f6-105">Za dodatne informacije pogledajte [Korištenje segmenata iz sustava Dynamics 365 Customer Insights s uslugom Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="263f6-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="263f6-106">Preduvjet</span><span class="sxs-lookup"><span data-stu-id="263f6-106">Prerequisite</span></span>

- <span data-ttu-id="263f6-107">Zapisi o kontaktima moraju biti prisutni u sustavu Dynamics 365 Marketing prije nego što možete izvesti segment iz Customer Insights u Marketing.</span><span class="sxs-lookup"><span data-stu-id="263f6-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="263f6-108">Pročitajte više o tome kako preuzeti kontakte u [Dynamics 365 Marketing pomoću Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="263f6-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="263f6-109">Izvoz segmenata iz uvida u ciljnu skupinnu u Marketing neće stvoriti nove zapise o kontaktima u instancama programa Marketing.</span><span class="sxs-lookup"><span data-stu-id="263f6-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="263f6-110">Zapisi o kontaktima iz programa Marketing moraju se preuzeti u uvide u ciljnu skupinu i koristiti kao izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="263f6-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="263f6-111">Trebaju se uključiti i u objedinjeni entitet Klijent da bi mapirali ID-jeve klijenta u ID-jeve kontakta prije nego što se segmenti mogu izvesti.</span><span class="sxs-lookup"><span data-stu-id="263f6-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="263f6-112">Konfiguracija poveznika za Marketing</span><span class="sxs-lookup"><span data-stu-id="263f6-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="263f6-113">U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.</span><span class="sxs-lookup"><span data-stu-id="263f6-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="263f6-114">U odjeljku **Dynamics 365 Marketing** odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="263f6-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="263f6-115">Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="263f6-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="263f6-116">Unesite URL za Marketing vaše tvrtke ili ustanove u polje **Adresa poslužitelja**.</span><span class="sxs-lookup"><span data-stu-id="263f6-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="263f6-117">U odjeljku **Račun administratora poslužitelja** odaberite **Prijava** i odaberite račun usluge Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="263f6-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="263f6-118">Mapirajte polje ID-a klijenta na ID kontakta sustava Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="263f6-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="263f6-119">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="263f6-119">Select **Next**.</span></span>

1. <span data-ttu-id="263f6-120">Odaberite jedan segment ili više njih.</span><span class="sxs-lookup"><span data-stu-id="263f6-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="263f6-121">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="263f6-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="263f6-122">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="263f6-122">Export the data</span></span>

<span data-ttu-id="263f6-123">Možete [izvesti podatke na zahtjev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="263f6-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="263f6-124">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="263f6-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]