---
title: Obogaćivanje profila klijenata podacima tvrtke Microsoft
description: Koristite Microsoftove vlasničke podatke da biste obogatili korisničke podatke afinitetima i Udio prisutnosti.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 12704ec46832e9463e6115db6c4df64e72bf4f97
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8372664"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Obogaćivanje profila kupaca afinitetima i Udio prisutnosti (pregled)

Koristite Microsoftove vlasničke podatke da biste obogatili podatke o klijentima afinitetima robne marke, afinitetima interesa i Udio prisutnosti (SoV). Ti afiniteti i SoV temelje se na podacima osoba s demografijom sličnom vašim klijentima. Te vam informacije pomažu da bolje razumijete i segmentijete svoje klijente na temelju njihovih afiniteta ili SoV-a prema određenim robnim markama i interesima.

U uvidima u ciljnu skupinu idite na **Podaci** > **Obogaćivanje** da biste [konfigurirali i pregledali obogaćivanja](enrichment-hub.md).

Da biste konfigurirali afinitete robne marke i obogaćivanje soV-a, idite na karticu **Discover** i odaberite **Obogati moje podatke** na pločici **Robne marke**.

Da biste konfigurirali afinitete interesa i obogaćivanje soV-a, idite na karticu **Otkrivanje** i odaberite **Obogati moje podatke** na **pločici Interesi**.

   > [!div class="mx-imgBorder"]
   > ![Pločice Robna marka i Interesi.](media/BrandsInterest-tile-Hub.png "pločice Robne marke i Interes")

## <a name="how-we-determine-affinities-and-sov"></a>Kako određujemo afinitete i SoV

Microsoftove podatke o internetskom pretraživanju upotrebljavamo da bismo pronašli afinitete i SoV za robne marke i interese u različitim demografskim segmentima (definiranima prema dobi, spolu ili lokaciji). Količina internetskog pretraživanja robne marke ili interesa čini osnovu za određivanje afiniteta ili soV-a. Međutim, svaki od njih pruža drugačiju perspektivu razumijevanju vaših kupaca.

- Afinitet je komparativan u demografskim segmentima. Te informacije možete koristiti za identifikaciju demografskih segmenata koji imaju najveći afinitet prema određenoj robnoj marki ili interesu u usporedbi s drugim segmentima.

- Udio prisutnosti je komparativna u svim odabranim robnim markama ili interesima. Te informacije možete upotrijebiti da biste utvrdili koja robna marka ili interes ima najveći udio glasa za određeni demografski segment u usporedbi s drugim robnim markama ili interesima koje ste odabrali.

## <a name="affinity-level-and-score"></a>Razina i ocjena afiniteta

Na svakom obogaćenom profilu klijenta pružamo dvije povezane vrijednosti: razinu afiniteta i ocjenu afiniteta. Te vam vrijednosti pomažu odrediti koliko je jak afinitet prema demografskom segmentu tog profila, prema marki ili interesu u usporedbi s ostalim demografskim segmentima.

*Razina afiniteta* sastoji se od četiri razine, a *ocjena afiniteta* izračunava se na skali od 100 točaka koja se mapira na razine afiniteta.


|Razina afiniteta |Ocjena afiniteta  |
|---------|---------|
|Vrlo visoko     | 85 – 100       |
|Visoko     | 70 – 84        |
|Srednji     | 35 – 69        |
|Nisko     | 1 – 34        |

Ovisno o granularnosti koju biste željeli za mjerenje afiniteta, možete koristiti razinu ili ocjenu afiniteta. Ocjena afiniteta daje vam precizniju kontrolu.

## <a name="share-of-voice-sov"></a>Udio prisutnosti (SoV)

SoV izračunavamo na skali od 100 točaka. Ukupni SoV u svim robnim markama ili interesima za svaki obogaćeni profil kupaca dodaje do 100. Za razliku od afiniteta, SoV je u odnosu na marke i interese koje odaberete. Na primjer, vrijednosti SoV za "Microsoft" mogu se razlikovati ako su odabrane robne marke ("Microsoft", "GitHub") u odnosu na ("Microsoft", "LinkedIn").

## <a name="supported-countriesregions"></a>Podržane zemlje/regije

Trenutno podržavamo sljedeće mogućnosti zemlje/regije: Australija, Kanada (engleski), Francuska, Njemačka, Ujedinjeno Kraljevstvo ili Sjedinjene Države (engleski).

Da biste odabrali zemlju ili regiju, otvorite **Obogaćivanje marki** ili **Obogaćivanje interesa** pa odaberite **Promijeni** pored opcije **Država/regija**. U oknu **Postavke zemlje/regije** odaberite mogućnost i odaberite **Primijeni**.

### <a name="implications-related-to-country-selection"></a>Implikacije povezane s odabirom zemlje

- Kada [odabirete vlastite marke](#define-your-brands-or-interests), sustav pruža prijedloge na temelju odabrane države ili regije.

- Kada [odabirete industriju](#define-your-brands-or-interests), dobit ćete najrelevantnije marke ili interese na temelju odabrane države ili regije.

- Kada [obogaćujemo profile](#refresh-enrichment), obogatit ćemo sve profile kupaca za koje dobivamo podatke za odabrane marke i interese, uključujući profile koji nisu u odabranoj državi ili regiji. Na primjer, ako ste odabrali Njemačku, obogatit ćemo profile koji se nalaze u Sjedinjenim Državama ako imamo dostupne podatke za odabrane brendove i interese u SAD-u.

## <a name="configure-enrichment"></a>Konfiguracija obogaćivanja

Vođeno iskustvo pomaže vam u konfiguraciji obogaćivanja. 

### <a name="define-your-brands-or-interests"></a>Definirajte svoje robne marke ili interese

Odaberite do pet robnih marki ili interesa pomoću jedne ili obje ove mogućnosti:

- **Djelatnot** : Na padajućem popisu odaberite svoju djelatnost, a zatim odaberite vodeće marke ili interese za tu djelatnost.
- **Odaberite vlastito**: Unesite marku ili interes koji su relevantni za vašu tvrtku ili ustanovu, a zatim odaberite među odgovarajućim prijedlozima. Ako nismo naveli robnu marku ili interes koji tražite, pošaljite nam povratne informacije putem veze **Predloži**.

### <a name="review-enrichment-preferences"></a>Preferencije obogaćivanja pregleda

Pregledajte zadane preference obogaćivanja i ažurirajte ih ako je potrebno.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Snimka zaslona prozora s preferencama obogaćivanja.":::

### <a name="select-entity-to-enrich"></a>Odabir entiteta za obogaćivanje

Odaberite **Obogaćeni entitet** i odaberite skup podataka želite obogatiti Microsoftovim podacima. Možete odabrati entitet Klijent za obogaćivanje svih vaših profila klijenta ili odaberite segmentni entitet za obogaćivanje samo profila klijenata sadržanih u tom segmentu.

### <a name="map-your-fields"></a>Mapirajte svoja polja

Mapirajte polja iz svojeg objedinjenog entiteta klijenta da biste definirali demografski segment koji želite da sustav koristi za obogaćivanje vaših podataka o klijentu. Mapirajte državu/regiju i najmanje atribute Datum rođenja ili Spol. Usto, morate mapirati barem jedan grad (i saveznu državu/pokrajinu) ili poštanski broj. Odaberite **Uredi** da biste definirali mapiranje polja i odaberite **Primijeni** kada završite. Odaberite **Spremi** da biste dovršili mapiranje polja.

Sljedeći su formati i vrijednosti podržani (vrijednosti ne razlikuju velika i mala slova):

- **Datum rođenja**: Preporučujemo da se datum rođenja pretvara u vrstu DateTime tijekom obrade podataka. Alternativno, to može biti niz u [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formatu "yyyy-MM-dd" ili "yyyy-MM-ddTHH: mm: ss".
- **Spol**: muški, ženski, nepoznato.
- **Poštanski broj** : peteroznamenkasti poštanski brojevi za Sjedinjene Države, standardni poštanski broj svugdje drugdje.
- **Grad**: Naziv grada na engleskom jeziku.
- **Država/provincija**: Skraćenica od dva slova za SAD i Kanadu. Skraćenica od dva ili tri slova za Australiju. Nije primjenjivo za Francusku, Njemačku ili Ujedinjeno Kraljevstvo.
- **Zemlja/regija**:

  - SAD: Sjedinjene Američke Države, Sjedinjene Države, SAD, SAD, Amerika
  - CA: Kanada, Kalifornija
  - GB: Ujedinjeno Kraljevstvo, UK, Velika Britanija, GB, Ujedinjeno Kraljevstvo Velike Britanije i Sjeverne Irske, Ujedinjeno Kraljevstvo Velike Britanije
  - AU: Australija, AU, Zajednica Australije
  - FR: Francuska, FR, Francuska Republika
  - DE: Njemačka, njemački, Deutschland, Allemagne, DE, Savezna Republika Njemačka, Republika Njemačka

## <a name="review-and-name-the-enrichment"></a>Pregled i imenovanje obogaćivanja

Na kraju možete pregledati informacije i dati naziv za obogaćivanje.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stranica za pregled i imenovanje interesa.":::

## <a name="refresh-enrichment"></a>Osvježavanje obogaćivanja

Pokrenite obogaćivanje nakon konfiguriranja robnih marki, interesa i mapiranja polja za demografske podatke. Za pokretanje postupka odaberite **Pokreni** na stranici za konfiguriranje robne marke ili interesa. Usto možete sustavu dopustiti automatsko pokretanje obogaćivanja kao dio zakazanog osvježenja.

Ovisno o veličini vaših podataka o klijentima, može potrajati nekoliko minuta dok se obogaćivanje ne dovrši.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon pokretanja postupka obogaćivanja, idite na **Moja obogaćivanja** za pregled ukupnog broja obogaćenih klijenata i analizu robnih marki ili interesa na obogaćenim profilima klijenta.

:::image type="content" source="media/my-enrichments.png" alt-text="Pretpregled rezultata nakon pokretanja postupka obogaćivanja.":::

Pronaći ćete grafikon s brojem obogaćenih profila klijenata tijekom vremena i pretpregledima obogaćenih entiteta. Pregledajte obogaćene podatke **tako da odaberete Pogledajte više** na **grafikonima Razina** afiniteta ili **Udio prisutnosti**. Obogaćeni podaci za robne marke idu **entitetima BrandAffinityFromMicrosoft** i **BrandShareOfVoiceFromMicrosoft**. Podaci za interese su u **entitetima InterestAffinityFromMicrosoft** i **InterestShareOfVoiceFromMicrosoft**. Ti su entiteti navedeni i u grupi **Obogaćivanje** u **Podaci** > **Entiteti**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Prikaz podataka o obogaćivanju na kartici klijenta

Robna marka i interes SoV također se mogu vidjeti na pojedinačnim karticama kupaca. Idite na **Klijenti** i odaberite profil klijenta. Na kartici kupca pronaći ćete grafikone za robnu marku ili soV koji zanimaju na temelju osoba u demografskom profilu tog kupca.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica klijenta s obogaćenim podacima.":::

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
