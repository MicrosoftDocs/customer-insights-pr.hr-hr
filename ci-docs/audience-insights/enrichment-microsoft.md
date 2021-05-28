---
title: Obogaćivanje profila klijenata podacima tvrtke Microsoft
description: Koristite vlasničke podatke tvrtke Microsoft za obogaćivanje podataka o klijentima afinitetima prema brendovima i interesima.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064882"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="499f4-103">Obogaćivanje profila klijenta s afinitetima prema robnoj marki i interesima (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="499f4-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="499f4-104">Koristite vlasničke podatke tvrtke Microsoft za obogaćivanje podataka o klijentima afinitetima prema brendovima i interesima.</span><span class="sxs-lookup"><span data-stu-id="499f4-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="499f4-105">Ti se afiniteti određuju na temelju podataka osoba koje imaju slične demografske podatke kao i vaši klijenti.</span><span class="sxs-lookup"><span data-stu-id="499f4-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="499f4-106">Ove informacije pomažu vam da bolje razumijete i segmentirate svoje klijente na temelju njihovih afiniteta prema određenim robnim markama i interesima.</span><span class="sxs-lookup"><span data-stu-id="499f4-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="499f4-107">U uvidima u ciljnu skupinu idite na **Podaci** > **Obogaćivanje** da biste [konfigurirali i pregledali obogaćivanja](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="499f4-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="499f4-108">Da biste konfigurirali obogaćivanje afiniteta robne marke, idite na karticu **Otkrij** i odaberite **Obogati moje podatke** na pločici **Robne marke**.</span><span class="sxs-lookup"><span data-stu-id="499f4-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="499f4-109">Da biste konfigurirali obogaćivanje afiniteta interesa, idite na karticu **Otkrij** i odaberite **Obogati moje podatke** na pločici **Interesi**.</span><span class="sxs-lookup"><span data-stu-id="499f4-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="499f4-110">![Pločice Robne marke i interesi](media/BrandsInterest-tile-Hub.png "Pločice Robne marke i interesi")</span><span class="sxs-lookup"><span data-stu-id="499f4-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="499f4-111">Kako određujemo afinitete</span><span class="sxs-lookup"><span data-stu-id="499f4-111">How we determine affinities</span></span>

<span data-ttu-id="499f4-112">Koristimo Microsoftove podatke mrežnog pretraživanja za pronalaženje afiniteta prema brendovima i interesima u različitim demografskim segmentima (definiranima dobi, spolom ili lokacijom).</span><span class="sxs-lookup"><span data-stu-id="499f4-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="499f4-113">Opseg mrežnog pretraživanja robne marke ili interesa određuje koliki afinitet demografski segment, u usporedbi s ostalim segmentima, ima prema toj robnoj marki ili interesu.</span><span class="sxs-lookup"><span data-stu-id="499f4-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="499f4-114">Razina i ocjena afiniteta</span><span class="sxs-lookup"><span data-stu-id="499f4-114">Affinity level and score</span></span>

<span data-ttu-id="499f4-115">Na svakom obogaćenom profilu klijenta pružamo dvije povezane vrijednosti – razinu afiniteta i ocjenu afiniteta.</span><span class="sxs-lookup"><span data-stu-id="499f4-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="499f4-116">Te vam vrijednosti pomažu odrediti koliko je jak afinitet prema demografskom segmentu tog profila, prema marki ili interesu u usporedbi s ostalim demografskim segmentima.</span><span class="sxs-lookup"><span data-stu-id="499f4-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="499f4-117">*Razina afiniteta* sastoji se od četiri razine, a *ocjena afiniteta* izračunava se na skali od 100 točaka koja se mapira na razine afiniteta.</span><span class="sxs-lookup"><span data-stu-id="499f4-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="499f4-118">Razina afiniteta</span><span class="sxs-lookup"><span data-stu-id="499f4-118">Affinity level</span></span> |<span data-ttu-id="499f4-119">Ocjena afiniteta</span><span class="sxs-lookup"><span data-stu-id="499f4-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="499f4-120">Vrlo visoko</span><span class="sxs-lookup"><span data-stu-id="499f4-120">Very high</span></span>     | <span data-ttu-id="499f4-121">85 – 100</span><span class="sxs-lookup"><span data-stu-id="499f4-121">85-100</span></span>       |
|<span data-ttu-id="499f4-122">Visoko</span><span class="sxs-lookup"><span data-stu-id="499f4-122">High</span></span>     | <span data-ttu-id="499f4-123">70 – 84</span><span class="sxs-lookup"><span data-stu-id="499f4-123">70-84</span></span>        |
|<span data-ttu-id="499f4-124">Srednji</span><span class="sxs-lookup"><span data-stu-id="499f4-124">Medium</span></span>     | <span data-ttu-id="499f4-125">35 – 69</span><span class="sxs-lookup"><span data-stu-id="499f4-125">35-69</span></span>        |
|<span data-ttu-id="499f4-126">Nisko</span><span class="sxs-lookup"><span data-stu-id="499f4-126">Low</span></span>     | <span data-ttu-id="499f4-127">1 – 34</span><span class="sxs-lookup"><span data-stu-id="499f4-127">1-34</span></span>        |

<span data-ttu-id="499f4-128">Ovisno o granularnosti koju biste željeli za mjerenje afiniteta, možete koristiti razinu ili ocjenu afiniteta.</span><span class="sxs-lookup"><span data-stu-id="499f4-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="499f4-129">Ocjena afiniteta daje vam precizniju kontrolu.</span><span class="sxs-lookup"><span data-stu-id="499f4-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="499f4-130">Podržane zemlje/regije</span><span class="sxs-lookup"><span data-stu-id="499f4-130">Supported countries/regions</span></span>

<span data-ttu-id="499f4-131">Trenutno podržavamo sljedeće mogućnosti zemlje/regije: Australija, Kanada (engleski), Francuska, Njemačka, Ujedinjeno Kraljevstvo ili Sjedinjene Države (engleski).</span><span class="sxs-lookup"><span data-stu-id="499f4-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="499f4-132">Za odabir zemlje otvorite **Obogaćivanje marki** ili **Obogaćivanje interesa** i odaberite **Promijeni** pored **Zemlja/regija**.</span><span class="sxs-lookup"><span data-stu-id="499f4-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="499f4-133">U oknu **Postavke zemlje/regije** odaberite mogućnost i odaberite **Primijeni**.</span><span class="sxs-lookup"><span data-stu-id="499f4-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="499f4-134">Implikacije povezane s odabirom zemlje</span><span class="sxs-lookup"><span data-stu-id="499f4-134">Implications related to country selection</span></span>

- <span data-ttu-id="499f4-135">Kada [odabirete vlastite marke](#define-your-brands-or-interests), sustav pruža prijedloge na temelju odabrane države ili regije.</span><span class="sxs-lookup"><span data-stu-id="499f4-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="499f4-136">Kada [odabirete industriju](#define-your-brands-or-interests), dobit ćete najrelevantnije marke ili interese na temelju odabrane države ili regije.</span><span class="sxs-lookup"><span data-stu-id="499f4-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="499f4-137">Kada [obogaćujete profile](#refresh-enrichment), obogatit ćemo sve profile klijenata za koje dobivamo podatke za odabrane marke i interese.</span><span class="sxs-lookup"><span data-stu-id="499f4-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="499f4-138">Uključujući profile koji nisu u odabranoj državi ili regiji.</span><span class="sxs-lookup"><span data-stu-id="499f4-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="499f4-139">Na primjer, ako ste odabrali Njemačku, obogatit ćemo profile koji se nalaze u Sjedinjenim Državama ako imamo dostupne podatke za odabrane brendove i interese u SAD-u.</span><span class="sxs-lookup"><span data-stu-id="499f4-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="499f4-140">Konfiguracija obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="499f4-140">Configure Enrichment</span></span>

<span data-ttu-id="499f4-141">Vođeno iskustvo pomaže vam u konfiguraciji obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="499f4-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="499f4-142">Definirajte svoje robne marke ili interese</span><span class="sxs-lookup"><span data-stu-id="499f4-142">Define your brands or interests</span></span>

<span data-ttu-id="499f4-143">Odaberite jednu od sljedećih mogućnosti:</span><span class="sxs-lookup"><span data-stu-id="499f4-143">Select one of the following options:</span></span>

- <span data-ttu-id="499f4-144">**Industrija**: sustav identificira najbolje robne marke ili interese koji se odnose na vašu industriju i njima obogaćuje vaše podatke o klijentu.</span><span class="sxs-lookup"><span data-stu-id="499f4-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="499f4-145">**Odaberite vlastito**: na popisu robnih marki ili interesa koji su najvažniji za vašu tvrtku ili ustanovu odaberite do pet stavki.</span><span class="sxs-lookup"><span data-stu-id="499f4-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="499f4-146">Da biste dodali robnu marku ili interes, unesite je u područje za unos da biste dobili prijedloge utemeljene na podudaranju uvjeta.</span><span class="sxs-lookup"><span data-stu-id="499f4-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="499f4-147">Ako nismo naveli robnu marku ili interes koji tražite, pošaljite nam povratne informacije putem veze **Predloži**.</span><span class="sxs-lookup"><span data-stu-id="499f4-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="499f4-148">Preferencije obogaćivanja pregleda</span><span class="sxs-lookup"><span data-stu-id="499f4-148">Review enrichment preferences</span></span>

<span data-ttu-id="499f4-149">Pregledajte zadane preference obogaćivanja i ažurirajte ih ako je potrebno.</span><span class="sxs-lookup"><span data-stu-id="499f4-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Snimka zaslona prozora s preferencama obogaćivanja.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="499f4-151">Odabir entiteta za obogaćivanje</span><span class="sxs-lookup"><span data-stu-id="499f4-151">Select entity to enrich</span></span>

<span data-ttu-id="499f4-152">Odaberite **Obogaćeni entitet** i odaberite skup podataka koji želite obogatiti podacima o tvrtki iz Microsofta.</span><span class="sxs-lookup"><span data-stu-id="499f4-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="499f4-153">Možete odabrati entitet Klijent za obogaćivanje svih vaših profila klijenta ili odaberite segmentni entitet za obogaćivanje samo profila klijenata sadržanih u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="499f4-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="499f4-154">Mapirajte svoja polja</span><span class="sxs-lookup"><span data-stu-id="499f4-154">Map your fields</span></span>

<span data-ttu-id="499f4-155">Mapirajte polja iz svojeg objedinjenog entiteta klijenta da biste definirali demografski segment koji želite da sustav koristi za obogaćivanje vaših podataka o klijentu.</span><span class="sxs-lookup"><span data-stu-id="499f4-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="499f4-156">Mapirajte državu/regiju i najmanje atribute Datum rođenja ili Spol.</span><span class="sxs-lookup"><span data-stu-id="499f4-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="499f4-157">Usto, morate mapirati barem jedan grad (i saveznu državu/pokrajinu) ili poštanski broj.</span><span class="sxs-lookup"><span data-stu-id="499f4-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="499f4-158">Odaberite **Uredi** da biste definirali mapiranje polja i odaberite **Primijeni** kada završite.</span><span class="sxs-lookup"><span data-stu-id="499f4-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="499f4-159">Odaberite **Spremi** da biste dovršili mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="499f4-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="499f4-160">Sljedeći su formati i vrijednosti podržani, a vrijednosti ne razlikuju velika i mala slova:</span><span class="sxs-lookup"><span data-stu-id="499f4-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="499f4-161">**Datum rođenja**: Preporučujemo da se datum rođenja pretvara u vrstu DateTime tijekom obrade podataka.</span><span class="sxs-lookup"><span data-stu-id="499f4-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="499f4-162">Ili to može biti niz u formatu [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) „gggg-MM-dd” " ili „gggg-MM-ddTHH: mm: ssZ”.</span><span class="sxs-lookup"><span data-stu-id="499f4-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="499f4-163">**Spol**: muški, ženski, nepoznato</span><span class="sxs-lookup"><span data-stu-id="499f4-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="499f4-164">**Poštanski broj**: Peteroznamenkasti poštanski brojevi za SAD, standardni poštanski brojevi bilo gdje drugdje</span><span class="sxs-lookup"><span data-stu-id="499f4-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="499f4-165">**Grad**: Naziv grada na engleskom jeziku</span><span class="sxs-lookup"><span data-stu-id="499f4-165">**City**: City name in English</span></span>
- <span data-ttu-id="499f4-166">**Država/provincija**: Skraćenica od dva slova za SAD i Kanadu.</span><span class="sxs-lookup"><span data-stu-id="499f4-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="499f4-167">Skraćenica od dva ili tri slova za Australiju.</span><span class="sxs-lookup"><span data-stu-id="499f4-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="499f4-168">Nije primjenjivo za Francusku, Njemačku ili Ujedinjeno Kraljevstvo.</span><span class="sxs-lookup"><span data-stu-id="499f4-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="499f4-169">**Zemlja/regija**:</span><span class="sxs-lookup"><span data-stu-id="499f4-169">**Country/Region**:</span></span>

  - <span data-ttu-id="499f4-170">SAD: Sjedinjene Američke Države, Sjedinjene Države, SAD, SAD, Amerika</span><span class="sxs-lookup"><span data-stu-id="499f4-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="499f4-171">CA: Kanada, Kalifornija</span><span class="sxs-lookup"><span data-stu-id="499f4-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="499f4-172">GB: Ujedinjeno Kraljevstvo, UK, Velika Britanija, GB, Ujedinjeno Kraljevstvo Velike Britanije i Sjeverne Irske, Ujedinjeno Kraljevstvo Velike Britanije</span><span class="sxs-lookup"><span data-stu-id="499f4-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="499f4-173">AU: Australija, AU, Common Wealth Australije</span><span class="sxs-lookup"><span data-stu-id="499f4-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="499f4-174">FR: Francuska, FR, Francuska Republika</span><span class="sxs-lookup"><span data-stu-id="499f4-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="499f4-175">DE: Njemačka, njemački, Deutschland, Allemagne, DE, Savezna Republika Njemačka, Republika Njemačka</span><span class="sxs-lookup"><span data-stu-id="499f4-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="499f4-176">Pregled i imenovanje obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="499f4-176">Review and name the enrichment</span></span>

<span data-ttu-id="499f4-177">Na kraju možete pregledati informacije i dati naziv za obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="499f4-177">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stranica za pregled i imenovanje interesa.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="499f4-179">Osvježavanje obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="499f4-179">Refresh enrichment</span></span>

<span data-ttu-id="499f4-180">Pokrenite obogaćivanje nakon konfiguriranja robnih marki, interesa i mapiranja polja za demografske podatke.</span><span class="sxs-lookup"><span data-stu-id="499f4-180">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="499f4-181">Za pokretanje postupka odaberite **Pokreni** na stranici za konfiguriranje robne marke ili interesa.</span><span class="sxs-lookup"><span data-stu-id="499f4-181">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="499f4-182">Usto možete sustavu dopustiti automatsko pokretanje obogaćivanja kao dio zakazanog osvježenja.</span><span class="sxs-lookup"><span data-stu-id="499f4-182">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="499f4-183">Ovisno o veličini vaših podataka o klijentima, može potrajati nekoliko minuta dok se obogaćivanje ne dovrši.</span><span class="sxs-lookup"><span data-stu-id="499f4-183">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="499f4-184">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="499f4-184">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="499f4-185">Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="499f4-185">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="499f4-186">Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla.</span><span class="sxs-lookup"><span data-stu-id="499f4-186">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="499f4-187">Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="499f4-187">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="499f4-188">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="499f4-188">Enrichment results</span></span>

<span data-ttu-id="499f4-189">Nakon pokretanja postupka obogaćivanja, idite na **Moja obogaćivanja** za pregled ukupnog broja obogaćenih klijenata i analizu robnih marki ili interesa na obogaćenim profilima klijenta.</span><span class="sxs-lookup"><span data-stu-id="499f4-189">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Pretpregled rezultata nakon pokretanja postupka obogaćivanja":::

<span data-ttu-id="499f4-191">Pregledajte obogaćene podatke odabirom **Prikaz obogaćenih podataka** u grafikonu.</span><span class="sxs-lookup"><span data-stu-id="499f4-191">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="499f4-192">Obogaćeni podaci o robnim markama idu u entitet **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="499f4-192">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="499f4-193">Podaci o interesima su u entitetu **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="499f4-193">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="499f4-194">Ti su entiteti navedeni i u grupi **Obogaćivanje** u **Podaci** > **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="499f4-194">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="499f4-195">Prikaz podataka o obogaćivanju na kartici klijenta</span><span class="sxs-lookup"><span data-stu-id="499f4-195">See enrichment data on the customer card</span></span>

<span data-ttu-id="499f4-196">Afiniteti robne marke i interesa mogu se pogledati i na pojedinačnim karticama klijenata.</span><span class="sxs-lookup"><span data-stu-id="499f4-196">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="499f4-197">Idite na **Klijenti** i odaberite profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="499f4-197">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="499f4-198">Na korisničkoj kartici naći ćete grafikone za robne marke ili interese za koje ljudi u demografskom profilu tog kupca imaju afinitet.</span><span class="sxs-lookup"><span data-stu-id="499f4-198">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica klijenta s obogaćenim podacima":::

## <a name="next-steps"></a><span data-ttu-id="499f4-200">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="499f4-200">Next steps</span></span>

<span data-ttu-id="499f4-201">Nadogradite na svoje obogaćene podatke o klijentu.</span><span class="sxs-lookup"><span data-stu-id="499f4-201">Build on top of your enriched customer data.</span></span> <span data-ttu-id="499f4-202">Stvorite [Segmente](segments.md), [Mjere](measures.md), čak [izvezite podatke](export-destinations.md) da biste pružili personalizirano iskustvo svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="499f4-202">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
