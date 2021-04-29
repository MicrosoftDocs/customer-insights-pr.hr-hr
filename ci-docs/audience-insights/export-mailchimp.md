---
title: Izvoz podataka usluge Customer Insights u Mailchimp
description: Saznajte kako konfigurirati vezu i izvesti u Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759869"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="bb068-103">Izvoz popisa segmenata u Mailchimp (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="bb068-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="bb068-104">Izvezite segmente objedinjenih profila klijenata u Mailchimp da biste stvorili biltene i kampanje e-pošte.</span><span class="sxs-lookup"><span data-stu-id="bb068-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="bb068-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="bb068-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="bb068-106">Imate [račun za Mailchimp](https://mailchimp.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="bb068-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bb068-107">Mailchimp sadrži postojeće ciljne skupine i odgovarajuće ID-ove.</span><span class="sxs-lookup"><span data-stu-id="bb068-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="bb068-108">Dodatne informacije potražite u [ciljnim skupinama usluge Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="bb068-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="bb068-109">Imate [konfigurirane segmente](segments.md)</span><span class="sxs-lookup"><span data-stu-id="bb068-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="bb068-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="bb068-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bb068-111">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="bb068-111">Known limitations</span></span>

- <span data-ttu-id="bb068-112">Do 1 milijun profila po izvozu u Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bb068-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="bb068-113">Izvoz u Mailchimp ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="bb068-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="bb068-114">Izvoz segmenata s 1 milijun profila može potrajati do tri sata.</span><span class="sxs-lookup"><span data-stu-id="bb068-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="bb068-115">Broj profila koje možete izvesti u Mailchimp ovisi i ograničen je vašim ugovorom s tvrtkom Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bb068-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="bb068-116">Postavljanje veze s Mailchimp</span><span class="sxs-lookup"><span data-stu-id="bb068-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="bb068-117">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="bb068-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bb068-118">Odaberite **Dodaj vezu** i odaberite **Autopilot** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="bb068-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="bb068-119">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="bb068-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bb068-120">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="bb068-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bb068-121">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="bb068-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bb068-122">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="bb068-122">Choose who can use this connection.</span></span> <span data-ttu-id="bb068-123">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="bb068-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bb068-124">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bb068-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bb068-125">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="bb068-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bb068-126">Odaberite **Poveži** za inicijalizaciju veze s Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bb068-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="bb068-127">Odaberite mogućnost **Provjera autentičnosti pomoću usluge Mailchimp** i unesite svoje vjerodajnice za Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bb068-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="bb068-128">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bb068-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bb068-129">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="bb068-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="bb068-130">Konfiguracija poveznika</span><span class="sxs-lookup"><span data-stu-id="bb068-130">Configure the connector</span></span>

<span data-ttu-id="bb068-131">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="bb068-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bb068-132">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bb068-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bb068-133">Idite na **Podaci**> **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="bb068-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="bb068-134">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="bb068-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bb068-135">U polju **Veza za izvoz** odaberite vezu iz odjeljka Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bb068-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="bb068-136">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="bb068-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bb068-137">Unesite svoj **[ID ciljne skupine za Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="bb068-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="bb068-138">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="bb068-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="bb068-139">Neobavezno možete izvesti **Ime** i **Prezime** za stvaranje personaliziranije e-pošte.</span><span class="sxs-lookup"><span data-stu-id="bb068-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="bb068-140">Odaberite **Dodavanje atributa** za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="bb068-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="bb068-141">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="bb068-141">Select the segments you want to export.</span></span> <span data-ttu-id="bb068-142">U Mailchimp možete ukupno izvesti do 1 milijun profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="bb068-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="bb068-143">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="bb068-143">Select **Save**.</span></span>

<span data-ttu-id="bb068-144">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="bb068-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bb068-145">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bb068-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bb068-146">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bb068-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bb068-147">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="bb068-147">Data privacy and compliance</span></span>

<span data-ttu-id="bb068-148">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Mailchimp, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="bb068-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bb068-149">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Mailchimp ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="bb068-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bb068-150">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bb068-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bb068-151">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="bb068-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
