---
title: Izvoz podataka usluge Customer Insights u Mailchimp
description: Saznajte kako konfigurirati vezu s uslugom Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267164"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="d70e6-103">Poveznik za Mailchimp (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="d70e6-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="d70e6-104">Izvezite segmente objedinjenih profila klijenata u Mailchimp da biste stvorili biltene i kampanje e-pošte.</span><span class="sxs-lookup"><span data-stu-id="d70e6-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d70e6-105">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="d70e6-105">Prerequisites</span></span>

-   <span data-ttu-id="d70e6-106">Imate [račun za Mailchimp](https://mailchimp.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="d70e6-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d70e6-107">Mailchimp sadrži postojeće ciljne skupine i odgovarajuće ID-ove.</span><span class="sxs-lookup"><span data-stu-id="d70e6-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="d70e6-108">Dodatne informacije potražite u [ciljnim skupinama usluge Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="d70e6-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="d70e6-109">Imate [konfigurirane segmente](segments.md)</span><span class="sxs-lookup"><span data-stu-id="d70e6-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="d70e6-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="d70e6-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="d70e6-111">Povezivanje na Mailchimp</span><span class="sxs-lookup"><span data-stu-id="d70e6-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="d70e6-112">Otvorite **Administrator** > **Izvozna odredišta**.</span><span class="sxs-lookup"><span data-stu-id="d70e6-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d70e6-113">U odjeljku **Mailchimp** odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="d70e6-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="d70e6-114">Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="d70e6-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d70e6-115">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="d70e6-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d70e6-116">Unesite svoj **[ID ciljne skupine za Mailchimp](https://mailchimp.com/help/find-audience-id/)** i odaberite **Povezivanje** za inicijalizaciju veze s uslugom Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="d70e6-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="d70e6-117">Odaberite mogućnost **Provjera autentičnosti pomoću usluge Mailchimp** i unesite svoje vjerodajnice za Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="d70e6-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="d70e6-118">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d70e6-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Snimka zaslona s izvozom za vezu s uslugom Mailchimp":::

1. <span data-ttu-id="d70e6-120">Odaberite **Dalje** da biste konfigurirali izvoz.</span><span class="sxs-lookup"><span data-stu-id="d70e6-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="d70e6-121">Konfiguracija poveznika</span><span class="sxs-lookup"><span data-stu-id="d70e6-121">Configure the connector</span></span>

1. <span data-ttu-id="d70e6-122">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="d70e6-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="d70e6-123">Ako želite, možete izvesti stavke **Ime** i **Prezime** kao dodatna polja za stvaranje osobnijih poruka e-pošte.</span><span class="sxs-lookup"><span data-stu-id="d70e6-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="d70e6-124">Odaberite **Dodavanje atributa** za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="d70e6-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="d70e6-125">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="d70e6-125">Select the segments you want to export.</span></span> <span data-ttu-id="d70e6-126">U Mailchimp možete ukupno izvesti do 1 milijun profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="d70e6-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Odabir polja i segmenata za izvoz u Mailchimp":::

1. <span data-ttu-id="d70e6-128">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="d70e6-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d70e6-129">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="d70e6-129">Export the data</span></span>

<span data-ttu-id="d70e6-130">Možete [izvesti podatke na zahtjev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d70e6-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="d70e6-131">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d70e6-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d70e6-132">U usluzi Mailchimp svoje segmente sada možete pronaći u odjeljku [ciljne skupine usluge Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="d70e6-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d70e6-133">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="d70e6-133">Known limitations</span></span>

- <span data-ttu-id="d70e6-134">Do 1 milijun profila po izvozu u Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="d70e6-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="d70e6-135">Izvoz u Mailchimp ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="d70e6-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="d70e6-136">Izvoz segmenata s ukupno milijun profila može potrajati do tri sata zbog ograničenja na strani davatelja usluga.</span><span class="sxs-lookup"><span data-stu-id="d70e6-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="d70e6-137">Broj profila koje možete izvesti u Mailchimp ovisi i ograničen je vašim ugovorom s tvrtkom Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="d70e6-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d70e6-138">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="d70e6-138">Data privacy and compliance</span></span>

<span data-ttu-id="d70e6-139">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Mailchimp, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="d70e6-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d70e6-140">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Mailchimp ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="d70e6-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d70e6-141">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d70e6-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d70e6-142">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="d70e6-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]