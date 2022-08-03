---
title: Upravljanje indeksom pretraživanja i filtriranja za profile kupaca
description: Pronađite brzo informacije o objedinjenim profilima klijenata i filtrirajte određene atribute.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187900"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Upravljanje indeksom pretraživanja i filtriranja za profile kupaca

Rezultat objedinjavanja podataka o klijentima *je klijentski* entitet koji pruža jedinstven prikaz vaše ukupne baze klijenata. Da bi korisnici brzo [pronašli informacije o određenom klijentu ili grupi klijenata](customer-profiles.md), administrator mora konfigurirati **mogućnosti pretraživanja** i **filtriranja** za **stranicu Kupci**.

   :::image type="content" source="media/search-filter.png" alt-text="Pretraži filtar":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Definiranje atributa koji se mogu pretraživati i indeksiranih polja

Ako prvi put definirate atribute koji se mogu pretraživati kao administratora, najprije definirajte indeksirana polja. Preporučujemo da odaberete sve atribute po kojima korisnici mogu pretraživati i filtrirati klijente na stranici **Klijenti**. Mogu se navesti samo atributi koji postoje u *entitetu Klijent* stvoreni tijekom postupka objedinjavanja podataka.

1. Idite na **Klijenti** i odaberite **Indeks** pretraživanja i filtriranja.

1. Odaberite **+ Dodaj**.

1. Odaberite atribute na popisu koji želite dodati kao indeksirana polja i kliknite **Primijeni**.

1. Da biste dodali još atributa, odaberite **Dodaj**. Da biste uklonili odabrani atribut, odaberite ga, a zatim **izbrišite**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Stranica indeksa pretraživanja i filtriranja.":::

1. Odaberite **Pokreni** nakon što budete spremni primijeniti postavke pretraživanja i filtriranja. Nakon obrade promjena pogledajte ih na [karticama kupaca na stranici](customer-profiles.md) Kupac.

## <a name="define-filtering-options-for-a-given-attribute"></a>Definiranje mogućnosti filtriranja za određeni atribut

Postavite polja koja se mogu koristiti za filtriranje kupaca na **stranici Kupci**.

1. Idite na **Klijenti** i odaberite **Indeks** pretraživanja i filtriranja.

1. Odaberite atribut i **Dodaj filtar**. Definirajte broj rezultata i redoslijed kojim će biti organizirani. Ovisno o vrsti podataka atributa, pojavit će se jedno od sljedećih okna.

   - Atributi vrste nizova: navedite broj željenih rezultata u **oknu filtra** Niz i pravilo redoslijeda po kojem će biti organizirani.

   - Atributi numeričke vrste: navedite intervale uključene u **okno filtara** Broj i pravilo redoslijeda po kojem će biti organizirani.

   - Atributi vrste datuma: navedite intervale uključene u **okno filtra** Datum i pravilo redoslijeda po kojem će biti organizirani.

1. Odaberite **U redu**. Ponovite postupak za sve atribute prema kojima želite filtrirati.

1. Odaberite **Pokreni** nakon što budete spremni primijeniti postavke pretraživanja i filtriranja. Nakon obrade promjena pogledajte ih na [karticama kupaca na stranici](customer-profiles.md) Kupac.

## <a name="view-indexed-customer-fields"></a>Prikaz indeksiranih polja kupaca

Stranica indeksa **pretraživanja** i filtra prikazuje sljedeće informacije:

- **Naziv**: predstavlja naziv atributa kako se pojavljuje u entitetu *Kupac*.
- **Vrsta podataka**: određuje je li vrsta podataka niz, broj ili datum.
- **Uključeno u pretraživanje**: određuje može li se taj atribut koristiti za pretraživanje klijenata na stranici **Klijenti** koristeći polje **Pretraživanje**.
- **Dodavanje filtra**: kontrola za upravljanje načina na koji se taj atribut može koristiti za filtriranje na stranici **Klijenti**.

## <a name="next-steps"></a>Sljedeći koraci

Pregledajte [stranicu objedinjenih profila](customer-profiles.md) da biste potražili profile ili se koristili indeksiranim poljima za pregled podskupa svih objedinjenih profila.

[!INCLUDE [footer-include](includes/footer-banner.md)]
