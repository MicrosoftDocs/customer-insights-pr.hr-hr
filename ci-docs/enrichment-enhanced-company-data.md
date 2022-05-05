---
title: Poboljšanje podataka tvrtke
description: Obogatite i normalizirajte podatke tvrtke Microsoftovim modelima.
ms.date: 04/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6aa38afa7f92b512d19b4967fc1652b5e43ad094
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642195"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Obogaćivanje profila tvrtke poboljšanim podacima tvrtke

Koristite Microsoftove modele i kompilirane podatke tvrtke da biste ispravili, dopunili i standardizirali profile svoje tvrtke. Koristit [ćemo format](/common-data-model/schema/core/applicationcommon/account) Common Data Model za bolju točnost i uvide.

Također [možete poboljšati podatke tvrtke o izvorima](data-sources-enrichment.md) podataka kako biste poboljšali točnost podudaranja u procesu objedinjavanja podataka. 

Za javna poduzeća u Sjedinjenim Državama dostupne su informacije kao što su prihodi, burzovna pločica, industrija i još mnogo toga.  

## <a name="how-we-enhance-company-data"></a>Kako poboljšavamo podatke o tvrtki

Naš model prolazi kroz postupak u dva koraka kako bi poboljšao profil tvrtke. Prvo, normalizira naziv tvrtke. Na primjer, *Microsoft Corp* će se ispraviti i standardizirati na *Microsoft Corporation*. Pokušava pronaći podudaranje u Microsoftovim kompiliranim podacima tvrtke. Ako se pronađe podudaranje, profil tvrtke obogaćujemo podacima iz prikupljenih podataka tvrtke, uključujući naziv tvrtke.


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

Postoji nekoliko ograničenja s poboljšanim podacima. Model ne podržava stavke na donjem popisu.

1.  Potvrdite identitet tvrtke. Ne provjeravamo je li ulaz postojeća organizacija ili tvrtka koristi izlaz kao svoj standardni naziv.
2.  Sveobuhvatno pokrivaju tvrtke na globalnoj razini. Microsoftovi prikupljeni podaci o tvrtki imaju globalnu pokrivenost, ali nude najveću pokrivenost u Australiji, Kanadi, Velikoj Britaniji i Sjedinjenim Državama.
3.  Standardizirajte adrese tvrtki na globalnoj razini. Trenutno podržavamo standardizirane adrese u tim zemljama ili regijama: Australija, Kanada, Francuska, Njemačka, Italija, Japan, Ujedinjeno Kraljevstvo i Sjedinjene Američke Države.
4.  Jamstvena točnost ili svježina podataka. Kako se poslovne informacije često mijenjaju, ne možemo jamčiti da su poboljšani podaci o tvrtki uvijek točni ili ažurni.

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje**.

1. Na **pločici Poboljšani podaci tvrtke odaberite** Obogati moje **podatke**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Pločica za obogaćivanje u čvorištu za obogaćivanje podataka tvrtke.":::

1. Odaberite **Skup podataka o klijentu** pa odaberite entitet koji sadrži adrese koje želite obogatiti. Možete odabrati entitet *Klijent* za obogaćivanje adresa u svim vašim profilima klijenata ili odaberite entitet segmenta za obogaćivanje adresa samo u profilima klijenata sadržanih u tom segmentu.

1. Odaberite koja bi se vrsta polja iz profila vaše tvrtke trebala koristiti za podudaranje s Microsoftovim kompiliranim podacima tvrtke. Ovaj će odabir utjecati na polja za mapiranje kojima imate pristup u sljedećem koraku.

1.  Mapirajte polja poduzeća iz jedinstvenog entiteta kupca. Što više identifikatora ključeva i polja mapirate, veća je vjerojatnost veće stope podudaranja.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Korak mapiranja podataka prilikom konfiguriranja obogaćivanja tvrtke.":::

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja.

1. Navedite naziv za obogaćivanje i izlazni entitet.

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake. Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab). Vrijeme obrade ovisi o veličini vaših podataka o klijentima.

Nakon završetka postupka obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod stavkom **Moja obogaćivanja**. Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.

Uzorak obogaćenih podataka možete vidjeti u pločici pretpregleda **obogaćenih** kupaca. Odaberite **Vidi više** i odaberite karticu **Podaci** da biste pristupili detaljnom prikazu svakog obogaćenog profila.

### <a name="overview-card"></a>Kartica Pregled

Pregledna kartica prikazuje detalje o pokrivenosti obogaćivanja. 

* **Tvrtke obrađene i promijenjene**: Broj profila korisničkih tvrtki koji su uspješno obogaćeni.

* **Tvrtke su obrađene i nisu promijenjene**: broj profila korisničkih tvrtki koji su prepoznati, ali nisu promijenjeni. To se obično događa kada su ulazni podaci valjani i ne mogu se poboljšati obogaćivanjem.

* **Tvrtke koje nisu obrađene i nisu promijenjene**: broj profila korisničke tvrtke koji nisu prepoznati. To se obično događa za ulazne podatke koji nisu valjani ili ih obogaćivanje ne podržava.

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
