---
title: Izvoz podataka usluge Customer Insights u Autopilot
description: Saznajte kako konfigurirati vezu i izvesti u Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760134"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="f59e0-103">Izvoz segmenata u Autopilot (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="f59e0-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="f59e0-104">Izvezite segmente objedinjenih profila klijenata u Autopilot i koristite ih za marketing putem e-pošte u usluzi Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f59e0-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f59e0-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="f59e0-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f59e0-106">Imate [račun za Autopilot](https://www.autopilothq.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="f59e0-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f59e0-107">Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="f59e0-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f59e0-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="f59e0-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f59e0-109">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="f59e0-109">Known limitations</span></span>

- <span data-ttu-id="f59e0-110">U Autopilot možete ukupno izvesti do 100 000 profila.</span><span class="sxs-lookup"><span data-stu-id="f59e0-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="f59e0-111">Izvoz u Autopilot ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="f59e0-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="f59e0-112">Izvoz do 100 000 profila u Autopilot može potrajati do nekoliko sati.</span><span class="sxs-lookup"><span data-stu-id="f59e0-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="f59e0-113">Broj profila koje možete izvesti u Autopilot ovisi i ograničen je vašim ugovorom s tvrtkom Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f59e0-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="f59e0-114">Postavljanje veze s Autopilot</span><span class="sxs-lookup"><span data-stu-id="f59e0-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="f59e0-115">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="f59e0-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f59e0-116">Odaberite **Dodaj vezu** i odaberite **Autopilot** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="f59e0-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="f59e0-117">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="f59e0-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f59e0-118">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="f59e0-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f59e0-119">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="f59e0-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f59e0-120">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="f59e0-120">Choose who can use this connection.</span></span> <span data-ttu-id="f59e0-121">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="f59e0-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f59e0-122">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f59e0-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="f59e0-123">Unesite svoj [Ključ za API za Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="f59e0-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="f59e0-124">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="f59e0-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f59e0-125">Odaberite **Poveži** za inicijalizaciju veze s uslugom Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f59e0-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="f59e0-126">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f59e0-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f59e0-127">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="f59e0-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f59e0-128">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="f59e0-128">Configure an export</span></span>

<span data-ttu-id="f59e0-129">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="f59e0-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f59e0-130">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f59e0-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f59e0-131">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="f59e0-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f59e0-132">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="f59e0-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f59e0-133">U polju **Veza za izvoz** odaberite vezu iz odjeljka Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f59e0-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="f59e0-134">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="f59e0-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="f59e0-135">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="f59e0-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f59e0-136">Ponovite iste korake za ostala neobavezna polja kao što su **Ime**, **Prezime**.</span><span class="sxs-lookup"><span data-stu-id="f59e0-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="f59e0-137">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="f59e0-137">Select the segments you want to export.</span></span> <span data-ttu-id="f59e0-138">Snažno **preporučujemo da ne izvozite više od ukupno 100 000 profila klijenata** u uslugu Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f59e0-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="f59e0-139">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="f59e0-139">Select **Save**.</span></span>

<span data-ttu-id="f59e0-140">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="f59e0-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f59e0-141">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f59e0-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f59e0-142">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f59e0-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f59e0-143">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="f59e0-143">Data privacy and compliance</span></span>

<span data-ttu-id="f59e0-144">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Autopilot, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="f59e0-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f59e0-145">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Autopilot ispunjava sve obaveze zaštite privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="f59e0-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f59e0-146">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f59e0-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f59e0-147">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="f59e0-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
