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
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976033"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="95d04-103">Izvoz popisa segmenata u Facebook Ads Manager (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="95d04-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="95d04-104">Izvezite segmente objedinjenih korisničkih profila u Upravitelj Facebook oglasa radi izrade kampanja na Facebooku i Instagramu.</span><span class="sxs-lookup"><span data-stu-id="95d04-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="95d04-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="95d04-105">Prerequisites for connection</span></span>

- <span data-ttu-id="95d04-106">Morate imate [**Facebook Ad račun**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) koji uključuje [**Facebook poslovni račun**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="95d04-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="95d04-107">Morate biti administrator za [račun **Facebook oglasa**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="95d04-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="95d04-108">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="95d04-108">Known limitations</span></span>

- <span data-ttu-id="95d04-109">Do 10 milijuna profila klijenata po izvozu u Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="95d04-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="95d04-110">Izvoz u Facebook Ads Manager ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="95d04-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="95d04-111">Stvorite ili ažurirajte prilagođenu ciljnu skupinu na društvenoj mreži Facebook isključivo vrste *popis klijenata*.</span><span class="sxs-lookup"><span data-stu-id="95d04-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="95d04-112">Izvoz segmenata s ukupno 10 milijuna profila može trajati do 90 minuta.</span><span class="sxs-lookup"><span data-stu-id="95d04-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="95d04-113">Postavljanje veze s Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="95d04-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="95d04-114">Prije nego što korisnici mogu stvoriti izvoz, administrator mora konfigurirati vezu s uslugom i dopustiti suradnicima korištenje veze.</span><span class="sxs-lookup"><span data-stu-id="95d04-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="95d04-115">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="95d04-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="95d04-116">Odaberite **Dodaj vezu** i odaberite **Facebook Ads Manager** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="95d04-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="95d04-117">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="95d04-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="95d04-118">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="95d04-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="95d04-119">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="95d04-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="95d04-120">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="95d04-120">Choose who can use this connection.</span></span> <span data-ttu-id="95d04-121">Ako ništa ne poduzmete, prema zadanim će postavkama biti **Administratori**.</span><span class="sxs-lookup"><span data-stu-id="95d04-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="95d04-122">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="95d04-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="95d04-123">Provjera autentičnosti uz Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="95d04-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="95d04-124">Odaberite **Nastavi s Facebookom** da se prijavite na svoj račun Facebook oglasa.</span><span class="sxs-lookup"><span data-stu-id="95d04-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="95d04-125">Omogućite dozvolu za **upravljanje oglasima** nakon provjere autentičnosti pomoću usluge Facebook.</span><span class="sxs-lookup"><span data-stu-id="95d04-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="95d04-126">Odaberite **Upravitelj Facebook oglasa** s kojim želite raditi.</span><span class="sxs-lookup"><span data-stu-id="95d04-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="95d04-127">Odaberite **Postojeću prilagođenu publiku** s padajućeg popisa ili stvorite **Novu prilagođenu publiku**.</span><span class="sxs-lookup"><span data-stu-id="95d04-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="95d04-128">Za više informacija pogledajte [**Publike u Upravitelju Facebook oglasa**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="95d04-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="95d04-129">S ovim izvozom na društvenoj mreži Facebook možete stvarati ili ažurirati isključivo prilagođene ciljne skupine vrste *popis klijenata*.</span><span class="sxs-lookup"><span data-stu-id="95d04-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="95d04-130">U nekim slučajevima na padajućem popisu vidite prilagođene ciljne skupine različitih vrsta.</span><span class="sxs-lookup"><span data-stu-id="95d04-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="95d04-131">Odabir vrste različite od *popis klijenata* rezultirat će neuspjelim izvozom.</span><span class="sxs-lookup"><span data-stu-id="95d04-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="95d04-132">Pregledajte **Zaštita privatnosti podataka i usklađenost** i odaberite **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="95d04-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="95d04-133">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="95d04-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="95d04-134">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="95d04-134">Configure an export</span></span>

<span data-ttu-id="95d04-135">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="95d04-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="95d04-136">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="95d04-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="95d04-137">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="95d04-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="95d04-138">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="95d04-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="95d04-139">Pod **Veza za izvoz** odaberite vezu iz odjeljka **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="95d04-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="95d04-140">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="95d04-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="95d04-141">U polju **Odaberite ključni identifikator**, odaberite **E-pošta**, **Ime i adresa** ili **Telefon** koji će se poslati u Upravitelj Facebook oglasa.</span><span class="sxs-lookup"><span data-stu-id="95d04-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="95d04-142">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="95d04-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="95d04-143">Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za odabrani identifikator ključa.</span><span class="sxs-lookup"><span data-stu-id="95d04-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="95d04-144">[SAVJET] Najveće šanse za podudaranje pojavljuju se ako kao ključni identifikator odaberete **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="95d04-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="95d04-145">Dodavanje dodatnih identifikatora može poboljšati podudaranje.</span><span class="sxs-lookup"><span data-stu-id="95d04-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="95d04-146">Odaberite **Dodaj atribut** za mapiranje više atributa za slanje u Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="95d04-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="95d04-147">Atributi iz Facebook Ads Manager mapiraju se na sljedeće nazive prilagođene korisnicima: **FN** = **Ime**, **LN** = **Prezime**, **FI** = **Prvi inicijal**, **PHONE** = **Telefon**, **GEN** = **Spol**, **DOB** = **Datum rođenja**, **ST** = **Država**, **CT** = **Grad**, **ZIP** = **Poštanski broj**, **COUNTRY** = **Zemlja/regija**</span><span class="sxs-lookup"><span data-stu-id="95d04-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="95d04-148">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="95d04-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="95d04-149">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="95d04-149">Select **Save**.</span></span>

<span data-ttu-id="95d04-150">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="95d04-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="95d04-151">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="95d04-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="95d04-152">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="95d04-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="95d04-153">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="95d04-153">Data privacy and compliance</span></span>

<span data-ttu-id="95d04-154">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Upravitelj Facebook oglasa, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="95d04-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="95d04-155">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da usluga Facebook oglasi ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="95d04-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="95d04-156">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="95d04-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="95d04-157">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="95d04-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
