---
title: Poboljšanje podataka tvrtke
description: Obogatite i normalizirajte podatke tvrtke Microsoftovim modelima.
ms.date: 11/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: d11700c87f31cedc40d32b201251d8a9e2e2c312
ms.sourcegitcommit: dfc4843cc78857f1e3ca49d7b938e3ba77969169
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/15/2021
ms.locfileid: "7815885"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Obogaćivanje profila tvrtke poboljšanim podacima tvrtke

Koristite Microsoftove modele i sastavljene podatke tvrtke da biste ispravili, dopunili i standardizirali profile svoje tvrtke. Za bolju točnost i uvide koristit ćemo [format Common Data](/common-data-model/schema/core/applicationcommon/account) Model.

## <a name="how-we-enhance-company-data"></a>Kako poboljšavamo podatke tvrtke

Naš model prolazi kroz proces u dva koraka kako bi poboljšao profil tvrtke. Prvo, normalizira naziv tvrtke. Na primjer, *Microsoft Corp će se* ispraviti i standardizirati na *Microsoft Corporation*. Pokušava pronaći podudaranje u Microsoftovim prikupljenim podacima tvrtke. Ako se pronađe podudaranje, profil tvrtke obogaćujemo podacima iz naših prikupljenih podataka tvrtke, uključujući naziv tvrtke.


### <a name="example"></a>Primjer

Podaci o vašoj tvrtki možda neće slijediti standardizirani oblik i sadržavati pravopisne pogreške. Model pokušava riješiti te probleme i stvoriti dosljedne informacije.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Ograničenja

Postoji nekoliko ograničenja s poboljšanim podacima. Model ne podržava stavke na dolje navedenom popisu.

1.  Potvrdite identitet tvrtke. Ne provjeravamo je li unos postojeća organizacija ili da tvrtka koristi izlaz kao svoj standardni naziv.
2.  Sveobuhvatno pokrivaju tvrtke na globalnoj razini. Microsoftovi prikupljeni podaci o tvrtki imaju globalnu pokrivenost, ali nude najveću pokrivenost u Australiji, Kanadi, Ujedinjenom Kraljevstvu i Sjedinjenim Američkim Državama.
3.  Standardizirajte adrese tvrtke na globalnoj razini. Trenutno podržavamo standardizaciju adresa u tim zemljama ili regijama: Australiji, Kanadi, Francuskoj, Njemačkoj, Italiji, Japanu, Ujedinjenom Kraljevstvu i Sjedinjenim Američkim Državama.
4.  Jamčiti točnost ili svježinu podataka. Budući da se poslovne informacije često mijenjaju, ne možemo jamčiti da su pruženi poboljšani podaci o tvrtki uvijek točni ili ažurirani.

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje**.

1. Na pločici s poboljšanim podacima tvrtke odaberite **Obogati moje** **podatke**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Pločica za obogaćivanje u središtu za obogaćivanje podataka tvrtke.":::

1. Odaberite **Skup podataka o klijentu** pa odaberite entitet koji sadrži adrese koje želite obogatiti. Možete odabrati entitet *Klijent* za obogaćivanje adresa u svim vašim profilima klijenata ili odaberite entitet segmenta za obogaćivanje adresa samo u profilima klijenata sadržanih u tom segmentu.

1. Odaberite vrstu polja iz profila tvrtke koja će se koristiti za podudaranje s podacima Microsoftove kompilirane tvrtke. Ovaj će odabir utjecati na polja za mapiranje kojima imate pristup u sljedećem koraku.

1.  Mapirajte polja poduzeća iz entiteta objedinjenog kupca. Što više identifikatora ključeva i polja mapirate, veća je vjerojatnost veće stope podudaranja.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Korak mapiranja podataka prilikom konfiguriranja obogaćivanja tvrtke.":::

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
