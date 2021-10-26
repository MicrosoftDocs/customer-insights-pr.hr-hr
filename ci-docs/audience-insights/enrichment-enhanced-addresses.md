---
title: Obogaćivanje poboljšanja adrese
description: Obogatite i normalizirajte podatke o adresi profila klijenata pomoću Microsoftovih modela.
ms.date: 07/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: f56be1f4ecdac124ed76a0fb0eb1e313099248bf
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643359"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Obogaćivanje profila klijenata s poboljšanim adresama

Adrese u vašim podacima mogu biti nestrukturirane, nepotpune ili netočne. Koristite Microsoftove modele za normalizaciju i obogaćivanje adresa u [format Common Data Model](/common-data-model/schema/core/applicationcommon/address) radi veće preciznosti i uvida.

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

Model koristi tehnike temeljene na strojnom učenju za poboljšanje adresa. Iako primjenjujemo visoki prag pouzdanosti kada model mijenja ulaznu vrijednost, kao i kod svakog modela temeljenog na strojnom učenju, 100-postotna točnost nije zajamčena.

## <a name="supported-countries-or-regions"></a>Podržane države ili regije

Trenutno podržavamo obogaćivanje adresa u sljedećim državama ili regijama: 

- Australija
- Kanada
- Francuska
- Njemačka
- Italija
- Japan
- Ujedinjena Kraljevina
- Sjedinjene Države

Adrese moraju sadržavati vrijednost države/regije. Ne obrađujemo adrese za države ili regije koje nisu podržane i adrese koje nemaju navedenu državu ili regiju.

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje**.

1. Odaberite **Obogati moje podatke** na pločici **Poboljšane adrese**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Snimka zaslona pločice poboljšanih adresa.":::

1. Odaberite **Skup podataka o klijentu** pa odaberite entitet koji sadrži adrese koje želite obogatiti. Možete odabrati entitet *Klijent* za obogaćivanje adresa u svim vašim profilima klijenata ili odaberite entitet segmenta za obogaćivanje adresa samo u profilima klijenata sadržanih u tom segmentu.

1. Odaberite način formatiranja adresa u vašem skupu podataka. Odaberite **Adresa s jednim atributom** ako adrese u vašim podacima koriste jedno polje. Odaberite **Adresa s više atributa** ako adrese u vašim podacima koriste više od jednog polja podataka.

   > [!NOTE]
   > Država/regija obavezna je i za adrese s jednim i za one s više atributa. Adrese koje ne sadrže valjane ili podržane vrijednosti države/regije neće biti obogaćene.

1.  Mapirajte polja adrese iz vašeg objedinjenog entiteta klijenta.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Stranica mapiranja polja poboljšane adrese.":::

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja.

1. Navedite naziv za obogaćivanje i izlazni entitet.

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake. Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab). Vrijeme obrade ovisi o veličini vaših podataka o klijentima.

Nakon završetka postupka obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod stavkom **Moja obogaćivanja**. Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
