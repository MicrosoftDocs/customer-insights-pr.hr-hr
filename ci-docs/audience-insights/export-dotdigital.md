---
title: Izvoz podataka usluge Customer Insights u DotDigital
description: Saznajte kako konfigurirati vezu s uslugom DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644439"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="5003f-103">Poveznik za DotDigital (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="5003f-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="5003f-104">Izvezite segmente objedinjenih profila klijenata u adresare usluge DotDigital i koristite ih za kampanje, marketing putem e-pošte i za izgradnju segmenata klijenata pomoću usluge DotDigital.</span><span class="sxs-lookup"><span data-stu-id="5003f-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="5003f-105">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="5003f-105">Prerequisites</span></span>

-   <span data-ttu-id="5003f-106">Imate [račun za DotDigital](https://dotdigital.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="5003f-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5003f-107">DotDigital sadrži postojeće adresare i odgovarajuće ID-ove.</span><span class="sxs-lookup"><span data-stu-id="5003f-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="5003f-108">ID se može pronaći u URL-u kada odaberete i otvorite adresar.</span><span class="sxs-lookup"><span data-stu-id="5003f-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="5003f-109">Dodatne informacije potražite u [adresarima usluge DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="5003f-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="5003f-110">Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="5003f-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5003f-111">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="5003f-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="5003f-112">Povezivanje s uslugom DotDigital</span><span class="sxs-lookup"><span data-stu-id="5003f-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="5003f-113">Otvorite **Administrator** > **Izvozna odredišta**.</span><span class="sxs-lookup"><span data-stu-id="5003f-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="5003f-114">U odjeljku **DotDigital** odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="5003f-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="5003f-115">Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="5003f-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Okno za konfiguraciju za izvoz u DotDigital.":::

1. <span data-ttu-id="5003f-117">Unesite **korisničko ime i lozinku za DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="5003f-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="5003f-118">Unesite svoj **[ID adresara usluge DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="5003f-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="5003f-119">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="5003f-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5003f-120">Odaberite **Povezivanje** za inicijalizaciju veze s uslugom DotDigital.</span><span class="sxs-lookup"><span data-stu-id="5003f-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="5003f-121">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5003f-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5003f-122">Odaberite **Dalje** da biste konfigurirali izvoz.</span><span class="sxs-lookup"><span data-stu-id="5003f-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="5003f-123">Konfiguracija poveznika</span><span class="sxs-lookup"><span data-stu-id="5003f-123">Configure the connector</span></span>

1. <span data-ttu-id="5003f-124">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="5003f-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5003f-125">Ponovite iste korake za druga neobavezna polja kao što su **Ime**, **Prezime**, **Puno ime**, **Spol** i **Poštanski broj**.</span><span class="sxs-lookup"><span data-stu-id="5003f-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="5003f-126">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="5003f-126">Select the segments you want to export.</span></span> <span data-ttu-id="5003f-127">U DotDigital možete ukupno izvesti do 1 milijun profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="5003f-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="5003f-128">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="5003f-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="5003f-129">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="5003f-129">Export the data</span></span>

<span data-ttu-id="5003f-130">Možete [izvesti podatke na zahtjev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5003f-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="5003f-131">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5003f-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5003f-132">U usluzi DotDigital sada možete pronaći svoje segmente u [adresaru usluge DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="5003f-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5003f-133">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="5003f-133">Known limitations</span></span>

- <span data-ttu-id="5003f-134">Do 1 milijun profila po izvozu u DotDigital.</span><span class="sxs-lookup"><span data-stu-id="5003f-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="5003f-135">Izvoz u DotDigital ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="5003f-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="5003f-136">Izvoz segmenata s ukupno milijun profila može potrajati do 3 sata zbog ograničenja na strani davatelja usluga.</span><span class="sxs-lookup"><span data-stu-id="5003f-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="5003f-137">Broj profila koje možete izvesti u DotDigital ovisi i ograničen je vašim ugovorom s tvrtkom DotDigital.</span><span class="sxs-lookup"><span data-stu-id="5003f-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5003f-138">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="5003f-138">Data privacy and compliance</span></span>

<span data-ttu-id="5003f-139">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u DotDigital, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="5003f-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5003f-140">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da DotDigital ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="5003f-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="5003f-141">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5003f-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5003f-142">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="5003f-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
