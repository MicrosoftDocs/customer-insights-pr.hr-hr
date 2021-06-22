---
title: Izvoz podataka usluge Customer Insights na glavna računala SFTP
description: Saznajte kako konfigurirati vezu i izvesti na SFTP lokaciju.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 000b44dc8e5cc419132bd17e359fbdd5879caf1b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124310"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a><span data-ttu-id="b71f9-103">Izvoz segmenata i ostalih podataka na SFTP (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="b71f9-103">Export segments and other data to SFTP (preview)</span></span>

<span data-ttu-id="b71f9-104">Koristite svoje podatke o klijentima u aplikacijama trećih strana tako što ćete ih izvesti na lokaciju sigurnog protokola prijenosa datoteka (SFTP).</span><span class="sxs-lookup"><span data-stu-id="b71f9-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="b71f9-105">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="b71f9-105">Prerequisites for connection</span></span>

- <span data-ttu-id="b71f9-106">Dostupnost glavnog računala SFTP-a i odgovarajućih vjerodajnica.</span><span class="sxs-lookup"><span data-stu-id="b71f9-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b71f9-107">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="b71f9-107">Known limitations</span></span>

- <span data-ttu-id="b71f9-108">Vrijeme izvoza ovisi o performansama vašeg sustava.</span><span class="sxs-lookup"><span data-stu-id="b71f9-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="b71f9-109">Preporučujemo dvije CPU jezgre i 1 Gb memorije kao minimalnu konfiguraciju vašeg poslužitelja.</span><span class="sxs-lookup"><span data-stu-id="b71f9-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="b71f9-110">Izvoz entiteta s do 100 milijuna profila klijenata može potrajati 90 minuta kada se koristi preporučena minimalna konfiguracija dviju CPU jezgri i 1 Gb memorije.</span><span class="sxs-lookup"><span data-stu-id="b71f9-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="b71f9-111">Postavljanje veze sa SFTP</span><span class="sxs-lookup"><span data-stu-id="b71f9-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="b71f9-112">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="b71f9-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b71f9-113">Odaberite **Dodaj vezu** i odaberite **SFTP** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="b71f9-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="b71f9-114">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="b71f9-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b71f9-115">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="b71f9-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b71f9-116">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="b71f9-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b71f9-117">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="b71f9-117">Choose who can use this connection.</span></span> <span data-ttu-id="b71f9-118">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="b71f9-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b71f9-119">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b71f9-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b71f9-120">Navedite **Korisničko ime**, **Lozinku**, **Naziv glavnog računala** i **Mapu za izvoz** za vaš SFTP račun.</span><span class="sxs-lookup"><span data-stu-id="b71f9-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="b71f9-121">Odaberite **Provjeri** da biste testirali vezu.</span><span class="sxs-lookup"><span data-stu-id="b71f9-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="b71f9-122">Odaberite želite li izvesti svoje podatke **Komprimirane** ili **Nekomprimirane** i **graničnik polja** za izvezene datoteke.</span><span class="sxs-lookup"><span data-stu-id="b71f9-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="b71f9-123">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="b71f9-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b71f9-124">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="b71f9-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b71f9-125">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="b71f9-125">Configure an export</span></span>

<span data-ttu-id="b71f9-126">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="b71f9-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b71f9-127">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b71f9-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b71f9-128">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="b71f9-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b71f9-129">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="b71f9-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b71f9-130">U polju **Veza za izvoz** odaberite vezu iz odjeljka SFTP.</span><span class="sxs-lookup"><span data-stu-id="b71f9-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="b71f9-131">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="b71f9-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b71f9-132">Odaberite entitete, na primjer, segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="b71f9-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b71f9-133">Svaki odabrani entitet podijelit će se u do pet izlaznih datoteka prilikom izvoza.</span><span class="sxs-lookup"><span data-stu-id="b71f9-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="b71f9-134">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="b71f9-134">Select **Save**.</span></span>

<span data-ttu-id="b71f9-135">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="b71f9-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b71f9-136">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b71f9-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b71f9-137">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b71f9-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b71f9-138">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="b71f9-138">Data privacy and compliance</span></span>

<span data-ttu-id="b71f9-139">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka putem SFTP-a, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="b71f9-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b71f9-140">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da odredište za izvoz ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="b71f9-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b71f9-141">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b71f9-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b71f9-142">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="b71f9-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
