---
title: Izvoz podataka usluge Customer Insights u Marketo
description: Saznajte kako konfigurirati vezu i izvesti u Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759812"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="31a16-103">Izvoz segmenata u Marketo (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="31a16-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="31a16-104">Izvezite segmente objedinjenih profila klijenata da biste generirali kampanje, pružili marketing putem e-pošte i koristili određene grupe klijenata pomoću usluge Marketo.</span><span class="sxs-lookup"><span data-stu-id="31a16-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="31a16-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="31a16-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="31a16-106">Imate [račun za Marketo](https://login.marketo.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="31a16-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="31a16-107">Marketo sadrži postojeće popise i odgovarajuće ID-ove.</span><span class="sxs-lookup"><span data-stu-id="31a16-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="31a16-108">Dodatne informacije potražite u [popisima usluge Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="31a16-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="31a16-109">Imate [konfigurirane segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="31a16-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="31a16-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="31a16-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="31a16-111">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="31a16-111">Known limitations</span></span>

- <span data-ttu-id="31a16-112">Do 1 milijun profila po izvozu u Marketo.</span><span class="sxs-lookup"><span data-stu-id="31a16-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="31a16-113">Izvoz u Marketo ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="31a16-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="31a16-114">Izvoz segmenata s ukupno milijun profila može trajati do 3 sata.</span><span class="sxs-lookup"><span data-stu-id="31a16-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="31a16-115">Broj profila koje možete izvesti u Marketo ovisi i ograničen je vašim ugovorom s tvrtkom Marketo.</span><span class="sxs-lookup"><span data-stu-id="31a16-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="31a16-116">Postavljanje veze s Marketo</span><span class="sxs-lookup"><span data-stu-id="31a16-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="31a16-117">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="31a16-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="31a16-118">Odaberite **Dodaj vezu** i odaberite **Marketo** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="31a16-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="31a16-119">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="31a16-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="31a16-120">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="31a16-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="31a16-121">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="31a16-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="31a16-122">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="31a16-122">Choose who can use this connection.</span></span> <span data-ttu-id="31a16-123">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="31a16-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="31a16-124">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="31a16-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="31a16-125">Unesite svoj **[ID klijenta za Marketo, klijentski tajni ključ i naziv glavnog računala krajnje točke za REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="31a16-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="31a16-126">Odaberite **Slažem se** da biste potvrdili **Privatnost i usklađenost podataka** i odaberite **Povezivanje** za inicijalizaciju veze s uslugom Marketo.</span><span class="sxs-lookup"><span data-stu-id="31a16-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="31a16-127">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="31a16-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="31a16-128">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="31a16-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="31a16-129">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="31a16-129">Configure an export</span></span>

<span data-ttu-id="31a16-130">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="31a16-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="31a16-131">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="31a16-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="31a16-132">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="31a16-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="31a16-133">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="31a16-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="31a16-134">U polju **Veza za izvoz** odaberite vezu iz odjeljka Marketo.</span><span class="sxs-lookup"><span data-stu-id="31a16-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="31a16-135">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="31a16-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="31a16-136">Unesite svoj **[ID popisa usluge Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="31a16-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="31a16-137">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="31a16-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="31a16-138">Neobavezno možete izvesti **Ime**, **Prezime**, **Grad**, **Država** **Zemlja/Regija**  za stvaranje personaliziranije e-pošte.</span><span class="sxs-lookup"><span data-stu-id="31a16-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="31a16-139">Odaberite **Dodavanje atributa** za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="31a16-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="31a16-140">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="31a16-140">Select the segments you want to export.</span></span> <span data-ttu-id="31a16-141">U Marketo možete ukupno izvesti do 1 milijun profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="31a16-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="31a16-142">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="31a16-142">Select **Save**.</span></span>

<span data-ttu-id="31a16-143">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="31a16-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="31a16-144">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="31a16-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="31a16-145">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="31a16-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="31a16-146">U usluzi Marketo svoje segmente sada možete pronaći u odjeljku [popisi usluge Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="31a16-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="31a16-147">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="31a16-147">Data privacy and compliance</span></span>

<span data-ttu-id="31a16-148">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Marketo, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="31a16-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="31a16-149">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Marketo ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="31a16-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="31a16-150">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="31a16-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="31a16-151">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="31a16-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]