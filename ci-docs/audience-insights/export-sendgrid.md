---
title: Izvoz podataka usluge Customer Insights u SendGrid
description: Saznajte kako konfigurirati vezu s uslugom SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268723"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="9a208-103">Poveznik za SendGrid (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="9a208-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="9a208-104">Izvezite segmente objedinjenih profila klijenata u popise kontakata usluge SendGrid i koristite ih za kampanje i marketing putem e-pošte u usluzi SendGrid.</span><span class="sxs-lookup"><span data-stu-id="9a208-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="9a208-105">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="9a208-105">Prerequisites</span></span>

-   <span data-ttu-id="9a208-106">Imate [račun za SendGrid](https://sendgrid.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="9a208-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9a208-107">SendGrid sadrži postojeće popise kontakata i odgovarajuće ID-jeve.</span><span class="sxs-lookup"><span data-stu-id="9a208-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="9a208-108">Za dodatne informacije pogledajte [SendGrid – Upravljanje kontaktima](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="9a208-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="9a208-109">Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="9a208-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="9a208-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="9a208-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="9a208-111">Povezivanje s uslugom SendGrid</span><span class="sxs-lookup"><span data-stu-id="9a208-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="9a208-112">Otvorite **Administrator** > **Izvozna odredišta**.</span><span class="sxs-lookup"><span data-stu-id="9a208-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9a208-113">Pod **SendGrid** odaberite **Postavi**.</span><span class="sxs-lookup"><span data-stu-id="9a208-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="9a208-114">Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="9a208-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Okno za konfiguraciju izvoza usluge SendGrid.":::

1. <span data-ttu-id="9a208-116">Unesite svoj **Ključ za API za SendGrid** [Ključ za API za SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="9a208-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="9a208-117">Unesite svoj **[ID popisa usluge SendGridI](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="9a208-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="9a208-118">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="9a208-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9a208-119">Odaberite **Poveži** za inicijalizaciju veze s uslugom SendGrid.</span><span class="sxs-lookup"><span data-stu-id="9a208-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="9a208-120">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9a208-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9a208-121">Odaberite **Dalje** da biste konfigurirali izvoz.</span><span class="sxs-lookup"><span data-stu-id="9a208-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="9a208-122">Konfiguracija poveznika</span><span class="sxs-lookup"><span data-stu-id="9a208-122">Configure the connector</span></span>

1. <span data-ttu-id="9a208-123">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="9a208-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="9a208-124">Ponovite iste korake za ostala neobavezna polja kao što su **Ime**, **Prezime**, **Zemlja/Regija**, **Država**, **Grad** i **Poštanski broj**.</span><span class="sxs-lookup"><span data-stu-id="9a208-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="9a208-125">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="9a208-125">Select the segments you want to export.</span></span> <span data-ttu-id="9a208-126">Snažno **preporučujemo da ne izvozite više od ukupno 100 000 profila klijenata** u uslugu SendGrid.</span><span class="sxs-lookup"><span data-stu-id="9a208-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="9a208-127">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="9a208-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9a208-128">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="9a208-128">Export the data</span></span>

<span data-ttu-id="9a208-129">Možete [izvesti podatke na zahtjev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9a208-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9a208-130">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9a208-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9a208-131">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="9a208-131">Known limitations</span></span>

- <span data-ttu-id="9a208-132">Ukupno do 100 000 profila u SendGrid.</span><span class="sxs-lookup"><span data-stu-id="9a208-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="9a208-133">Izvoz u SendGrid ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="9a208-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="9a208-134">Izvoz do 100 000 profila u SendGrid može potrajati do nekoliko sati.</span><span class="sxs-lookup"><span data-stu-id="9a208-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="9a208-135">Broj profila koje možete izvesti u SendGrid ovisi i ograničen je vašim ugovorom s tvrtkom SendGrid.</span><span class="sxs-lookup"><span data-stu-id="9a208-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9a208-136">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="9a208-136">Data privacy and compliance</span></span>

<span data-ttu-id="9a208-137">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u SendGrid, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="9a208-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9a208-138">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da SendGrid ispunjava sve obaveze zaštite privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="9a208-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="9a208-139">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9a208-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9a208-140">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="9a208-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]