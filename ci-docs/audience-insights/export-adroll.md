---
title: Izvoz podataka usluge Customer Insights u AdRoll
description: Saznajte kako konfigurirati vezu s uslugom AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697065"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="c38f4-103">Poveznik za AdRoll (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="c38f4-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="c38f4-104">Izvezite segmente objedinjenih profila klijenata u AdRoll i upotrijebite ih za oglašavanje.</span><span class="sxs-lookup"><span data-stu-id="c38f4-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c38f4-105">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="c38f4-105">Prerequisites</span></span>

-   <span data-ttu-id="c38f4-106">Imate [račun za AdRoll](https://www.adroll.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="c38f4-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c38f4-107">Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="c38f4-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c38f4-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="c38f4-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="c38f4-109">Poveži s platformom AdRoll</span><span class="sxs-lookup"><span data-stu-id="c38f4-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="c38f4-110">Otvorite **Administrator** > **Izvozna odredišta**.</span><span class="sxs-lookup"><span data-stu-id="c38f4-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c38f4-111">U odjeljku **AdRoll** odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="c38f4-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="c38f4-112">Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="c38f4-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfiguracijsko okno za vezu za AdRoll.":::

1. <span data-ttu-id="c38f4-114">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="c38f4-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c38f4-115">Odaberite **Poveži** za inicijalizaciju veze s uslugom AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c38f4-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="c38f4-116">Odaberite mogućnost **Provjera autentičnosti pomoću usluge AdRoll** i unesite svoje vjerodajnice administratora za AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c38f4-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="c38f4-117">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c38f4-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c38f4-118">Unesite svoj **ID oglašivača za AdRoll** [Pogodno za oglašavanje za AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="c38f4-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="c38f4-119">Odaberite **Dalje** da biste konfigurirali izvoz.</span><span class="sxs-lookup"><span data-stu-id="c38f4-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c38f4-120">Konfiguracija poveznika</span><span class="sxs-lookup"><span data-stu-id="c38f4-120">Configure the connector</span></span>

1. <span data-ttu-id="c38f4-121">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="c38f4-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c38f4-122">Potrebno je izvesti segmente u AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c38f4-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="c38f4-123">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="c38f4-123">Select the segments you want to export.</span></span> <span data-ttu-id="c38f4-124">Odaberite segment s najmanje 100 članova.</span><span class="sxs-lookup"><span data-stu-id="c38f4-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="c38f4-125">Ne možete izvesti manje segmente.</span><span class="sxs-lookup"><span data-stu-id="c38f4-125">You can't export smaller segments.</span></span> <span data-ttu-id="c38f4-126">Uz to, maksimalna veličina segmenta za izvoz je 250 000 članova po izvozu.</span><span class="sxs-lookup"><span data-stu-id="c38f4-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="c38f4-127">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="c38f4-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c38f4-128">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="c38f4-128">Export the data</span></span>

<span data-ttu-id="c38f4-129">Možete [izvesti podatke na zahtjev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c38f4-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c38f4-130">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c38f4-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c38f4-131">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="c38f4-131">Known limitations</span></span>

- <span data-ttu-id="c38f4-132">U AdRoll možete izvesti do 250 000 profila po izvozu.</span><span class="sxs-lookup"><span data-stu-id="c38f4-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="c38f4-133">Ne možete izvesti segmente s manje od 100 profila u AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c38f4-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="c38f4-134">Izvoz u AdRoll ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="c38f4-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="c38f4-135">Izvoz do 250 000 profila u AdRoll može potrajati do 10 minuta.</span><span class="sxs-lookup"><span data-stu-id="c38f4-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="c38f4-136">Broj profila koje možete izvesti u AdRoll ovisi i ograničen je vašim ugovorom s tvrtkom AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c38f4-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c38f4-137">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="c38f4-137">Data privacy and compliance</span></span>

<span data-ttu-id="c38f4-138">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u AdRoll, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="c38f4-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c38f4-139">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da AdRoll ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="c38f4-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c38f4-140">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c38f4-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="c38f4-141">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="c38f4-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
