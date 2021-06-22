---
title: Izvoz podataka iz Customer Insights u LinkedIn Ads
description: Saznajte kako konfigurirati vezu i izvesti u LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124467"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="b24a5-103">Izvoz segmenata u LinkedIn Ads (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="b24a5-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="b24a5-104">Izvezite segmente objedinjenih profila klijenata u LinkedIn Ads kako biste stvorili podudarne ciljne skupine.</span><span class="sxs-lookup"><span data-stu-id="b24a5-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="b24a5-105">Upotrijebite podudarne ciljne publike za ciljanje tvrtki i ciljanje kontakata.</span><span class="sxs-lookup"><span data-stu-id="b24a5-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b24a5-106">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="b24a5-106">Prerequisites</span></span>

-   <span data-ttu-id="b24a5-107">Imate [Račun za LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="b24a5-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b24a5-108">Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="b24a5-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b24a5-109">Profili klijenata u izvezenim segmentima sadrže polje s adresom e-pošte.</span><span class="sxs-lookup"><span data-stu-id="b24a5-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b24a5-110">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="b24a5-110">Known limitations</span></span>

- <span data-ttu-id="b24a5-111">Možete izvesti do 100 000 profila po izvozu u LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="b24a5-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="b24a5-112">Izvoz u LinkedIn Ads ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="b24a5-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="b24a5-113">Izvoz do 100 000 profila u LinkedIn Ads može potrajati do 10 minuta.</span><span class="sxs-lookup"><span data-stu-id="b24a5-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="b24a5-114">Postavljanje veze s uslugom LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="b24a5-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="b24a5-115">U uvidima u ciljnu skupinu idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="b24a5-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b24a5-116">Odaberite **Dodaj vezu** i odaberite **LinkedIn Ads** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="b24a5-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="b24a5-117">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="b24a5-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b24a5-118">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="b24a5-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b24a5-119">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="b24a5-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b24a5-120">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="b24a5-120">Choose who can use this connection.</span></span> <span data-ttu-id="b24a5-121">Ako ništa ne poduzmete, prema zadanim će postavkama biti administratori.</span><span class="sxs-lookup"><span data-stu-id="b24a5-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="b24a5-122">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b24a5-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b24a5-123">Navedite svoj [ID računa za LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="b24a5-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="b24a5-124">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="b24a5-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b24a5-125">Odaberite **Poveži** za inicijalizaciju veze s Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="b24a5-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="b24a5-126">Odaberite **Provjeri autentičnost uz LinkedIn** i pružite svoje administratorske vjerodajnice za LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="b24a5-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="b24a5-127">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b24a5-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b24a5-128">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="b24a5-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b24a5-129">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="b24a5-129">Configure an export</span></span>

<span data-ttu-id="b24a5-130">Izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="b24a5-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="b24a5-131">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b24a5-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b24a5-132">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="b24a5-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b24a5-133">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="b24a5-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b24a5-134">U polju **Veza za izvoz** odaberite vezu iz odjeljka LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="b24a5-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="b24a5-135">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="b24a5-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b24a5-136">Odaberite želite li izvesti podatke radi [ciljanja kontakata](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ili [ciljanja tvrtki](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) u usluzi LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="b24a5-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="b24a5-137">U odjeljku **Podudaranje podataka** odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="b24a5-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b24a5-138">Obavezno je izvoziti segmente u LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="b24a5-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="b24a5-139">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="b24a5-139">Select the segments you want to export.</span></span> <span data-ttu-id="b24a5-140">Podudarne ciljne skupine u alatu LinkedIn Campaign Manager automatski će se stvoriti s nazivom segmenata koje ste odabrali za izvoz.</span><span class="sxs-lookup"><span data-stu-id="b24a5-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="b24a5-141">Svaki će segment rezultirati zasebnom podudarnom ciljnom skupinom.</span><span class="sxs-lookup"><span data-stu-id="b24a5-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="b24a5-142">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="b24a5-142">Select **Save**.</span></span>

<span data-ttu-id="b24a5-143">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="b24a5-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b24a5-144">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b24a5-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b24a5-145">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b24a5-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b24a5-146">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="b24a5-146">Data privacy and compliance</span></span>

<span data-ttu-id="b24a5-147">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u LinkedIn Ads, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="b24a5-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b24a5-148">Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da LinkedIn Ads ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="b24a5-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b24a5-149">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b24a5-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="b24a5-150">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="b24a5-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
