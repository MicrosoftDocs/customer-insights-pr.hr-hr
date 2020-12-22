---
title: Obogaćivanje profila klijenata pomoću platforme Microsoft Graph
description: Koristite vlasničke podatke iz programa Microsoft Graph da biste obogatili svoje podatke o klijentu s afinitetima prema robnoj marki i interesima.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405306"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Obogaćivanje profila klijenta s afinitetima prema robnoj marki i interesima (pretpregled)

Koristite vlasničke podatke iz programa Microsoft Graph da biste obogatili svoje podatke o klijentu s afinitetima prema robnoj marki i interesima. Ti se afiniteti određuju na temelju podataka osoba koje imaju slične demografske podatke kao i vaši klijenti. Ove informacije pomažu vam da bolje razumijete i segmentirate svoje klijente na temelju njihovih afiniteta prema određenim robnim markama i interesima.

U uvidima u ciljnu skupinu, idite na **Podaci** > **Obogaćivanje** da biste [konfigurirali i pregledali obogaćivanja](enrichment-hub.md).

Da biste konfigurirali obogaćivanje afiniteta robne marke, idite na karticu **Otkrij** i odaberite **Obogati moje podatke** na pločici **Robne marke**.

Da biste konfigurirali obogaćivanje afiniteta interesa, idite na karticu **Otkrij** i odaberite **Obogati moje podatke** na pločici **Interesi**.

   > [!div class="mx-imgBorder"]
   > ![Pločice Robne marke i interesi](media/BrandsInterest-tile-Hub.png "Pločice Robne marke i interesi")

## <a name="about-microsoft-graph"></a>O programu Microsoft Graph

Koristimo podatke mrežnog pretraživanja iz programa Microsoft Graph da bismo pronašli afinitete prema robnoj marki i interesima u različitim demografskim segmentima (definirano prema dobi, spolu ili mjestu). Opseg mrežnog pretraživanja robne marke ili interesa određuje koliki afinitet demografski segment, u usporedbi s ostalim segmentima, ima prema toj robnoj marki ili interesu.

[Saznajte više o programu Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Rezultat i pouzdanost afiniteta

**Rezultat afiniteta** izračunava se na skali od 100 bodova, a 100 predstavlja segment koji ima najveći afinitet prema robnoj marki ili interesu.

**Pouzdanost afiniteta** izračunava se i na ljestvici od 100 bodova. Označava razinu pouzdanosti sustava da segment ima afinitet prema robnoj marki ili interesu. Razina pouzdanosti temelji se na veličini segmenta i granularnosti segmenta. Veličina segmenta određena je količinom podataka koju imamo za određeni segment. Granularnost segmenta određuje se time koliko je atributa (dob, spol, mjesto) dostupno na profilu.

Ne normaliziramo rezultate za vaš skup podataka. Zbog toga možda nećete vidjeti sve moguće vrijednosti rezultata afiniteta za svoj skup podataka. Na primjer, u vašim podacima možda neće biti obogaćenog profila klijenta s ocjenom afiniteta 100. To je moguće ako u demografskom segmentu nema klijenta koji je postigao 100 za određenu robnu marku ili interes.

> [!TIP]
> Kada [stvarate segmente](segments.md) pomoću rezultata afiniteta, pregledajte raspodjelu rezultata afiniteta za svoj skup podataka prije nego što odlučite o odgovarajućim graničnim rezultatima. Na primjer, rezultat afiniteta od 10 može se smatrati značajnim u skupu podataka koji ima najviši rezultat afiniteta od samo 25 za određenu robnu marku ili interes.

## <a name="supported-countriesregions"></a>Podržane zemlje/regije

Trenutno podržavamo sljedeće mogućnosti zemlje/regije: Australija, Kanada (engleski), Francuska, Njemačka, Ujedinjeno Kraljevstvo ili Sjedinjene Države (engleski).

Za odabir zemlje otvorite **Obogaćivanje marki** ili **Obogaćivanje interesa** i odaberite **Promijeni** pored **Zemlja/regija**. U oknu **Postavke zemlje/regije** odaberite mogućnost i odaberite **Primijeni**.

### <a name="implications-related-to-country-selection"></a>Implikacije povezane s odabirom zemlje

- Prilikom [odabira vlastitih marki](#define-your-brands-or-interests), pružit ćemo prijedloge na temelju odabrane zemlje/regije.

- Pri [odabiru industrije](#define-your-brands-or-interests), identificirat ćemo najrelevantnije marke ili interese na temelju odabrane zemlje/regije.

- Prilikom [mapiranja vaših polja](#map-your-fields), ako polje Zemlja/regija nije mapirano, koristit ćemo podatke iz Microsoft Graph iz odabrane zemlje/regije za obogaćivanje korisničkih profila. Taj ćemo odabir koristiti i za obogaćivanje korisničkih profila koji nemaju dostupne podatke o zemlji/regiji.

- Prilikom [obogaćivanja profila](#refresh-enrichment) obogatit ćemo sve profile klijenata za koje imamo dostupne podatke iz Microsoft Graph za odabrane marke i interese, uključujući profile koji nisu u odabranoj zemlji/regiji. Na primjer, ako ste odabrali Njemačku, obogatit ćemo profile smještene u Sjedinjenim Državama ako imamo dostupne podatke iz Microsoft Graph za odabrane marke i interese u SAD-u.

## <a name="configure-enrichment"></a>Konfiguracija obogaćivanja

Konfiguriranje obogaćivanja robnih marki ili interesa sastoji se od dva koraka:

### <a name="define-your-brands-or-interests"></a>Definirajte svoje robne marke ili interese

Odaberite jednu od sljedećih mogućnosti:

- **Industrija**: sustav identificira najbolje robne marke ili interese koji se odnose na vašu industriju i njima obogaćuje vaše podatke o klijentu.
- **Odaberite vlastito**: na popisu robnih marki ili interesa koji su najvažniji za vašu tvrtku ili ustanovu odaberite do pet stavki.

Da biste dodali robnu marku ili interes, unesite je u područje za unos da biste dobili prijedloge utemeljene na podudaranju uvjeta. Ako nismo naveli robnu marku ili interes koji tražite, pošaljite nam povratne informacije putem veze **Predloži**.

### <a name="map-your-fields"></a>Mapirajte svoja polja

Mapirajte polja s vašeg objedinjenog entiteta klijenta u najmanje dva atributa za definiranje demografskog segmenta koji želite koristiti za obogaćivanje podataka o klijentu. Odaberite **Uredi** da biste definirali mapiranje polja i odaberite **Primijeni** kada završite. Odaberite **Spremi** da biste dovršili mapiranje polja.

Sljedeći su formati i vrijednosti podržani, a vrijednosti ne razlikuju velika i mala slova:

- **Datum rođenja**: Preporučujemo da se datum rođenja pretvara u vrstu DateTime tijekom obrade podataka. Ili to može biti niz u formatu [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) „gggg-MM-dd” " ili „gggg-MM-ddTHH: mm: ssZ”.
- **Spol**: muški, ženski, nepoznato
- **Poštanski broj**: Peteroznamenkasti poštanski brojevi za SAD, standardni poštanski brojevi bilo gdje drugdje
- **Grad**: Naziv grada na engleskom jeziku
- **Država/provincija**: Skraćenica od dva slova za SAD i Kanadu. Skraćenica od dva ili tri slova za Australiju. Nije primjenjivo za Francusku, Njemačku ili Ujedinjeno Kraljevstvo.
- **Zemlja/regija**:

  - SAD: Sjedinjene Američke Države, Sjedinjene Države, SAD, SAD, Amerika
  - CA: Kanada, Kalifornija
  - GB: Ujedinjeno Kraljevstvo, UK, Velika Britanija, GB, Ujedinjeno Kraljevstvo Velike Britanije i Sjeverne Irske, Ujedinjeno Kraljevstvo Velike Britanije
  - AU: Australija, AU, Common Wealth Australije
  - FR: Francuska, FR, Francuska Republika
  - DE: Njemačka, njemački, Deutschland, Allemagne, DE, Savezna Republika Njemačka, Republika Njemačka

## <a name="refresh-enrichment"></a>Osvježavanje obogaćivanja

Pokrenite obogaćivanje nakon konfiguriranja robnih marki, interesa i mapiranja polja za demografske podatke. Za pokretanje postupka odaberite **Pokreni** na stranici za konfiguriranje robne marke ili interesa. Usto možete sustavu dopustiti automatsko pokretanje obogaćivanja kao dio zakazanog osvježenja.
Ovisno o veličini vaših podataka o klijentima, može potrajati nekoliko minuta dok se obogaćivanje ne dovrši.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies). Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla. Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon pokretanja postupka obogaćivanja, idite na **Moja obogaćivanja** za pregled ukupnog broja obogaćenih klijenata i analizu robnih marki ili interesa na obogaćenim profilima klijenta.

:::image type="content" source="media/my-enrichments.png" alt-text="Pretpregled rezultata nakon pokretanja postupka obogaćivanja":::

Pregledajte obogaćene podatke odabirom **Prikaz obogaćenih podataka** u grafikonu. Obogaćeni podaci o robnim markama idu u entitet **BrandAffinityFromMicrosoft**. Podaci o interesima su u entitetu **InterestAffinityFromMicrosoft**. Ti su entiteti navedeni i u grupi **Obogaćivanje** u **Podaci** > **Entiteti**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Prikaz podataka o obogaćivanju na kartici klijenta

Afiniteti robne marke i interesa mogu se pogledati i na pojedinačnim karticama klijenata. Idite na **Klijenti** i odaberite profil klijenta. Na korisničkoj kartici naći ćete grafikone za robne marke ili interese za koje ljudi u demografskom profilu tog kupca imaju afinitet.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica klijenta s obogaćenim podacima":::

## <a name="next-steps"></a>Sljedeći koraci

Nadogradite na svoje obogaćene podatke o klijentu. Stvorite [Segmente](segments.md), [Mjere](measures.md), čak [izvezite podatke](export-destinations.md) da biste pružili personalizirano iskustvo svojim klijentima.
