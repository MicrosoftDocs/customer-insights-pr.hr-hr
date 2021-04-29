---
title: Obogaćivanje pomoću obogaćivanja treće strane tvrke Experian
description: Opće informacije o obogaćivanju treće strane tvrtke Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896364"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="15fff-103">Obogaćivanje profila klijenata demografskim podacima tvrtke Experian (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="15fff-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="15fff-104">Experian je svjetski predvodnik u izvješćivanju o potrošačkim i poslovnim kreditima i marketinškim uslugama.</span><span class="sxs-lookup"><span data-stu-id="15fff-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="15fff-105">Uz Experianove usluge obogaćivanja podataka možete izgraditi bolje temelje za razumijevanje svojih klijenata obogaćujući profile svojih klijenata demografskim podacima kao što su veličina kućanstva, prihod i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="15fff-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="15fff-106">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="15fff-106">Prerequisites</span></span>

<span data-ttu-id="15fff-107">Za konfiguraciju Experiana potrebno je ispuniti sljedeće preduvjete:</span><span class="sxs-lookup"><span data-stu-id="15fff-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="15fff-108">Trebate imati aktivnu pretplatu na Experian.</span><span class="sxs-lookup"><span data-stu-id="15fff-108">You have an active Experian subscription.</span></span> <span data-ttu-id="15fff-109">Kako biste nabavili pretplatu, izravno se [obratite tvrtki Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="15fff-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="15fff-110">[Saznajte više o obogaćivanju podataka od strane tvrtke Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="15fff-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="15fff-111">Administrator je već konfigurirao vezu s Experianom *ili* imate [administratorske](permissions.md#administrator) dozvole.</span><span class="sxs-lookup"><span data-stu-id="15fff-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="15fff-112">Potrebni su vam i ID korisnika, ID strane i broj modela za vaš račun sigurnog prijevoza (ST) za koji je omogućen SSH koji je Experian stvorio za vas.</span><span class="sxs-lookup"><span data-stu-id="15fff-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="15fff-113">Konfiguracija za obogaćivanje</span><span class="sxs-lookup"><span data-stu-id="15fff-113">Configure the enrichment</span></span>

1. <span data-ttu-id="15fff-114">Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.</span><span class="sxs-lookup"><span data-stu-id="15fff-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="15fff-115">Odaberite **Obogati moje podatke** na pločici Experian.</span><span class="sxs-lookup"><span data-stu-id="15fff-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="15fff-116">![Pločica Experian](media/experian-tile.png "Pločica Experian")</span><span class="sxs-lookup"><span data-stu-id="15fff-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="15fff-117">Odaberite [vezu](connections.md) s padajućeg popisa.</span><span class="sxs-lookup"><span data-stu-id="15fff-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="15fff-118">Ako nijedna veza nije dostupna, obratite se administratoru.</span><span class="sxs-lookup"><span data-stu-id="15fff-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="15fff-119">Ako ste administrator, vezu možete stvoriti odabirom **Dodaj vezu** i odabirom Experian s padajućeg izbornika.</span><span class="sxs-lookup"><span data-stu-id="15fff-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="15fff-120">Odaberite **Poveži se s Experianom** za potvrdu odabira veze.</span><span class="sxs-lookup"><span data-stu-id="15fff-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="15fff-121">Odaberite **Sljedeće** i odaberite **Skup podataka klijenta** koji želite obogatiti demografskim podacima iz Experiana.</span><span class="sxs-lookup"><span data-stu-id="15fff-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="15fff-122">Možete odabrati entitet **Klijent** za obogaćivanje svih vaših korisničkih profila ili odaberite segmentni entitet za obogaćivanje samo korisničkih profila sadržanih u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="15fff-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Snimka zaslona prilikom odabira skupa podataka o klijentu.":::

1. <span data-ttu-id="15fff-124">Odaberite **Sljedeće** i definirajte koja se vrsta polja iz vaših objedinjenih profila treba koristiti za traženje odgovarajućih demografskih podataka iz Experiana.</span><span class="sxs-lookup"><span data-stu-id="15fff-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="15fff-125">Potrebno je barem jedno od polja **Ime i adresa**, **Telefon** ili **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="15fff-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="15fff-126">Za veću točnost podudaranja mogu se dodati do dva druga polja.</span><span class="sxs-lookup"><span data-stu-id="15fff-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="15fff-127">Ovaj će odabir utjecati na polja za mapiranje kojima imate pristup u sljedećem koraku.</span><span class="sxs-lookup"><span data-stu-id="15fff-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="15fff-128">Više atributa ključnih identifikatora poslanih Experianu vjerojatno daje veću stopu podudaranja.</span><span class="sxs-lookup"><span data-stu-id="15fff-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="15fff-129">Odaberite **Sljedeće** da biste započeli mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="15fff-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="15fff-130">Definirajte koja se polja iz vaših objedinjenih profila trebaju koristiti za traženje odgovarajućih demografskih podataka iz Experiana.</span><span class="sxs-lookup"><span data-stu-id="15fff-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="15fff-131">Obavezna su polja označena.</span><span class="sxs-lookup"><span data-stu-id="15fff-131">Required fields are marked.</span></span>

1. <span data-ttu-id="15fff-132">Navedite naziv za obogaćivanje i naziv za izlazni entitet.</span><span class="sxs-lookup"><span data-stu-id="15fff-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="15fff-133">Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.</span><span class="sxs-lookup"><span data-stu-id="15fff-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="15fff-134">Konfiguriranje veze za Experian</span><span class="sxs-lookup"><span data-stu-id="15fff-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="15fff-135">Morate biti administrator da biste konfigurirali veze.</span><span class="sxs-lookup"><span data-stu-id="15fff-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="15fff-136">Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćivanja *ili* idite na **Admin** > **Veze** i odaberite **Postavi** na pločici Experian.</span><span class="sxs-lookup"><span data-stu-id="15fff-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="15fff-137">Odaberite **Početak rada**.</span><span class="sxs-lookup"><span data-stu-id="15fff-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="15fff-138">Unesite naziv za vezu u dijaloški okvir **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="15fff-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="15fff-139">Unesite valjani ID korisnika, ID strane i broj modela za svoj račun za Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="15fff-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="15fff-140">Pregledajte i dajte svoj pristanak za **Zaštita privatnosti podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**</span><span class="sxs-lookup"><span data-stu-id="15fff-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="15fff-141">Odaberi **Potvrdi** za provjeru valjanosti konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="15fff-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="15fff-142">Nakon dovršetka provjere valjanosti odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="15fff-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Okno za konfiguraciju veze za Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="15fff-144">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="15fff-144">Enrichment results</span></span>

<span data-ttu-id="15fff-145">Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake.</span><span class="sxs-lookup"><span data-stu-id="15fff-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="15fff-146">Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="15fff-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="15fff-147">Vrijeme obrade ovisit će o veličini vaših podataka o klijentu i postupcima obogaćivanja koje je za vaš račun postavio Experian.</span><span class="sxs-lookup"><span data-stu-id="15fff-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="15fff-148">Nakon završetka postupka obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod stavkom **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="15fff-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="15fff-149">Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="15fff-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="15fff-150">Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.</span><span class="sxs-lookup"><span data-stu-id="15fff-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="15fff-151">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="15fff-151">Next steps</span></span>

<span data-ttu-id="15fff-152">Nadogradite na svoje obogaćene podatke o klijentu.</span><span class="sxs-lookup"><span data-stu-id="15fff-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="15fff-153">Stvorite [segmente](segments.md), [mjere](measures.md), pa i [izvezite podatke](export-destinations.md) kako biste svojim klijentima pružili personalizirano iskustvo.</span><span class="sxs-lookup"><span data-stu-id="15fff-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="15fff-154">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="15fff-154">Data privacy and compliance</span></span>

<span data-ttu-id="15fff-155">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Experian, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="15fff-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="15fff-156">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Experian ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="15fff-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="15fff-157">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="15fff-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="15fff-158">Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="15fff-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
