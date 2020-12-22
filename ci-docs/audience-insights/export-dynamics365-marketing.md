---
title: Izvoz podataka usluge Customer Insights u Dynamics 365 Marketing
description: Saznajte kako konfigurirati vezu s uslugom Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643764"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="44ce1-103">Poveznik za Dynamics 365 Marketing (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="44ce1-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="44ce1-104">Upotrijebite [segmente](segments.md) za stvaranje kampanja i kontaktiranje određenih grupa klijenata koristeći Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="44ce1-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="44ce1-105">Za dodatne informacije pogledajte [Korištenje segmenata iz sustava Dynamics 365 Customer Insights s uslugom Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="44ce1-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="44ce1-106">Preduvjet</span><span class="sxs-lookup"><span data-stu-id="44ce1-106">Prerequisite</span></span>

<span data-ttu-id="44ce1-107">Zapisi kontakata [iz usluge Dynamics 365 Marketing uneseni pomoću usluge Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="44ce1-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="44ce1-108">Konfiguracija poveznika za Marketing</span><span class="sxs-lookup"><span data-stu-id="44ce1-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="44ce1-109">U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.</span><span class="sxs-lookup"><span data-stu-id="44ce1-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="44ce1-110">U odjeljku **Dynamics 365 Marketing** odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="44ce1-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="44ce1-111">Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="44ce1-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="44ce1-112">Unesite URL za Marketing vaše tvrtke ili ustanove u polje **Adresa poslužitelja**.</span><span class="sxs-lookup"><span data-stu-id="44ce1-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="44ce1-113">U odjeljku **Račun administratora poslužitelja** odaberite **Prijava** i odaberite račun usluge Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="44ce1-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="44ce1-114">Mapirajte polje ID-a klijenta na ID kontakta sustava Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="44ce1-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="44ce1-115">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="44ce1-115">Select **Next**.</span></span>

1. <span data-ttu-id="44ce1-116">Odaberite jedan segment ili više njih.</span><span class="sxs-lookup"><span data-stu-id="44ce1-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="44ce1-117">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="44ce1-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="44ce1-118">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="44ce1-118">Export the data</span></span>

<span data-ttu-id="44ce1-119">Možete [izvesti podatke na zahtjev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="44ce1-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="44ce1-120">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="44ce1-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
