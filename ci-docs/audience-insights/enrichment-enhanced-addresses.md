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
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965569"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Obogaćivanje profila klijenata s poboljšanim adresama

Adrese u vašim podacima mogu biti nestrukturirane, nepotpune ili netočne. Koristite Microsoftove modele za normalizaciju i obogaćivanje adresa u [format Common Data Model](/common-data-model/schema/core/applicationcommon/address) radi veće preciznosti i uvida.

## <a name="how-we-enhance-addresses"></a>Kako poboljšavamo adrese

Naš model prolazi postupak u dva koraka za poboljšanje adrese. Prvo raščlanjuje adresu kako bi identificirao njezine komponente i stavlja ih u strukturirani format. Zatim koristimo umjetnu inteligenciju da bismo ispravili, upotpunili i standardizirali vrijednosti u adresi.

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

Model koristi tehnike temeljene na strojnom učenju za poboljšanje adresa. Iako primjenjujemo visoki prag pouzdanosti kada model mijenja ulaznu vrijednost, kao i kod bilo kojeg modela temeljenog na strojnom učenju, točnost od 100 % nije zajamčena.

## <a name="supported-countries-or-regions"></a>Podržane države ili regije

Trenutno podržavamo obogaćivanje adresa u sljedećim državama ili regijama: 

- Australija
- Kanada
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
   > Država/regija je obavezna i za adresu s jednim atributom i za adresu s više atributa. Adrese koje ne sadrže valjane ili podržane vrijednosti države/regije neće biti obogaćene

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

Nadogradite na svoje obogaćene podatke o klijentu. Stvorite [segmente](segments.md), [mjere](measures.md), pa i [izvezite podatke](export-destinations.md) kako biste svojim klijentima pružili personalizirano iskustvo.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
