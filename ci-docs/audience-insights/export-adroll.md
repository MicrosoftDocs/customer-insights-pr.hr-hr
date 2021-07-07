---
title: Izvoz podataka usluge Customer Insights u AdRoll
description: Saznajte kako konfigurirati vezu i izvesti u AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304799"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="8e762-103">Izvoz segmenata u AdRoll (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="8e762-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="8e762-104">Izvezite segmente objedinjenih profila klijenata u AdRoll i upotrijebite ih za oglašavanje.</span><span class="sxs-lookup"><span data-stu-id="8e762-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="8e762-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="8e762-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="8e762-106">Imate [račun za AdRoll](https://www.adroll.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="8e762-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8e762-107">Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="8e762-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8e762-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="8e762-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8e762-109">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="8e762-109">Known limitations</span></span>

- <span data-ttu-id="8e762-110">Odjednom možete izvesti najviše 250.000 profila u AdRoll.</span><span class="sxs-lookup"><span data-stu-id="8e762-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="8e762-111">Ne možete izvesti segmente s manje od 100 profila u AdRoll.</span><span class="sxs-lookup"><span data-stu-id="8e762-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="8e762-112">Izvoz u AdRoll ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="8e762-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="8e762-113">Izvoz do 250.000 profila u AdRoll može potrajati do 10 minuta.</span><span class="sxs-lookup"><span data-stu-id="8e762-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="8e762-114">Broj profila koje možete izvesti u AdRoll ovisi o vašem ugovoru sa servisom AdRoll.</span><span class="sxs-lookup"><span data-stu-id="8e762-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="8e762-115">Postavljanje veze s AdRoll</span><span class="sxs-lookup"><span data-stu-id="8e762-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="8e762-116">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="8e762-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8e762-117">Odaberite **Dodaj vezu** i odaberite **AdRoll** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="8e762-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="8e762-118">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="8e762-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8e762-119">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="8e762-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8e762-120">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="8e762-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8e762-121">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="8e762-121">Choose who can use this connection.</span></span> <span data-ttu-id="8e762-122">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="8e762-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8e762-123">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8e762-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8e762-124">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="8e762-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8e762-125">Odaberite **Poveži** za inicijalizaciju veze s uslugom AdRoll.</span><span class="sxs-lookup"><span data-stu-id="8e762-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="8e762-126">Odaberite mogućnost **Provjera autentičnosti pomoću usluge AdRoll** i unesite svoje vjerodajnice administratora za AdRoll.</span><span class="sxs-lookup"><span data-stu-id="8e762-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="8e762-127">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8e762-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8e762-128">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="8e762-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8e762-129">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="8e762-129">Configure an export</span></span>

<span data-ttu-id="8e762-130">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="8e762-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8e762-131">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8e762-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8e762-132">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="8e762-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8e762-133">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="8e762-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8e762-134">U polju **Veza za izvoz** odaberite vezu iz odjeljka AdRoll.</span><span class="sxs-lookup"><span data-stu-id="8e762-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="8e762-135">Ako ne vidite naziv ovog odjeljka, tada vam nisu dostupne veze ove vrste.</span><span class="sxs-lookup"><span data-stu-id="8e762-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="8e762-136">Unesite svoj **ID oglašivača za AdRoll**.</span><span class="sxs-lookup"><span data-stu-id="8e762-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="8e762-137">Za više informacija pogledajte članak [Profili oglašivača za AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="8e762-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="8e762-138">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="8e762-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8e762-139">Potrebno je izvesti segmente u AdRoll.</span><span class="sxs-lookup"><span data-stu-id="8e762-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="8e762-140">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="8e762-140">Select the segments you want to export.</span></span> <span data-ttu-id="8e762-141">Odaberite segment s najmanje 100 članova.</span><span class="sxs-lookup"><span data-stu-id="8e762-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="8e762-142">Ne možete izvesti manje segmente.</span><span class="sxs-lookup"><span data-stu-id="8e762-142">You can't export smaller segments.</span></span> <span data-ttu-id="8e762-143">Uz to, maksimalna veličina segmenta za izvoz je 250.000 članova po izvozu.</span><span class="sxs-lookup"><span data-stu-id="8e762-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="8e762-144">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="8e762-144">Select **Save**.</span></span>

<span data-ttu-id="8e762-145">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="8e762-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8e762-146">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8e762-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="8e762-147">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8e762-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8e762-148">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="8e762-148">Data privacy and compliance</span></span>

<span data-ttu-id="8e762-149">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u AdRoll, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="8e762-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8e762-150">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da AdRoll ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="8e762-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8e762-151">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8e762-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="8e762-152">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="8e762-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
