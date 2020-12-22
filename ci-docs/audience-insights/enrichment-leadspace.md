---
title: Obogaćivanje profila tvrtki pomoću obogaćivanja treće strane tvrtke Leadspace
description: Opće informacije o obogaćivanju treće strane tvrtke Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668714"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="2153c-103">Obogaćivanje profila tvrtke uz Leadspace (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="2153c-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="2153c-104">Leadspace je tvrtka za proučavanje podataka koja pruža B2B platformu za podatke o klijentima.</span><span class="sxs-lookup"><span data-stu-id="2153c-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="2153c-105">Klijentima pruža objedinjene korisničke profile kako bi tvrtke obogatile svoje podatke.</span><span class="sxs-lookup"><span data-stu-id="2153c-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="2153c-106">Obogaćivanja uključuju dodatne atribute poput veličine tvrtke, lokacije, grane industrije i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="2153c-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2153c-107">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="2153c-107">Prerequisites</span></span>

<span data-ttu-id="2153c-108">Za konfiguriranje Leadspacea, potrebno je ispuniti sljedeće preduvjete:</span><span class="sxs-lookup"><span data-stu-id="2153c-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="2153c-109">Imate aktivnu licencu za Leadspace i "vječni ključ" (koji se naziva **Leadspace token**).</span><span class="sxs-lookup"><span data-stu-id="2153c-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="2153c-110">Kontaktirajte izravno [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) za detalje o njihovom proizvodu.</span><span class="sxs-lookup"><span data-stu-id="2153c-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="2153c-111">Imate dozvole [administratora](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="2153c-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="2153c-112">Imati [objedinjene korisničke profile](customer-profiles.md) za tvrtke.</span><span class="sxs-lookup"><span data-stu-id="2153c-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="2153c-113">Konfiguracija</span><span class="sxs-lookup"><span data-stu-id="2153c-113">Configuration</span></span>

1. <span data-ttu-id="2153c-114">U uvidima u ciljnu skupinu idite u odjeljak **Podaci** > **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="2153c-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="2153c-115">Odaberite **Obogati moje podatke** na pločici Leadspace.</span><span class="sxs-lookup"><span data-stu-id="2153c-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snimka zaslona pločice Leadspace.":::

1. <span data-ttu-id="2153c-117">Odaberite **Početak**, a zatim unesite aktivni **Leadspace token** (vječni ključ).</span><span class="sxs-lookup"><span data-stu-id="2153c-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="2153c-118">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="2153c-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="2153c-119">Potvrdite oba unosa odabirom mogućnosti **Povezivanje s uslugom Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="2153c-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="2153c-120">Odaberite **Mapiranje podataka** i definirajte koja se polja iz vaših objedinjenih profila trebaju koristiti za traženje odgovarajućih podataka tvrtke iz usluge Leadspace.</span><span class="sxs-lookup"><span data-stu-id="2153c-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="2153c-121">Polje **Naziv tvrtke** je obavezno.</span><span class="sxs-lookup"><span data-stu-id="2153c-121">The **Name of company** field is required.</span></span> <span data-ttu-id="2153c-122">Za veću preciznost podudaranja, mogu se dodati do dva druga polja, **Web-stranica tvrtke** i **Lokacija tvrtke**.</span><span class="sxs-lookup"><span data-stu-id="2153c-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okno za mapiranje polja usluge Leadspace.":::
   
1. <span data-ttu-id="2153c-124">Odaberite **Primijeni** za dovršetak mapiranja polja.</span><span class="sxs-lookup"><span data-stu-id="2153c-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="2153c-125">Odaberite **Pokreni** kako biste obogatili profile tvrtke.</span><span class="sxs-lookup"><span data-stu-id="2153c-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="2153c-126">Trajanje obogaćivanja ovisi o broju objedinjenih profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="2153c-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2153c-127">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="2153c-127">Enrichment results</span></span>

<span data-ttu-id="2153c-128">Nakon osvježavanja obogaćivanja, možete pregledati novoobogaćene podatke tvrtke pod [Moja obogaćivanja](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="2153c-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="2153c-129">Možete pronaći vrijeme posljednjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="2153c-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="2153c-130">Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.</span><span class="sxs-lookup"><span data-stu-id="2153c-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="2153c-131">Za dodatne informacije pogledajte [API-ji za Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="2153c-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2153c-132">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="2153c-132">Next steps</span></span>

<span data-ttu-id="2153c-133">Nadogradite na svoje obogaćene podatke o klijentu.</span><span class="sxs-lookup"><span data-stu-id="2153c-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2153c-134">Stvorite [segmente](segments.md), [mjere](measures.md), pa i [izvezite podatke](export-destinations.md) kako biste svojim klijentima pružili personalizirano iskustvo.</span><span class="sxs-lookup"><span data-stu-id="2153c-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2153c-135">Privatnost podataka i sukladnost</span><span class="sxs-lookup"><span data-stu-id="2153c-135">Data privacy and compliance</span></span>

<span data-ttu-id="2153c-136">Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Leadspace, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci.</span><span class="sxs-lookup"><span data-stu-id="2153c-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2153c-137">Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Leadspace ispunjava sve obaveze privatnosti ili sigurnosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="2153c-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2153c-138">Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2153c-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2153c-139">Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.</span><span class="sxs-lookup"><span data-stu-id="2153c-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>