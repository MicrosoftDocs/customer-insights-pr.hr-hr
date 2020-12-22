---
title: Izvoz podataka usluge Customer Insights na glavna računala SFTP
description: Saznajte kako konfigurirati vezu sa SFTP računalom.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643494"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="6f03a-103">Poveznik za SFTP (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="6f03a-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="6f03a-104">Koristite svoje korisničke podatke u aplikacijama treće strane tako da ih izvezete na glavno računalo s protokolom Secure File Transfer Protocol (SFTP).</span><span class="sxs-lookup"><span data-stu-id="6f03a-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6f03a-105">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="6f03a-105">Prerequisites</span></span>

- <span data-ttu-id="6f03a-106">Dostupnost SFTP računala i odgovarajućih vjerodajnica.</span><span class="sxs-lookup"><span data-stu-id="6f03a-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="6f03a-107">Povezivanje sa SFTP-om</span><span class="sxs-lookup"><span data-stu-id="6f03a-107">Connect to SFTP</span></span>

1. <span data-ttu-id="6f03a-108">Otvorite **Administrator** > **Izvozna odredišta**.</span><span class="sxs-lookup"><span data-stu-id="6f03a-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6f03a-109">Pod **SFTP**, odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="6f03a-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="6f03a-110">Dodijelite odredištu prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="6f03a-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="6f03a-111">Navedite **Korisničko ime**, **Lozinku** i **Naziv glavnog računala** za vaš SFTP račun.</span><span class="sxs-lookup"><span data-stu-id="6f03a-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="6f03a-112">Primjer: Ako je korijenska mapa vašeg SFTP poslužitelja /root/folder, a želite da se podaci izvezu u root/folder/ci_export_destination_folder, glavno bi računalo trebalo biti sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="6f03a-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="6f03a-113">Odaberite **Provjeri** da biste testirali vezu.</span><span class="sxs-lookup"><span data-stu-id="6f03a-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="6f03a-114">Nakon uspješne provjere, odaberite želite li izvesti svoje podatke **Komprimirane** ili **Nekomprimirane** i odaberite **razdjelnik polja** za izvezene datoteke.</span><span class="sxs-lookup"><span data-stu-id="6f03a-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="6f03a-115">Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.</span><span class="sxs-lookup"><span data-stu-id="6f03a-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6f03a-116">Odaberite **Dalje** za početak konfiguriranja izvoza.</span><span class="sxs-lookup"><span data-stu-id="6f03a-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="6f03a-117">Konfiguriranje veze</span><span class="sxs-lookup"><span data-stu-id="6f03a-117">Configure the connection</span></span>

1. <span data-ttu-id="6f03a-118">Odaberite **atribute klijenta** koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="6f03a-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="6f03a-119">Možete izvesti jedan ili više atributa.</span><span class="sxs-lookup"><span data-stu-id="6f03a-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="6f03a-120">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="6f03a-120">Select **Next**.</span></span>

1. <span data-ttu-id="6f03a-121">Odaberite segmente koje želite izvesti.</span><span class="sxs-lookup"><span data-stu-id="6f03a-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="6f03a-122">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="6f03a-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6f03a-123">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="6f03a-123">Export the data</span></span>

<span data-ttu-id="6f03a-124">Možete [izvesti podatke na zahtjev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6f03a-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6f03a-125">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6f03a-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6f03a-126">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="6f03a-126">Data privacy and compliance</span></span>

<span data-ttu-id="6f03a-127">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka putem SFTP-a, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="6f03a-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6f03a-128">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da odredište za izvoz ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="6f03a-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6f03a-129">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6f03a-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6f03a-130">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="6f03a-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
