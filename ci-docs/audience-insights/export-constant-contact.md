---
title: Izvoz podataka o Customer Insights u Constant Contact
description: Saznajte kako konfigurirati vezu i izvesti u Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760491"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="78a40-103">Izvoz popisa segmenata u Constant Contact (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="78a40-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="78a40-104">Izvezite segmente objedinjenih profila klijenata u Constant Contact i koristite ih za marketinške aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="78a40-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="78a40-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="78a40-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="78a40-106">Imate [Račun Constant Contact](https://www.constantcontact.com/account-home) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="78a40-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="78a40-107">Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="78a40-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="78a40-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="78a40-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="78a40-109">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="78a40-109">Known limitations</span></span>

- <span data-ttu-id="78a40-110">Možete izvesti do 1 milijun profila po izvozu u Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="78a40-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="78a40-111">Izvoz u Constant Contact ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="78a40-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="78a40-112">Izvoz do 1 milijun profila u Constant Contact može potrajati do 1 sat.</span><span class="sxs-lookup"><span data-stu-id="78a40-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="78a40-113">Broj profila koje možete izvesti u Constant Contact ovisi i ograničen je vašim ugovorom s tvrtkom Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="78a40-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="78a40-114">Postavljanje veze s Constant Contact</span><span class="sxs-lookup"><span data-stu-id="78a40-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="78a40-115">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="78a40-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="78a40-116">Odaberite **Dodaj vezu** i odaberite **Constant Contact** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="78a40-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="78a40-117">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="78a40-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="78a40-118">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="78a40-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="78a40-119">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="78a40-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="78a40-120">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="78a40-120">Choose who can use this connection.</span></span> <span data-ttu-id="78a40-121">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="78a40-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="78a40-122">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="78a40-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="78a40-123">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="78a40-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="78a40-124">Odaberite **Poveži** za inicijalizaciju veze s Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="78a40-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="78a40-125">Odaberite **Provjeri autentičnost uz Constant Contact** i pružite svoje administratorske vjerodajnice za Constant Contactr.</span><span class="sxs-lookup"><span data-stu-id="78a40-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="78a40-126">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="78a40-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="78a40-127">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="78a40-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="78a40-128">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="78a40-128">Configure an export</span></span>

<span data-ttu-id="78a40-129">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="78a40-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="78a40-130">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="78a40-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="78a40-131">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="78a40-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="78a40-132">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="78a40-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="78a40-133">U polju **Veza za izvoz** odaberite vezu iz odjeljka Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="78a40-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="78a40-134">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="78a40-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="78a40-135">Unesite svoje [**ID popisa za Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="78a40-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="78a40-136">Otvorite popis u Constant Contact da biste pronašli ID popisa u URL-u.</span><span class="sxs-lookup"><span data-stu-id="78a40-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="78a40-137">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="78a40-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="78a40-138">Obavezno je izvoziti segmente u Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="78a40-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="78a40-139">Ako želite, možete izvesti stavke Ime i Prezime kao dodatna polja za stvaranje osobnijih poruka e-pošte.</span><span class="sxs-lookup"><span data-stu-id="78a40-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="78a40-140">Odaberite **Dodavanje atributa** za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="78a40-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="78a40-141">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="78a40-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="78a40-142">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="78a40-142">Select **Save**.</span></span>

<span data-ttu-id="78a40-143">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="78a40-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="78a40-144">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="78a40-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="78a40-145">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="78a40-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="78a40-146">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="78a40-146">Data privacy and compliance</span></span>

<span data-ttu-id="78a40-147">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Constant Contact dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="78a40-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="78a40-148">Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Constant Contact ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="78a40-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="78a40-149">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="78a40-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="78a40-150">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="78a40-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
