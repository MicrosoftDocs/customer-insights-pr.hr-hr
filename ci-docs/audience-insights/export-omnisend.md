---
title: Izvoz podataka iz Customer Insights u Omnisend
description: Saznajte kako konfigurirati vezu i izvesti u Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124466"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="7aba3-103">Izvoz segmenata u Omnisend (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="7aba3-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="7aba3-104">Izvezite segmente objedinjenih profila klijenata u Omnisend i koristite ih za marketinške aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="7aba3-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7aba3-105">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="7aba3-105">Prerequisites</span></span>

-   <span data-ttu-id="7aba3-106">Imate [Račun za Omnisend](https://www.omnisend.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="7aba3-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7aba3-107">Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="7aba3-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="7aba3-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="7aba3-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7aba3-109">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="7aba3-109">Known limitations</span></span>

- <span data-ttu-id="7aba3-110">Po izvozu u Omnisend možete izvesti do 1 milijun profila, a dovršavanje može potrajati do 4 sata.</span><span class="sxs-lookup"><span data-stu-id="7aba3-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="7aba3-111">Izvoz u Omnisend ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="7aba3-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="7aba3-112">Broj profila koje možete izvesti u Omnisend ovisi o vašem ugovoru s tvrtkom Omnisend.</span><span class="sxs-lookup"><span data-stu-id="7aba3-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="7aba3-113">Postavljanje veze s uslugom Omnisend</span><span class="sxs-lookup"><span data-stu-id="7aba3-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="7aba3-114">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="7aba3-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7aba3-115">Odaberite **Dodaj vezu** i odaberite **Omnisend** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="7aba3-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="7aba3-116">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="7aba3-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7aba3-117">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="7aba3-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7aba3-118">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="7aba3-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7aba3-119">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="7aba3-119">Choose who can use this connection.</span></span> <span data-ttu-id="7aba3-120">Prema zadanim postavkama to su samo administratori.</span><span class="sxs-lookup"><span data-stu-id="7aba3-120">By default it's only administrators.</span></span> <span data-ttu-id="7aba3-121">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7aba3-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7aba3-122">Unesite svoj [Ključ za API za Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="7aba3-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="7aba3-123">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="7aba3-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7aba3-124">Odaberite **Poveži** za inicijalizaciju veze s uslugom Omnisend.</span><span class="sxs-lookup"><span data-stu-id="7aba3-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="7aba3-125">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7aba3-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7aba3-126">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="7aba3-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="7aba3-127">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="7aba3-127">Configure an export</span></span>

<span data-ttu-id="7aba3-128">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="7aba3-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7aba3-129">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7aba3-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7aba3-130">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="7aba3-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7aba3-131">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="7aba3-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7aba3-132">U polju **Veza za izvoz** odaberite vezu iz odjeljka Omnisend.</span><span class="sxs-lookup"><span data-stu-id="7aba3-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="7aba3-133">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="7aba3-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7aba3-134">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="7aba3-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7aba3-135">Obavezno je izvoziti segmente u Omnisend.</span><span class="sxs-lookup"><span data-stu-id="7aba3-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="7aba3-136">Ako želite, možete izvesti Ime, Prezime, Adresu, Državu/Regiju, Državu, Grad i Poštanski broj za stvaranje personaliziranije e-pošte.</span><span class="sxs-lookup"><span data-stu-id="7aba3-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="7aba3-137">Odaberite **Dodavanje atributa** za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="7aba3-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="7aba3-138">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="7aba3-138">Select **Save**.</span></span>

<span data-ttu-id="7aba3-139">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="7aba3-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7aba3-140">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7aba3-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7aba3-141">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7aba3-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7aba3-142">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="7aba3-142">Data privacy and compliance</span></span>

<span data-ttu-id="7aba3-143">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Ommisend, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="7aba3-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7aba3-144">Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Omnisend ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="7aba3-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7aba3-145">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7aba3-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="7aba3-146">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="7aba3-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
