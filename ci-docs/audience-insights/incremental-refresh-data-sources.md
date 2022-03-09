---
title: Postupno osvježavanje za Power Query izvore podataka utemeljene na izvorima podataka
description: Osvježite nove i ažurirane podatke za velike izvore podataka na temelju sustava Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 62632efda3c0c7e53fcdd8864b053ba93e2918bc
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353672"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Postupno osvježavanje izvora podataka na temelju Power Query

U ovom se članku govori o konfiguriranju inkrementalnog osvježavanja za izvore podataka na temelju sustava Power Query.

Dodatno osvježavanje izvora podataka pruža sljedeće prednosti:

- **Brže se osvježava** - osvježavaju se samo podaci koji su se promijenili. Na primjer, možete osvježiti samo posljednjih pet dana povijesnog skupa podataka.
- **Povećana pouzdanost** - uz manja osvježenja, ne morate dugo održavati veze s nestalnim sustavima izvora, čime se smanjuje opasnost od problema s vezom.
- **Smanjena potrošnja resursa** - osvježavanje samo podskupine ukupnih podataka dovodi do učinkovitije upotrebe računalnih resursa i smanjuje ekološki otisak.

## <a name="configure-incremental-refresh"></a>Konfiguriranje postupnog osvježavanja

Publika uvidi omogućuju postupno osvježavanje izvora podataka uvezenih putem Power Query inkrementalnog gutanja te podrške. Na primjer, baze podataka Azure SQL s poljima datuma i vremena, koja pokazuju kada su zapisi podataka posljednji put ažurirani.

1. [Kreirajte novu izvor podataka na osnovu Power Query](connect-power-query.md).

1. **Navedite naziv** izvor podataka.

1. Odaberite izvor podataka koja podržava postupno osvježavanje, kao što je [baza podataka](/power-query/connectors/azuresqldatabase) Azure SQL.

1. Odaberite entitete ili tablice koje ćete unijeti.

1. Dovršite korake pretvaranja i odaberite **Dalje**.

1. U dijaloškom okviru **Postavljanje inkrementalnog osvježavanja** odaberite **Postavljanje** da biste otvorili **Postavke inkrementalnog osvježavanja**. Ako odaberete **Preskoči**, izvor podataka osvježit će cijeli skup podataka.
   > [!TIP]
   > Kasnije možete primijeniti i inkrementalno osvježavanje uređivanjem postojećeg izvora podataka.

1. U odjeljku **Postavke inkrementalnog osvježavanja** konfigurirat ćete inkrementalno osvježavanje za sve entitete koje ste odabrali prilikom izrade izvora podataka.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurirajte entitete u izvoru podataka za inkrementalno osvježavanje.":::

1. Odaberite entitet i navedite sljedeće podatke:

   - **Definiranje primarnog ključa**: odaberite primarni ključ za entitet ili tablicu.
   - **Definirajte polje "zadnji put ažurirano"**: ovo polje prikazuje samo atribute datuma ili vremena vrste. Odaberite atribut koji pokazuje kada su zapisi zadnji put ažurirani. Upotrijebit će se za prepoznavanje zapisa koji ulaze u vremenski okvir dodatnog osvježavanja.
   - **Provjeri ima li ažuriranja svakih**: navedite vremenski okvir za inkrementalno osvježavanje.

1. Odaberite **Spremi** da biste dovršili izradu izvora podataka. Početno osvježavanje podataka bit će potpuno osvježavanje. Nakon toga, inkrementalno osvježavanje podataka izvodi se kao što je konfigurirano u prethodnom koraku.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
