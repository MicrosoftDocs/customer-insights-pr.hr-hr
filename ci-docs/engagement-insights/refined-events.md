---
title: Stvorite i izmijenite događaje
description: Kako stvarati i izmjenjivati događaje.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 935dc4cd41218842e8406b747daef47de04e337a
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606187"
---
# <a name="create-and-modify-events"></a>Stvorite i izmijenite događaje

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Događaj je podatak koji predstavlja ponašanje korisnika, kao što je aktivnost na web-mjestu.

- *Osnovni* događaj bilježi kada korisnik pregleda stranicu (događaj prikaza) ili kada stupi u interakciju sa sadržajem (događaj radnje).
- *Pročišćeni* događaj virtualni je prikaz osnovnog događaja. Pročišćene događaje definirate uklanjanjem i dodavanjem svojstava ili filtriranjem događaja na temelju vrijednosti svojstava.

## <a name="prerequisites"></a>Preduvjeti

Da bi dohvatilo događaje, web-mjesto mora se prvo povezati s uvidima u angažman s pomoću isječka koda. Dodatne informacije potražite u odjeljku [Instaliranje web-SDK-a na web-mjestu](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Prvo povežite svoje podatke.":::

## <a name="create-refined-events"></a>Stvori događaje sužene pretrage

Koristite pročišćene događaje za smanjivanje djelokruga osnovnog događaja za [izvoz](export-events.md) ili uklanjanje svojstava koja nisu potrebna za izlaganje.

> [!NOTE]
> Nakon što na web-mjesto dodate web-SDK, možete pregledati osnovne događaje i stvoriti događaje sužene pretrage. 

Za prikaz osnovnih događaja:

1. Idite u odjeljak **Podaci** u lijevom navigacijskom oknu.

1. Odaberite **Događaji** da biste vidjeli popis svih događaja u radnom prostoru.

    :::image type="content" source="media/data-events.png" alt-text="Pregledajte događaje.":::

Da biste stvorili događaj sužene pretrage od osnovnog događaja: 

1. Idite na **Podaci** > **Događaji** i odaberite **+ Novi događaji** na vrhu zaslonu.

1. U dijaloškom okviru **Novi događaji** odaberite **Stvori događaje sužene pretrage**, a zatim odaberite **Dalje**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Čarobnjak za stvaranje novih događaja.":::
     
1. U dijaloškom okviru **Novi događaji** unesite sljedeće podatke:

   - Odaberite događaj s padajućeg popisa **Osnovni događaji**.
   - Unesite naziv u okvir **Pročišćeni zaslonski naziv događaja**.
   - Neobavezno ažurirajte predloženi **Stvarni naziv** bez korištenja razmaka.

1. Odaberite **Stvori** da biste primijenili svoje postavke.

Događaj sužene pretrage sad se prikazuje na popisu **Događaji**.

### <a name="edit-event-name"></a>Uređivanje naziva događaja

Možete promijeniti naziv i svojstva osnovnog događaja ili događaja sužene pretrage.

1. Idite na **Podaci** > **Događaji**. 

1. Odaberite **Više [...]** za događaj i odaberite **Uredi naziv**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Mogućnosti za stvaranje pročišćenih događaja.":::

3. Ažurirajte naziv događaja i odaberite **Preimenuj**.

### <a name="view-the-details-of-a-refined-event"></a>Prikaz pojedinosti događaja sužene pretrage:

1. Na popisu **Događaj** odaberite osnovni događaj ili događaj sužene pretrage. 

1. Odaberite **Dodaj i ukloni svojstva** pri vrhu zaslona da biste otvorili okno **Uredi svojstva**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Dodajte i uklonite svojstva.":::

1. Pomoću potvrdnih okvira odaberite svojstva koja želite prikazati i ona koja želite sakriti. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Uredite svojstva za pročišćene događaje.":::

1. Odaberite **Potvrdi** da biste primijenili svoj odabir, a zatim odaberite **Spremi**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Uređivanje odabranih svojstava za događaj sužene pretrage

1. Idite na **Podaci** > **Događaji** i odaberite pročišćene događaje da biste otvorili detaljan prikaz.
1. Odaberite **Dodaj i ukloni svojstva**. 
1. Uredite odabir potvrdnih okvira.
1. Odaberite **Potvrdi** i onda **Spremi** da biste primijenili promjene.

Za informacije o izvozu događaja pogledajte [Izvoz događaja](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
