---
title: Izvoz podataka usluge Customer Insights na glavna računala SFTP
description: Saznajte kako konfigurirati vezu sa SFTP računalom.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267989"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="8cc16-103">Poveznik za SFTP (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="8cc16-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="8cc16-104">Koristite svoje korisničke podatke u aplikacijama treće strane tako da ih izvezete na glavno računalo s protokolom Secure File Transfer Protocol (SFTP).</span><span class="sxs-lookup"><span data-stu-id="8cc16-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8cc16-105">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="8cc16-105">Prerequisites</span></span>

- <span data-ttu-id="8cc16-106">Dostupnost glavnog računala SFTP-a i odgovarajućih vjerodajnica.</span><span class="sxs-lookup"><span data-stu-id="8cc16-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="8cc16-107">Povezivanje s SFTP-om</span><span class="sxs-lookup"><span data-stu-id="8cc16-107">Connect to SFTP</span></span>

1. <span data-ttu-id="8cc16-108">Otvorite **Administrator** > **Izvozna odredišta**.</span><span class="sxs-lookup"><span data-stu-id="8cc16-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8cc16-109">Pod **SFTP**, odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="8cc16-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="8cc16-110">Dodijelite odredištu prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="8cc16-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8cc16-111">Navedite **Korisničko ime**, **Lozinku**, **Naziv glavnog računala** i **Mapu za izvoz** za vaš SFTP račun.</span><span class="sxs-lookup"><span data-stu-id="8cc16-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="8cc16-112">Odaberite **Provjeri** da biste testirali vezu.</span><span class="sxs-lookup"><span data-stu-id="8cc16-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="8cc16-113">Nakon uspješne provjere valjanosti odaberite želite li izvesti svoje podatke kao **Komprimirane** ili **Raspakirane** i odaberite **graničnik polja** za izvezene datoteke.</span><span class="sxs-lookup"><span data-stu-id="8cc16-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="8cc16-114">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="8cc16-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8cc16-115">Odaberite **Dalje** za početak konfiguriranja izvoza.</span><span class="sxs-lookup"><span data-stu-id="8cc16-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="8cc16-116">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="8cc16-116">Configure the export</span></span>

1. <span data-ttu-id="8cc16-117">Odaberite entitete, na primjer, segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="8cc16-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8cc16-118">Svaki odabrani entitet imat će do pet izlaznih datoteka prilikom izvoza.</span><span class="sxs-lookup"><span data-stu-id="8cc16-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="8cc16-119">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="8cc16-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8cc16-120">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="8cc16-120">Export the data</span></span>

<span data-ttu-id="8cc16-121">Možete [izvesti podatke na zahtjev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8cc16-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8cc16-122">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8cc16-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8cc16-123">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="8cc16-123">Known limitations</span></span>

- <span data-ttu-id="8cc16-124">Vrijeme izvoza ovisi o performansama vašeg sustava.</span><span class="sxs-lookup"><span data-stu-id="8cc16-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="8cc16-125">Preporučujemo dvije CPU jezgre i 1 Gb memorije kao minimalnu konfiguraciju vašeg poslužitelja.</span><span class="sxs-lookup"><span data-stu-id="8cc16-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="8cc16-126">Izvoz entiteta s do 100 milijuna profila klijenata može potrajati 90 minuta kada se koristi preporučena minimalna konfiguracija dviju CPU jezgri i 1 Gb memorije.</span><span class="sxs-lookup"><span data-stu-id="8cc16-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8cc16-127">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="8cc16-127">Data privacy and compliance</span></span>

<span data-ttu-id="8cc16-128">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka putem SFTP-a, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="8cc16-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8cc16-129">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da odredište za izvoz ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="8cc16-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8cc16-130">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8cc16-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8cc16-131">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="8cc16-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]