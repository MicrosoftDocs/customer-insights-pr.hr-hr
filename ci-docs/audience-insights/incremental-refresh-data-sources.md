---
title: Inkrementalno osvježavanje za izvore podataka koji se temelje na dodatku Power Query
description: Osvježite nove i ažurirane podatke za velike izvore podataka koji se temelje na platformi Power Query.
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 03f76bcfc7336d8430146e8a26ffa649c6a17db0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596812"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Dodatno osvježavanje izvora podataka koji se temelje na platformi Power Query

Dodatno osvježavanje izvora podataka pruža sljedeće prednosti:

- **Brže se osvježava** - osvježavaju se samo podaci koji su se promijenili. Na primjer, možete osvježiti samo posljednjih pet dana povijesnog skupa podataka.
- **Povećana pouzdanost** - uz manja osvježenja, ne morate dugo održavati veze s nestalnim sustavima izvora, čime se smanjuje opasnost od problema s vezom.
- **Smanjena potrošnja resursa** - osvježavanje samo podskupine ukupnih podataka dovodi do učinkovitije upotrebe računalnih resursa i smanjuje ekološki otisak.

## <a name="configure-incremental-refresh"></a>Konfiguriranje postupnog osvježavanja

Uvidi u ciljnu skupinu omogućuju inkrementalno osvježavanje za izvore podataka uvezene putem dodatka Power Query koji podržava inkrementalnu obradu. Na primjer, baze podataka Azure SQL s poljima datuma i vremena, koja pokazuju kada su zapisi podataka posljednji put ažurirani.

1. [Stvorite novi izvor podataka koji se temelji na platformi Power Query](connect-power-query.md).

1. Unesite naziv izvora podataka.

1. Odaberite izvor podataka koji podržava inkrementalno osvježavanje, poput baze podataka Azure SQL.

1. Odaberite entitete ili tablice koje ćete unijeti.

1. Dovršite korake pretvaranja i odaberite **Dalje**.

1. U dijaloškom okviru **Postavljanje inkrementalnog osvježavanja** odaberite **Postavljanje** da biste otvorili **Postavke inkrementalnog osvježavanja**. Ako odaberete **Preskoči**, izvor podataka osvježit će cijeli skup podataka.
   > [!TIP]
   > Kasnije možete primijeniti i inkrementalno osvježavanje uređivanjem postojećeg izvora podataka.

1. U odjeljku **Postavke inkrementalnog osvježavanja** konfigurirat ćete inkrementalno osvježavanje za sve entitete koje ste odabrali prilikom izrade izvora podataka.

   > [!div class="mx-imgBorder"]
   > ![Konfiguriranje entiteta u izvoru podataka za inkrementalno osvježavanje](media/incremental-refresh-settings.png "Konfiguriranje entiteta u izvoru podataka za inkrementalno osvježavanje")

1. Odaberite entitet i navedite sljedeće podatke:

   - **Definiranje primarnog ključa**: odaberite primarni ključ za entitet ili tablicu.
   - **Definirajte polje "zadnji put ažurirano"**: ovo polje prikazuje samo atribute datuma ili vremena vrste. Odaberite atribut koji pokazuje kada su zapisi zadnji put ažurirani. Upotrijebit će se za prepoznavanje zapisa koji ulaze u vremenski okvir dodatnog osvježavanja.
   - **Provjeri ima li ažuriranja svakih**: navedite vremenski okvir za inkrementalno osvježavanje.

1. Odaberite **Spremi** da biste dovršili izradu izvora podataka. Početno osvježavanje podataka bit će potpuno osvježavanje. Nakon toga, inkrementalno osvježavanje podataka izvodi se kao što je konfigurirano u prethodnom koraku.


[!INCLUDE[footer-include](../includes/footer-banner.md)]