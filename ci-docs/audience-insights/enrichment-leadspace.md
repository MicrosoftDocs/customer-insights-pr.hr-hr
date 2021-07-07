---
title: Obogaćivanje profila tvrtki pomoću obogaćivanja treće strane tvrtke Leadspace
description: Opće informacije o obogaćivanju treće strane tvrtke Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305193"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="eb305-103">Obogaćivanje profila tvrtke uz Leadspace (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="eb305-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="eb305-104">Leadspace je tvrtka za proučavanje podataka koja pruža B2B platformu za podatke o klijentima.</span><span class="sxs-lookup"><span data-stu-id="eb305-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="eb305-105">Klijentima pruža objedinjene korisničke profile kako bi tvrtke obogatile svoje podatke.</span><span class="sxs-lookup"><span data-stu-id="eb305-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="eb305-106">Obogaćivanja uključuju više atributa, kao što su veličina, lokacija, djelatnost i ostali podaci o tvrtki.</span><span class="sxs-lookup"><span data-stu-id="eb305-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eb305-107">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="eb305-107">Prerequisites</span></span>

<span data-ttu-id="eb305-108">Za konfiguriranje Leadspacea, potrebno je ispuniti sljedeće preduvjete:</span><span class="sxs-lookup"><span data-stu-id="eb305-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="eb305-109">Imate aktivnu licencu Leadspace.</span><span class="sxs-lookup"><span data-stu-id="eb305-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="eb305-110">Imati [objedinjene korisničke profile](customer-profiles.md) za tvrtke.</span><span class="sxs-lookup"><span data-stu-id="eb305-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="eb305-111">Vezu Leadspace administrator je već konfigurirao ili imate [administratorske](permissions.md#administrator) dozvole i „trajni ključ” (u daljnjem tekstu **Token za Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="eb305-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="eb305-112">Obratite se izravno tvrtki [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) za pojedinosti o njihovu proizvodu.</span><span class="sxs-lookup"><span data-stu-id="eb305-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="eb305-113">Konfiguracija za obogaćivanje</span><span class="sxs-lookup"><span data-stu-id="eb305-113">Configure the enrichment</span></span>

1. <span data-ttu-id="eb305-114">U uvidima u ciljnu skupinu idite u odjeljak **Podaci** > **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="eb305-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="eb305-115">Odaberite **Obogati moje podatke** na pločici Leadspace i odaberite **Započni**.</span><span class="sxs-lookup"><span data-stu-id="eb305-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snimka zaslona pločice Leadspace.":::

1. <span data-ttu-id="eb305-117">Odaberite [vezu](connections.md) s padajućeg popisa.</span><span class="sxs-lookup"><span data-stu-id="eb305-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="eb305-118">Ako nijedna veza nije dostupna, obratite se administratoru.</span><span class="sxs-lookup"><span data-stu-id="eb305-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="eb305-119">Ako ste administrator, vezu možete stvoriti odabirom **Dodaj vezu** i **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="eb305-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="eb305-120">Odaberite **Poveži se s Leadspace** za potvrdu veze.</span><span class="sxs-lookup"><span data-stu-id="eb305-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="eb305-121">Odaberite **Sljedeće** i odaberite **Skup podataka klijenta** koji želite obogatiti podacima o tvrtki iz Leadspace.</span><span class="sxs-lookup"><span data-stu-id="eb305-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="eb305-122">Možete odabrati entitet **Klijent** za obogaćivanje svih vaših korisničkih profila ili odaberite segmentni entitet za obogaćivanje samo korisničkih profila sadržanih u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="eb305-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Snimka zaslona prilikom odabira skupa podataka o klijentu.":::

1. <span data-ttu-id="eb305-124">Odaberite **Sljedeće** i definirajte koja se polja iz vaših objedinjenih profila koriste za traženje odgovarajućih podataka o tvrtki iz Leadspace.</span><span class="sxs-lookup"><span data-stu-id="eb305-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="eb305-125">Polje **Naziv tvrtke** je obavezno.</span><span class="sxs-lookup"><span data-stu-id="eb305-125">The **Name of company** field is required.</span></span> <span data-ttu-id="eb305-126">Za veću preciznost podudaranja, mogu se dodati do dva druga polja, **Web-stranica tvrtke** i **Lokacija tvrtke**.</span><span class="sxs-lookup"><span data-stu-id="eb305-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okno za mapiranje polja usluge Leadspace.":::

1. <span data-ttu-id="eb305-128">Odaberite **Sljedeće** da biste dovršili mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="eb305-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="eb305-129">Navedite naziv za obogaćivanje i odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.</span><span class="sxs-lookup"><span data-stu-id="eb305-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="eb305-130">Konfiguriranje veze za Leadspace</span><span class="sxs-lookup"><span data-stu-id="eb305-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="eb305-131">Morate biti administrator da biste konfigurirali veze.</span><span class="sxs-lookup"><span data-stu-id="eb305-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="eb305-132">Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćivanja *ili* idite na **Admin** > **Veze** i odaberite **Postavi** na pločici Leadspace.</span><span class="sxs-lookup"><span data-stu-id="eb305-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="eb305-133">Odaberite **Početak rada**.</span><span class="sxs-lookup"><span data-stu-id="eb305-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="eb305-134">Unesite naziv za vezu u dijaloški okvir **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="eb305-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="eb305-135">Navedite valjani token za Leadspace.</span><span class="sxs-lookup"><span data-stu-id="eb305-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="eb305-136">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom opcije **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="eb305-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="eb305-137">Odaberi **Potvrdi** za provjeru valjanosti konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="eb305-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="eb305-138">Nakon dovršetka provjere valjanosti odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="eb305-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Stranica za konfiguraciju veze za Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="eb305-140">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="eb305-140">Enrichment results</span></span>

<span data-ttu-id="eb305-141">Nakon osvježavanja obogaćivanja, možete pregledati novoobogaćene podatke tvrtke pod [Moja obogaćivanja](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="eb305-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="eb305-142">Možete pronaći vrijeme posljednjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="eb305-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="eb305-143">Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.</span><span class="sxs-lookup"><span data-stu-id="eb305-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="eb305-144">Za dodatne informacije pogledajte [API-ji za Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="eb305-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="eb305-145">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="eb305-145">Next steps</span></span>

<span data-ttu-id="eb305-146">Nadogradite na svoje obogaćene podatke o klijentu.</span><span class="sxs-lookup"><span data-stu-id="eb305-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="eb305-147">Stvorite [segmente](segments.md) i [mjere](measures.md), pa čak i [izvezite podatke](export-destinations.md) radi pružanja personaliziranih iskustava svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="eb305-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="eb305-148">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="eb305-148">Data privacy and compliance</span></span>

<span data-ttu-id="eb305-149">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Leadspace, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="eb305-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="eb305-150">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Leadspace ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="eb305-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="eb305-151">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="eb305-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="eb305-152">Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="eb305-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
