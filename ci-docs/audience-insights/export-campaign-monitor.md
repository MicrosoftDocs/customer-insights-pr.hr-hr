---
title: Izvoz podataka o Customer Insights u Campaign Monitor
description: Saznajte kako konfigurirati vezu i izvesti u Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760492"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a><span data-ttu-id="27205-103">Izvoz popisa segmenata u Campaign Monitor (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="27205-103">Export segment lists to Campaign Monitor (preview)</span></span>

<span data-ttu-id="27205-104">Izvezite segmente objedinjenih profila klijenata u Campaign Monitor i koristite ih za marketinške aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="27205-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="27205-105">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="27205-105">Prerequisites</span></span>

-   <span data-ttu-id="27205-106">Imate [Račun Campaign Monitor](https://www.campaignmonitor.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="27205-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="27205-107">Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="27205-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="27205-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="27205-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="27205-109">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="27205-109">Known limitations</span></span>

- <span data-ttu-id="27205-110">Možete izvesti do 1 milijun profila po izvozu u Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="27205-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="27205-111">Izvoz u Campaign Monitor ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="27205-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="27205-112">Izvoz do 1 milijun profila u Campaign Monitor može potrajati do 20 minuta.</span><span class="sxs-lookup"><span data-stu-id="27205-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="27205-113">Broj profila koje možete izvesti u Campaign Monitor ovisi i ograničen je vašim ugovorom s tvrtkom Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="27205-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="27205-114">Postavljanje veze s Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="27205-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="27205-115">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="27205-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="27205-116">Odaberite **Dodaj vezu** i odaberite **Campaign Monitor** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="27205-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="27205-117">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="27205-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="27205-118">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="27205-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="27205-119">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="27205-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="27205-120">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="27205-120">Choose who can use this connection.</span></span> <span data-ttu-id="27205-121">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="27205-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="27205-122">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="27205-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="27205-123">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="27205-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="27205-124">Odaberite **Poveži** za inicijalizaciju veze s Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="27205-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="27205-125">Odaberite **Provjeri autentičnost uz Campaign Monitor** i pružite svoje administratorske vjerodajnice za Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="27205-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="27205-126">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="27205-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="27205-127">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="27205-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="27205-128">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="27205-128">Configure an export</span></span>

<span data-ttu-id="27205-129">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="27205-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="27205-130">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="27205-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="27205-131">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="27205-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="27205-132">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="27205-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="27205-133">U polju **Veza za izvoz** odaberite vezu iz odjeljka Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="27205-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="27205-134">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="27205-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="27205-135">Unesite svoj [**ID popisa za Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="27205-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="27205-136">[Generirajte ključ za API](https://www.campaignmonitor.com/api/getting-started/) iz **Postavke računa** u Campaign Monitor kao prvo da biste prikazali ID popisa za API.</span><span class="sxs-lookup"><span data-stu-id="27205-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="27205-137">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="27205-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="27205-138">Obavezno je izvoziti segmente u Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="27205-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="27205-139">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="27205-139">Select **Save**.</span></span>

<span data-ttu-id="27205-140">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="27205-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="27205-141">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="27205-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="27205-142">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="27205-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="27205-143">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="27205-143">Data privacy and compliance</span></span>

<span data-ttu-id="27205-144">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Campaign Monitor dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="27205-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="27205-145">Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Campaign Monitor ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="27205-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="27205-146">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="27205-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="27205-147">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="27205-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
