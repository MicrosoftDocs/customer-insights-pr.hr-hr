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
ms.openlocfilehash: 51b150cbf5d9cfb3a5df42e680bcfa57ec5496cb
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617868"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Obogaćivanje profila klijenta s afinitetima prema robnoj marki i interesima (pretpregled)

Koristite vlasničke podatke tvrtke Microsoft za obogaćivanje podataka o klijentima afinitetima prema brendovima i interesima. Ovi afiniteti temelje se na podacim od osoba u demografskim skupinama sličnima onima vaših klijenata. Ove informacije pomažu vam da bolje razumijete i segmentirate svoje klijente na temelju njihovih afiniteta prema određenim robnim markama i interesima.

U uvidima u ciljnu skupinu idite na **Podaci** > **Obogaćivanje** da biste [konfigurirali i pregledali obogaćivanja](enrichment-hub.md).

Da biste konfigurirali obogaćivanje afiniteta robne marke, idite na karticu **Otkrij** i odaberite **Obogati moje podatke** na pločici **Robne marke**.

Da biste konfigurirali obogaćivanje afiniteta interesa, idite na karticu **Otkrij** i odaberite **Obogati moje podatke** na pločici **Interesi**.

   > [!div class="mx-imgBorder"]
   > ![Pločice Robna marka i Interesi.](media/BrandsInterest-tile-Hub.png "pločice Robne marke i Interes")

## <a name="how-we-determine-affinities"></a>Kako određujemo afinitete

Koristimo Microsoftove podatke mrežnog pretraživanja za pronalaženje afiniteta prema brendovima i interesima u različitim demografskim segmentima (definiranima dobi, spolom ili lokacijom). Opseg mrežnog pretraživanja robne marke ili interesa određuje koliki afinitet demografski segment, u usporedbi s ostalim segmentima, ima prema toj robnoj marki ili interesu.

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

Odaberite **Obogaćeni entitet** i odaberite skup podataka koji želite obogatiti podacima o tvrtki iz Microsofta. Možete odabrati entitet Klijent za obogaćivanje svih vaših profila klijenta ili odaberite segmentni entitet za obogaćivanje samo profila klijenata sadržanih u tom segmentu.

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

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies). Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla. Nakon odabira **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, datum posljednje obrade i sve pogreške i upozorenja povezana sa zadatkom.

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon pokretanja postupka obogaćivanja, idite na **Moja obogaćivanja** za pregled ukupnog broja obogaćenih klijenata i analizu robnih marki ili interesa na obogaćenim profilima klijenta.

:::image type="content" source="media/my-enrichments.png" alt-text="Pretpregled rezultata nakon pokretanja postupka obogaćivanja.":::

Pregledajte obogaćene podatke odabirom **Prikaz obogaćenih podataka** u grafikonu. Obogaćeni podaci o robnim markama idu u entitet **BrandAffinityFromMicrosoft**. Podaci o interesima su u entitetu **InterestAffinityFromMicrosoft**. Ti su entiteti navedeni i u grupi **Obogaćivanje** u **Podaci** > **Entiteti**.

Vidjet ćete grafikon s brojem obogaćenih profila klijenata tijekom vremena i pretpregled obogaćenog entiteta. Odaberite **Pokaži više** na pločici za pretpregled da biste otvorili obogaćeni entitet.

## <a name="see-enrichment-data-on-the-customer-card"></a>Prikaz podataka o obogaćivanju na kartici klijenta

Afiniteti robne marke i interesa mogu se pogledati i na pojedinačnim karticama klijenata. Idite na **Klijenti** i odaberite profil klijenta. Na korisničkoj kartici naći ćete grafikone za robne marke ili interese za koje ljudi u demografskom profilu tog kupca imaju afinitet.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica klijenta s obogaćenim podacima.":::

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
