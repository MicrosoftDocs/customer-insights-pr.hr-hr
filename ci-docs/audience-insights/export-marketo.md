---
title: Izvoz podataka usluge Customer Insights u Marketo
description: Saznajte kako konfigurirati vezu i izvesti u Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059307"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="efabf-103">Izvoz segmenata u Marketo (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="efabf-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="efabf-104">Izvezite segmente objedinjenih profila klijenata da biste generirali kampanje, pružili marketing putem e-pošte i koristili određene grupe klijenata pomoću usluge Marketo.</span><span class="sxs-lookup"><span data-stu-id="efabf-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="efabf-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="efabf-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="efabf-106">Imate [račun za Marketo](https://login.marketo.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="efabf-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="efabf-107">Marketo sadrži postojeće popise i odgovarajuće ID-ove.</span><span class="sxs-lookup"><span data-stu-id="efabf-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="efabf-108">Dodatne informacije potražite u [popisima usluge Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="efabf-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="efabf-109">Imate [konfigurirane segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="efabf-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="efabf-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="efabf-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="efabf-111">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="efabf-111">Known limitations</span></span>

- <span data-ttu-id="efabf-112">Do 1 milijun profila po izvozu u Marketo.</span><span class="sxs-lookup"><span data-stu-id="efabf-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="efabf-113">Izvoz u Marketo ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="efabf-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="efabf-114">Izvoz segmenata s ukupno milijun profila može trajati do 3 sata.</span><span class="sxs-lookup"><span data-stu-id="efabf-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="efabf-115">Broj profila koje možete izvesti u Marketo ovisi i ograničen je vašim ugovorom s tvrtkom Marketo.</span><span class="sxs-lookup"><span data-stu-id="efabf-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="efabf-116">Postavljanje veze s Marketo</span><span class="sxs-lookup"><span data-stu-id="efabf-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="efabf-117">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="efabf-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="efabf-118">Odaberite **Dodaj vezu** i odaberite **Marketo** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="efabf-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="efabf-119">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="efabf-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="efabf-120">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="efabf-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="efabf-121">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="efabf-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="efabf-122">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="efabf-122">Choose who can use this connection.</span></span> <span data-ttu-id="efabf-123">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="efabf-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="efabf-124">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="efabf-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="efabf-125">Unesite svoj **[ID klijenta za Marketo, klijentski tajni ključ i naziv glavnog računala krajnje točke za REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="efabf-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="efabf-126">Naziv glavnog računala krajnje točke za REST je samo naziv glavnog računala, bez `https://`.</span><span class="sxs-lookup"><span data-stu-id="efabf-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="efabf-127">Primjer: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="efabf-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="efabf-128">Odaberite **Slažem se** da biste potvrdili **Privatnost i usklađenost podataka** i odaberite **Povezivanje** za inicijalizaciju veze s uslugom Marketo.</span><span class="sxs-lookup"><span data-stu-id="efabf-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="efabf-129">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="efabf-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="efabf-130">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="efabf-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="efabf-131">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="efabf-131">Configure an export</span></span>

<span data-ttu-id="efabf-132">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="efabf-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="efabf-133">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="efabf-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="efabf-134">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="efabf-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="efabf-135">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="efabf-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="efabf-136">U polju **Veza za izvoz** odaberite vezu iz odjeljka Marketo.</span><span class="sxs-lookup"><span data-stu-id="efabf-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="efabf-137">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="efabf-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="efabf-138">Unesite svoj **[ID popisa usluge Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="efabf-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="efabf-139">ID popisa je čisto numerička vrijednost.</span><span class="sxs-lookup"><span data-stu-id="efabf-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="efabf-140">Na primjer, ako je vaš ID popisa usluge Marketo ST12345A7, uklonite znak prije i iza brojeva i unesite `12345`.</span><span class="sxs-lookup"><span data-stu-id="efabf-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="efabf-141">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="efabf-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="efabf-142">Neobavezno možete izvesti **Ime**, **Prezime**, **Grad**, **Država** **Zemlja/Regija**  za stvaranje personaliziranije e-pošte.</span><span class="sxs-lookup"><span data-stu-id="efabf-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="efabf-143">Odaberite **Dodavanje atributa** za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="efabf-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="efabf-144">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="efabf-144">Select the segments you want to export.</span></span> <span data-ttu-id="efabf-145">U Marketo možete ukupno izvesti do 1 milijun profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="efabf-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="efabf-146">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="efabf-146">Select **Save**.</span></span>

<span data-ttu-id="efabf-147">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="efabf-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="efabf-148">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="efabf-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="efabf-149">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="efabf-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="efabf-150">U usluzi Marketo svoje segmente sada možete pronaći u odjeljku [popisi usluge Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="efabf-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="efabf-151">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="efabf-151">Data privacy and compliance</span></span>

<span data-ttu-id="efabf-152">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Marketo, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="efabf-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="efabf-153">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Marketo ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="efabf-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="efabf-154">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="efabf-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="efabf-155">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="efabf-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
