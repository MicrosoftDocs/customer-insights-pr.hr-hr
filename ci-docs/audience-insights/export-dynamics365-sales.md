---
title: Izvoz podataka usluge Customer Insights u Dynamics 365 Sales
description: Saznajte kako konfigurirati vezu s uslugom Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643809"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="be8f4-103">Poveznik za Dynamics 365 Sales (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="be8f4-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="be8f4-104">Upotrijebite podatke o klijentima za izradu popisa zainteresiranih, daljnje praćenje tijekova rada i slanje promocija pomoću aplikacije Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="be8f4-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="be8f4-105">Preduvjet</span><span class="sxs-lookup"><span data-stu-id="be8f4-105">Prerequisite</span></span>

<span data-ttu-id="be8f4-106">Zapisi kontakata [iz usluge Dynamics 365 Sales uneseni pomoću usluge Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="be8f4-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="be8f4-107">Konfiguracija poveznika za Sales</span><span class="sxs-lookup"><span data-stu-id="be8f4-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="be8f4-108">U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.</span><span class="sxs-lookup"><span data-stu-id="be8f4-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="be8f4-109">U odjeljku **Dynamics 365 Sales** odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="be8f4-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="be8f4-110">Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="be8f4-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="be8f4-111">Unesite URL za Sales vaše tvrtke ili ustanove u polje **Adresa poslužitelja**.</span><span class="sxs-lookup"><span data-stu-id="be8f4-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="be8f4-112">U odjeljku **Račun administratora poslužitelja** odaberite **Prijava** i odaberite račun usluge Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="be8f4-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="be8f4-113">Mapirajte polje ID-a klijenta na ID kontakta sustava Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="be8f4-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="be8f4-114">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="be8f4-114">Select **Next**.</span></span>

1. <span data-ttu-id="be8f4-115">Odaberite jedan segment ili više njih.</span><span class="sxs-lookup"><span data-stu-id="be8f4-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="be8f4-116">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="be8f4-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="be8f4-117">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="be8f4-117">Export the data</span></span>

<span data-ttu-id="be8f4-118">Možete [izvesti podatke na zahtjev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="be8f4-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="be8f4-119">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="be8f4-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
