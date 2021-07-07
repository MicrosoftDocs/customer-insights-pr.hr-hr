---
title: Izvoz podataka značajke Customer Insights u ActiveCampaign
description: Saznajte kako konfigurirati vezu i izvesti u ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314590"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="163f1-103">Izvoz segmenata u ActiveCampaign (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="163f1-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="163f1-104">Izvezite segmente objedinjenih profila kupaca u ActiveCampaign i upotrijebite ih za marketinške aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="163f1-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="163f1-105">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="163f1-105">Prerequisites</span></span>

-   <span data-ttu-id="163f1-106">Imate [račun za ActiveCampaign](https://www.activecampaign.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="163f1-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="163f1-107">Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="163f1-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="163f1-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje s adresom e-pošte.</span><span class="sxs-lookup"><span data-stu-id="163f1-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="163f1-109">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="163f1-109">Known limitations</span></span>

- <span data-ttu-id="163f1-110">Po izvozu u ActiveCampaign možete izvesti do 1 milijun profila, a dovršavanje može potrajati i do 90 minuta.</span><span class="sxs-lookup"><span data-stu-id="163f1-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="163f1-111">Izvoz u ActiveCampaign ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="163f1-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="163f1-112">Broj profila koje možete izvesti u ActiveCampaign ovisi o vašem ugovoru sa servisom ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="163f1-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="163f1-113">Postavljanje veze na ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="163f1-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="163f1-114">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="163f1-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="163f1-115">Odaberite **Dodavanje veze** pa odaberite **ActiveCampaign** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="163f1-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="163f1-116">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="163f1-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="163f1-117">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="163f1-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="163f1-118">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="163f1-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="163f1-119">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="163f1-119">Choose who can use this connection.</span></span> <span data-ttu-id="163f1-120">Prema zadanim postavkama to su samo administratori.</span><span class="sxs-lookup"><span data-stu-id="163f1-120">By default, it's only administrators.</span></span> <span data-ttu-id="163f1-121">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="163f1-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="163f1-122">Unesite svoj [ključ API-ja za ActiveCampaign i naziv hosta REST krajnje točke](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="163f1-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="163f1-123">Naziv glavnog računala krajnje točke za REST je samo naziv glavnog računala, bez https://.</span><span class="sxs-lookup"><span data-stu-id="163f1-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="163f1-124">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="163f1-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="163f1-125">Odaberite **Spoji** za pokretanje veze na ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="163f1-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="163f1-126">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="163f1-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="163f1-127">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="163f1-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="163f1-128">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="163f1-128">Configure an export</span></span>

<span data-ttu-id="163f1-129">Izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="163f1-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="163f1-130">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="163f1-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="163f1-131">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="163f1-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="163f1-132">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="163f1-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="163f1-133">U polju **Veza za izvoz** odaberite vezu iz odjeljka ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="163f1-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="163f1-134">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="163f1-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="163f1-135">Unesite svoj [**ID popisa za ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="163f1-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="163f1-136">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="163f1-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="163f1-137">Obvezno je izvoziti segmente u ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="163f1-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="163f1-138">Po želji možete izvesti Ime, Prezime, i Telefon da biste stvorili personaliziraniju e-poštu.</span><span class="sxs-lookup"><span data-stu-id="163f1-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="163f1-139">Odaberite Dodavanje atributa za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="163f1-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="163f1-140">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="163f1-140">Select **Save**.</span></span>

<span data-ttu-id="163f1-141">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="163f1-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="163f1-142">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="163f1-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="163f1-143">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="163f1-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="163f1-144">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="163f1-144">Data privacy and compliance</span></span>

<span data-ttu-id="163f1-145">Kad omogućite Dynamics 365 Customer Insights za prijenos podataka u ActiveCampaign dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke poput osobnih podataka.</span><span class="sxs-lookup"><span data-stu-id="163f1-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="163f1-146">Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da ActiveCampaign ispunjava sve obveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="163f1-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="163f1-147">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="163f1-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="163f1-148">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="163f1-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
