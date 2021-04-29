---
title: Izvoz podataka usluge Customer Insights u SendGrid
description: Saznajte kako konfigurirati vezu i izvesti u SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759756"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="20a9d-103">Izvoz segmenata u SendGrid (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="20a9d-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="20a9d-104">Izvezite segmente objedinjenih profila klijenata u popise kontakata usluge SendGrid i koristite ih za kampanje i marketing putem e-pošte u usluzi SendGrid.</span><span class="sxs-lookup"><span data-stu-id="20a9d-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="20a9d-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="20a9d-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="20a9d-106">Imate [račun za SendGrid](https://sendgrid.com/) i odgovarajuće vjerodajnice administratora.</span><span class="sxs-lookup"><span data-stu-id="20a9d-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="20a9d-107">SendGrid sadrži postojeće popise kontakata i odgovarajuće ID-jeve.</span><span class="sxs-lookup"><span data-stu-id="20a9d-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="20a9d-108">Za dodatne informacije pogledajte [SendGrid – Upravljanje kontaktima](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="20a9d-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="20a9d-109">Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="20a9d-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="20a9d-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="20a9d-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="20a9d-111">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="20a9d-111">Known limitations</span></span>

- <span data-ttu-id="20a9d-112">Ukupno do 100 000 profila u SendGrid.</span><span class="sxs-lookup"><span data-stu-id="20a9d-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="20a9d-113">Izvoz u SendGrid ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="20a9d-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="20a9d-114">Izvoz do 100 000 profila u SendGrid može potrajati do nekoliko sati.</span><span class="sxs-lookup"><span data-stu-id="20a9d-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="20a9d-115">Broj profila koje možete izvesti u SendGrid ovisi i ograničen je vašim ugovorom s tvrtkom SendGrid.</span><span class="sxs-lookup"><span data-stu-id="20a9d-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="20a9d-116">Postavljanje veze sa SendGrid</span><span class="sxs-lookup"><span data-stu-id="20a9d-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="20a9d-117">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="20a9d-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="20a9d-118">Odaberite **Dodaj vezu** i odaberite **SendGrid** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="20a9d-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="20a9d-119">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="20a9d-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="20a9d-120">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="20a9d-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="20a9d-121">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="20a9d-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="20a9d-122">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="20a9d-122">Choose who can use this connection.</span></span> <span data-ttu-id="20a9d-123">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="20a9d-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="20a9d-124">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="20a9d-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="20a9d-125">Unesite svoj **Ključ za API za SendGrid** [Ključ za API za SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="20a9d-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="20a9d-126">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="20a9d-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="20a9d-127">Odaberite **Poveži** za inicijalizaciju veze s uslugom SendGrid.</span><span class="sxs-lookup"><span data-stu-id="20a9d-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="20a9d-128">Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="20a9d-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="20a9d-129">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="20a9d-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="20a9d-130">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="20a9d-130">Configure an export</span></span>

<span data-ttu-id="20a9d-131">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="20a9d-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="20a9d-132">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="20a9d-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="20a9d-133">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="20a9d-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="20a9d-134">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="20a9d-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="20a9d-135">U polju **Veza za izvoz** odaberite vezu iz odjeljka SendGrid.</span><span class="sxs-lookup"><span data-stu-id="20a9d-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="20a9d-136">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="20a9d-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="20a9d-137">Unesite svoj **[ID popisa usluge SendGridI](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="20a9d-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="20a9d-138">U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="20a9d-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="20a9d-139">Ponovite iste korake za ostala neobavezna polja kao što su **Ime**, **Prezime**, **Zemlja/Regija**, **Država**, **Grad** i **Poštanski broj**.</span><span class="sxs-lookup"><span data-stu-id="20a9d-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="20a9d-140">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="20a9d-140">Select the segments you want to export.</span></span> <span data-ttu-id="20a9d-141">Snažno **preporučujemo da ne izvozite više od ukupno 100 000 profila klijenata** u uslugu SendGrid.</span><span class="sxs-lookup"><span data-stu-id="20a9d-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="20a9d-142">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="20a9d-142">Select **Save**.</span></span>

<span data-ttu-id="20a9d-143">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="20a9d-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="20a9d-144">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="20a9d-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="20a9d-145">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="20a9d-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="20a9d-146">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="20a9d-146">Data privacy and compliance</span></span>

<span data-ttu-id="20a9d-147">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u SendGrid, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="20a9d-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="20a9d-148">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da SendGrid ispunjava sve obaveze zaštite privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="20a9d-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="20a9d-149">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="20a9d-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="20a9d-150">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="20a9d-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]