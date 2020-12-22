---
title: Pretražite i filtrirajte profile klijenata
description: Pronađite brzo informacije o objedinjenim profilima klijenata i filtrirajte određene atribute.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405341"
---
# <a name="customer-profiles-search--filter-index"></a>Profili klijenta: indeks pretraživanja i filtriranja

Rezultat objedinjavanja podataka vaših klijenata jest entitet Profil klijenta koji pruža objedinjeni pregled nad ukupnom bazom klijenata. Da biste brzo [pronašli informacije o određenom klijentu ili grupi klijenata](customer-profiles.md) možete konfigurirati mogućnosti **Pretraži** i **Filtriraj** na stranici **Klijenti**. Pročitajte više o tome kako administratori mogu uređivati atribute na stranici **Pretraži i filtriraj indeks**, koja je dostupna korisnicima za pretraživanje i filtriranje.

> [!div class="mx-imgBorder"]
> ![Pretraži filtar](media/search-filter.png "Pretraži filtar")

## <a name="add-fields-and-specify-attributes"></a>Dodajte polja i odredite atribute

Ako kao administrator po prvi put definirate atribute koje je moguće pretraživati, prvo trebate definirati indeksirana polja. Preporučujemo da odaberete sve atribute po kojima korisnici mogu pretraživati i filtrirati klijente na stranici **Klijenti**. Možete odrediti samo atribute koji postoje na entitetu Profil klijenta, koji ste izradili tijekom postupka objedinjavanja podataka.

1. Otvorite stranicu **Kupci** i odaberite **Pretraži i filtriraj indeks**.

> [!NOTE]
> Stvaramo zadanu konfiguraciju indeksa pretraživanja na dostupnim atributima u entitetu Kupac na temelju sljedećih semantičkih vrsta definiranih na stranici Karta.
> - Ime, prezime, srednje ime, puno ime osobe
> - Naziv organizacije
> - Adresa e-pošte
> - Telefonski broj
> - Podaci o lokaciji

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
