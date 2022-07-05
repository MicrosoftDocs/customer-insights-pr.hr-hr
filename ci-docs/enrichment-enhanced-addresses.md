---
title: Obogatite profile kupaca poboljšanim adresama (sadrži videozapise)
description: Obogatite i normalizirajte podatke o adresi profila klijenata pomoću Microsoftovih modela.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082067"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Obogatite profile kupaca poboljšanim adresama

Adrese u vašim podacima mogu biti nestrukturirane, nepotpune ili netočne. Koristite Microsoftove modele za normalizaciju i obogaćivanje adresa u [format Common Data Model](/common-data-model/schema/core/applicationcommon/address) radi veće preciznosti i uvida.

Također [možete obogatiti adrese na izvorima](data-sources-enrichment.md) podataka kako biste poboljšali točnost podudaranja u procesu ujedinjenja podataka. 

## <a name="how-we-enhance-addresses"></a>Kako poboljšavamo adrese

Naš model prolazi postupak u dva koraka za poboljšanje adrese. Prvo raščlanjuje adresu kako bi identificirao njezine komponente i stavlja ih u strukturirani format. Zatim koristimo AI za ispravljanje, popunjavanje i standardizaciju vrijednosti u adresi.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Primjer

Podaci o adresi mogu biti u nestandardnom formatu i sadržavati pravopisne pogreške. Model može riješiti ove probleme i stvoriti dosljedne adrese u objedinjenim profilima klijenata.

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

### <a name="limitations"></a>Ograničenja

Poboljšane adrese funkcioniraju samo s vrijednostima koje već postoje u unesenim podacima o adresi. Model ne radi sljedeće:

1. Provjerava je li adresa valjana.
2. Provjerava je li bilo koja vrijednost, poput poštanskih brojeva ili naziva ulica, valjana.
3. Mijenja vrijednosti koje ne prepoznaje.

Model koristi tehnike temeljene na strojnom učenju za poboljšanje adresa. Kao i kod bilo kojeg modela temeljenog na strojnom učenju, 100 posto točnosti nije zajamčena.

## <a name="supported-countries-or-regions"></a>Podržane države ili regije

Trenutno podržavamo obogaćivanje adresa u sljedećim državama ili regijama:

- Australija
- Kanada
- Francuska
- Njemačka
- Italija
- Japan
- Velika Britanija
- Sjedinjene Države

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

1. Odaberite **Obogati moje podatke** na pločici **Poboljšane adrese**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Snimka zaslona pločice poboljšanih adresa.":::

1. Pregledajte pregled, a zatim odaberite **Dalje**.

1. Odaberite skup podataka **kupca** i odaberite profil ili segment koji želite obogatiti. Subjekt *Kupac* obogaćuje sve vaše profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Odaberite način formatiranja adresa u vašem skupu podataka. Odaberite **Adresa s jednim atributom** ako adrese u vašim podacima koriste jedno polje. Odaberite **Adresa s više atributa** ako adrese u vašim podacima koriste više od jednog polja podataka.

1. Odaberite **Dalje** i mapirajte polja adrese iz jedinstvenog entiteta klijenta.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Stranica mapiranja polja poboljšane adrese.":::

   > [!NOTE]
   > Država/regija obavezna je i za adrese s jednim i za one s više atributa. Adrese koje ne sadrže valjane ili podržane vrijednosti države/regije neće biti obogaćene.

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja.

1. Navedite naziv **za** obogaćivanje i izlazni **entitet**.

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

## <a name="view-enrichment-results"></a>Prikaz rezultata obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Broj **kupaca obogaćenih poljem** pruža dubinsku analizu pokrivenosti svakog obogaćenog polja.

### <a name="overview-card"></a>Kartica Pregled

Kartica **Pregled** promjena kupaca prikazuje pojedinosti o pokrivenosti obogaćivanjem:

- **Obrađene i promijenjene** adrese: broj profila kupaca s adresama koje su uspješno obogaćene.
- **Adrese obrađene i nisu promijenjene**: broj profila klijenata s adresama koje su prepoznate, ali nisu promijenjene. To se obično događa kada su ulazni podaci valjani i ne mogu se poboljšati obogaćivanjem.
- **Adrese koje nisu obrađene i nisu promijenjene**: broj profila s adresama koje nisu prepoznate. Obično za ulazne podatke koji nisu valjani ili nisu podržani obogaćivanjem.

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
