---
title: Postupno osvježavanje za Power Query izvore podataka koji se temelje na njima
description: Osvježite nove i ažurirane podatke za velike izvore podataka na temelju programa Power Query.
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
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642374"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Postupno osvježavanje izvora podataka na temelju Power Query

U ovom se članku opisuje kako konfigurirati inkrementalno osvježavanje za izvore podataka na temelju programa Power Query.

Dodatno osvježavanje izvora podataka pruža sljedeće prednosti:

- **Brže se osvježava** - osvježavaju se samo podaci koji su se promijenili. Na primjer, možete osvježiti samo posljednjih pet dana povijesnog skupa podataka.
- **Povećana pouzdanost** - uz manja osvježenja, ne morate dugo održavati veze s nestalnim sustavima izvora, čime se smanjuje opasnost od problema s vezom.
- **Smanjena potrošnja resursa** - osvježavanje samo podskupine ukupnih podataka dovodi do učinkovitije upotrebe računalnih resursa i smanjuje ekološki otisak.

## <a name="configure-incremental-refresh"></a>Konfiguriranje inkrementalnog osvježavanja

Customer Insights omogućuje postupno osvježavanje izvora podataka uvezenih putem Power Query te podrške postupnog gutanja. Na primjer, baze podataka Azure SQL s poljima datuma i vremena, koja pokazuju kada su zapisi podataka posljednji put ažurirani.

1. [Kreirajte novi izvor podataka na temelju programa Power Query](connect-power-query.md).

1. Navedite naziv **za** izvor podataka.

1. Odaberite izvor podataka koja podržava postupno osvježavanje, kao [što je baza podataka](/power-query/connectors/azuresqldatabase) Azure SQL.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
