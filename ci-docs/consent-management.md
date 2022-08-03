---
title: Koristi pristanak korisnika
description: Poštujte preferencije pristanka kupaca u Customer Insights uvozom podataka o pristanku.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188038"
---
# <a name="use-customer-consent"></a>Koristi pristanak korisnika

Propisi o zaštiti podataka i privatnosti pružaju pojedincima pravo da upravljaju načinom na koji organizacija koristi svoje osobne podatke. Primjeri takvih propisa su Opća uredba o zaštiti podataka u Europskoj uniji ili Kalifornijski zakon o privatnosti potrošača u Sjedinjenim Državama. Ovi propisi omogućuju ljudima da odustanu od prikupljanja, obrade ili dijeljenja svojih osobnih podataka s trećim stranama.  

Kupci mogu odlučiti povući ili uskratiti svoj pristanak za određene oblike kontakta. Također mogu zatražiti da ih isključite iz prikupljanja, pohrane, korištenja ili prodaje njihovih osobnih podataka. Važno je da vaša organizacija poštuje pristanak svih kupaca i preferencije privatnosti.  

Dynamics 365 Customer Insights pomaže vam ispoštovati zahtjeve svojih kupaca uvozom i pohranjivanjem njihovih preferencija kao dijela jedinstvenih korisničkih profila.

Ako se podaci o pristanku pohranjuju odvojeno od vaših korisničkih profila, [dodajte podatke o pristanku kao novi izvor podataka](#import-and-unify-consent-data). U postupak objedinjavanja podataka dodaje se izvor podataka koji sadrži podatke o pristanku. Uspješno ujedinjenje podataka o pristanku i korisničkih profila tada dovodi do jedinstvenih korisničkih profila koji sadrže podatke o pristanku. Za korisničke profile koji već sadrže podatke o pristanku idite izravno na odjeljak s podacima o [pristanku za upotrebu](#use-consent-data).

## <a name="prerequisites"></a>Preduvjeti

Sljedeće informacije moraju biti dostupne u vašim izvornim podacima kako bi se podaci o pristanku objedinili s drugim profilima kupaca:

- Zamjenski ključ za mapiranje podataka o pristanku na korisničke profile u customer insights. Na primjer, adresa e-pošte ili telefonski broj.
- Vrijednost pristanka za određivanje statusa privole kupca.

Razmislite o dodavanju sljedećih *neobaveznih* informacija:

- Primarni ključ za ažuriranje statusa pristanka ako klijent zatraži promjenu.
- Vrsta privole, ako postoji više načina obrade podataka o kupcima.
- Datum pristanka ili bilo koja druga vrsta podataka relevantnih za vaše scenarije pristanka.

Primjer tablice jednostavne baze podataka pristanka s više mogućnosti pristanka:

|ID pristanka (primarni ključ)   |E-pošta (zamjenski ključ)  |Mogućnost pristanka  |Vrijednost pristanka  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Novinska brošura       |  Pogrešno       |
|2    |  holly@contoso.com       |  Ažuriranja proizvoda       |  Točno       |
|3    |  frank@contoso.com       |  Novinska brošura       | Točno        |
|4    |  frank@contoso.com       |  Ažuriranja proizvoda       |  Pogrešno       |

## <a name="import-and-unify-consent-data"></a>Uvoz i objedinjavanje podataka o pristanku

Uvezite podatke o pristanku na isti način na koji unosite druge izvore podataka u Customer Insights. Dodatne informacije o podržanim izvorima podataka i načinu njihova uvoza potražite u članku [Pregled izvora podataka](data-sources.md).

Dodatne informacije o objedinjavanju izvora podataka potražite u članku [Pregled](data-unification.md) ujedinjenja podataka.

## <a name="use-consent-data"></a>Korištenje podataka o pristanku

Nakon što vaši podaci o pristanku budu dio vaših jedinstvenih korisničkih profila, možete ih koristiti u Customer Insights. Na primjer, stvorite segment s pravilom kako biste osigurali da poštujete postavke privatnosti i zaštite podataka svojih kupaca. Pravila koja podržavaju preference pristanka koriste se za isključivanje korisnika iz segmenta koji se temelji na atributima profila. Dodajte pravilo segmentu koje isključuje profile kupaca koji nisu dali pristanak za kontakt.

Pozivajući se na gornju oglednu tablicu, segment može sadržavati ovo pravilo:`Consent option=Newsletter & Consent value=True`. Ova konfiguracija rezultira segmentom koji poštuje postavke kontakta za slanje biltena.

Dodatne informacije o izgradnji segmenata potražite u članku [Stvaranje segmenata](segment-builder.md).

Nakon kreiranja segmenta možete koristiti jednu od mnogih [mogućnosti](export-destinations.md) izvoza za korištenje segmenta u drugim aplikacijama.

## <a name="ensure-updated-consent-status"></a>Osigurajte ažurirani status pristanka

Važno je ažurirati status pristanka za svoje klijente. Zakazano osvježavanje u customer insights uvijek uvozi najnovije stanje vaših izvora podataka. Te se informacije zatim obrađuju objedinjavanjem podataka i rezultiraju ažuriranim profilima kupaca. Ti se ažurirani profili zatim koriste za osvježavanje segmenata kako biste bili sigurni da radite s najnovijim informacijama.

Drugim riječima, provjerite imaju li izvorišni podaci koji se uvoze u Customer Insights uvijek najnovije informacije.

Dodatne informacije potražite u članku [Ručno](segments.md#refresh-segments) osvježavanje segmenata ili [konfiguriranje zakazanog osvježavanja](system.md#schedule-tab).

[!INCLUDE [footer-include](includes/footer-banner.md)]
