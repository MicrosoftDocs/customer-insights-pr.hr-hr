---
title: Izvoz podataka usluge Customer Insights u DotDigital
description: Saznajte kako konfigurirati vezu i izvesti u DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124402"
---
# <a name="export-segments-to-dotdigital-preview"></a><span data-ttu-id="8e9e7-103">Izvoz segmenata u DotDigital (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="8e9e7-103">Export segments to DotDigital (preview)</span></span>

<span data-ttu-id="8e9e7-104">Izvezite segmente objedinjenih profila klijenata u adresare usluge DotDigital i koristite ih za kampanje, marketing putem e-pošte i za izgradnju segmenata klijenata pomoću usluge DotDigital.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="8e9e7-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="8e9e7-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="8e9e7-106">Imate [račun za DotDigital](https://dotdigital.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8e9e7-107">DotDigital sadrži postojeće adresare i odgovarajuće ID-ove.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="8e9e7-108">ID se može pronaći u URL-u kada odaberete i otvorite adresar.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="8e9e7-109">Dodatne informacije potražite u [adresarima usluge DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="8e9e7-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="8e9e7-110">Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8e9e7-111">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8e9e7-112">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="8e9e7-112">Known limitations</span></span>

- <span data-ttu-id="8e9e7-113">Do 1 milijun profila po izvozu u DotDigital.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="8e9e7-114">Izvoz u DotDigital ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="8e9e7-115">Izvoz segmenata s ukupno milijun profila može potrajati do 3 sata zbog ograničenja na strani davatelja usluga.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="8e9e7-116">Broj profila koje možete izvesti u DotDigital ovisi i ograničen je vašim ugovorom s tvrtkom DotDigital.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="8e9e7-117">Postavljanje veze s DotDigital</span><span class="sxs-lookup"><span data-stu-id="8e9e7-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="8e9e7-118">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8e9e7-119">Odaberite **Dodaj vezu** i odaberite **DotDigital** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="8e9e7-120">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8e9e7-121">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8e9e7-122">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8e9e7-123">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-123">Choose who can use this connection.</span></span> <span data-ttu-id="8e9e7-124">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8e9e7-125">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8e9e7-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8e9e7-126">Unesite **korisničko ime i lozinku za DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="8e9e7-127">Unesite svoj **[ID adresara usluge DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="8e9e7-128">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8e9e7-129">Odaberite **Povezivanje** za inicijalizaciju veze s uslugom DotDigital.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="8e9e7-130">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8e9e7-131">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="8e9e7-132">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="8e9e7-132">Configure an export</span></span>

<span data-ttu-id="8e9e7-133">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8e9e7-134">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8e9e7-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8e9e7-135">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8e9e7-136">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8e9e7-137">U polju **Veza za izvoz** odaberite vezu iz odjeljka DotDigital.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="8e9e7-138">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="8e9e7-139">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8e9e7-140">Ponovite iste korake za druga neobavezna polja kao što su **Ime**, **Prezime**, **Puno ime**, **Spol** i **Poštanski broj**.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="8e9e7-141">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-141">Select the segments you want to export.</span></span> <span data-ttu-id="8e9e7-142">U DotDigital možete ukupno izvesti do 1 milijun profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="8e9e7-143">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-143">Select **Save**.</span></span>

<span data-ttu-id="8e9e7-144">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8e9e7-145">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8e9e7-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8e9e7-146">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8e9e7-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="8e9e7-147">U usluzi DotDigital sada možete pronaći svoje segmente u [adresaru usluge DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="8e9e7-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8e9e7-148">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="8e9e7-148">Data privacy and compliance</span></span>

<span data-ttu-id="8e9e7-149">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u DotDigital, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8e9e7-150">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da DotDigital ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="8e9e7-151">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8e9e7-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8e9e7-152">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="8e9e7-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
