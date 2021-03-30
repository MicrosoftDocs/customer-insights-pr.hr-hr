---
title: Izvoz podataka usluge Customer Insights u Marketo
description: Saznajte kako konfigurirati vezu s uslugom Marketo.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597962"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="0f863-103">Poveznik za Marketo (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="0f863-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="0f863-104">Izvezite segmente objedinjenih profila klijenata da biste generirali kampanje, pružili marketing putem e-pošte i koristili određene grupe klijenata pomoću usluge Marketo.</span><span class="sxs-lookup"><span data-stu-id="0f863-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f863-105">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="0f863-105">Prerequisites</span></span>

-   <span data-ttu-id="0f863-106">Imate [račun za Marketo](https://login.marketo.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="0f863-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0f863-107">Marketo sadrži postojeće popise i odgovarajuće ID-ove.</span><span class="sxs-lookup"><span data-stu-id="0f863-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="0f863-108">Dodatne informacije potražite u [popisima usluge Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="0f863-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="0f863-109">Imate [konfigurirane segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="0f863-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="0f863-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="0f863-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="0f863-111">Povezivanje s uslugom Marketo</span><span class="sxs-lookup"><span data-stu-id="0f863-111">Connect to Marketo</span></span>

1. <span data-ttu-id="0f863-112">Otvorite **Administrator** > **Izvozna odredišta**.</span><span class="sxs-lookup"><span data-stu-id="0f863-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0f863-113">U odjeljku **Marketo** odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="0f863-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="0f863-114">Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="0f863-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0f863-115">Unesite svoj **[ID klijenta usluge Marketo, klijentski tajni ključ i naziv glavnog računala krajnje točke za REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="0f863-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="0f863-116">Unesite svoj **[ID popisa usluge Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="0f863-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="0f863-117">Odaberite **Slažem se** da biste potvrdili **Privatnost i usklađenost podataka** i odaberite **Povezivanje** za inicijalizaciju veze s uslugom Marketo.</span><span class="sxs-lookup"><span data-stu-id="0f863-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="0f863-118">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0f863-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Snimka zaslona s izvozom za vezu s uslugom Marketo":::

1. <span data-ttu-id="0f863-120">Odaberite **Dalje** da biste konfigurirali izvoz.</span><span class="sxs-lookup"><span data-stu-id="0f863-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0f863-121">Konfiguracija poveznika</span><span class="sxs-lookup"><span data-stu-id="0f863-121">Configure the connector</span></span>

1. <span data-ttu-id="0f863-122">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="0f863-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="0f863-123">Ako želite, možete izvesti stavke **Ime**, **Prezime**, **Grad**, **Pokrajina** i **Država/regija** kao dodatna polja za stvaranje osobnijih poruka e-pošte.</span><span class="sxs-lookup"><span data-stu-id="0f863-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="0f863-124">Odaberite **Dodavanje atributa** za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="0f863-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0f863-125">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="0f863-125">Select the segments you want to export.</span></span> <span data-ttu-id="0f863-126">U Marketo možete ukupno izvesti do 1 milijun profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="0f863-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Odabir polja i segmenata za izvoz u Marketo":::

1. <span data-ttu-id="0f863-128">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="0f863-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0f863-129">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="0f863-129">Export the data</span></span>

<span data-ttu-id="0f863-130">Možete [izvesti podatke na zahtjev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0f863-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0f863-131">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0f863-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0f863-132">U usluzi Marketo svoje segmente sada možete pronaći u odjeljku [popisi usluge Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="0f863-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0f863-133">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="0f863-133">Known limitations</span></span>

- <span data-ttu-id="0f863-134">Do 1 milijun profila po izvozu u Marketo.</span><span class="sxs-lookup"><span data-stu-id="0f863-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="0f863-135">Izvoz u Marketo ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="0f863-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="0f863-136">Izvoz segmenata s ukupno milijun profila može trajati do 3 sata.</span><span class="sxs-lookup"><span data-stu-id="0f863-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="0f863-137">Broj profila koje možete izvesti u Marketo ovisi i ograničen je vašim ugovorom s tvrtkom Marketo.</span><span class="sxs-lookup"><span data-stu-id="0f863-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0f863-138">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="0f863-138">Data privacy and compliance</span></span>

<span data-ttu-id="0f863-139">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Marketo, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="0f863-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0f863-140">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Marketo ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="0f863-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0f863-141">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0f863-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0f863-142">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="0f863-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]