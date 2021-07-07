---
title: Izvoz podataka značajke Customer Insights u Sendinblue
description: Saznajte kako konfigurirati vezu i izvesti u Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314589"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="0f217-103">Izvoz segmenata u Sendinblue (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="0f217-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="0f217-104">Segmente objedinjenih klijenskih profila izvezite za generiranje kampanja, pružanje marketinga putem e-pošte i iskorištavanje određenih grupa klijenata uz Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="0f217-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="0f217-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="0f217-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="0f217-106">Imate [račun za Sendinblue](https://www.sendinblue.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="0f217-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0f217-107">Ima postojećih popisa na servisu Sendinblue i odgovarajućih ID-ova.</span><span class="sxs-lookup"><span data-stu-id="0f217-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="0f217-108">Imate [konfigurirane segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="0f217-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="0f217-109">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="0f217-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0f217-110">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="0f217-110">Known limitations</span></span>

- <span data-ttu-id="0f217-111">Do 1 milijun profila po izvozu u Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="0f217-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="0f217-112">Izvoz u Sendinblue ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="0f217-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="0f217-113">Izvoz segmenata s ukupno 1 milijun profila može trajati do 90 minuta.</span><span class="sxs-lookup"><span data-stu-id="0f217-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="0f217-114">Broj profila koje možete izvesti u Sendinblue ovisi o vašem ugovoru sa servisom Sendinblue i njime je ograničen.</span><span class="sxs-lookup"><span data-stu-id="0f217-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="0f217-115">Postavljanje veze na Sendinblue</span><span class="sxs-lookup"><span data-stu-id="0f217-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="0f217-116">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="0f217-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0f217-117">Odaberite **Dodavanje veze** pa odaberite **Sendinblue** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="0f217-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="0f217-118">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="0f217-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0f217-119">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="0f217-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0f217-120">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="0f217-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0f217-121">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="0f217-121">Choose who can use this connection.</span></span> <span data-ttu-id="0f217-122">Prema zadanim postavkama to su samo administratori.</span><span class="sxs-lookup"><span data-stu-id="0f217-122">By default it's only administrators.</span></span> <span data-ttu-id="0f217-123">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0f217-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0f217-124">Unesite svoj **[ključ API-ja za SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="0f217-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="0f217-125">Odaberite **Slažem se** da biste potvrdili **Privatnost podataka i usklađenost** pa odaberite **Spoji** za pokretanje veze sa servisom Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="0f217-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="0f217-126">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0f217-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0f217-127">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="0f217-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0f217-128">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="0f217-128">Configure an export</span></span>

<span data-ttu-id="0f217-129">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="0f217-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0f217-130">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0f217-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0f217-131">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="0f217-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0f217-132">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="0f217-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0f217-133">U polju **Veza za izvoz** odaberite vezu iz odjeljka Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="0f217-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="0f217-134">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="0f217-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0f217-135">Unesite svoj **ID popisa za Sendinblue**</span><span class="sxs-lookup"><span data-stu-id="0f217-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="0f217-136">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="0f217-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="0f217-137">Po želji možete izvesti **Ime**, **Prezime** i **Telefon**  da biste stvorili personaliziraniju e-poštu.</span><span class="sxs-lookup"><span data-stu-id="0f217-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="0f217-138">Odaberite **Dodavanje atributa** za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="0f217-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0f217-139">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="0f217-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="0f217-140">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="0f217-140">Select **Save**.</span></span>

<span data-ttu-id="0f217-141">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="0f217-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0f217-142">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0f217-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0f217-143">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0f217-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0f217-144">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="0f217-144">Data privacy and compliance</span></span>

<span data-ttu-id="0f217-145">Kad omogućite Dynamics 365 Customer Insights za prijenos podataka u Sendinblue dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke poput osobnih podataka.</span><span class="sxs-lookup"><span data-stu-id="0f217-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0f217-146">Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Sendinblue ispunjava sve obveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="0f217-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0f217-147">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0f217-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0f217-148">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="0f217-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
