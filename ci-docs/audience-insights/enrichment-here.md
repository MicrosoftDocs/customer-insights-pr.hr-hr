---
title: Obogaćivanje uz obogaćivanje treće strane HERE Technologies
description: Opće informacije o obogaćivanju treće strane tvrtke HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305285"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="bb574-103">Obogaćivanje profila klijenata pomoću usluge HERE Technologies (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="bb574-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="bb574-104">HERE Technologies je tvrtka za lokacijsku platformu koja pruža podatke i usluge usmjerene na lokaciju.</span><span class="sxs-lookup"><span data-stu-id="bb574-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="bb574-105">Pomoću usluga obogaćivanja podataka tvrtke HERE Technologies možete stvoriti preciznije razumijevanje lokacije svojih klijenata uz normalizaciju adrese, izvlačenje zemljopisne širine i dužine i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="bb574-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bb574-106">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="bb574-106">Prerequisites</span></span>

<span data-ttu-id="bb574-107">Da biste konfigurirali obogaćivanje usluge HERE Technologies, moraju biti ispunjeni sljedeći preduvjeti:</span><span class="sxs-lookup"><span data-stu-id="bb574-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="bb574-108">Imate aktivnu pretplatu za HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bb574-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="bb574-109">Da biste dobili pretplatu, možete se [prijaviti ovdje](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ili izravno [kontaktirati tvrtku HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="bb574-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="bb574-110">Saznajte više o obogaćivanju lokacije tvrtke HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bb574-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="bb574-111">Dostupna je [veza](connections.md) na HERE *ili* imate dozvole [administratora](permissions.md#administrator) i API ključ za HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bb574-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="bb574-112">Konfiguracija za obogaćivanje</span><span class="sxs-lookup"><span data-stu-id="bb574-112">Configure the enrichment</span></span>

1. <span data-ttu-id="bb574-113">Idite na **Podaci** > **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="bb574-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="bb574-114">Odaberite **Obogati moje podatke** na pločici HERE Technologies i odaberite **Započni**.</span><span class="sxs-lookup"><span data-stu-id="bb574-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bb574-115">![Pločica za HERE Technologies](media/HERE-tile.png "Pločica za HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="bb574-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="bb574-116">Odaberite [vezu](connections.md) s padajućeg popisa.</span><span class="sxs-lookup"><span data-stu-id="bb574-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="bb574-117">Ako nijedna veza nije dostupna, obratite se administratoru.</span><span class="sxs-lookup"><span data-stu-id="bb574-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="bb574-118">Ako ste administrator, vezu možete stvoriti odabirom **Dodaj vezu**.</span><span class="sxs-lookup"><span data-stu-id="bb574-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="bb574-119">Odaberite **HERE Technologies** na padajućem popisu.</span><span class="sxs-lookup"><span data-stu-id="bb574-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="bb574-120">Odaberite **Poveži se s HERE Technologies** za potvrdu odabira.</span><span class="sxs-lookup"><span data-stu-id="bb574-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="bb574-121">Odaberite **Sljedeće** i odaberite **Skup podataka klijenta** koji želite obogatiti lokacijskim podacima iz HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bb574-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="bb574-122">Možete odabrati entitet **Klijent** za obogaćivanje svih vaših korisničkih profila ili odaberite segmentni entitet za obogaćivanje samo korisničkih profila sadržanih u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="bb574-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Snimka zaslona prilikom odabira skupa podataka o klijentu.":::

1. <span data-ttu-id="bb574-124">Odaberite želite li mapirati polja na primarnu i/ili sekundarnu adresu.</span><span class="sxs-lookup"><span data-stu-id="bb574-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="bb574-125">Možete odrediti mapiranje polja za obje adrese i obogatiti profile za obje adrese zasebno.</span><span class="sxs-lookup"><span data-stu-id="bb574-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="bb574-126">Na primjer, ako postoji kućna i poslovna adresa.</span><span class="sxs-lookup"><span data-stu-id="bb574-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="bb574-127">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="bb574-127">Select **Next**.</span></span>

1. <span data-ttu-id="bb574-128">Definirajte koja se polja iz vaših objedinjenih profila trebaju koristiti za traženje odgovarajućih podataka o lokaciji iz usluge HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bb574-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="bb574-129">Polja **Ulica 1** i **Poštanski broj** su obavezna za odabranu primarnu i/ili sekundarnu adresu.</span><span class="sxs-lookup"><span data-stu-id="bb574-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="bb574-130">Za veću točnost podudaranja može se dodati više polja.</span><span class="sxs-lookup"><span data-stu-id="bb574-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bb574-131">![Stranica za konfiguraciju obogaćivanja usluge HERE Technologies](media/enrichment-HERE-configuration.png "Stranica za konfiguraciju obogaćivanja usluge HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="bb574-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="bb574-132">Odaberite **Sljedeće** da biste dovršili mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="bb574-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="bb574-133">Navedite naziv za obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="bb574-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="bb574-134">Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.</span><span class="sxs-lookup"><span data-stu-id="bb574-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="bb574-135">Konfiguriranje veze za HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="bb574-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="bb574-136">Morate biti administrator da biste konfigurirali veze.</span><span class="sxs-lookup"><span data-stu-id="bb574-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="bb574-137">Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćivanja *ili* idite na **Admin** > **Veze** i odaberite **Postavi** na pločici HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bb574-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="bb574-138">Unesite naziv za vezu u dijaloški okvir **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="bb574-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="bb574-139">Navedite valjani ključ za API za HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bb574-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="bb574-140">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom opcije **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="bb574-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="bb574-141">Odaberi **Potvrdi** za provjeru valjanosti konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="bb574-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="bb574-142">Nakon dovršetka provjere valjanosti odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="bb574-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bb574-143">![Stranica za konfiguraciju veze za HERE technologies](media/enrichment-HERE-connection.png "Stranica za konfiguraciju veze za HERE technologies")</span><span class="sxs-lookup"><span data-stu-id="bb574-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="bb574-144">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="bb574-144">Enrichment results</span></span>

<span data-ttu-id="bb574-145">Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake.</span><span class="sxs-lookup"><span data-stu-id="bb574-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="bb574-146">Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bb574-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bb574-147">Vrijeme obrade ovisit će o veličini vaših podataka o klijentu i vremenu odziva API-ja u usluzi HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bb574-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="bb574-148">Nakon završetka postupka obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod stavkom **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="bb574-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="bb574-149">Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="bb574-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="bb574-150">Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.</span><span class="sxs-lookup"><span data-stu-id="bb574-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bb574-151">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="bb574-151">Next steps</span></span>

<span data-ttu-id="bb574-152">Nadogradite na svoje obogaćene podatke o klijentu.</span><span class="sxs-lookup"><span data-stu-id="bb574-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="bb574-153">Stvorite [segmente](segments.md) i [mjere](measures.md), pa čak i [izvezite podatke](export-destinations.md) radi pružanja personaliziranih iskustava svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="bb574-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bb574-154">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="bb574-154">Data privacy and compliance</span></span>

<span data-ttu-id="bb574-155">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u HERE Technologies, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="bb574-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bb574-156">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da HERE Technologies ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="bb574-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bb574-157">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bb574-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bb574-158">Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="bb574-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
