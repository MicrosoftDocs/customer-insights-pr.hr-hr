---
title: LiveRamp poveznik
description: Saznajte kako konfigurirati vezu i izvesti u LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760318"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="31fe8-103">Izvoz segmenata u LiveRamp&reg; (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="31fe8-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="31fe8-104">Aktivirajte svoje podatke u LiveRamp da biste se povezali s više od 500 platformi putem digitalnih i društvenih mreža te televizora.</span><span class="sxs-lookup"><span data-stu-id="31fe8-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="31fe8-105">Radite sa svojim podacima na usluzi LiveRamp kako biste ciljali, suzbili i personalizirali oglasne kampanje.</span><span class="sxs-lookup"><span data-stu-id="31fe8-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="31fe8-106">Preduvjeti za vezu</span><span class="sxs-lookup"><span data-stu-id="31fe8-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="31fe8-107">Za upotrebu ovog poveznika potrebna vam je pretplata na LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="31fe8-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="31fe8-108">Da biste se pretplatili, izravno [kontaktirajte LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="31fe8-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="31fe8-109">[Saznajte više o usluzi LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="31fe8-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="31fe8-110">Postavljanje veze s LiveRamp</span><span class="sxs-lookup"><span data-stu-id="31fe8-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="31fe8-111">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="31fe8-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="31fe8-112">Odaberite **Dodaj vezu** i odaberite **LiveRamp** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="31fe8-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="31fe8-113">Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="31fe8-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="31fe8-114">Naziv i vrsta veze opisuju tu vezu.</span><span class="sxs-lookup"><span data-stu-id="31fe8-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="31fe8-115">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="31fe8-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="31fe8-116">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="31fe8-116">Choose who can use this connection.</span></span> <span data-ttu-id="31fe8-117">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="31fe8-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="31fe8-118">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="31fe8-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="31fe8-119">Unesite **Korisničko ime** i **Lozinku** za račun LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="31fe8-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="31fe8-120">Ove vjerodajnice mogu biti različite od vaših vjerodajnica za LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="31fe8-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="31fe8-121">Odaberite **Provjeri** da biste testirali vezu s uslugom LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="31fe8-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="31fe8-122">Nakon uspješne provjere dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="31fe8-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="31fe8-123">Odaberite **Spremi** da biste završili vezu.</span><span class="sxs-lookup"><span data-stu-id="31fe8-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="31fe8-124">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="31fe8-124">Configure an export</span></span>

<span data-ttu-id="31fe8-125">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="31fe8-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="31fe8-126">Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="31fe8-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="31fe8-127">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="31fe8-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="31fe8-128">Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="31fe8-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="31fe8-129">U polju **Veza za izvoz** odaberite vezu iz odjeljka LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="31fe8-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="31fe8-130">Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.</span><span class="sxs-lookup"><span data-stu-id="31fe8-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="31fe8-131">U polju **Odabir identifikatora ključa** odaberite **E-pošta**, **Ime i adresa** ili **Telefon** da biste ih poslali usluzi LiveRamp radi potvrde identiteta.</span><span class="sxs-lookup"><span data-stu-id="31fe8-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="31fe8-132">![Poveznik za LiveRamp s mapiranjem atributa](media/export-liveramp-segments.png "Poveznik za LiveRamp s mapiranjem atributa")</span><span class="sxs-lookup"><span data-stu-id="31fe8-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="31fe8-133">Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za odabrani identifikator ključa.</span><span class="sxs-lookup"><span data-stu-id="31fe8-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="31fe8-134">Odaberite **Dodaj atribut** za mapiranje više atributa za slanje u LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="31fe8-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="31fe8-135">Ako pošaljete više atributa identifikatora ključa usluzi LiveRamp, vjerojatno ćete dobiti višu stopu podudaranja.</span><span class="sxs-lookup"><span data-stu-id="31fe8-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="31fe8-136">Odaberite segmente koje želite eksportirati u LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="31fe8-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="31fe8-137">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="31fe8-137">Select **Save**.</span></span>

<span data-ttu-id="31fe8-138">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="31fe8-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="31fe8-139">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="31fe8-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="31fe8-140">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="31fe8-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="31fe8-141">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="31fe8-141">Data privacy and compliance</span></span>

<span data-ttu-id="31fe8-142">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Liveramp, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="31fe8-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="31fe8-143">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Liveramp ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="31fe8-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="31fe8-144">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="31fe8-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="31fe8-145">Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="31fe8-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
