---
title: Obogaćivanje pomoću obogaćivanja treće strane tvrke HERE Technologies
description: Opće informacije o obogaćivanju treće strane tvrtke HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668669"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="496f4-103">Obogaćivanje profila klijenata pomoću usluge HERE Technologies (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="496f4-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="496f4-104">HERE Technologies je tvrtka za lokacijsku platformu koja pruža podatke i usluge usmjerene na lokaciju.</span><span class="sxs-lookup"><span data-stu-id="496f4-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="496f4-105">Pomoću usluga obogaćivanja podataka tvrtke HERE Technologies možete stvoriti preciznije razumijevanje lokacije svojih klijenata uz normalizaciju adrese, izvlačenje zemljopisne širine i dužine i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="496f4-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="496f4-106">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="496f4-106">Prerequisites</span></span>

<span data-ttu-id="496f4-107">Da biste konfigurirali obogaćivanje usluge HERE Technologies, moraju biti ispunjeni sljedeći preduvjeti:</span><span class="sxs-lookup"><span data-stu-id="496f4-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="496f4-108">Imate aktivnu pretplatu za HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="496f4-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="496f4-109">Da biste dobili pretplatu, možete se [prijaviti ovdje](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ili izravno [kontaktirati tvrtku HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="496f4-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="496f4-110">Saznajte više o obogaćivanju lokacije tvrtke HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="496f4-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="496f4-111">Imate API ključ za HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="496f4-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="496f4-112">Imate dozvole [administratora](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="496f4-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="496f4-113">Konfiguracija</span><span class="sxs-lookup"><span data-stu-id="496f4-113">Configuration</span></span>

1. <span data-ttu-id="496f4-114">Idite na **Podaci** > **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="496f4-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="496f4-115">Odaberite **Obogaćivanje mojih podataka** na pločici za HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="496f4-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="496f4-116">![Pločica za HERE Technologies](media/HERE-tile.png "Pločica za HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="496f4-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="496f4-117">Unesite aktivni **API ključ za HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="496f4-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="496f4-118">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="496f4-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="496f4-119">Potvrdite oba unosa odabirom mogućnosti **Povezivanje s uslugom HERE**.</span><span class="sxs-lookup"><span data-stu-id="496f4-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="496f4-120">Odaberite **Dodavanje podataka** i odaberite želite li mapirati polja na primarnu i/ili sekundarnu adresu.</span><span class="sxs-lookup"><span data-stu-id="496f4-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="496f4-121">Možete odrediti mapiranje polja za obje adrese (na primjer, kućnu i poslovnu adresu) i obogatiti profile za obje adrese zasebno.</span><span class="sxs-lookup"><span data-stu-id="496f4-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="496f4-122">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="496f4-122">Select **Next**.</span></span>

1. <span data-ttu-id="496f4-123">Definirajte koja se polja iz vaših objedinjenih profila trebaju koristiti za traženje odgovarajućih podataka o lokaciji iz usluge HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="496f4-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="496f4-124">Polja **Ulica 1** i **Poštanski broj** su obavezna za odabranu primarnu i/ili sekundarnu adresu.</span><span class="sxs-lookup"><span data-stu-id="496f4-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="496f4-125">Za veću točnost podudaranja može se dodati više polja.</span><span class="sxs-lookup"><span data-stu-id="496f4-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="496f4-126">![Stranica za konfiguraciju obogaćivanja usluge HERE Technologies](media/enrichment-HERE-configuration.png "Stranica za konfiguraciju obogaćivanja usluge HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="496f4-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="496f4-127">Odaberite **Primijeni** za dovršetak mapiranja polja.</span><span class="sxs-lookup"><span data-stu-id="496f4-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="496f4-128">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="496f4-128">Enrichment results</span></span>

<span data-ttu-id="496f4-129">Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake.</span><span class="sxs-lookup"><span data-stu-id="496f4-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="496f4-130">Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="496f4-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="496f4-131">Vrijeme obrade ovisit će o veličini vaših podataka o klijentu i vremenu odziva API-ja u usluzi HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="496f4-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="496f4-132">Nakon završetka postupka obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod stavkom **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="496f4-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="496f4-133">Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="496f4-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="496f4-134">Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.</span><span class="sxs-lookup"><span data-stu-id="496f4-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="496f4-135">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="496f4-135">Next steps</span></span>

<span data-ttu-id="496f4-136">Nadogradite na svoje obogaćene podatke o klijentu.</span><span class="sxs-lookup"><span data-stu-id="496f4-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="496f4-137">Stvorite [segmente](segments.md), [mjere](measures.md), pa i [izvezite podatke](export-destinations.md) kako biste svojim klijentima pružili personalizirano iskustvo.</span><span class="sxs-lookup"><span data-stu-id="496f4-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="496f4-138">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="496f4-138">Data privacy and compliance</span></span>

<span data-ttu-id="496f4-139">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u HERE Technologies, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="496f4-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="496f4-140">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da HERE Technologies ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="496f4-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="496f4-141">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="496f4-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="496f4-142">Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="496f4-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
