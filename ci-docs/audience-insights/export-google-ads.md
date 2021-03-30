---
title: Izvoz podataka usluge Customer Insights u Google Ads
description: Saznajte kako konfigurirati vezu s uslugom Google Ads.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598238"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="f4599-103">Poveznik za Google Ads (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="f4599-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="f4599-104">Izvezite segmente objedinjenih profila klijenata u popis ciljnih skupina usluge Google Ads i upotrijebite ih za oglašavanje na uslugama Google pretraživanje, Gmail, YouTube i Google prikazivačkoj mreži.</span><span class="sxs-lookup"><span data-stu-id="f4599-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f4599-105">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="f4599-105">Prerequisites</span></span>

-   <span data-ttu-id="f4599-106">Imate [račun za Google Ads](https://ads.google.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="f4599-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f4599-107">Google Ads sadrži postojeće ciljne skupine i odgovarajuće ID-ove.</span><span class="sxs-lookup"><span data-stu-id="f4599-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="f4599-108">Dodatne informacije potražite u [ciljnim skupinama usluge Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="f4599-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="f4599-109">Imate [konfigurirane segmente](segments.md)</span><span class="sxs-lookup"><span data-stu-id="f4599-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="f4599-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polja koja predstavljaju adresu e-pošte, ime i prezime</span><span class="sxs-lookup"><span data-stu-id="f4599-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="f4599-111">Povezivanje s uslugom Google Ads</span><span class="sxs-lookup"><span data-stu-id="f4599-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="f4599-112">Otvorite **Administrator** > **Izvozna odredišta**.</span><span class="sxs-lookup"><span data-stu-id="f4599-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f4599-113">U odjeljku **Google Ads** odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="f4599-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="f4599-114">Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="f4599-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f4599-115">Unesite svoj **[ID klijenta za Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="f4599-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="f4599-116">Unesite svoj **[token razvojnog inženjera koji je odobren za Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="f4599-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="f4599-117">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="f4599-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f4599-118">Unesite svoj **[ID ciljne skupine za Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i odaberite **Povezivanje** za inicijalizaciju veze s uslugom Google Ads.</span><span class="sxs-lookup"><span data-stu-id="f4599-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="f4599-119">Odaberite mogućnost **Provjera autentičnosti pomoću usluge Google Ads** i unesite svoje vjerodajnice za Google Ads.</span><span class="sxs-lookup"><span data-stu-id="f4599-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="f4599-120">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f4599-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Snimka zaslona s izvozom za vezu s uslugom Google Ads":::

1. <span data-ttu-id="f4599-122">Odaberite **Dalje** da biste konfigurirali izvoz.</span><span class="sxs-lookup"><span data-stu-id="f4599-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f4599-123">Konfiguracija poveznika</span><span class="sxs-lookup"><span data-stu-id="f4599-123">Configure the connector</span></span>

1. <span data-ttu-id="f4599-124">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="f4599-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f4599-125">Ponovite iste korake za polja **Ime** i **Prezime**.</span><span class="sxs-lookup"><span data-stu-id="f4599-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="f4599-126">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="f4599-126">Select the segments you want to export.</span></span> <span data-ttu-id="f4599-127">U Google Ads možete ukupno izvesti do 1 milijun profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="f4599-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="f4599-128">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="f4599-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f4599-129">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="f4599-129">Export the data</span></span>

<span data-ttu-id="f4599-130">Možete [izvesti podatke na zahtjev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f4599-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f4599-131">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f4599-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f4599-132">U usluzi Google Ads sada možete pronaći svoje segmente u odjeljku [ciljne skupine usluge Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="f4599-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f4599-133">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="f4599-133">Known limitations</span></span>

- <span data-ttu-id="f4599-134">Do 1 milijun profila po izvozu u Google Ads.</span><span class="sxs-lookup"><span data-stu-id="f4599-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="f4599-135">Izvoz u Google Ads ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="f4599-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="f4599-136">Izvoz segmenata s ukupno milijun profila može potrajati do 5 minuta zbog ograničenja na strani davatelja usluga.</span><span class="sxs-lookup"><span data-stu-id="f4599-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="f4599-137">Podudaranje u usluzi Google Ads može potrajati do 48 sati.</span><span class="sxs-lookup"><span data-stu-id="f4599-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f4599-138">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="f4599-138">Data privacy and compliance</span></span>

<span data-ttu-id="f4599-139">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Google Ads, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="f4599-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f4599-140">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Google Ads ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="f4599-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f4599-141">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f4599-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f4599-142">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="f4599-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]