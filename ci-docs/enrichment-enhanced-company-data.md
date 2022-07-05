---
title: Obogatite profile tvrtki poboljšanim podacima tvrtke
description: Obogatite i normalizirajte podatke tvrtke Microsoftovim modelima.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054239"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>Obogatite profile tvrtki poboljšanim podacima tvrtke

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

Model ne radi sljedeće:

- Potvrdite identitet tvrtke. Ne provjeravamo je li ulaz postojeća organizacija ili tvrtka koristi izlaz kao svoj standardni naziv.
- Sveobuhvatno pokrivaju tvrtke na globalnoj razini. Microsoftovi prikupljeni podaci o tvrtki imaju globalnu pokrivenost, ali nude najveću pokrivenost u Australiji, Kanadi, Velikoj Britaniji i Sjedinjenim Državama.
- Standardizirajte adrese tvrtki na globalnoj razini. Trenutno podržavamo standardizirane adrese u tim zemljama ili regijama: Australija, Kanada, Francuska, Njemačka, Italija, Japan, Ujedinjeno Kraljevstvo i Sjedinjene Američke Države.
- Jamstvena točnost ili svježina podataka. Kako se poslovne informacije često mijenjaju, ne možemo jamčiti da su poboljšani podaci o tvrtki uvijek točni ili ažurni.

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

1. Na **pločici Poboljšani podaci tvrtke odaberite** Obogati moje **podatke**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Pločica za obogaćivanje u čvorištu za obogaćivanje podataka tvrtke.":::

1. Pregledajte pregled, a zatim odaberite **Dalje**.

1. Odaberite skup podataka **kupca** i odaberite profil ili segment koji želite obogatiti. Subjekt *Kupac* obogaćuje sve vaše profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Odaberite koju vrstu polja iz profila tvrtke želite koristiti za podudaranje s Microsoftovim prikupljenim podacima tvrtke. Ovaj će odabir utjecati na polja za mapiranje kojima imate pristup u sljedećem koraku.

1. Odaberite **Dalje**.

1. Preslikajte polja tvrtke na Microsoftove podatke tvrtke. Za veću točnost podudaranja dodajte još polja.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Korak mapiranja podataka prilikom konfiguriranja obogaćivanja tvrtke.":::

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja.

1. Navedite naziv **za** obogaćivanje i izlazni **entitet**.

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

1. Odaberite **Pokreni** da biste pokrenuli postupak obogaćivanja ili zatvorili da biste se vratili na **stranicu Obogaćivanje**.

## <a name="view-enrichment-results"></a>Prikaz rezultata obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Kartica Pregled

Pločica **Pregled** promjena kupaca prikazuje detalje o pokrivenosti obogaćivanjem

- **Tvrtke obrađene i promijenjene**: Broj profila korisničkih tvrtki koji su uspješno obogaćeni.
- **Tvrtke su obrađene i nisu promijenjene**: broj profila korisničkih tvrtki koji su prepoznati, ali nisu promijenjeni. To se obično događa kada su ulazni podaci valjani i ne mogu se poboljšati obogaćivanjem.
- **Tvrtke koje nisu obrađene i nisu promijenjene**: broj profila korisničke tvrtke koji nisu prepoznati. To se obično događa za ulazne podatke koji nisu valjani ili ih obogaćivanje ne podržava.

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
