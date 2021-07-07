---
title: Obogaćivanje uz obogaćivanje treće strane Experian
description: Opće informacije o obogaćivanju treće strane Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309811"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="e2254-103">Obogaćivanje klijentskih profila demografskim podacima tvrtke Experian (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="e2254-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="e2254-104">Experian je svjetski predvodnik u izvještavanju o potrošačkim i poslovnim kreditima i marketinškim uslugama.</span><span class="sxs-lookup"><span data-stu-id="e2254-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="e2254-105">Uz usluge obogaćivanja podataka tvrtke Experian možete steći dublje razumijevanje svojih klijenata obogaćujući klijentske profile demografskim podacima kao što su veličina kućanstva, prihod i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="e2254-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e2254-106">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="e2254-106">Prerequisites</span></span>

<span data-ttu-id="e2254-107">Za konfiguriranja servisa Experian potrebno je ispuniti sljedeće preduvjete:</span><span class="sxs-lookup"><span data-stu-id="e2254-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e2254-108">Imate aktivnu pretplatu na Experian.</span><span class="sxs-lookup"><span data-stu-id="e2254-108">You have an active Experian subscription.</span></span> <span data-ttu-id="e2254-109">Da biste dobili pretplatu, izravno se [obratite Experianu](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="e2254-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="e2254-110">[Saznajte više o obogaćivanju podataka Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="e2254-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="e2254-111">Administrator je već konfigurirao vezu Experian *ili* imate [administratorske](permissions.md#administrator) dozvole.</span><span class="sxs-lookup"><span data-stu-id="e2254-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="e2254-112">Također su vam potrebni Korisnički ID, ID stranke i Broj modela za vaš račun sigurnog prijenosa (ST) s omogućenim SSH koji je Experian stvorio za vas.</span><span class="sxs-lookup"><span data-stu-id="e2254-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="e2254-113">Podržane zemlje/regije</span><span class="sxs-lookup"><span data-stu-id="e2254-113">Supported countries/regions</span></span>

<span data-ttu-id="e2254-114">Trenutno podržavamo obogaćivanje profila kupaca samo u Sjedinjenim Državama.</span><span class="sxs-lookup"><span data-stu-id="e2254-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="e2254-115">Konfiguracija za obogaćivanje</span><span class="sxs-lookup"><span data-stu-id="e2254-115">Configure the enrichment</span></span>

1. <span data-ttu-id="e2254-116">Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.</span><span class="sxs-lookup"><span data-stu-id="e2254-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="e2254-117">Odaberite **Obogati moje podatke** na pločici Experian.</span><span class="sxs-lookup"><span data-stu-id="e2254-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2254-118">![Experian pločic](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="e2254-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="e2254-119">Odaberite [vezu](connections.md) s padajućeg popisa.</span><span class="sxs-lookup"><span data-stu-id="e2254-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="e2254-120">Ako nijedna veza nije dostupna, obratite se administratoru.</span><span class="sxs-lookup"><span data-stu-id="e2254-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="e2254-121">Ako ste administrator, vezu možete stvoriti odabirom **Dodaj vezu** pa odabirom Experian s padajućeg popisa.</span><span class="sxs-lookup"><span data-stu-id="e2254-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="e2254-122">Odaberite **Spoji na Experian** za potvrdu odabira veze.</span><span class="sxs-lookup"><span data-stu-id="e2254-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="e2254-123">Odaberite **Dalje** pa odaberite **Skup podataka klijenta** koji želite obogatiti demografskim podacima servisa Experian.</span><span class="sxs-lookup"><span data-stu-id="e2254-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="e2254-124">Možete odabrati entitet **Klijent** za obogaćivanje svih vaših korisničkih profila ili odaberite segmentni entitet za obogaćivanje samo korisničkih profila sadržanih u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="e2254-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Snimka zaslona prilikom odabira skupa podataka o klijentu.":::

1. <span data-ttu-id="e2254-126">Odaberite **Dalje** pa definirajte koja se vrsta polja iz vaših objedinjenih profila treba koristiti za traženje odgovarajućih demografskih podataka servisa Experian.</span><span class="sxs-lookup"><span data-stu-id="e2254-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="e2254-127">Potrebno je barem jedno od polja **Ime i adresa**, **Telefon** ili **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="e2254-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="e2254-128">Za veću točnost podudaranja mogu se dodati do dva druga polja.</span><span class="sxs-lookup"><span data-stu-id="e2254-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="e2254-129">Ovaj će odabir utjecati na polja za mapiranje kojima imate pristup u sljedećem koraku.</span><span class="sxs-lookup"><span data-stu-id="e2254-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="e2254-130">Više atributa identifikatora ključa poslanih servisu Experian vjerojatno donosi višu stopu podudaranja.</span><span class="sxs-lookup"><span data-stu-id="e2254-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="e2254-131">Odaberite **Sljedeće** da biste započeli mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="e2254-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="e2254-132">Definirajte koja polja iz vaših objedinjenih profila treba koristiti za traženje odgovarajućih demografskih podataka servisa Experian.</span><span class="sxs-lookup"><span data-stu-id="e2254-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="e2254-133">Obavezna su polja označena.</span><span class="sxs-lookup"><span data-stu-id="e2254-133">Required fields are marked.</span></span>

1. <span data-ttu-id="e2254-134">Navedite naziv za obogaćivanje i naziv za izlazni entitet.</span><span class="sxs-lookup"><span data-stu-id="e2254-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="e2254-135">Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.</span><span class="sxs-lookup"><span data-stu-id="e2254-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="e2254-136">Konfiguriranje veze za Experian</span><span class="sxs-lookup"><span data-stu-id="e2254-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="e2254-137">Morate biti administrator da biste konfigurirali veze.</span><span class="sxs-lookup"><span data-stu-id="e2254-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="e2254-138">Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćivanja *ili* idite na **Administrator** > **Veze** pa odaberite **Postavljanje** na pločici Experian.</span><span class="sxs-lookup"><span data-stu-id="e2254-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="e2254-139">Odaberite **Početak rada**.</span><span class="sxs-lookup"><span data-stu-id="e2254-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="e2254-140">Unesite naziv za vezu u dijaloški okvir **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="e2254-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="e2254-141">Unesite važeći Korisnički ID, ID stranke i Broj modela za svoj račun sigurnog prijenosa za Experian.</span><span class="sxs-lookup"><span data-stu-id="e2254-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="e2254-142">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom opcije **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="e2254-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="e2254-143">Odaberi **Potvrdi** za provjeru valjanosti konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="e2254-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="e2254-144">Nakon dovršetka provjere valjanosti odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="e2254-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Okno konfiguracije veze na Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="e2254-146">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="e2254-146">Enrichment results</span></span>

<span data-ttu-id="e2254-147">Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake.</span><span class="sxs-lookup"><span data-stu-id="e2254-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e2254-148">Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e2254-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e2254-149">Vrijeme obrade ovisit će o veličini vaših podataka o klijentima i postupcima obogaćivanja koje je za vaš račun postavio Experian.</span><span class="sxs-lookup"><span data-stu-id="e2254-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="e2254-150">Nakon završetka postupka obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod stavkom **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="e2254-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="e2254-151">Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="e2254-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e2254-152">Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.</span><span class="sxs-lookup"><span data-stu-id="e2254-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e2254-153">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="e2254-153">Next steps</span></span>

<span data-ttu-id="e2254-154">Nadogradite na svoje obogaćene podatke o klijentu.</span><span class="sxs-lookup"><span data-stu-id="e2254-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e2254-155">Stvorite [segmente](segments.md) i [mjere](measures.md), pa čak i [izvezite podatke](export-destinations.md) radi pružanja personaliziranih iskustava svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="e2254-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e2254-156">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="e2254-156">Data privacy and compliance</span></span>

<span data-ttu-id="e2254-157">Kad omogućite Dynamics 365 Customer Insights za prijenos podataka u Experian, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke poput osobnih podataka.</span><span class="sxs-lookup"><span data-stu-id="e2254-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e2254-158">Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Experian ispunjava sve obveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="e2254-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e2254-159">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e2254-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e2254-160">Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="e2254-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
