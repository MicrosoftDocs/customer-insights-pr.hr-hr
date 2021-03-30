---
title: Obogaćivanje pomoću obogaćivanja treće strane tvrke HERE Technologies
description: Opće informacije o obogaćivanju treće strane tvrtke HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597732"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="3d8df-103">Obogaćivanje profila klijenata pomoću usluge HERE Technologies (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="3d8df-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="3d8df-104">HERE Technologies je tvrtka za lokacijsku platformu koja pruža podatke i usluge usmjerene na lokaciju.</span><span class="sxs-lookup"><span data-stu-id="3d8df-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="3d8df-105">Pomoću usluga obogaćivanja podataka tvrtke HERE Technologies možete stvoriti preciznije razumijevanje lokacije svojih klijenata uz normalizaciju adrese, izvlačenje zemljopisne širine i dužine i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="3d8df-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3d8df-106">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="3d8df-106">Prerequisites</span></span>

<span data-ttu-id="3d8df-107">Da biste konfigurirali obogaćivanje usluge HERE Technologies, moraju biti ispunjeni sljedeći preduvjeti:</span><span class="sxs-lookup"><span data-stu-id="3d8df-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3d8df-108">Imate aktivnu pretplatu za HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3d8df-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="3d8df-109">Da biste dobili pretplatu, možete se [prijaviti ovdje](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ili izravno [kontaktirati tvrtku HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="3d8df-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="3d8df-110">Saznajte više o obogaćivanju lokacije tvrtke HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3d8df-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="3d8df-111">Imate API ključ za HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3d8df-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="3d8df-112">Imate dozvole [administratora](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="3d8df-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="3d8df-113">Konfiguracija</span><span class="sxs-lookup"><span data-stu-id="3d8df-113">Configuration</span></span>

1. <span data-ttu-id="3d8df-114">Idite na **Podaci** > **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="3d8df-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="3d8df-115">Odaberite **Obogaćivanje mojih podataka** na pločici za HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3d8df-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3d8df-116">![Pločica za HERE Technologies](media/HERE-tile.png "Pločica za HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="3d8df-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="3d8df-117">Unesite aktivni **API ključ za HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="3d8df-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="3d8df-118">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="3d8df-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="3d8df-119">Potvrdite oba unosa odabirom mogućnosti **Povezivanje s uslugom HERE**.</span><span class="sxs-lookup"><span data-stu-id="3d8df-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="3d8df-120">Odaberite **Dodaj podatke** i odaberite **Skup korisničkih podataka** koji želite obogatiti podacima o mjestu iz sustava HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3d8df-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="3d8df-121">Možete odabrati entitet **Klijent** za obogaćivanje svih vaših korisničkih profila ili odaberite segmentni entitet za obogaćivanje samo korisničkih profila sadržanih u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="3d8df-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Snimka zaslona prilikom odabira skupa podataka o klijentu.":::

1. <span data-ttu-id="3d8df-123">Odaberite želite li mapirati polja na primarnu i/ili sekundarnu adresu.</span><span class="sxs-lookup"><span data-stu-id="3d8df-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="3d8df-124">Možete odrediti mapiranje polja za obje adrese (na primjer, kućnu i poslovnu adresu) i obogatiti profile za obje adrese zasebno.</span><span class="sxs-lookup"><span data-stu-id="3d8df-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="3d8df-125">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="3d8df-125">Select **Next**.</span></span>

1. <span data-ttu-id="3d8df-126">Definirajte koja se polja iz vaših objedinjenih profila trebaju koristiti za traženje odgovarajućih podataka o lokaciji iz usluge HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3d8df-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="3d8df-127">Polja **Ulica 1** i **Poštanski broj** su obavezna za odabranu primarnu i/ili sekundarnu adresu.</span><span class="sxs-lookup"><span data-stu-id="3d8df-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="3d8df-128">Za veću točnost podudaranja može se dodati više polja.</span><span class="sxs-lookup"><span data-stu-id="3d8df-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3d8df-129">![Stranica za konfiguraciju obogaćivanja usluge HERE Technologies](media/enrichment-HERE-configuration.png "Stranica za konfiguraciju obogaćivanja usluge HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="3d8df-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="3d8df-130">Odaberite **Primijeni** za dovršetak mapiranja polja.</span><span class="sxs-lookup"><span data-stu-id="3d8df-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="3d8df-131">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="3d8df-131">Enrichment results</span></span>

<span data-ttu-id="3d8df-132">Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake.</span><span class="sxs-lookup"><span data-stu-id="3d8df-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="3d8df-133">Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3d8df-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3d8df-134">Vrijeme obrade ovisit će o veličini vaših podataka o klijentu i vremenu odziva API-ja u usluzi HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3d8df-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="3d8df-135">Nakon završetka postupka obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod stavkom **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="3d8df-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="3d8df-136">Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="3d8df-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3d8df-137">Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.</span><span class="sxs-lookup"><span data-stu-id="3d8df-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3d8df-138">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="3d8df-138">Next steps</span></span>

<span data-ttu-id="3d8df-139">Nadogradite na svoje obogaćene podatke o klijentu.</span><span class="sxs-lookup"><span data-stu-id="3d8df-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3d8df-140">Stvorite [segmente](segments.md), [mjere](measures.md), pa i [izvezite podatke](export-destinations.md) kako biste svojim klijentima pružili personalizirano iskustvo.</span><span class="sxs-lookup"><span data-stu-id="3d8df-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3d8df-141">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="3d8df-141">Data privacy and compliance</span></span>

<span data-ttu-id="3d8df-142">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u HERE Technologies, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="3d8df-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3d8df-143">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da HERE Technologies ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="3d8df-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3d8df-144">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3d8df-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3d8df-145">Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="3d8df-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]