---
title: Postupno osvježavanje izvora Power Query podataka i izvora podataka servisa Azure Data Lake
description: Osvježite nove i ažurirane podatke za velike izvore podataka koji se temelje na izvorima podataka ili na Power Query servisu Azure data lake.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012016"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Postupno osvježavanje izvora Power Query podataka i izvora podataka servisa Azure Data Lake

U ovom se članku opisuje kako konfigurirati postupno osvježavanje za izvore podataka koji se temelje na podatkovnom jezeru Power Query azure ili azure data lake.

Dodatno osvježavanje izvora podataka pruža sljedeće prednosti:

- **Brže se osvježava** - osvježavaju se samo podaci koji su se promijenili. Na primjer, možete osvježiti samo posljednjih pet dana povijesnog skupa podataka.
- **Povećana pouzdanost** - uz manja osvježenja, ne morate dugo održavati veze s nestalnim sustavima izvora, čime se smanjuje opasnost od problema s vezom.
- **Smanjena potrošnja resursa** - osvježavanje samo podskupine ukupnih podataka dovodi do učinkovitije upotrebe računalnih resursa i smanjuje ekološki otisak.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Konfiguriranje inkrementalnog osvježavanja za izvore podataka na temelju Power Query

Customer Insights omogućuje postupno osvježavanje izvora podataka uvezenih putem Power Query te podrške postupnog gutanja. Na primjer, baze podataka Azure SQL s poljima datuma i vremena, koja pokazuju kada su zapisi podataka posljednji put ažurirani.

1. [Kreirajte novi izvor podataka na temelju programa Power Query](connect-power-query.md).

1. Odaberite izvor podataka koja podržava inkrementalno osvježavanje, kao [što je baza podataka azure SQL](/power-query/connectors/azuresqldatabase).

1. Odaberite entitete ili tablice koje ćete unijeti.

1. Dovršite korake pretvaranja i odaberite **Dalje**.

1. U dijaloškom okviru **Postavljanje inkrementalnog osvježavanja** odaberite **Postavljanje** da biste otvorili **Postavke inkrementalnog osvježavanja**. Ako odaberete **Preskoči**, izvor podataka osvježit će cijeli skup podataka.
   > [!TIP]
   > Kasnije možete primijeniti i inkrementalno osvježavanje uređivanjem postojećeg izvora podataka.

1. U odjeljku **Postavke inkrementalnog osvježavanja** konfigurirat ćete inkrementalno osvježavanje za sve entitete koje ste odabrali prilikom izrade izvora podataka.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurirajte postavke inkrementalnog osvježavanja.":::

1. Odaberite entitet i navedite sljedeće podatke:

   - **Definiranje primarnog ključa**: odaberite primarni ključ za entitet ili tablicu.
   - **Definirajte polje "zadnji put ažurirano"**: ovo polje prikazuje samo atribute datuma ili vremena vrste. Odaberite atribut koji pokazuje kada su zapisi zadnji put ažurirani. Upotrijebit će se za prepoznavanje zapisa koji ulaze u vremenski okvir dodatnog osvježavanja.
   - **Provjeri ima li ažuriranja svakih**: navedite vremenski okvir za inkrementalno osvježavanje.

1. Odaberite **Spremi** da biste dovršili izradu izvora podataka. Početno osvježavanje podataka bit će potpuno osvježavanje. Nakon toga, inkrementalno osvježavanje podataka izvodi se kao što je konfigurirano u prethodnom koraku.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Konfiguriranje inkrementalnog osvježavanja za izvore podataka servisa Azure Data Lake

Customer Insights omogućuje postupno osvježavanje izvora podataka povezanih s programom Azure Data Lake Storage. Da biste koristili inkrementalno gutanje i osvježavanje za entitet, konfigurirajte taj entitet prilikom dodavanja izvor podataka azure data lake izvor podataka ili novijih prilikom uređivanja izvor podataka. Mapa podataka entiteta mora sadržavati sljedeće mape:

- **FullData**: Mapa s podatkovnim datotekama koje sadrže početne zapise
- **InkrementalData**: Mapa s mapama hijerarhije datuma/vremena u **obliku gggg/mm/dd/hh** koja sadrži inkrementalna ažuriranja. **hh** predstavlja UTC sat ažuriranja i sadrži **mape Upserts** i **Deletes**. **Upserts** sadrži podatkovne datoteke s ažuriranjima postojećih zapisa ili novih zapisa. **Brisanja sadrže podatkovne** datoteke sa zapisima koje treba ukloniti.

1. Prilikom dodavanja ili uređivanja izvor podataka dođite do **okna Atributi** za entitet.

1. Pregledajte atribute. Provjerite je li stvoreni ili zadnji ažurirani atribut datuma postavljen s oblikom podataka dateTime *i* vrstom **Calendar**.Date *Semantic*.**·** Po potrebi uredite atribut i odaberite **Gotovo**.

1. **U oknu Odabir entiteta** uredite entitet. Potvrđen je **okvir Inkremental ingestion**.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Konfigurirajte entitete u izvoru podataka za inkrementalno osvježavanje.":::

   1. Pronađite korijensku mapu koja sadrži datoteke .csv ili .parketa za potpune podatke, inkrementalne nadogradnje podataka i dodatne podatke.
   1. Unesite proširenje za potpune podatke i obje inkrementalne datoteke (\. csv ili \. parket).
   1. Odaberite **Spremi**.

1. Za **Posljednje ažuriranje** odaberite atribut datumske vremenske oznake.

1. Ako primarni **ključ** nije odabran, odaberite primarni ključ. Primarni ključ je atribut jedinstven za entitet. Da bi atribut bio važeći primarni ključ, on ne bi trebao uključivati dvostruke vrijednosti, vrijednosti koje nedostaju ili vrijednosti nula. Atributi vrste podataka nizova, cijelog broja i GUID-a podržani su kao primarni ključevi.

1. Odaberite **Zatvori** da biste spremili i zatvorili okno.

1. Nastavite s dodavanjem ili uređivanjem izvor podataka.

[!INCLUDE [footer-include](includes/footer-banner.md)]
