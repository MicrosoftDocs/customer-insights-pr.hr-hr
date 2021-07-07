---
title: Izvoz podataka značajke Customer Insights u Salesforce Marketing Cloud
description: Saznajte kako konfigurirati vezu i izvesti u Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314588"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="00568-103">Izvoz segmenata i ostalih podataka u Salesforce Marketing Cloud (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="00568-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="00568-104">Upotrijebite podatke o klijentima na servisu Salesforce Marketing Cloud tako što ćete ih izvesti preko lokacije protokola za sigurni prijenos datoteka (SFTP).</span><span class="sxs-lookup"><span data-stu-id="00568-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="00568-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="00568-105">Prerequisites for connection</span></span>

- <span data-ttu-id="00568-106">Dostupnost SFTP hosta i odgovarajućih vjerodajnica administratora.</span><span class="sxs-lookup"><span data-stu-id="00568-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="00568-107">Kako postaviti SFTP lokacije za Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="00568-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="00568-108">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="00568-108">Known limitations</span></span>

- <span data-ttu-id="00568-109">Vrijeme izvoza ovisi o performansama vašeg sustava.</span><span class="sxs-lookup"><span data-stu-id="00568-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="00568-110">Preporučujemo dvije CPU jezgre i 1 Gb memorije kao minimalnu konfiguraciju vašeg poslužitelja.</span><span class="sxs-lookup"><span data-stu-id="00568-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="00568-111">Izvoz entiteta s do 100 milijuna korisničkih profila može potrajati 90 minuta kada se koristi preporučena minimalna konfiguracija.</span><span class="sxs-lookup"><span data-stu-id="00568-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="00568-112">Postavljanje veze na Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="00568-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="00568-113">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="00568-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="00568-114">Odaberite **Dodavanje veze** pa odaberite **Salesforce Marketing Cloud** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="00568-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="00568-115">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="00568-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="00568-116">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="00568-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="00568-117">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="00568-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="00568-118">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="00568-118">Choose who can use this connection.</span></span> <span data-ttu-id="00568-119">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="00568-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="00568-120">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="00568-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="00568-121">Navedite **Korisničko ime**, **Lozinku**, **Naziv glavnog računala** i **Mapu za izvoz** za vaš SFTP račun.</span><span class="sxs-lookup"><span data-stu-id="00568-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="00568-122">Odaberite **Provjeri** da biste testirali vezu.</span><span class="sxs-lookup"><span data-stu-id="00568-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="00568-123">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="00568-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="00568-124">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="00568-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="00568-125">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="00568-125">Configure an export</span></span>

<span data-ttu-id="00568-126">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="00568-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="00568-127">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="00568-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="00568-128">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="00568-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="00568-129">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="00568-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="00568-130">U polju **Veza za izvoz** odaberite vezu iz odjeljka SFTP.</span><span class="sxs-lookup"><span data-stu-id="00568-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="00568-131">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="00568-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="00568-132">Odaberite želite li izvesti svoje podatke **Komprimirane** ili **Nekomprimirane** i **graničnik polja** za izvezene datoteke.</span><span class="sxs-lookup"><span data-stu-id="00568-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="00568-133">Odaberite entitete, na primjer, segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="00568-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="00568-134">Svaki odabrani entitet podijelit će se u do pet izlaznih datoteka prilikom izvoza.</span><span class="sxs-lookup"><span data-stu-id="00568-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="00568-135">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="00568-135">Select **Save**.</span></span>

<span data-ttu-id="00568-136">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="00568-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="00568-137">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="00568-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="00568-138">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="00568-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="00568-139">Uvoz podataka značajke Customer Insights sa SFTP lokacije u Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="00568-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="00568-140">Stvorite [proširenja podataka na servisu Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) za uvoz podatkovne datoteke servisa Customer Insights sa SFTP lokacije.</span><span class="sxs-lookup"><span data-stu-id="00568-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="00568-141">[Uvoz podataka sa SFTP lokacije](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) u proširenje podataka servisa Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="00568-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="00568-142">Postavite automatizaciju za uvoz podataka u proširenja podataka.</span><span class="sxs-lookup"><span data-stu-id="00568-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="00568-143">Naučite više o [automatizacijama ispuštanja datoteka i zakazanim automatizacijama](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="00568-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="00568-144">Definirajte [automatizaciju ispuštanja datoteka](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ili  [zakazanu automatizaciju](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="00568-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="00568-145">Evo primjera [automatizacije sa SFTP-om](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="00568-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="00568-146">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="00568-146">Data privacy and compliance</span></span>

<span data-ttu-id="00568-147">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka putem SFTP-a, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="00568-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="00568-148">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da odredište za izvoz ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="00568-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="00568-149">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="00568-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="00568-150">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="00568-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
