---
title: Obogaćivanje poboljšanja adrese
description: Obogatite i normalizirajte podatke o adresi profila klijenata pomoću Microsoftovih modela.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305423"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="b9e07-103">Obogaćivanje profila klijenata s poboljšanim adresama</span><span class="sxs-lookup"><span data-stu-id="b9e07-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="b9e07-104">Adrese u vašim podacima mogu biti nestrukturirane, nepotpune ili netočne.</span><span class="sxs-lookup"><span data-stu-id="b9e07-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="b9e07-105">Koristite Microsoftove modele za normalizaciju i obogaćivanje adresa u [format Common Data Model](/common-data-model/schema/core/applicationcommon/address) radi veće preciznosti i uvida.</span><span class="sxs-lookup"><span data-stu-id="b9e07-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="b9e07-106">Kako poboljšavamo adrese</span><span class="sxs-lookup"><span data-stu-id="b9e07-106">How we enhance addresses</span></span>

<span data-ttu-id="b9e07-107">Naš model prolazi postupak u dva koraka za poboljšanje adrese.</span><span class="sxs-lookup"><span data-stu-id="b9e07-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="b9e07-108">Prvo raščlanjuje adresu kako bi identificirao njezine komponente i stavlja ih u strukturirani format.</span><span class="sxs-lookup"><span data-stu-id="b9e07-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="b9e07-109">Zatim koristimo AI za ispravljanje, popunjavanje i standardizaciju vrijednosti u adresi.</span><span class="sxs-lookup"><span data-stu-id="b9e07-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="b9e07-110">Primjer</span><span class="sxs-lookup"><span data-stu-id="b9e07-110">Example</span></span>

<span data-ttu-id="b9e07-111">Podaci o adresi mogu biti u nestandardnom formatu i sadržavati pravopisne pogreške.</span><span class="sxs-lookup"><span data-stu-id="b9e07-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="b9e07-112">Model može riješiti ove probleme i stvoriti dosljedne adrese u objedinjenim profilima klijenata.</span><span class="sxs-lookup"><span data-stu-id="b9e07-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="b9e07-113">Ograničenja</span><span class="sxs-lookup"><span data-stu-id="b9e07-113">Limitations</span></span>

<span data-ttu-id="b9e07-114">Poboljšane adrese funkcioniraju samo s vrijednostima koje već postoje u unesenim podacima o adresi.</span><span class="sxs-lookup"><span data-stu-id="b9e07-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="b9e07-115">Model ne radi sljedeće:</span><span class="sxs-lookup"><span data-stu-id="b9e07-115">The model doesn't:</span></span> 

1. <span data-ttu-id="b9e07-116">Provjerava je li adresa valjana.</span><span class="sxs-lookup"><span data-stu-id="b9e07-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="b9e07-117">Provjerava je li bilo koja vrijednost, poput poštanskih brojeva ili naziva ulica, valjana.</span><span class="sxs-lookup"><span data-stu-id="b9e07-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="b9e07-118">Mijenja vrijednosti koje ne prepoznaje.</span><span class="sxs-lookup"><span data-stu-id="b9e07-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="b9e07-119">Model koristi tehnike temeljene na strojnom učenju za poboljšanje adresa.</span><span class="sxs-lookup"><span data-stu-id="b9e07-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="b9e07-120">Iako primjenjujemo visoki prag pouzdanosti kada model mijenja ulaznu vrijednost, kao i kod svakog modela temeljenog na strojnom učenju, 100-postotna točnost nije zajamčena.</span><span class="sxs-lookup"><span data-stu-id="b9e07-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="b9e07-121">Podržane države ili regije</span><span class="sxs-lookup"><span data-stu-id="b9e07-121">Supported countries or regions</span></span>

<span data-ttu-id="b9e07-122">Trenutno podržavamo obogaćivanje adresa u sljedećim državama ili regijama:</span><span class="sxs-lookup"><span data-stu-id="b9e07-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="b9e07-123">Australija</span><span class="sxs-lookup"><span data-stu-id="b9e07-123">Australia</span></span>
- <span data-ttu-id="b9e07-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="b9e07-124">Canada</span></span>
- <span data-ttu-id="b9e07-125">Ujedinjena Kraljevina</span><span class="sxs-lookup"><span data-stu-id="b9e07-125">United Kingdom</span></span>
- <span data-ttu-id="b9e07-126">Sjedinjene Države</span><span class="sxs-lookup"><span data-stu-id="b9e07-126">United States</span></span>

<span data-ttu-id="b9e07-127">Adrese moraju sadržavati vrijednost države/regije.</span><span class="sxs-lookup"><span data-stu-id="b9e07-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="b9e07-128">Ne obrađujemo adrese za države ili regije koje nisu podržane i adrese koje nemaju navedenu državu ili regiju.</span><span class="sxs-lookup"><span data-stu-id="b9e07-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="b9e07-129">Konfiguracija za obogaćivanje</span><span class="sxs-lookup"><span data-stu-id="b9e07-129">Configure the enrichment</span></span>

1. <span data-ttu-id="b9e07-130">Idite na **Podaci** > **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="b9e07-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="b9e07-131">Odaberite **Obogati moje podatke** na pločici **Poboljšane adrese**.</span><span class="sxs-lookup"><span data-stu-id="b9e07-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Snimka zaslona pločice poboljšanih adresa.":::

1. <span data-ttu-id="b9e07-133">Odaberite **Skup podataka o klijentu** pa odaberite entitet koji sadrži adrese koje želite obogatiti.</span><span class="sxs-lookup"><span data-stu-id="b9e07-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="b9e07-134">Možete odabrati entitet *Klijent* za obogaćivanje adresa u svim vašim profilima klijenata ili odaberite entitet segmenta za obogaćivanje adresa samo u profilima klijenata sadržanih u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="b9e07-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="b9e07-135">Odaberite način formatiranja adresa u vašem skupu podataka.</span><span class="sxs-lookup"><span data-stu-id="b9e07-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="b9e07-136">Odaberite **Adresa s jednim atributom** ako adrese u vašim podacima koriste jedno polje.</span><span class="sxs-lookup"><span data-stu-id="b9e07-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="b9e07-137">Odaberite **Adresa s više atributa** ako adrese u vašim podacima koriste više od jednog polja podataka.</span><span class="sxs-lookup"><span data-stu-id="b9e07-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b9e07-138">Država/regija obavezna je i za adrese s jednim i za one s više atributa.</span><span class="sxs-lookup"><span data-stu-id="b9e07-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="b9e07-139">Adrese koje ne sadrže valjane ili podržane vrijednosti države/regije neće biti obogaćene.</span><span class="sxs-lookup"><span data-stu-id="b9e07-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="b9e07-140">Mapirajte polja adrese iz vašeg objedinjenog entiteta klijenta.</span><span class="sxs-lookup"><span data-stu-id="b9e07-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Stranica mapiranja polja poboljšane adrese.":::

1. <span data-ttu-id="b9e07-142">Odaberite **Sljedeće** da biste dovršili mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="b9e07-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="b9e07-143">Navedite naziv za obogaćivanje i izlazni entitet.</span><span class="sxs-lookup"><span data-stu-id="b9e07-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="b9e07-144">Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.</span><span class="sxs-lookup"><span data-stu-id="b9e07-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="b9e07-145">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="b9e07-145">Enrichment results</span></span>

<span data-ttu-id="b9e07-146">Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake.</span><span class="sxs-lookup"><span data-stu-id="b9e07-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="b9e07-147">Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b9e07-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b9e07-148">Vrijeme obrade ovisi o veličini vaših podataka o klijentima.</span><span class="sxs-lookup"><span data-stu-id="b9e07-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="b9e07-149">Nakon završetka postupka obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod stavkom **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="b9e07-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="b9e07-150">Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="b9e07-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b9e07-151">Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.</span><span class="sxs-lookup"><span data-stu-id="b9e07-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b9e07-152">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="b9e07-152">Next steps</span></span>

<span data-ttu-id="b9e07-153">Nadogradite na svoje obogaćene podatke o klijentu.</span><span class="sxs-lookup"><span data-stu-id="b9e07-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b9e07-154">Stvorite [segmente](segments.md) i [mjere](measures.md), pa čak i [izvezite podatke](export-destinations.md) radi pružanja personaliziranih iskustava svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="b9e07-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
