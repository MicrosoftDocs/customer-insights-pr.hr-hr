---
title: Obogaćivanje pomoću obogaćivanja treće strane tvrke Experian
description: Opće informacije o obogaćivanju treće strane tvrtke Experian.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269551"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="ddd1d-103">Obogaćivanje profila klijenata demografskim podacima tvrtke Experian (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="ddd1d-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="ddd1d-104">Experian je svjetski predvodnik u izvješćivanju o potrošačkim i poslovnim kreditima i marketinškim uslugama.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="ddd1d-105">Uz Experianove usluge obogaćivanja podataka možete izgraditi bolje temelje za razumijevanje svojih klijenata obogaćujući profile svojih klijenata demografskim podacima kao što su veličina kućanstva, prihod i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ddd1d-106">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="ddd1d-106">Prerequisites</span></span>

<span data-ttu-id="ddd1d-107">Za konfiguraciju Experiana potrebno je ispuniti sljedeće preduvjete:</span><span class="sxs-lookup"><span data-stu-id="ddd1d-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="ddd1d-108">Trebate imati aktivnu pretplatu na Experian.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-108">You have an active Experian subscription.</span></span> <span data-ttu-id="ddd1d-109">Kako biste nabavili pretplatu, izravno se [obratite tvrtki Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="ddd1d-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="ddd1d-110">[Saznajte više o obogaćivanju podataka od strane tvrtke Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="ddd1d-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="ddd1d-111">Trebate imati ID korisnika, ID stranke i broj modela za svoj SSH-omogućeni račun sigurnog prijenosa (ST, Secure Transport) koji je Experian stvorio za vas.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="ddd1d-112">Imate dozvole [administratora](permissions.md#administrator) u uvidima u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="ddd1d-113">Konfiguracija</span><span class="sxs-lookup"><span data-stu-id="ddd1d-113">Configuration</span></span>

1. <span data-ttu-id="ddd1d-114">Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="ddd1d-115">Odaberite **Obogati moje podatke** na pločici Experian.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ddd1d-116">![Pločica Experian](media/experian-tile.png "Pločica Experian")</span><span class="sxs-lookup"><span data-stu-id="ddd1d-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="ddd1d-117">Odaberite **Početak** i unesite ID korisnika, ID stranke i broj modela za svoj Experian račun za siguran prijenos.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="ddd1d-118">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="ddd1d-119">Potvrdite sve unose odabirom mogućnosti **Primijeni**.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="ddd1d-120">Mapirajte svoja polja</span><span class="sxs-lookup"><span data-stu-id="ddd1d-120">Map your fields</span></span>

1.  <span data-ttu-id="ddd1d-121">Odaberite **Dodaj podatke** i odaberite **Skup korisničkih podataka** koji želite obogatiti demografskim podacima iz sustava Experian.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="ddd1d-122">Možete odabrati entitet **Klijent** za obogaćivanje svih vaših korisničkih profila ili odaberite segmentni entitet za obogaćivanje samo korisničkih profila sadržanih u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="ddd1d-123">Odaberite svoje identifikatore ključa iz **Naziv i adresa**, **E-poošta** ili **Telefon** da biste ih poslali u Experian radi rješavanja identiteta.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="ddd1d-124">Više atributa ključnih identifikatora poslanih Experianu vjerojatno daje veću stopu podudaranja.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="ddd1d-125">Odaberite **Dalje** i mapirajte odgovarajuće atribute iz vašeg objedinjenog entiteta klijenta za odabrana polja ključnih identifikatora.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="ddd1d-126">Odaberite **Dodaj atribut** kako biste mapirali sve dodatne atribute koje biste željeli poslati Experianu.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="ddd1d-127">Odaberite **Spremi** da biste dovršili mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ddd1d-128">![Mapiranja polja Experian](media/experian-field-mapping.png "Mapiranja polja Experian")</span><span class="sxs-lookup"><span data-stu-id="ddd1d-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ddd1d-129">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="ddd1d-129">Enrichment results</span></span>

<span data-ttu-id="ddd1d-130">Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="ddd1d-131">Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ddd1d-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ddd1d-132">Vrijeme obrade ovisit će o veličini vaših podataka o klijentu i postupcima obogaćivanja koje je za vaš račun postavio Experian.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="ddd1d-133">Nakon završetka postupka obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod stavkom **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="ddd1d-134">Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ddd1d-135">Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ddd1d-136">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="ddd1d-136">Next steps</span></span>

<span data-ttu-id="ddd1d-137">Nadogradite na svoje obogaćene podatke o klijentu.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ddd1d-138">Stvorite [segmente](segments.md), [mjere](measures.md), pa i [izvezite podatke](export-destinations.md) kako biste svojim klijentima pružili personalizirano iskustvo.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ddd1d-139">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="ddd1d-139">Data privacy and compliance</span></span>

<span data-ttu-id="ddd1d-140">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Experian, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ddd1d-141">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Experian ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ddd1d-142">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ddd1d-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ddd1d-143">Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="ddd1d-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]