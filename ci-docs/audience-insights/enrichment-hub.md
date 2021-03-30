---
title: Obogaćivanje objedinjenih profila klijenata
description: Koristite mogućnosti za obogaćivanje podataka o klijentima.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597686"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="4bd7c-103">Obogaćivanje za korisničke profile (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="4bd7c-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="4bd7c-104">Koristite podatke iz izvora poput Microsofta i drugih partnera kako biste obogatili podatke o klijentima.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica središta za obogaćivanje":::

<span data-ttu-id="4bd7c-106">U uvidima u ciljnu skupinu idite na **Podaci** > **Obogaćivanje** za rad s mogućnostima obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="4bd7c-107">Da biste stvorili ili uredili obogaćivanja, morate imati dozvole Suradnik ili Administrator.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="4bd7c-108">Za dodatne informacije pogledajte [Dozvole](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4bd7c-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="4bd7c-109">Na kartici **Otkrivanje** pronaći ćete sljedeća obogaćivanja:</span><span class="sxs-lookup"><span data-stu-id="4bd7c-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="4bd7c-110">[Robne marke](enrichment-microsoft-graph.md) pruža Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="4bd7c-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="4bd7c-111">[Interesi](enrichment-microsoft-graph.md) pruža Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="4bd7c-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="4bd7c-112">[Podatke o tvrtki](enrichment-leadspace.md) omogućuje tvrtka Leadspace</span><span class="sxs-lookup"><span data-stu-id="4bd7c-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="4bd7c-113">[Demografske podatke](enrichment-experian.md) omogućuje tvrtka Experian</span><span class="sxs-lookup"><span data-stu-id="4bd7c-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="4bd7c-114">[Podatke o lokaciji](enrichment-here.md) pruža tvrtka HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="4bd7c-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="4bd7c-115">[Prilagođeni podaci](enrichment-SFTP-custom-import.md) putem Protokola sigurnog prijenosa datoteka (SFTP)</span><span class="sxs-lookup"><span data-stu-id="4bd7c-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="4bd7c-116">Na kartici **Moja obogaćivanja** možete vidjeti obogaćivanja koja ste konfigurirali i urediti njihova svojstva.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="4bd7c-117">Upravljanje postojećim obogaćivanjima</span><span class="sxs-lookup"><span data-stu-id="4bd7c-117">Manage existing enrichments</span></span>

<span data-ttu-id="4bd7c-118">Idite na **Moja obogaćivanja** da biste vidjeli sva konfigurirana obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="4bd7c-119">Svako obogaćivanje predstavljeno je kao redak koji uključuje dodatne informacije o obogaćivanju.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="4bd7c-120">Odaberite obogaćivanje da biste vidjeli dostupne mogućnosti.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="4bd7c-121">Ili možete odabrati elipsu (...) na stavci popisa da biste vidjeli mogućnosti.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Mogućnosti upravljanja obogaćivanjima na popisu obogaćivanja":::

- <span data-ttu-id="4bd7c-123">**Prikaži** pojedinosti o obogaćivanju brojem obogaćenih profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="4bd7c-124">**Uredi** konfiguraciju obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="4bd7c-125">**Pokreni** obogaćivanje za ažuriranje profila kupaca najnovijim podacima.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="4bd7c-126">**Deaktiviraj** postojeće obogaćivanje za zaustavljanje automatskog osvježavanja prilikom svakog zakazanog osvježavanja.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="4bd7c-127">Podaci iz posljednjeg uspješnog osvježavanja i dalje će biti dostupni.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="4bd7c-128">**Aktiviraj** neaktivno obogaćivanje za ponovno pokretanje automatskog osvježavanja sa svakim zakazanim osvježavanjem.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="4bd7c-129">**Izbrišite** obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="4bd7c-130">Možete pokrenuti ili deaktivirati više obogaćivanja odjednom njihovim odabirom na popisu.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="4bd7c-131">Mogućnosti prikaza i uređivanja nisu dostupne kao skupna radnja i istovremeno rade samo za jedno obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="4bd7c-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]