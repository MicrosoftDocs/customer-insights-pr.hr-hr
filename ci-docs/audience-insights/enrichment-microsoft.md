---
title: Obogaćivanje profila klijenata podacima tvrtke Microsoft
description: Koristite vlasničke podatke tvrtke Microsoft za obogaćivanje podataka o klijentima afinitetima prema brendovima i interesima.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305147"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="80a4e-103">Obogaćivanje profila klijenta s afinitetima prema robnoj marki i interesima (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="80a4e-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="80a4e-104">Koristite vlasničke podatke tvrtke Microsoft za obogaćivanje podataka o klijentima afinitetima prema brendovima i interesima.</span><span class="sxs-lookup"><span data-stu-id="80a4e-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="80a4e-105">Ovi afiniteti temelje se na podacim od osoba u demografskim skupinama sličnima onima vaših klijenata.</span><span class="sxs-lookup"><span data-stu-id="80a4e-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="80a4e-106">Ove informacije pomažu vam da bolje razumijete i segmentirate svoje klijente na temelju njihovih afiniteta prema određenim robnim markama i interesima.</span><span class="sxs-lookup"><span data-stu-id="80a4e-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="80a4e-107">U uvidima u ciljnu skupinu idite na **Podaci** > **Obogaćivanje** da biste [konfigurirali i pregledali obogaćivanja](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="80a4e-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="80a4e-108">Da biste konfigurirali obogaćivanje afiniteta robne marke, idite na karticu **Otkrij** i odaberite **Obogati moje podatke** na pločici **Robne marke**.</span><span class="sxs-lookup"><span data-stu-id="80a4e-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="80a4e-109">Da biste konfigurirali obogaćivanje afiniteta interesa, idite na karticu **Otkrij** i odaberite **Obogati moje podatke** na pločici **Interesi**.</span><span class="sxs-lookup"><span data-stu-id="80a4e-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="80a4e-110">![pločice Robne marke i Interesi](media/BrandsInterest-tile-Hub.png "pločice Robne marke i Interes")</span><span class="sxs-lookup"><span data-stu-id="80a4e-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="80a4e-111">Kako određujemo afinitete</span><span class="sxs-lookup"><span data-stu-id="80a4e-111">How we determine affinities</span></span>

<span data-ttu-id="80a4e-112">Koristimo Microsoftove podatke mrežnog pretraživanja za pronalaženje afiniteta prema brendovima i interesima u različitim demografskim segmentima (definiranima dobi, spolom ili lokacijom).</span><span class="sxs-lookup"><span data-stu-id="80a4e-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="80a4e-113">Opseg mrežnog pretraživanja robne marke ili interesa određuje koliki afinitet demografski segment, u usporedbi s ostalim segmentima, ima prema toj robnoj marki ili interesu.</span><span class="sxs-lookup"><span data-stu-id="80a4e-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="80a4e-114">Razina i ocjena afiniteta</span><span class="sxs-lookup"><span data-stu-id="80a4e-114">Affinity level and score</span></span>

<span data-ttu-id="80a4e-115">Na svakom obogaćenom profilu klijenta pružamo dvije povezane vrijednosti: razinu afiniteta i ocjenu afiniteta.</span><span class="sxs-lookup"><span data-stu-id="80a4e-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="80a4e-116">Te vam vrijednosti pomažu odrediti koliko je jak afinitet prema demografskom segmentu tog profila, prema marki ili interesu u usporedbi s ostalim demografskim segmentima.</span><span class="sxs-lookup"><span data-stu-id="80a4e-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="80a4e-117">*Razina afiniteta* sastoji se od četiri razine, a *ocjena afiniteta* izračunava se na skali od 100 točaka koja se mapira na razine afiniteta.</span><span class="sxs-lookup"><span data-stu-id="80a4e-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="80a4e-118">Razina afiniteta</span><span class="sxs-lookup"><span data-stu-id="80a4e-118">Affinity level</span></span> |<span data-ttu-id="80a4e-119">Ocjena afiniteta</span><span class="sxs-lookup"><span data-stu-id="80a4e-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="80a4e-120">Vrlo visoko</span><span class="sxs-lookup"><span data-stu-id="80a4e-120">Very high</span></span>     | <span data-ttu-id="80a4e-121">85 – 100</span><span class="sxs-lookup"><span data-stu-id="80a4e-121">85-100</span></span>       |
|<span data-ttu-id="80a4e-122">Visoko</span><span class="sxs-lookup"><span data-stu-id="80a4e-122">High</span></span>     | <span data-ttu-id="80a4e-123">70 – 84</span><span class="sxs-lookup"><span data-stu-id="80a4e-123">70-84</span></span>        |
|<span data-ttu-id="80a4e-124">Srednji</span><span class="sxs-lookup"><span data-stu-id="80a4e-124">Medium</span></span>     | <span data-ttu-id="80a4e-125">35 – 69</span><span class="sxs-lookup"><span data-stu-id="80a4e-125">35-69</span></span>        |
|<span data-ttu-id="80a4e-126">Nisko</span><span class="sxs-lookup"><span data-stu-id="80a4e-126">Low</span></span>     | <span data-ttu-id="80a4e-127">1 – 34</span><span class="sxs-lookup"><span data-stu-id="80a4e-127">1-34</span></span>        |

<span data-ttu-id="80a4e-128">Ovisno o granularnosti koju biste željeli za mjerenje afiniteta, možete koristiti razinu ili ocjenu afiniteta.</span><span class="sxs-lookup"><span data-stu-id="80a4e-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="80a4e-129">Ocjena afiniteta daje vam precizniju kontrolu.</span><span class="sxs-lookup"><span data-stu-id="80a4e-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="80a4e-130">Podržane zemlje/regije</span><span class="sxs-lookup"><span data-stu-id="80a4e-130">Supported countries/regions</span></span>

<span data-ttu-id="80a4e-131">Trenutno podržavamo sljedeće mogućnosti zemlje/regije: Australija, Kanada (engleski), Francuska, Njemačka, Ujedinjeno Kraljevstvo ili Sjedinjene Države (engleski).</span><span class="sxs-lookup"><span data-stu-id="80a4e-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="80a4e-132">Da biste odabrali zemlju ili regiju, otvorite **Obogaćivanje marki** ili **Obogaćivanje interesa** pa odaberite **Promijeni** pored opcije **Država/regija**.</span><span class="sxs-lookup"><span data-stu-id="80a4e-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="80a4e-133">U oknu **Postavke zemlje/regije** odaberite mogućnost i odaberite **Primijeni**.</span><span class="sxs-lookup"><span data-stu-id="80a4e-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="80a4e-134">Implikacije povezane s odabirom zemlje</span><span class="sxs-lookup"><span data-stu-id="80a4e-134">Implications related to country selection</span></span>

- <span data-ttu-id="80a4e-135">Kada [odabirete vlastite marke](#define-your-brands-or-interests), sustav pruža prijedloge na temelju odabrane države ili regije.</span><span class="sxs-lookup"><span data-stu-id="80a4e-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="80a4e-136">Kada [odabirete industriju](#define-your-brands-or-interests), dobit ćete najrelevantnije marke ili interese na temelju odabrane države ili regije.</span><span class="sxs-lookup"><span data-stu-id="80a4e-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="80a4e-137">Kada [obogaćujemo profile](#refresh-enrichment), obogatit ćemo sve profile kupaca za koje dobivamo podatke za odabrane marke i interese, uključujući profile koji nisu u odabranoj državi ili regiji.</span><span class="sxs-lookup"><span data-stu-id="80a4e-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="80a4e-138">Na primjer, ako ste odabrali Njemačku, obogatit ćemo profile koji se nalaze u Sjedinjenim Državama ako imamo dostupne podatke za odabrane brendove i interese u SAD-u.</span><span class="sxs-lookup"><span data-stu-id="80a4e-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="80a4e-139">Konfiguracija obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="80a4e-139">Configure enrichment</span></span>

<span data-ttu-id="80a4e-140">Vođeno iskustvo pomaže vam u konfiguraciji obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="80a4e-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="80a4e-141">Definirajte svoje robne marke ili interese</span><span class="sxs-lookup"><span data-stu-id="80a4e-141">Define your brands or interests</span></span>

<span data-ttu-id="80a4e-142">Odaberite do pet robnih marki ili interesa pomoću jedne ili obje ove mogućnosti:</span><span class="sxs-lookup"><span data-stu-id="80a4e-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="80a4e-143">**Djelatnot** : Na padajućem popisu odaberite svoju djelatnost, a zatim odaberite vodeće marke ili interese za tu djelatnost.</span><span class="sxs-lookup"><span data-stu-id="80a4e-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="80a4e-144">**Odaberite vlastito**: Unesite marku ili interes koji su relevantni za vašu tvrtku ili ustanovu, a zatim odaberite među odgovarajućim prijedlozima.</span><span class="sxs-lookup"><span data-stu-id="80a4e-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="80a4e-145">Ako nismo naveli robnu marku ili interes koji tražite, pošaljite nam povratne informacije putem veze **Predloži**.</span><span class="sxs-lookup"><span data-stu-id="80a4e-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="80a4e-146">Preferencije obogaćivanja pregleda</span><span class="sxs-lookup"><span data-stu-id="80a4e-146">Review enrichment preferences</span></span>

<span data-ttu-id="80a4e-147">Pregledajte zadane preference obogaćivanja i ažurirajte ih ako je potrebno.</span><span class="sxs-lookup"><span data-stu-id="80a4e-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Snimka zaslona prozora s preferencama obogaćivanja.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="80a4e-149">Odabir entiteta za obogaćivanje</span><span class="sxs-lookup"><span data-stu-id="80a4e-149">Select entity to enrich</span></span>

<span data-ttu-id="80a4e-150">Odaberite **Obogaćeni entitet** i odaberite skup podataka koji želite obogatiti podacima o tvrtki iz Microsofta.</span><span class="sxs-lookup"><span data-stu-id="80a4e-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="80a4e-151">Možete odabrati entitet Klijent za obogaćivanje svih vaših profila klijenta ili odaberite segmentni entitet za obogaćivanje samo profila klijenata sadržanih u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="80a4e-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="80a4e-152">Mapirajte svoja polja</span><span class="sxs-lookup"><span data-stu-id="80a4e-152">Map your fields</span></span>

<span data-ttu-id="80a4e-153">Mapirajte polja iz svojeg objedinjenog entiteta klijenta da biste definirali demografski segment koji želite da sustav koristi za obogaćivanje vaših podataka o klijentu.</span><span class="sxs-lookup"><span data-stu-id="80a4e-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="80a4e-154">Mapirajte državu/regiju i najmanje atribute Datum rođenja ili Spol.</span><span class="sxs-lookup"><span data-stu-id="80a4e-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="80a4e-155">Usto, morate mapirati barem jedan grad (i saveznu državu/pokrajinu) ili poštanski broj.</span><span class="sxs-lookup"><span data-stu-id="80a4e-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="80a4e-156">Odaberite **Uredi** da biste definirali mapiranje polja i odaberite **Primijeni** kada završite.</span><span class="sxs-lookup"><span data-stu-id="80a4e-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="80a4e-157">Odaberite **Spremi** da biste dovršili mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="80a4e-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="80a4e-158">Sljedeći su formati i vrijednosti podržani (vrijednosti ne razlikuju velika i mala slova):</span><span class="sxs-lookup"><span data-stu-id="80a4e-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="80a4e-159">**Datum rođenja**: Preporučujemo da se datum rođenja pretvara u vrstu DateTime tijekom obrade podataka.</span><span class="sxs-lookup"><span data-stu-id="80a4e-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="80a4e-160">Alternativno, to može biti niz u [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formatu "yyyy-MM-dd" ili "yyyy-MM-ddTHH: mm: ss".</span><span class="sxs-lookup"><span data-stu-id="80a4e-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="80a4e-161">**Spol**: muški, ženski, nepoznato.</span><span class="sxs-lookup"><span data-stu-id="80a4e-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="80a4e-162">**Poštanski broj** : peteroznamenkasti poštanski brojevi za Sjedinjene Države, standardni poštanski broj svugdje drugdje.</span><span class="sxs-lookup"><span data-stu-id="80a4e-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="80a4e-163">**Grad**: Naziv grada na engleskom jeziku.</span><span class="sxs-lookup"><span data-stu-id="80a4e-163">**City**: City name in English.</span></span>
- <span data-ttu-id="80a4e-164">**Država/provincija**: Skraćenica od dva slova za SAD i Kanadu.</span><span class="sxs-lookup"><span data-stu-id="80a4e-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="80a4e-165">Skraćenica od dva ili tri slova za Australiju.</span><span class="sxs-lookup"><span data-stu-id="80a4e-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="80a4e-166">Nije primjenjivo za Francusku, Njemačku ili Ujedinjeno Kraljevstvo.</span><span class="sxs-lookup"><span data-stu-id="80a4e-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="80a4e-167">**Zemlja/regija**:</span><span class="sxs-lookup"><span data-stu-id="80a4e-167">**Country/Region**:</span></span>

  - <span data-ttu-id="80a4e-168">SAD: Sjedinjene Američke Države, Sjedinjene Države, SAD, SAD, Amerika</span><span class="sxs-lookup"><span data-stu-id="80a4e-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="80a4e-169">CA: Kanada, Kalifornija</span><span class="sxs-lookup"><span data-stu-id="80a4e-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="80a4e-170">GB: Ujedinjeno Kraljevstvo, UK, Velika Britanija, GB, Ujedinjeno Kraljevstvo Velike Britanije i Sjeverne Irske, Ujedinjeno Kraljevstvo Velike Britanije</span><span class="sxs-lookup"><span data-stu-id="80a4e-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="80a4e-171">AU: Australija, AU, Zajednica Australije</span><span class="sxs-lookup"><span data-stu-id="80a4e-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="80a4e-172">FR: Francuska, FR, Francuska Republika</span><span class="sxs-lookup"><span data-stu-id="80a4e-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="80a4e-173">DE: Njemačka, njemački, Deutschland, Allemagne, DE, Savezna Republika Njemačka, Republika Njemačka</span><span class="sxs-lookup"><span data-stu-id="80a4e-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="80a4e-174">Pregled i imenovanje obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="80a4e-174">Review and name the enrichment</span></span>

<span data-ttu-id="80a4e-175">Na kraju možete pregledati informacije i dati naziv za obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="80a4e-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stranica za pregled i imenovanje interesa.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="80a4e-177">Osvježavanje obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="80a4e-177">Refresh enrichment</span></span>

<span data-ttu-id="80a4e-178">Pokrenite obogaćivanje nakon konfiguriranja robnih marki, interesa i mapiranja polja za demografske podatke.</span><span class="sxs-lookup"><span data-stu-id="80a4e-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="80a4e-179">Za pokretanje postupka odaberite **Pokreni** na stranici za konfiguriranje robne marke ili interesa.</span><span class="sxs-lookup"><span data-stu-id="80a4e-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="80a4e-180">Usto možete sustavu dopustiti automatsko pokretanje obogaćivanja kao dio zakazanog osvježenja.</span><span class="sxs-lookup"><span data-stu-id="80a4e-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="80a4e-181">Ovisno o veličini vaših podataka o klijentima, može potrajati nekoliko minuta dok se obogaćivanje ne dovrši.</span><span class="sxs-lookup"><span data-stu-id="80a4e-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="80a4e-182">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="80a4e-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="80a4e-183">Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="80a4e-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="80a4e-184">Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla.</span><span class="sxs-lookup"><span data-stu-id="80a4e-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="80a4e-185">Nakon odabira **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, datum posljednje obrade i sve pogreške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="80a4e-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="80a4e-186">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="80a4e-186">Enrichment results</span></span>

<span data-ttu-id="80a4e-187">Nakon pokretanja postupka obogaćivanja, idite na **Moja obogaćivanja** za pregled ukupnog broja obogaćenih klijenata i analizu robnih marki ili interesa na obogaćenim profilima klijenta.</span><span class="sxs-lookup"><span data-stu-id="80a4e-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Pretpregled rezultata nakon pokretanja postupka obogaćivanja":::

<span data-ttu-id="80a4e-189">Pregledajte obogaćene podatke odabirom **Prikaz obogaćenih podataka** u grafikonu.</span><span class="sxs-lookup"><span data-stu-id="80a4e-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="80a4e-190">Obogaćeni podaci o robnim markama idu u entitet **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="80a4e-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="80a4e-191">Podaci o interesima su u entitetu **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="80a4e-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="80a4e-192">Ti su entiteti navedeni i u grupi **Obogaćivanje** u **Podaci** > **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="80a4e-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="80a4e-193">Prikaz podataka o obogaćivanju na kartici klijenta</span><span class="sxs-lookup"><span data-stu-id="80a4e-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="80a4e-194">Afiniteti robne marke i interesa mogu se pogledati i na pojedinačnim karticama klijenata.</span><span class="sxs-lookup"><span data-stu-id="80a4e-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="80a4e-195">Idite na **Klijenti** i odaberite profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="80a4e-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="80a4e-196">Na korisničkoj kartici naći ćete grafikone za robne marke ili interese za koje ljudi u demografskom profilu tog kupca imaju afinitet.</span><span class="sxs-lookup"><span data-stu-id="80a4e-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica klijenta s obogaćenim podacima":::

## <a name="next-steps"></a><span data-ttu-id="80a4e-198">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="80a4e-198">Next steps</span></span>

<span data-ttu-id="80a4e-199">Nadogradite na svoje obogaćene podatke o klijentu.</span><span class="sxs-lookup"><span data-stu-id="80a4e-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="80a4e-200">Stvorite [Segmente](segments.md) i [Mjere](measures.md), pa čak i [izvezite podatke](export-destinations.md) radi pružanja personaliziranih iskustava svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="80a4e-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
