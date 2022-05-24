---
title: Uklanjanje duplikata prije objedinjavanja podataka
description: Drugi korak u procesu ujedinjenja je odabir zapisa koji ćete zadržati kada se pronađu duplikati.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8742927"
---
# <a name="remove-duplicates-before-unifying-data"></a>Uklanjanje duplikata prije objedinjavanja podataka

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Ovaj korak u objedinjavanju po želji vam omogućuje postavljanje pravila za rukovanje dupliciranim zapisima unutar entiteta. *Deduplikacija* identificira duplicirane zapise i spaja ih u jedan zapis. Izvorni zapisi povezuju se s objedinjenim zapisom sa zamjenskim ID-ovima. Ako pravila nisu konfigurirana, primjenjuju se sistemski definirana pravila.

## <a name="include-enriched-entities-preview"></a>Uključi obogaćene entitete (pretpregled)

Ako ste obogatili entitete na razini izvor podataka kako biste poboljšali rezultate ujedinjenja, odaberite ih. Dodatne informacije potražite u odjeljku [Obogaćivanje izvora podataka](data-sources-enrichment.md).

1. **Na stranici Duplicirani zapisi** pri vrhu stranice odaberite **Koristi obogaćene entitete**.

1. U oknu **Koristi obogaćene entitete** odaberite jedan ili više obogaćenih entiteta.

1. Odaberite **Gotovo**.

## <a name="define-deduplication-rules"></a>Definiranje pravila deduplikacije

1. **Na stranici Duplicirani zapisi** odaberite entitet i odaberite **Dodaj pravilo** da biste definirali pravila deduplikacije.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Snimka zaslona sa stranicama dupliciranih zapisa s istaknutim prikazom":::

   1. **U oknu Dodavanje pravila** unesite sljedeće informacije:
      - **Odaberite polje**: Odaberite s popisa dostupnih polja iz entiteta za koji želite provjeriti ima li duplikata. Odaberite polja koja su vjerojatno jedinstvena za svakog pojedinog klijenta. Na primjer, adresa e-pošte ili kombinacija imena, grada i telefonskog broja.
      - **Normalizacija**: Odaberite jednu od sljedećih mogućnosti normalizacije za odabrane atribute.
        - **Brojevi**: Pretvara druge numeričke sustave, kao što su rimski brojevi, u arapske brojeve. *VIII* postaje *8*.
        - **Simboli**: uklanja sve simbole i posebne znakove. *Head&Shoulder* postaje *HeadShoulder*.
        - **Tekst u mala slova: pretvara sav znak u mala slova**. *SVE VELIKA SLOVA i Velika početna slova* postaje *sve velika slova i velika početna slova*.
        - **Vrsta (telefon, ime, adresa, organizacija)**: Standardizira imena, naslove, telefonske brojeve, adrese itd.
        - **Unicode u ASCII**: Pretvara unicode notaciju u ASCII znakove. */u00B2* postaje *2*.
        - **Whitespace**: Uklanja sve razmake. *Pozdrav,   svijete* postaje *Pozdrav,svijete*.
      - **Preciznost**: postavite razinu preciznosti koja će se primjenjivati za ovaj uvjet.
        - **Osnovno**: Odaberite nisko *(30%)*, *srednje (60%)*, *visoko (80%)* i *točno (100%)*. Odaberite **Točno** da bi odgovarali samo zapisima koji odgovaraju 100 posto.
        - **Prilagođeno**: postavite postotak kojem zapisi moraju odgovarati. Sustav će upariti samo zapise koji prelaze ovaj prag.
      - **Naziv**: naziv pravila.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Snimka zaslona s prikazom dodavanje okna pravila za uklanjanje duplikata.":::

   1. Po želji odaberite **Dodaj** > **uvjet** da biste pravilu dodali dodatne uvjete. Uvjeti su povezani logičkim operatorom AND i stoga se izvršavaju samo ako su ispunjeni svi uvjeti.

   1. Po želji dodaj **iznimku** > **da** biste dodali iznimke da biste [pravilu](match-entities.md#add-exceptions-to-a-rule) dodali iznimke. Iznimke se koriste za rješavanje rijetkih slučajeva lažno pozitivnih i lažno negativnih rezultata.

   1. Odaberite **Gotovo** da biste stvorili pravilo.

1. Ako želite, [dodajte još pravila](#define-deduplication-rules).

1. Odaberite entitet, a zatim **Uredite preference spajanja**.

1. **U oknu Preference spajanja**:
   1. Odaberite jednu od tri mogućnosti da biste odredili koji će zapis zadržati ako se pronađe duplikat:
      - **Najispunjeniji**: identificira zapis s najviše ispunjenih polja atributa kao pobjednički zapis. To je zadana mogućnost spajanja.
      - **Najnoviji**: Identificira pobjednički zapis na temelju nedavnosti. Zahtijeva datum ili numeričko polje za definiranje nedavnosti.
      - **Najstariji**: Identificira pobjednički zapis na temelju starosti. Zahtijeva datum ili numeričko polje za definiranje nedavnosti.
      
      U slučaju izjednačenja, rekord pobjednika je onaj s MAX(PK) ili većom vrijednošću primarnog ključa.
      
   1. Po želji, da biste definirali preference spajanja na pojedinačnim atributima entiteta, pri dnu okna odaberite **Dodatno**. Na primjer, možete odabrati zadržavanje najnovije e-pošte I najcjelovitije adrese iz različitih zapisa. Proširite entitet da biste vidjeli sve njegove atribute i definirali koju mogućnost koristiti za pojedinačne atribute. Ako odaberete mogućnost koja se temelji na recesiji, morate navesti i polje datuma/vremena koje definira recesiju.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Okno s preferencama naprednog spajanja koje prikazuje nedavnu e-poštu i potpunu adresu":::

   1. Odaberite **Gotovo** da biste primijenili preference spajanja.

1. Nakon definiranja pravila deduplikacije i preferenci spajanja odaberite **Dalje**.
  
> [!div class="nextstepaction"]
> [Sljedeći korak za jedan entitet: Objedinjavanje polja](merge-entities.md)

> [!div class="nextstepaction"]
> [Sljedeći korak za više entiteta: Podudarni uvjeti](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Izlazna vrijednost uklanjanja duplikata kao entitet

Postupak dodjele stvara novi deduplicirani entitet za svaki od izvornih entiteta. Ti se entiteti mogu pronaći zajedno s **ConflationMatchPairs:CustomerInsights** u odjeljku **Sustav** na stranici **Entiteti** s nazivom **Deduplication_DataSource_Entity**.

Entitet izlazne vrijednosti uklanjanja duplikata sadrži sljedeće informacije:

- ID-jevi/ključevi
  - Polja primarnog ključa i alternativnog ID-a. Zamjensko polje ID-a sastoji se od svih alternativnih ID-ova identificiranih za zapis.
  - Polje Deduplication_GroupId prikazuje grupu ili klaster identificiran unutar entiteta koji grupira sve slične zapise na temelju navedenih polja uklanjanja duplikata. To se koristi u svrhu obrade sustava. Ako nisu navedena ručna pravila za uklanjanje duplikata i ako se primjenjuju pravila za uklanjanje duplikata koja je definirao sustav, ovo polje možda nećete pronaći u entitetu izlazne vrijednosti uklanjanja duplikata.
  - Deduplication_WinnerId: Ovo polje sadrži ID pobjednika iz identificiranih grupa ili klastera. Ako je Deduplication_WinnerId jednak vrijednosti primarnog ključa za zapis, to znači da je zapis pobjednički zapis.
- Polja koja se koriste za definiranje pravila za uklanjanje duplikata.
- Polja Pravilo i Ocjena označavaju koja su pravila za uklanjanja duplikata primijenjena i ocjenu koju vraća algoritam podudaranja.

[!INCLUDE[footer-include](includes/footer-banner.md)]
