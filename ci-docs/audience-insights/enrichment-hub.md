---
title: Obogaćivanje objedinjenih profila klijenata
description: Koristite mogućnosti za obogaćivanje podataka o klijentima.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954478"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obogaćivanje za korisničke profile (pretpregled)

Koristite podatke iz izvora poput Microsofta i drugih partnera kako biste obogatili podatke o klijentima.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica središta za obogaćivanje":::

U uvidima u ciljnu skupinu idite na **Podaci** > **Obogaćivanje** za rad s mogućnostima obogaćivanja.    
Da biste stvorili ili uredili obogaćivanja, morate imati dozvole Suradnik ili Administrator. Za dodatne informacije pogledajte [Dozvole](permissions.md).

Na kartici **Otkrivanje** pronaći ćete sljedeća obogaćivanja:

- [Brendovi](enrichment-microsoft.md) koje je omogućio Microsoft
- [Interesi](enrichment-microsoft.md) koje je omogućio Microsoft
- [Poboljšane adrese](enrichment-enhanced-addresses.md) koje je omogućio Microsoft
- [Podatke o tvrtki](enrichment-leadspace.md) omogućuje tvrtka Leadspace
- [Demografske podatke](enrichment-experian.md) omogućuje tvrtka Experian
- [Podatke o lokaciji](enrichment-here.md) pruža tvrtka HERE Technologies
- [Prilagođeni podaci](enrichment-SFTP-custom-import.md) putem Protokola sigurnog prijenosa datoteka (SFTP)

Na kartici **Moja obogaćivanja** možete vidjeti obogaćivanja koja ste konfigurirali i urediti njihova svojstva.

## <a name="manage-existing-enrichments"></a>Upravljanje postojećim obogaćivanjima

Idite na **Moja obogaćivanja** da biste vidjeli sva konfigurirana obogaćivanja. Svako obogaćivanje predstavljeno je kao redak koji uključuje dodatne informacije o obogaćivanju.

Odaberite obogaćivanje da biste vidjeli dostupne mogućnosti. Možete odabrati i elipsu (...) na stavci popisa da biste vidjeli mogućnosti.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Mogućnosti upravljanja obogaćivanjima na popisu obogaćivanja":::

- **Prikaži** pojedinosti o obogaćivanju brojem obogaćenih profila klijenata.
- **Uredi** konfiguraciju obogaćivanja.
- **Pokreni** obogaćivanje za ažuriranje profila kupaca najnovijim podacima.
- **Deaktiviraj** postojeće obogaćivanje za zaustavljanje automatskog osvježavanja prilikom svakog zakazanog osvježavanja. Podaci iz posljednjeg uspješnog osvježavanja i dalje će biti dostupni. **Aktiviraj** neaktivno obogaćivanje za ponovno pokretanje automatskog osvježavanja sa svakim zakazanim osvježavanjem.
- **Izbrišite** obogaćivanje.

Možete pokrenuti ili deaktivirati više obogaćivanja odjednom njihovim odabirom na popisu. Mogućnosti prikaza i uređivanja nisu dostupne kao skupna radnja i istovremeno rade samo za jedno obogaćivanje.

## <a name="enrichments-and-connections"></a>Obogaćivanja i veze

Obogaćivanja treće strane konfigurirana su pomoću [veza](connections.md) koje administrator postavlja s vjerodajnicama i daje pristanak za prijenos podataka. Vezu mogu koristiti administratori i suradnici da bi konfigurirali obogaćivanja.  

## <a name="multiple-enrichments-of-the-same-type"></a>Višestruka obogaćivanja iste vrste

Entitet koji treba obogatiti naveden je tijekom konfiguracije obogaćivanja, što vam omogućuje obogaćivanje samo podskupina vaših profila. Na primjer, obogatite podatke samo za određeni segment. Možete konfigurirati nekoliko obogaćivanja iste vrste i ponovno koristiti istu vezu. Neka obogaćivanja imat će ograničenja u broju obogaćivanja iste vrste koja se mogu stvoriti. Ograničenja i trenutna upotreba mogu se vidjeti na stranici **Obogaćivanje**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
