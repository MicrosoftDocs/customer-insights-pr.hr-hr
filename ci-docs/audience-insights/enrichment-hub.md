---
title: Obogaćivanje objedinjenih profila klijenata
description: Koristite mogućnosti za obogaćivanje podataka o klijentima.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954478"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="e63bc-103">Obogaćivanje za korisničke profile (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="e63bc-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="e63bc-104">Koristite podatke iz izvora poput Microsofta i drugih partnera kako biste obogatili podatke o klijentima.</span><span class="sxs-lookup"><span data-stu-id="e63bc-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica središta za obogaćivanje":::

<span data-ttu-id="e63bc-106">U uvidima u ciljnu skupinu idite na **Podaci** > **Obogaćivanje** za rad s mogućnostima obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="e63bc-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="e63bc-107">Da biste stvorili ili uredili obogaćivanja, morate imati dozvole Suradnik ili Administrator.</span><span class="sxs-lookup"><span data-stu-id="e63bc-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="e63bc-108">Za dodatne informacije pogledajte [Dozvole](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e63bc-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="e63bc-109">Na kartici **Otkrivanje** pronaći ćete sljedeća obogaćivanja:</span><span class="sxs-lookup"><span data-stu-id="e63bc-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="e63bc-110">[Brendovi](enrichment-microsoft.md) koje je omogućio Microsoft</span><span class="sxs-lookup"><span data-stu-id="e63bc-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="e63bc-111">[Interesi](enrichment-microsoft.md) koje je omogućio Microsoft</span><span class="sxs-lookup"><span data-stu-id="e63bc-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="e63bc-112">[Poboljšane adrese](enrichment-enhanced-addresses.md) koje je omogućio Microsoft</span><span class="sxs-lookup"><span data-stu-id="e63bc-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="e63bc-113">[Podatke o tvrtki](enrichment-leadspace.md) omogućuje tvrtka Leadspace</span><span class="sxs-lookup"><span data-stu-id="e63bc-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="e63bc-114">[Demografske podatke](enrichment-experian.md) omogućuje tvrtka Experian</span><span class="sxs-lookup"><span data-stu-id="e63bc-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="e63bc-115">[Podatke o lokaciji](enrichment-here.md) pruža tvrtka HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="e63bc-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="e63bc-116">[Prilagođeni podaci](enrichment-SFTP-custom-import.md) putem Protokola sigurnog prijenosa datoteka (SFTP)</span><span class="sxs-lookup"><span data-stu-id="e63bc-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="e63bc-117">Na kartici **Moja obogaćivanja** možete vidjeti obogaćivanja koja ste konfigurirali i urediti njihova svojstva.</span><span class="sxs-lookup"><span data-stu-id="e63bc-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="e63bc-118">Upravljanje postojećim obogaćivanjima</span><span class="sxs-lookup"><span data-stu-id="e63bc-118">Manage existing enrichments</span></span>

<span data-ttu-id="e63bc-119">Idite na **Moja obogaćivanja** da biste vidjeli sva konfigurirana obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="e63bc-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="e63bc-120">Svako obogaćivanje predstavljeno je kao redak koji uključuje dodatne informacije o obogaćivanju.</span><span class="sxs-lookup"><span data-stu-id="e63bc-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="e63bc-121">Odaberite obogaćivanje da biste vidjeli dostupne mogućnosti.</span><span class="sxs-lookup"><span data-stu-id="e63bc-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="e63bc-122">Možete odabrati i elipsu (...) na stavci popisa da biste vidjeli mogućnosti.</span><span class="sxs-lookup"><span data-stu-id="e63bc-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Mogućnosti upravljanja obogaćivanjima na popisu obogaćivanja":::

- <span data-ttu-id="e63bc-124">**Prikaži** pojedinosti o obogaćivanju brojem obogaćenih profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="e63bc-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="e63bc-125">**Uredi** konfiguraciju obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="e63bc-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="e63bc-126">**Pokreni** obogaćivanje za ažuriranje profila kupaca najnovijim podacima.</span><span class="sxs-lookup"><span data-stu-id="e63bc-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="e63bc-127">**Deaktiviraj** postojeće obogaćivanje za zaustavljanje automatskog osvježavanja prilikom svakog zakazanog osvježavanja.</span><span class="sxs-lookup"><span data-stu-id="e63bc-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="e63bc-128">Podaci iz posljednjeg uspješnog osvježavanja i dalje će biti dostupni.</span><span class="sxs-lookup"><span data-stu-id="e63bc-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="e63bc-129">**Aktiviraj** neaktivno obogaćivanje za ponovno pokretanje automatskog osvježavanja sa svakim zakazanim osvježavanjem.</span><span class="sxs-lookup"><span data-stu-id="e63bc-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="e63bc-130">**Izbrišite** obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="e63bc-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="e63bc-131">Možete pokrenuti ili deaktivirati više obogaćivanja odjednom njihovim odabirom na popisu.</span><span class="sxs-lookup"><span data-stu-id="e63bc-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="e63bc-132">Mogućnosti prikaza i uređivanja nisu dostupne kao skupna radnja i istovremeno rade samo za jedno obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="e63bc-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="e63bc-133">Obogaćivanja i veze</span><span class="sxs-lookup"><span data-stu-id="e63bc-133">Enrichments and connections</span></span>

<span data-ttu-id="e63bc-134">Obogaćivanja treće strane konfigurirana su pomoću [veza](connections.md) koje administrator postavlja s vjerodajnicama i daje pristanak za prijenos podataka.</span><span class="sxs-lookup"><span data-stu-id="e63bc-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="e63bc-135">Vezu mogu koristiti administratori i suradnici da bi konfigurirali obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="e63bc-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="e63bc-136">Višestruka obogaćivanja iste vrste</span><span class="sxs-lookup"><span data-stu-id="e63bc-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="e63bc-137">Entitet koji treba obogatiti naveden je tijekom konfiguracije obogaćivanja, što vam omogućuje obogaćivanje samo podskupina vaših profila.</span><span class="sxs-lookup"><span data-stu-id="e63bc-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="e63bc-138">Na primjer, obogatite podatke samo za određeni segment.</span><span class="sxs-lookup"><span data-stu-id="e63bc-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="e63bc-139">Možete konfigurirati nekoliko obogaćivanja iste vrste i ponovno koristiti istu vezu.</span><span class="sxs-lookup"><span data-stu-id="e63bc-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="e63bc-140">Neka obogaćivanja imat će ograničenja u broju obogaćivanja iste vrste koja se mogu stvoriti.</span><span class="sxs-lookup"><span data-stu-id="e63bc-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="e63bc-141">Ograničenja i trenutna upotreba mogu se vidjeti na stranici **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="e63bc-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
