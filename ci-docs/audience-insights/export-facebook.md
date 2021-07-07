---
title: Izvoz podataka usluge Customer Insights u Upravitelj Facebook oglasa
description: Saznajte kako konfigurirati vezu i izvesti u Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305101"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="5e864-103">Izvoz popisa segmenata u Facebook Ads Manager (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="5e864-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="5e864-104">Izvezite segmente objedinjenih korisničkih profila u Upravitelj Facebook oglasa radi izrade kampanja na Facebooku i Instagramu.</span><span class="sxs-lookup"><span data-stu-id="5e864-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="5e864-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="5e864-105">Prerequisites for connection</span></span>

- <span data-ttu-id="5e864-106">Morate imati [**račun za Facebook oglase**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) koji uključuje [**poslovni račun za Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="5e864-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="5e864-107">Morate biti administrator na [**računu za Facebook oglase**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="5e864-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5e864-108">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="5e864-108">Known limitations</span></span>

- <span data-ttu-id="5e864-109">Do 10 milijuna profila kupaca po izvozu u Facebook Upravitelj oglasa.</span><span class="sxs-lookup"><span data-stu-id="5e864-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="5e864-110">Izvoz u Facebook Ads Manager ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="5e864-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="5e864-111">Stvorite ili ažurirajte prilagođenu ciljnu skupinu na društvenoj mreži Facebook isključivo vrste *popis klijenata*.</span><span class="sxs-lookup"><span data-stu-id="5e864-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="5e864-112">Izvoz segmenata s ukupno 10 milijuna profila može trajati do 90 minuta.</span><span class="sxs-lookup"><span data-stu-id="5e864-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="5e864-113">Postavljanje veze s Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="5e864-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="5e864-114">Prije nego što korisnici mogu stvoriti izvoz, administrator mora konfigurirati vezu s uslugom i dopustiti suradnicima korištenje veze.</span><span class="sxs-lookup"><span data-stu-id="5e864-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="5e864-115">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="5e864-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5e864-116">Odaberite **Dodaj vezu** i odaberite **Facebook Ads Manager** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="5e864-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="5e864-117">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="5e864-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5e864-118">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="5e864-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5e864-119">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="5e864-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5e864-120">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="5e864-120">Choose who can use this connection.</span></span> <span data-ttu-id="5e864-121">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="5e864-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5e864-122">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5e864-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5e864-123">Provjera autentičnosti uz Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="5e864-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="5e864-124">Odaberite **Nastavi uz Facebook** za prijavu na svoj račun za Facebook oglase.</span><span class="sxs-lookup"><span data-stu-id="5e864-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="5e864-125">Omogućite dozvolu za **upravljanje oglasima** nakon provjere autentičnosti pomoću usluge Facebook.</span><span class="sxs-lookup"><span data-stu-id="5e864-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="5e864-126">Odaberite **Upravitelj Facebook oglasa** s kojim želite raditi.</span><span class="sxs-lookup"><span data-stu-id="5e864-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="5e864-127">Odaberite **Postojeća prilagođena publika** s padajućeg popisa ili stvorite opciju **Nova prilagođena publika**.</span><span class="sxs-lookup"><span data-stu-id="5e864-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="5e864-128">Za više informacija pogledajte [**Publike u Upravitelju Facebook oglasa**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="5e864-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="5e864-129">S ovim izvozom na društvenoj mreži Facebook možete stvarati ili ažurirati isključivo prilagođene ciljne skupine vrste *popis klijenata*.</span><span class="sxs-lookup"><span data-stu-id="5e864-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="5e864-130">U nekim slučajevima na padajućem popisu vidite prilagođene publike različitih vrsta.</span><span class="sxs-lookup"><span data-stu-id="5e864-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="5e864-131">Odabir vrste različite od *popis klijenata* rezultirat će neuspjelim izvozom.</span><span class="sxs-lookup"><span data-stu-id="5e864-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="5e864-132">Pregledajte **Zaštita privatnosti podataka i usklađenost** i odaberite **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="5e864-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="5e864-133">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="5e864-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5e864-134">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="5e864-134">Configure an export</span></span>

<span data-ttu-id="5e864-135">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="5e864-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5e864-136">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5e864-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5e864-137">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="5e864-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5e864-138">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="5e864-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="5e864-139">Pod **Veza za izvoz** odaberite vezu iz odjeljka **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="5e864-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="5e864-140">Ako ne vidite naziv ovog odjeljka, tada vam nisu dostupne veze ove vrste.</span><span class="sxs-lookup"><span data-stu-id="5e864-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="5e864-141">U polju **Odaberite ključni identifikator**, odaberite **E-pošta**, **Ime i adresa** ili **Telefon** koji će se poslati u Upravitelj Facebook oglasa.</span><span class="sxs-lookup"><span data-stu-id="5e864-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="5e864-142">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="5e864-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="5e864-143">Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za odabrani identifikator ključa.</span><span class="sxs-lookup"><span data-stu-id="5e864-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="5e864-144">Najveći izgledi za podudaranje pojavljuju se ako kao ključni identifikator odaberete **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="5e864-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="5e864-145">Dodavanje dodatnih identifikatora može poboljšati podudaranje.</span><span class="sxs-lookup"><span data-stu-id="5e864-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="5e864-146">Odaberite **Dodaj atribut** za mapiranje više atributa za slanje u Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="5e864-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="5e864-147">Atributi iz Facebook Ads Manager mapiraju se na sljedeće nazive prilagođene korisnicima: **FN** = **Ime**, **LN** = **Prezime**, **FI** = **Prvi inicijal**, **PHONE** = **Telefon**, **GEN** = **Spol**, **DOB** = **Datum rođenja**, **ST** = **Država**, **CT** = **Grad**, **ZIP** = **Poštanski broj**, **COUNTRY** = **Zemlja/regija**</span><span class="sxs-lookup"><span data-stu-id="5e864-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="5e864-148">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="5e864-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="5e864-149">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="5e864-149">Select **Save**.</span></span>

<span data-ttu-id="5e864-150">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="5e864-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5e864-151">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5e864-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="5e864-152">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5e864-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5e864-153">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="5e864-153">Data privacy and compliance</span></span>

<span data-ttu-id="5e864-154">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Upravitelj Facebook oglasa, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="5e864-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5e864-155">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da usluga Facebook oglasi ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="5e864-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="5e864-156">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5e864-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5e864-157">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="5e864-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
