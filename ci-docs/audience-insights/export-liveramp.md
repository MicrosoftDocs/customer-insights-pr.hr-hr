---
title: LiveRamp poveznik
description: Saznajte kako izvesti podatke u LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667175"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="f6b79-103">Poveznik za LiveRamp&reg; (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="f6b79-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="f6b79-104">Aktivirajte svoje podatke na usluzi LiveRamp da biste se povezali s preko 500 platformi u digitalnim, društvenim i TV ekosustavima.</span><span class="sxs-lookup"><span data-stu-id="f6b79-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="f6b79-105">Radite sa svojim podacima na usluzi LiveRamp kako biste ciljali, suzbili i personalizirali oglasne kampanje.</span><span class="sxs-lookup"><span data-stu-id="f6b79-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f6b79-106">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="f6b79-106">Prerequisites</span></span>

- <span data-ttu-id="f6b79-107">Za upotrebu ovog poveznika potrebna vam je pretplata na LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f6b79-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="f6b79-108">Da biste se pretplatili, izravno [kontaktirajte LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="f6b79-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="f6b79-109">[Saznajte više o usluzi LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="f6b79-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="f6b79-110">Povezivanje na uslugu LiveRamp</span><span class="sxs-lookup"><span data-stu-id="f6b79-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="f6b79-111">U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.</span><span class="sxs-lookup"><span data-stu-id="f6b79-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f6b79-112">Na pločici **LiveRamp** odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="f6b79-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="f6b79-113">Dodijelite odredištu prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="f6b79-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f6b79-114">Unesite **Korisničko ime** i **Lozinku** za račun LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="f6b79-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="f6b79-115">Ove vjerodajnice mogu biti različite od vaših vjerodajnica za LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="f6b79-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="f6b79-116">Odaberite **Provjeri** da biste testirali vezu s uslugom LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f6b79-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="f6b79-117">Nakon uspješne provjere dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="f6b79-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="f6b79-118">Odaberite **Dalje** za postavljanje poveznika za LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f6b79-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f6b79-119">Konfiguracija poveznika</span><span class="sxs-lookup"><span data-stu-id="f6b79-119">Configure the connector</span></span>

1. <span data-ttu-id="f6b79-120">U polju **Odabir identifikatora ključa** odaberite **E-pošta**, **Ime i adresa** ili **Telefon** da biste ih poslali usluzi LiveRamp radi potvrde identiteta.</span><span class="sxs-lookup"><span data-stu-id="f6b79-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="f6b79-121">Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za odabrani identifikator ključa.</span><span class="sxs-lookup"><span data-stu-id="f6b79-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="f6b79-122">Odaberite **Dodavanje atributa** za mapiranje dodatnih atributa koje treba poslati u LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f6b79-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="f6b79-123">Ako pošaljete više atributa identifikatora ključa usluzi LiveRamp, vjerojatno ćete dobiti višu stopu podudaranja.</span><span class="sxs-lookup"><span data-stu-id="f6b79-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="f6b79-124">Odaberite segmente koje želite eksportirati u LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f6b79-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="f6b79-125">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="f6b79-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f6b79-126">![Poveznik za LiveRamp s mapiranjem atributa](media/export-liveramp-segments.png "Poveznik za LiveRamp s mapiranjem atributa")</span><span class="sxs-lookup"><span data-stu-id="f6b79-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f6b79-127">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="f6b79-127">Export the data</span></span>

<span data-ttu-id="f6b79-128">Izvoz će započeti ubrzo ako su ispunjeni svi preduvjeti za izvoz.</span><span class="sxs-lookup"><span data-stu-id="f6b79-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="f6b79-129">Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f6b79-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="f6b79-130">Nakon uspješnog izvoza možete se prijaviti u LiveRamp Onboarding da biste aktivirali i distribuirali svoje podatke.</span><span class="sxs-lookup"><span data-stu-id="f6b79-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f6b79-131">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="f6b79-131">Data privacy and compliance</span></span>

<span data-ttu-id="f6b79-132">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Liveramp, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="f6b79-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f6b79-133">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Liveramp ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="f6b79-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f6b79-134">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f6b79-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f6b79-135">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="f6b79-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>