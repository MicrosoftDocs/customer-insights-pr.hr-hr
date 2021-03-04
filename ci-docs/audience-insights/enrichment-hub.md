---
title: Obogaćivanje objedinjenih profila klijenata
description: Koristite mogućnosti za obogaćivanje podataka o klijentima.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269459"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obogaćivanje za korisničke profile (pretpregled)

Koristite podatke iz izvora poput Microsofta i drugih partnera kako biste obogatili podatke o klijentima.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica središta za obogaćivanje":::

U uvidima u ciljnu skupinu idite na **Podaci** > **Obogaćivanje** za rad s mogućnostima obogaćivanja.    
Da biste stvorili ili uredili obogaćivanja, morate imati dozvole Suradnik ili Administrator. Za dodatne informacije pogledajte [Dozvole](permissions.md).

Na kartici **Otkrivanje** pronaći ćete sljedeća obogaćivanja:

- [Robne marke](enrichment-microsoft-graph.md) pruža Microsoft Graph
- [Interesi](enrichment-microsoft-graph.md) pruža Microsoft Graph
- [Podatke o tvrtki](enrichment-leadspace.md) omogućuje tvrtka Leadspace
- [Demografske podatke](enrichment-experian.md) omogućuje tvrtka Experian
- [Podatke o lokaciji](enrichment-here.md) pruža tvrtka HERE Technologies
- [Prilagođeni podaci](enrichment-SFTP-custom-import.md) putem Protokola sigurnog prijenosa datoteka (SFTP)

Na kartici **Moja obogaćivanja** možete vidjeti obogaćivanja koja ste konfigurirali i urediti njihova svojstva.

## <a name="manage-existing-enrichments"></a>Upravljanje postojećim obogaćivanjima

Idite na **Moja obogaćivanja** da biste vidjeli sva konfigurirana obogaćivanja. Svako obogaćivanje predstavljeno je kao redak koji uključuje dodatne informacije o obogaćivanju.

Odaberite obogaćivanje da biste vidjeli dostupne mogućnosti. Ili možete odabrati elipsu (...) na stavci popisa da biste vidjeli mogućnosti.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Mogućnosti upravljanja obogaćivanjima na popisu obogaćivanja":::

- **Prikaži** pojedinosti o obogaćivanju brojem obogaćenih profila klijenata.
- **Uredi** konfiguraciju obogaćivanja.
- **Pokreni** obogaćivanje za ažuriranje profila kupaca najnovijim podacima.
- **Deaktiviraj** postojeće obogaćivanje za zaustavljanje automatskog osvježavanja prilikom svakog zakazanog osvježavanja. Podaci iz posljednjeg uspješnog osvježavanja i dalje će biti dostupni. **Aktiviraj** neaktivno obogaćivanje za ponovno pokretanje automatskog osvježavanja sa svakim zakazanim osvježavanjem.
- **Izbrišite** obogaćivanje.

Možete pokrenuti ili deaktivirati više obogaćivanja odjednom njihovim odabirom na popisu. Mogućnosti prikaza i uređivanja nisu dostupne kao skupna radnja i istovremeno rade samo za jedno obogaćivanje.


[!INCLUDE[footer-include](../includes/footer-banner.md)]