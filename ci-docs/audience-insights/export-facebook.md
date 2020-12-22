---
title: Izvoz podataka usluge Customer Insights u Upravitelj Facebook oglasa
description: Saznajte kako konfigurirati vezu s Upraviteljem Facebook oglasa.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643674"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="a1f08-103">Poveznik za Upravitelj Facebook oglasa (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="a1f08-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="a1f08-104">Izvezite segmente objedinjenih korisničkih profila u Upravitelj Facebook oglasa radi izrade kampanja na Facebooku i Instagramu.</span><span class="sxs-lookup"><span data-stu-id="a1f08-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a1f08-105">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="a1f08-105">Prerequisites</span></span>

- <span data-ttu-id="a1f08-106">Trebate imati [račun **Facebook oglasa**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) koji obuhvaća [poslovni **Facebook račun**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="a1f08-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="a1f08-107">Morate biti administrator za [račun **Facebook oglasa**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="a1f08-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="a1f08-108">Povezivanje s Upraviteljem Facebook oglasa</span><span class="sxs-lookup"><span data-stu-id="a1f08-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="a1f08-109">Otvorite **Administrator** > **Izvozna odredišta**.</span><span class="sxs-lookup"><span data-stu-id="a1f08-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a1f08-110">Pod **Upravitelj Facebook oglasa**, odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="a1f08-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="a1f08-111">Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="a1f08-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a1f08-112">Odaberite **Nastavi s Facebookom** da se prijavite na svoj račun Facebook oglasa.</span><span class="sxs-lookup"><span data-stu-id="a1f08-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="a1f08-113">Omogućite dozvolu za **upravljanje oglasima** nakon provjere autentičnosti pomoću usluge Facebook.</span><span class="sxs-lookup"><span data-stu-id="a1f08-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="a1f08-114">Odaberite **Upravitelj Facebook oglasa** s kojim želite raditi.</span><span class="sxs-lookup"><span data-stu-id="a1f08-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="a1f08-115">Odaberite **Postojeću prilagođenu publiku** s padajućeg popisa ili stvorite **Novu prilagođenu publiku**.</span><span class="sxs-lookup"><span data-stu-id="a1f08-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="a1f08-116">Za više informacija pogledajte [**Publike u Upravitelju Facebook oglasa**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="a1f08-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="a1f08-117">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="a1f08-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a1f08-118">Odaberite **Dalje** da biste konfigurirali izvoz.</span><span class="sxs-lookup"><span data-stu-id="a1f08-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="a1f08-119">Konfiguracija poveznika</span><span class="sxs-lookup"><span data-stu-id="a1f08-119">Configure the connector</span></span>

1. <span data-ttu-id="a1f08-120">U polju **Odaberite ključni identifikator**, odaberite **E-pošta**, **Ime i adresa** ili **Telefon** koji će se poslati u Upravitelj Facebook oglasa.</span><span class="sxs-lookup"><span data-stu-id="a1f08-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="a1f08-121">Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za odabrani identifikator ključa.</span><span class="sxs-lookup"><span data-stu-id="a1f08-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="a1f08-122">[SAVJET] Najveće šanse za podudaranje pojavljuju se ako kao ključni identifikator odaberete **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="a1f08-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="a1f08-123">Dodavanje dodatnih identifikatora može poboljšati podudaranje.</span><span class="sxs-lookup"><span data-stu-id="a1f08-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="a1f08-124">Odaberite **Dodaj atribut** da biste mapirali dodatnih atributa koji se šalju Upravitelju Facebook oglasa.</span><span class="sxs-lookup"><span data-stu-id="a1f08-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="a1f08-125">Atributi iz Upravitelja Facebook oglasa preslikavaju se na sljedeća korisnička imena: **FN** = **Ime**, **LN** = **Prezime**, **FI** = **Prvi inicijal**, **PHONE** = **Telefon**, **GEN** = **Pol**, **DOB** = **Datum rođenja**, **ST** = **Savezna država**, **CT** = **Grad**, **ZIP** = **Poštanski broj**, **COUNTRY** = **Država / regija**</span><span class="sxs-lookup"><span data-stu-id="a1f08-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="a1f08-126">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="a1f08-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="a1f08-127">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="a1f08-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a1f08-128">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="a1f08-128">Export the data</span></span>

<span data-ttu-id="a1f08-129">Možete [izvesti podatke na zahtjev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a1f08-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a1f08-130">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a1f08-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a1f08-131">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="a1f08-131">Data privacy and compliance</span></span>

<span data-ttu-id="a1f08-132">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Upravitelj Facebook oglasa, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="a1f08-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a1f08-133">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da usluga Facebook oglasi ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="a1f08-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a1f08-134">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a1f08-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a1f08-135">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="a1f08-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
