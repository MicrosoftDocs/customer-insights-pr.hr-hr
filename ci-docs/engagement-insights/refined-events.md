---
title: Stvaranje i izmjena događaja sužene pretrage
description: Kako stvoriti i izmijeniti pročišćene događaje.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034765"
---
# <a name="create-and-modify-refined-events"></a>Stvaranje i izmjena događaja sužene pretrage

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Događaj je podatak koji predstavlja ponašanje korisnika, kao što je aktivnost na web-mjestu.

- *Osnovni* događaj bilježi kada korisnik pregleda stranicu (događaj prikaza) ili kada stupi u interakciju sa sadržajem (događaj radnje).
- *Pročišćeni* događaj virtualni je prikaz osnovnog događaja. Pročišćene događaje definirate uklanjanjem i dodavanjem svojstava ili filtriranjem događaja na temelju vrijednosti svojstava.

Koristite pročišćene događaje za smanjivanje djelokruga osnovnog događaja za [izvoz](export-events.md) ili uklanjanje svojstava koja nisu potrebna za izlaganje.

## <a name="create-refined-events"></a>Stvaranje profinjenih događaja

Postoje tri načina za stvaranje pročišćenog događaja iz osnovnog događaja. 

1. Idite na **Podaci**> **Događaji** i odaberite jednu od sljedećih mogućnosti:
    - Odaberite **Novi događaji** i zatim odaberite **Stvori pročišćene događaje**.
    - Odaberite osnovni događaj da biste otvorili detaljan prikaz i odaberite **Stvori pročišćene događaje** s gornjeg izbornika.
    - Odaberite **Više [...]** za otvaranje izbornika prečaca za osnovni događaj. Zatim odaberite **Stvori pročišćene događaje**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Mogućnosti za stvaranje pročišćenih događaja.":::

1. U dijaloškom okviru **Stvori pročišćene događaje** unesite sljedeće podatke:

- Odaberite događaj iz padajućeg izbornika **Osnovni događaji** ako stvarate novi događaj.
- Unesite naziv u okvir **Pročišćeni zaslonski naziv događaja**.
- Neobavezno ažurirajte predloženi **Stvarni naziv** bez korištenja razmaka.

3. Odaberite **Stvori** da biste primijenili svoje postavke.

1. U detaljnom prikazu svojeg pročišćenog događaja odaberite **Dodaj i ukloni svojstva** da biste otvorili okno **Uredi svojstva**. 

1. Pomoću potvrdnih okvira odaberite svojstva koja želite prikazati i ona koja želite sakriti. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Uredite svojstva za pročišćene događaje.":::

1. Odaberite **Potvrdi** da biste primijenili svoj odabir.

1. Odaberite **Spremi** da biste spremili konfiguraciju.

## <a name="edit-refined-events"></a>Uređivanje pročišćenih događaja

Možete promijeniti naziv i svojstva pročišćenog događaja.

### <a name="edit-event-name"></a>Uređivanje naziva događaja

1. Idite na **Podaci** > **Događaji**. 
1. Odaberite **Više [...]** za događaj i odaberite **Uredi naziv**.
1. Ažurirajte naziv događaja i odaberite **Preimenuj**.

### <a name="edit-selected-properties"></a>Uređivanje odabranih svojstava

1. Idite na **Podaci** > **Događaji** i odaberite pročišćene događaje da biste otvorili detaljan prikaz.
1. Odaberite **Dodaj i ukloni svojstva**. 
1. Uredite odabir potvrdnih okvira.
1. Odaberite **Potvrdi** i onda **Spremi** da biste primijenili promjene.

Za informacije o izvozu događaja pogledajte [Izvoz događaja](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
