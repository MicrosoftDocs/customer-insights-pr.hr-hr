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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895996"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="8bf87-103">Obogaćivanje za korisničke profile (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="8bf87-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="8bf87-104">Koristite podatke iz izvora poput Microsofta i drugih partnera kako biste obogatili podatke o klijentima.</span><span class="sxs-lookup"><span data-stu-id="8bf87-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica središta za obogaćivanje":::

<span data-ttu-id="8bf87-106">U uvidima u ciljnu skupinu idite na **Podaci** > **Obogaćivanje** za rad s mogućnostima obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="8bf87-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="8bf87-107">Da biste stvorili ili uredili obogaćivanja, morate imati dozvole Suradnik ili Administrator.</span><span class="sxs-lookup"><span data-stu-id="8bf87-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="8bf87-108">Za dodatne informacije pogledajte [Dozvole](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8bf87-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="8bf87-109">Na kartici **Otkrivanje** pronaći ćete sljedeća obogaćivanja:</span><span class="sxs-lookup"><span data-stu-id="8bf87-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="8bf87-110">[Brendovi](enrichment-microsoft.md) koje je omogućio Microsoft</span><span class="sxs-lookup"><span data-stu-id="8bf87-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="8bf87-111">[Interesi](enrichment-microsoft.md) koje je omogućio Microsoft</span><span class="sxs-lookup"><span data-stu-id="8bf87-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="8bf87-112">[Podatke o tvrtki](enrichment-leadspace.md) omogućuje tvrtka Leadspace</span><span class="sxs-lookup"><span data-stu-id="8bf87-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="8bf87-113">[Demografske podatke](enrichment-experian.md) omogućuje tvrtka Experian</span><span class="sxs-lookup"><span data-stu-id="8bf87-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="8bf87-114">[Podatke o lokaciji](enrichment-here.md) pruža tvrtka HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="8bf87-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="8bf87-115">[Prilagođeni podaci](enrichment-SFTP-custom-import.md) putem Protokola sigurnog prijenosa datoteka (SFTP)</span><span class="sxs-lookup"><span data-stu-id="8bf87-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="8bf87-116">Na kartici **Moja obogaćivanja** možete vidjeti obogaćivanja koja ste konfigurirali i urediti njihova svojstva.</span><span class="sxs-lookup"><span data-stu-id="8bf87-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="8bf87-117">Upravljanje postojećim obogaćivanjima</span><span class="sxs-lookup"><span data-stu-id="8bf87-117">Manage existing enrichments</span></span>

<span data-ttu-id="8bf87-118">Idite na **Moja obogaćivanja** da biste vidjeli sva konfigurirana obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="8bf87-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="8bf87-119">Svako obogaćivanje predstavljeno je kao redak koji uključuje dodatne informacije o obogaćivanju.</span><span class="sxs-lookup"><span data-stu-id="8bf87-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="8bf87-120">Odaberite obogaćivanje da biste vidjeli dostupne mogućnosti.</span><span class="sxs-lookup"><span data-stu-id="8bf87-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="8bf87-121">Možete odabrati i elipsu (...) na stavci popisa da biste vidjeli mogućnosti.</span><span class="sxs-lookup"><span data-stu-id="8bf87-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Mogućnosti upravljanja obogaćivanjima na popisu obogaćivanja":::

- <span data-ttu-id="8bf87-123">**Prikaži** pojedinosti o obogaćivanju brojem obogaćenih profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="8bf87-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="8bf87-124">**Uredi** konfiguraciju obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="8bf87-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="8bf87-125">**Pokreni** obogaćivanje za ažuriranje profila kupaca najnovijim podacima.</span><span class="sxs-lookup"><span data-stu-id="8bf87-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="8bf87-126">**Deaktiviraj** postojeće obogaćivanje za zaustavljanje automatskog osvježavanja prilikom svakog zakazanog osvježavanja.</span><span class="sxs-lookup"><span data-stu-id="8bf87-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="8bf87-127">Podaci iz posljednjeg uspješnog osvježavanja i dalje će biti dostupni.</span><span class="sxs-lookup"><span data-stu-id="8bf87-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="8bf87-128">**Aktiviraj** neaktivno obogaćivanje za ponovno pokretanje automatskog osvježavanja sa svakim zakazanim osvježavanjem.</span><span class="sxs-lookup"><span data-stu-id="8bf87-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="8bf87-129">**Izbrišite** obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="8bf87-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="8bf87-130">Možete pokrenuti ili deaktivirati više obogaćivanja odjednom njihovim odabirom na popisu.</span><span class="sxs-lookup"><span data-stu-id="8bf87-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="8bf87-131">Mogućnosti prikaza i uređivanja nisu dostupne kao skupna radnja i istovremeno rade samo za jedno obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="8bf87-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="8bf87-132">Obogaćivanja i veze</span><span class="sxs-lookup"><span data-stu-id="8bf87-132">Enrichments and connections</span></span>

<span data-ttu-id="8bf87-133">Obogaćivanja treće strane konfigurirana su pomoću [veza](connections.md) koje administrator postavlja s vjerodajnicama i daje pristanak za prijenos podataka.</span><span class="sxs-lookup"><span data-stu-id="8bf87-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="8bf87-134">Vezu mogu koristiti administratori i suradnici da bi konfigurirali obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="8bf87-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="8bf87-135">Višestruka obogaćivanja iste vrste</span><span class="sxs-lookup"><span data-stu-id="8bf87-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="8bf87-136">Entitet koji treba obogatiti naveden je tijekom konfiguracije obogaćivanja, što vam omogućuje obogaćivanje samo podskupina vaših profila.</span><span class="sxs-lookup"><span data-stu-id="8bf87-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="8bf87-137">Na primjer, obogatite podatke samo za određeni segment.</span><span class="sxs-lookup"><span data-stu-id="8bf87-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="8bf87-138">Možete konfigurirati nekoliko obogaćivanja iste vrste i ponovno koristiti istu vezu.</span><span class="sxs-lookup"><span data-stu-id="8bf87-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="8bf87-139">Neka obogaćivanja imat će ograničenja u broju obogaćivanja iste vrste koja se mogu stvoriti.</span><span class="sxs-lookup"><span data-stu-id="8bf87-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="8bf87-140">Ograničenja i trenutna upotreba mogu se vidjeti na stranici **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="8bf87-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
