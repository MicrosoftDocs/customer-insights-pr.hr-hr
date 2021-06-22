---
title: Izvoz podataka usluge Customer Insights u Microsoftovo oglašavanje
description: Saznajte kako konfigurirati vezu i izvesti u Microsoftovo oglašavanje.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124465"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="5b053-103">Izvoz segmenata u Microsoftovo oglašavanje (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="5b053-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="5b053-104">Izvezite segmente usluge Customer Insights u Microsoftovo oglašavanje da biste stvorili ciljne skupine Podudaranje klijenta.</span><span class="sxs-lookup"><span data-stu-id="5b053-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="5b053-105">Upotrijebite ove ciljne skupine za svoje reklamne kampanje.</span><span class="sxs-lookup"><span data-stu-id="5b053-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5b053-106">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="5b053-106">Prerequisites</span></span>

-   <span data-ttu-id="5b053-107">[Račun za Microsoftovo oglašavanje](https://ads.microsoft.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="5b053-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5b053-108">Prihvatili ste uvjete korištenja Podudaranja klijenata.</span><span class="sxs-lookup"><span data-stu-id="5b053-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="5b053-109">[Konfigurirani segmenti](segments.md) u uvidima u ciljne skupine.</span><span class="sxs-lookup"><span data-stu-id="5b053-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5b053-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje s adresom e-pošte.</span><span class="sxs-lookup"><span data-stu-id="5b053-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5b053-111">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="5b053-111">Known limitations</span></span>

- <span data-ttu-id="5b053-112">Možete izvesti do 500 000 profila po izvozu u Microsoftovo oglašavanje.</span><span class="sxs-lookup"><span data-stu-id="5b053-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="5b053-113">Izvoz u Microsoftovo oglašavanje ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="5b053-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="5b053-114">Izvoz do 500 000 profila u Microsoftovo oglašavanje može potrajati do 10 minuta.</span><span class="sxs-lookup"><span data-stu-id="5b053-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="5b053-115">Postavljanje veze s Microsoftovim oglašavanjem</span><span class="sxs-lookup"><span data-stu-id="5b053-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="5b053-116">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="5b053-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5b053-117">Odaberite **Dodaj vezu** i odaberite **Microsoftovo oglašavanje** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="5b053-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="5b053-118">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="5b053-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5b053-119">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="5b053-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5b053-120">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="5b053-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5b053-121">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="5b053-121">Choose who can use this connection.</span></span> <span data-ttu-id="5b053-122">Zadana postavka su administratori.</span><span class="sxs-lookup"><span data-stu-id="5b053-122">The default is administrators.</span></span> <span data-ttu-id="5b053-123">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5b053-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5b053-124">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="5b053-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5b053-125">Odaberite **Poveži** za inicijalizaciju veze s Microsoftovim oglašavanjem.</span><span class="sxs-lookup"><span data-stu-id="5b053-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="5b053-126">Odaberite **Provjeri autentičnost uz Microsoftovo oglašavanje** i pružite svoje administratorske vjerodajnice za Microsoftovo oglašavanje.</span><span class="sxs-lookup"><span data-stu-id="5b053-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="5b053-127">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5b053-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5b053-128">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="5b053-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5b053-129">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="5b053-129">Configure an export</span></span>

<span data-ttu-id="5b053-130">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="5b053-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5b053-131">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5b053-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5b053-132">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="5b053-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5b053-133">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="5b053-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5b053-134">U polju **Veza za izvoz** odaberite vezu iz odjeljka Microsoftovo oglašavanje.</span><span class="sxs-lookup"><span data-stu-id="5b053-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="5b053-135">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="5b053-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5b053-136">Odaberite segmente za izvoz.</span><span class="sxs-lookup"><span data-stu-id="5b053-136">Select the segments to export.</span></span> <span data-ttu-id="5b053-137">Ciljne skupine Podudaranje klijenata u Microsoftovom oglašavanju stvaraju se automatski s nazivom segmenata odabranih za izvoz.</span><span class="sxs-lookup"><span data-stu-id="5b053-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="5b053-138">Svaki će segment rezultirati zasebnom ciljnom skupinom Podudaranje klijenata.</span><span class="sxs-lookup"><span data-stu-id="5b053-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="5b053-139">Unesite svoj **ID klijenta Microsoftova oglašavanja i ID računa**.</span><span class="sxs-lookup"><span data-stu-id="5b053-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="5b053-140">ID klijenta (`cid`) i ID računa (`aid`) možete pronaći u parametrima URL-a kada ste prijavljeni u Microsoftovo oglašavanje.</span><span class="sxs-lookup"><span data-stu-id="5b053-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="5b053-141">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta sa adresom e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="5b053-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="5b053-142">Obavezno je izvoziti segmente u Microsoftovo oglašavanje.</span><span class="sxs-lookup"><span data-stu-id="5b053-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="5b053-143">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="5b053-143">Select **Save**.</span></span>

<span data-ttu-id="5b053-144">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="5b053-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5b053-145">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5b053-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5b053-146">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5b053-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5b053-147">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="5b053-147">Data privacy and compliance</span></span>

<span data-ttu-id="5b053-148">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Microsoftovo oglašavanje, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="5b053-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5b053-149">Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Microsoftovo oglašavanje ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="5b053-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5b053-150">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5b053-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="5b053-151">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="5b053-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
