---
title: Izvoz podataka iz Customer Insights u RollWorks
description: Saznajte kako konfigurirati vezu i izvesti u RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760493"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="62522-103">Izvoz popisa segmenata u RollWorks (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="62522-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="62522-104">Izvezite segmente objedinjenih profila klijenata u RollWorks i koristite ih za oglašavanje.</span><span class="sxs-lookup"><span data-stu-id="62522-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="62522-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="62522-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="62522-106">Imate [Račun za RollWorks](https://www.rollworks.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="62522-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="62522-107">Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="62522-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="62522-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="62522-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="62522-109">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="62522-109">Known limitations</span></span>

- <span data-ttu-id="62522-110">Možete izvesti do 250 000 profila po izvozu u RollWorks.</span><span class="sxs-lookup"><span data-stu-id="62522-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="62522-111">Ne možete izvesti segmente s manje od 100 profila u RollWorks.</span><span class="sxs-lookup"><span data-stu-id="62522-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="62522-112">Izvoz u RollWorks ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="62522-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="62522-113">Izvoz do 250 000 profila u RollWorks može potrajati do 10 minuta.</span><span class="sxs-lookup"><span data-stu-id="62522-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="62522-114">Broj profila koje možete izvesti u RollWorks ovisi i ograničen je vašim ugovorom s tvrtkom RollWorks.</span><span class="sxs-lookup"><span data-stu-id="62522-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="62522-115">Postavljanje veze s RollWorks</span><span class="sxs-lookup"><span data-stu-id="62522-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="62522-116">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="62522-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="62522-117">Odaberite **Dodaj vezu** i odaberite **RollWorks** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="62522-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="62522-118">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="62522-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="62522-119">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="62522-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="62522-120">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="62522-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="62522-121">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="62522-121">Choose who can use this connection.</span></span> <span data-ttu-id="62522-122">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="62522-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="62522-123">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="62522-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="62522-124">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="62522-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="62522-125">Odaberite **Poveži** za inicijalizaciju veze s RollWorks.</span><span class="sxs-lookup"><span data-stu-id="62522-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="62522-126">Odaberite **Provjeri autentičnost uz RollWorks** i pružite svoje administratorske vjerodajnice za RollWorks.</span><span class="sxs-lookup"><span data-stu-id="62522-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="62522-127">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="62522-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="62522-128">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="62522-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="62522-129">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="62522-129">Configure an export</span></span>

<span data-ttu-id="62522-130">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="62522-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="62522-131">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="62522-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="62522-132">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="62522-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="62522-133">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="62522-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="62522-134">U polju **Veza za izvoz** odaberite vezu iz odjeljka RollWorks.</span><span class="sxs-lookup"><span data-stu-id="62522-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="62522-135">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="62522-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="62522-136">Unesite svoj **ID oglašivača za RollWorks** [Oglas za RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="62522-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="62522-137">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="62522-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="62522-138">Obavezno je izvoziti segmente u RollWorks.</span><span class="sxs-lookup"><span data-stu-id="62522-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="62522-139">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="62522-139">Select the segments you want to export.</span></span> <span data-ttu-id="62522-140">Odaberite segment s najmanje 100 članova.</span><span class="sxs-lookup"><span data-stu-id="62522-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="62522-141">Ne možete izvesti manje segmente.</span><span class="sxs-lookup"><span data-stu-id="62522-141">You can't export smaller segments.</span></span> <span data-ttu-id="62522-142">Uz to, maksimalna veličina segmenta za izvoz je 250 000 članova po izvozu.</span><span class="sxs-lookup"><span data-stu-id="62522-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="62522-143">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="62522-143">Select **Save**.</span></span>

<span data-ttu-id="62522-144">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="62522-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="62522-145">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="62522-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="62522-146">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="62522-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="62522-147">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="62522-147">Data privacy and compliance</span></span>

<span data-ttu-id="62522-148">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u RollWorks dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="62522-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="62522-149">Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da RollWorks ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="62522-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="62522-150">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="62522-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="62522-151">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="62522-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
