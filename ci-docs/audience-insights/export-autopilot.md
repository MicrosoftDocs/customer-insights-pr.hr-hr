---
title: Izvoz podataka usluge Customer Insights u Autopilot
description: Saznajte kako konfigurirati vezu s uslugom Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269229"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="8de9b-103">Poveznik za Autopilot (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="8de9b-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="8de9b-104">Izvezite segmente objedinjenih profila klijenata u Autopilot i koristite ih za marketing putem e-pošte u usluzi Autopilot.</span><span class="sxs-lookup"><span data-stu-id="8de9b-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="8de9b-105">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="8de9b-105">Prerequisites</span></span>

-   <span data-ttu-id="8de9b-106">Imate [račun za Autopilot](https://www.autopilothq.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="8de9b-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8de9b-107">Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="8de9b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8de9b-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="8de9b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="8de9b-109">Povezivanje s uslugom Autopilot</span><span class="sxs-lookup"><span data-stu-id="8de9b-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="8de9b-110">Otvorite **Administrator** > **Izvozna odredišta**.</span><span class="sxs-lookup"><span data-stu-id="8de9b-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8de9b-111">Pod **Autopilot** odaberite **Postavi**.</span><span class="sxs-lookup"><span data-stu-id="8de9b-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="8de9b-112">Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="8de9b-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfiguracijsko okno za vezu za Autopilot.":::

1. <span data-ttu-id="8de9b-114">Unesite svoj **Ključ za API za Autopilot** [Ključ za API za Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="8de9b-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="8de9b-115">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="8de9b-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8de9b-116">Odaberite **Poveži** za inicijalizaciju veze s uslugom Autopilot.</span><span class="sxs-lookup"><span data-stu-id="8de9b-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="8de9b-117">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8de9b-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8de9b-118">Odaberite **Dalje** da biste konfigurirali izvoz.</span><span class="sxs-lookup"><span data-stu-id="8de9b-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="8de9b-119">Konfiguracija poveznika</span><span class="sxs-lookup"><span data-stu-id="8de9b-119">Configure the connector</span></span>

1. <span data-ttu-id="8de9b-120">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="8de9b-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8de9b-121">Ponovite iste korake za ostala neobavezna polja kao što su **Ime**, **Prezime**.</span><span class="sxs-lookup"><span data-stu-id="8de9b-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="8de9b-122">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="8de9b-122">Select the segments you want to export.</span></span> <span data-ttu-id="8de9b-123">Snažno **preporučujemo da ne izvozite više od ukupno 100 000 profila klijenata** u uslugu Autopilot.</span><span class="sxs-lookup"><span data-stu-id="8de9b-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="8de9b-124">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="8de9b-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8de9b-125">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="8de9b-125">Export the data</span></span>

<span data-ttu-id="8de9b-126">Možete [izvesti podatke na zahtjev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8de9b-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8de9b-127">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8de9b-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8de9b-128">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="8de9b-128">Known limitations</span></span>

- <span data-ttu-id="8de9b-129">U Autopilot možete ukupno izvesti do 100 000 profila.</span><span class="sxs-lookup"><span data-stu-id="8de9b-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="8de9b-130">Izvoz u Autopilot ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="8de9b-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="8de9b-131">Izvoz do 100 000 profila u Autopilot može potrajati do nekoliko sati.</span><span class="sxs-lookup"><span data-stu-id="8de9b-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="8de9b-132">Broj profila koje možete izvesti u Autopilot ovisi i ograničen je vašim ugovorom s tvrtkom Autopilot.</span><span class="sxs-lookup"><span data-stu-id="8de9b-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8de9b-133">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="8de9b-133">Data privacy and compliance</span></span>

<span data-ttu-id="8de9b-134">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Autopilot, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="8de9b-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8de9b-135">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Autopilot ispunjava sve obaveze zaštite privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="8de9b-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="8de9b-136">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8de9b-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8de9b-137">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="8de9b-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]