---
title: Obogaćivanje profila tvrtki pomoću obogaćivanja treće strane tvrtke Leadspace
description: Opće informacije o obogaćivanju treće strane tvrtke Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269413"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Obogaćivanje profila tvrtke uz Leadspace (pretpregled)

Leadspace je tvrtka za proučavanje podataka koja pruža B2B platformu za podatke o klijentima. Klijentima pruža objedinjene korisničke profile kako bi tvrtke obogatile svoje podatke. Obogaćivanja uključuju dodatne atribute poput veličine tvrtke, lokacije, grane industrije i još mnogo toga.

## <a name="prerequisites"></a>Preduvjeti

Za konfiguriranje Leadspacea, potrebno je ispuniti sljedeće preduvjete:

- Imate aktivnu licencu za Leadspace i "vječni ključ" (koji se naziva **Leadspace token**). Kontaktirajte izravno [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) za detalje o njihovom proizvodu.
- Imate dozvole [administratora](permissions.md#administrator).
- Imati [objedinjene korisničke profile](customer-profiles.md) za tvrtke.

## <a name="configuration"></a>Konfiguracija

1. U uvidima u ciljnu skupinu idite u odjeljak **Podaci** > **Obogaćivanje**.

1. Odaberite **Obogati moje podatke** na pločici Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snimka zaslona pločice Leadspace.":::

1. Odaberite **Početak**, a zatim unesite aktivni **Leadspace token** (vječni ključ). Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**. Potvrdite oba unosa odabirom mogućnosti **Povezivanje s uslugom Leadspace**.

1. Odaberite **Mapiraj podatke** i odaberite skup podataka koji želite obogatiti podacima o tvrtki iz sustava Leadspace. Možete odabrati entitet *Klijent* za obogaćivanje svih vaših profila klijenta ili odaberite segmentni entitet za obogaćivanje samo profila klijenata sadržanih u tom segmentu.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Odaberite između profila klijenta i obogaćivanja segmenata.":::

1. Odaberite **Sljedeće** i definirajte koja se polja iz vaših objedinjenih profila trebaju koristiti za traženje odgovarajućih podataka o tvrtki iz sustava Leadspace. Polje **Naziv tvrtke** je obavezno. Za veću preciznost podudaranja, mogu se dodati do dva druga polja, **Web-stranica tvrtke** i **Lokacija tvrtke**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okno za mapiranje polja usluge Leadspace.":::
   
1. Odaberite **Primijeni** za dovršetak mapiranja polja.

1. Odaberite **Pokreni** kako biste obogatili profile tvrtke. Trajanje obogaćivanja ovisi o broju objedinjenih profila klijenata.

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon osvježavanja obogaćivanja, možete pregledati novoobogaćene podatke tvrtke pod [Moja obogaćivanja](enrichment-hub.md). Možete pronaći vrijeme posljednjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.

Za dodatne informacije pogledajte [API-ji za Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Sljedeći koraci

Nadogradite na svoje obogaćene podatke o klijentu. Stvorite [segmente](segments.md), [mjere](measures.md), pa i [izvezite podatke](export-destinations.md) kako biste svojim klijentima pružili personalizirano iskustvo.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Leadspace, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Leadspace ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE[footer-include](../includes/footer-banner.md)]