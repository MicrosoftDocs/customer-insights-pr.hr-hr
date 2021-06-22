---
title: Izvoz podataka iz Customer Insights u Snapchat
description: Saznajte kako konfigurirati vezu i izvesti u Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124034"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="f3ffe-103">Izvoz segmenata u Snapchat (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="f3ffe-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="f3ffe-104">Izvezite segmente objedinjenih profila klijenata u Snapchat i koristite ih za oglašavanje.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f3ffe-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="f3ffe-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f3ffe-106">Imate [Snapchat poslovni račun](https://business.snapchat.com/), [Snapchat Ads račun](https://ads.snapchat.com/) i odgovarajuće administratorske vjerodajnice.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f3ffe-107">Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f3ffe-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f3ffe-109">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="f3ffe-109">Known limitations</span></span>

- <span data-ttu-id="f3ffe-110">Izvoz u Snapchat ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="f3ffe-111">Izvoz do 1 milijun profila u Snapchat može potrajati do 15 minuta.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="f3ffe-112">Postavljanje veze za Snapchat</span><span class="sxs-lookup"><span data-stu-id="f3ffe-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="f3ffe-113">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f3ffe-114">Odaberite **Dodaj vezu** i odaberite **Snapchat** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="f3ffe-115">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f3ffe-116">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f3ffe-117">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f3ffe-118">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-118">Choose who can use this connection.</span></span> <span data-ttu-id="f3ffe-119">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f3ffe-120">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f3ffe-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f3ffe-121">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f3ffe-122">Odaberite **Poveži** za inicijalizaciju veze sa Snapchat.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="f3ffe-123">Odaberite **Provjeri autentičnost uz Snapchat** i pružite svoje administratorske vjerodajnice za Snapchat.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="f3ffe-124">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f3ffe-125">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f3ffe-126">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="f3ffe-126">Configure an export</span></span>

<span data-ttu-id="f3ffe-127">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f3ffe-128">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f3ffe-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f3ffe-129">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f3ffe-130">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f3ffe-131">U polju **Veza za izvoz** odaberite vezu iz odjeljka Snapchat.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="f3ffe-132">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f3ffe-133">Unesite [**ID ciljne skupine za Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="f3ffe-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="f3ffe-134">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f3ffe-135">Obavezno je izvoziti segmente u Snapchat.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="f3ffe-136">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="f3ffe-137">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-137">Select **Save**.</span></span>

<span data-ttu-id="f3ffe-138">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f3ffe-139">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f3ffe-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f3ffe-140">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f3ffe-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f3ffe-141">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="f3ffe-141">Data privacy and compliance</span></span>

<span data-ttu-id="f3ffe-142">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Snapchat dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f3ffe-143">Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Snapchat ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f3ffe-144">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f3ffe-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="f3ffe-145">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="f3ffe-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
