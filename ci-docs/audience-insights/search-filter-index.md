---
title: Pretražite i filtrirajte profile klijenata
description: Pronađite brzo informacije o objedinjenim profilima klijenata i filtrirajte određene atribute.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597134"
---
# <a name="customer-profiles-search--filter-index"></a>Profili klijenta: indeks pretraživanja i filtriranja

Rezultat objedinjavanja podataka vaših klijenata jest entitet Profil klijenta koji pruža objedinjeni pregled nad ukupnom bazom klijenata. Da biste brzo [pronašli informacije o određenom klijentu ili grupi klijenata](customer-profiles.md) možete konfigurirati mogućnosti **Pretraži** i **Filtriraj** na stranici **Klijenti**. Pročitajte više o tome kako administratori mogu uređivati atribute na stranici **Pretraži i filtriraj indeks**, koja je dostupna korisnicima za pretraživanje i filtriranje.

> [!div class="mx-imgBorder"]
> ![Pretraži filtar](media/search-filter.png "Pretraži filtar")

## <a name="add-fields-and-specify-attributes"></a>Dodajte polja i odredite atribute

Ako kao administrator po prvi put definirate atribute koje je moguće pretraživati, prvo trebate definirati indeksirana polja. Preporučujemo da odaberete sve atribute po kojima korisnici mogu pretraživati i filtrirati klijente na stranici **Klijenti**. Možete odrediti samo atribute koji postoje na entitetu Profil klijenta, koji ste izradili tijekom postupka objedinjavanja podataka.

1. Otvorite stranicu **Kupci** i odaberite **Pretraži i filtriraj indeks**.

2. Odaberite **+ Dodaj** da biste odredili indeksirana polja.

3. Na popisu odaberite atribute koje želite dodati kao indeksirana polja. Uvijek možete dodati više atributa odabirom mogućnosti **Dodaj**. Također, možete ukloniti sve odabrane atribute odabirom simbola **Ukloni**.

## <a name="explore-the-indexed-customer-fields-table"></a>Istraživanje tablice polja indeksiranih klijenata

U tablici su dostupne sljedeće informacije.

- **Naziv**: predstavlja naziv atributa kako se pojavljuje u entitetu Profil klijenta.
- **Vrsta podataka**: određuje je li vrsta podataka niz, broj ili datum.
- **Uključeno u pretraživanje**: određuje može li se taj atribut koristiti za pretraživanje klijenata na stranici **Klijenti** koristeći polje **Pretraživanje**.
- **Dodavanje filtra**: kontrola za upravljanje načina na koji se taj atribut može koristiti za filtriranje na stranici **Klijenti**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Uređivanje opcija filtriranja za određeni atribut

Izbornik **Filtar** na stranici **Klijenti** može uključivati različit broj razina atributa (na primjer, različite dobne skupine prema kojima se filtriraju klijenti).

1. Odaberite **Dodaj filtar** za određeni atribut na stranici **Pretraži i filtriraj indeks**. Možete definirati broj rezultata i redoslijed po kojem će biti organizirani. Ovisno o vrsti podataka atributa prikazat će se jedna od sljedećih ploča.

- Atributi vrste niza: odredite broj željenih rezultata u oknu **Mogućnosti filtra niza** i pravila redoslijeda prema kojima će biti organizirani.

- Atributi vrste broja: odredite uključene intervale u oknu **Mogućnosti filtra broja** i pravila redoslijeda prema kojima će biti organizirani.

- Atributi vrste datuma: odredite uključene intervale u oknu **Mogućnosti filtra datuma** i pravila redoslijeda prema kojima će biti organizirani.

2. Odaberite **Spremi** za primjenu izmjena.

3. Odaberite **Pokreni** kad budete spremni primijeniti svoje postavke.

## <a name="next-steps"></a>Sljedeći koraci

Idite na stranicu **Klijenti** za pretraživanje korisničkih profila ili upotrijebite indeksirana polja za prikaz podskupa svih korisničkih profila.


[!INCLUDE[footer-include](../includes/footer-banner.md)]