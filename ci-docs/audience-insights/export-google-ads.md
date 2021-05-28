---
title: Izvoz podataka usluge Customer Insights u Google Ads
description: Saznajte kako konfigurirati vezu i izvesti u Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976309"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="98723-103">Izvoz segmenata u Google Ads (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="98723-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="98723-104">Izvezite segmente objedinjenih profila klijenata u popis ciljnih skupina usluge Google Ads i upotrijebite ih za oglašavanje na uslugama Google pretraživanje, Gmail, YouTube i Google prikazivačkoj mreži.</span><span class="sxs-lookup"><span data-stu-id="98723-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="98723-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="98723-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="98723-106">Imate [račun za Google Ads](https://ads.google.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="98723-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="98723-107">Imate [odobreni token za Google Ads Developer](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="98723-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="98723-108">Ispunjavate zahtjeve [Pravila podudaranja klijenata](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="98723-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="98723-109">Ispunjavate zahtjeve [veličina popisa ponovno zainteresiranih](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="98723-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="98723-110">Google Ads sadrži postojeće ciljne skupine i odgovarajuće ID-ove.</span><span class="sxs-lookup"><span data-stu-id="98723-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="98723-111">Dodatne informacije potražite u [ciljnim skupinama usluge Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="98723-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="98723-112">Imate [konfigurirane segmente](segments.md)</span><span class="sxs-lookup"><span data-stu-id="98723-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="98723-113">Objedinjeni profili klijenata u izvezenim segmentima sadrže polja koja predstavljaju adresu e-pošte, ime i prezime</span><span class="sxs-lookup"><span data-stu-id="98723-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="98723-114">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="98723-114">Known limitations</span></span>

- <span data-ttu-id="98723-115">Do 1 milijun profila po izvozu u Google Ads.</span><span class="sxs-lookup"><span data-stu-id="98723-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="98723-116">Izvoz u Google Ads ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="98723-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="98723-117">Izvoz segmenata s ukupno milijun profila može potrajati do 5 minuta zbog ograničenja na strani davatelja usluga.</span><span class="sxs-lookup"><span data-stu-id="98723-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="98723-118">Podudaranje u usluzi Google Ads može potrajati do 48 sati.</span><span class="sxs-lookup"><span data-stu-id="98723-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="98723-119">Postavljanje veze s Google Ads</span><span class="sxs-lookup"><span data-stu-id="98723-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="98723-120">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="98723-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="98723-121">Odaberite **Dodaj vezu** i odaberite **Google Ads** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="98723-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="98723-122">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="98723-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="98723-123">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="98723-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="98723-124">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="98723-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="98723-125">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="98723-125">Choose who can use this connection.</span></span> <span data-ttu-id="98723-126">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="98723-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="98723-127">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="98723-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="98723-128">Unesite svoj **[ID klijenta za Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="98723-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="98723-129">Unesite svoj **[token razvojnog inženjera koji je odobren za Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="98723-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="98723-130">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="98723-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="98723-131">Odaberite mogućnost **Provjera autentičnosti pomoću usluge Google Ads** i unesite svoje vjerodajnice za Google Ads.</span><span class="sxs-lookup"><span data-stu-id="98723-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="98723-132">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="98723-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="98723-133">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="98723-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="98723-134">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="98723-134">Configure an export</span></span>

<span data-ttu-id="98723-135">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="98723-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="98723-136">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="98723-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="98723-137">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="98723-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="98723-138">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="98723-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="98723-139">U polju **Veza za izvoz** odaberite vezu iz odjeljka Google Ads.</span><span class="sxs-lookup"><span data-stu-id="98723-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="98723-140">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="98723-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="98723-141">Unesite svoj **[ID ciljne skupine za Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i odaberite **Povezivanje** za inicijalizaciju veze s uslugom Google Ads.</span><span class="sxs-lookup"><span data-stu-id="98723-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="98723-142">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="98723-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="98723-143">Ponovite iste korake za polja **Ime** i **Prezime**.</span><span class="sxs-lookup"><span data-stu-id="98723-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="98723-144">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="98723-144">Select the segments you want to export.</span></span> <span data-ttu-id="98723-145">U Google Ads možete ukupno izvesti do 1 milijun profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="98723-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="98723-146">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="98723-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="98723-147">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="98723-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="98723-148">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="98723-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="98723-149">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="98723-149">Data privacy and compliance</span></span>

<span data-ttu-id="98723-150">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Google Ads, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="98723-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="98723-151">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Google Ads ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="98723-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="98723-152">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="98723-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="98723-153">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="98723-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
