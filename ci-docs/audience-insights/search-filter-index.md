---
title: Pretražite i filtrirajte profile klijenata
description: Pronađite brzo informacije o objedinjenim profilima klijenata i filtrirajte određene atribute.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: 4445f44b87a5947c3dfcf43ddb49dca9f25b69aa
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354500"
---
# <a name="customer-profiles-search--filter-index"></a>Profili klijenta: indeks pretraživanja i filtriranja

Rezultat objedinjavanja podataka vaših klijenata jest entitet Profil klijenta koji pruža objedinjeni pregled nad ukupnom bazom klijenata. Da biste brzo [pronašli informacije o određenom klijentu ili grupi klijenata](customer-profiles.md) možete konfigurirati mogućnosti **Pretraži** i **Filtriraj** na stranici **Klijenti**. Pročitajte više o tome kako administratori mogu uređivati atribute na stranici **Pretraži i filtriraj indeks**, koja je dostupna korisnicima za pretraživanje i filtriranje.

   :::image type="content" source="media/search-filter.png" alt-text="Pretraži filtar":::

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

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

3. Odaberite **Pokreni** kad budete spremni primijeniti svoje postavke. Nakon obrade promjena, pronaći ćete ih u [karticama klijenta na stranici Klijenti](customer-profiles.md). 

## <a name="next-steps"></a>Sljedeći koraci

Pregledajte [stranicu objedinjenih profila](customer-profiles.md) da biste potražili profile ili se koristili indeksiranim poljima za pregled podskupa svih objedinjenih profila.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
