---
title: Konfiguracija sustava u uvidima u ciljnu skupinu
description: Saznajte više o postavkama sustava u mogućnosti uvidi u ciljnu skupinu Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405338"
---
# <a name="system-configuration"></a>Konfiguracija sustava

Stranica **Sustav** uključuje četiri kartice: **Stanje**, **Raspored**, **O sustavu** i **Općenito**.

> [!div class="mx-imgBorder"]
> ![Stranica sustava](media/system-tabs.png "Stranica sustava")

## <a name="status-tab"></a>Kartica Status

Kartica **Status** omogućuje praćenje tijeka uvlačenja podataka, izvoza podataka i nekoliko važnih proizvodnih procesa. Pregledajte podatke na ovoj kartici da biste osigurali dovršetak aktivnih procesa.

Ova kartica sadrži tablice stanja **Izvori podataka**, **Sustavni procesi** i **Priprema podataka**. Svaka tablica prati **Naziv** zadatka i odgovarajućeg entiteta, **Status** najnovijeg pokretanja i vrijeme za **Zadnje ažuriranje**.

Prikažite pojedinosti o posljednjih nekoliko pokretanja zadatka odabirom njegova naziva.

### <a name="status-types"></a>Vrste statusa

Postoji šest vrsta stanja za zadatke. Sljedeće vrste statusa prikazuju se i na stranicama *Podudaranje*, *Spajanje*, *Izvori podataka*, *Segmenti*, *Mjere*, *Obogaćivanje*, *Aktivnosti* i *Predviđanja*:

- **Obrada:** zadatak je u tijeku. Status se može promijeniti u Uspješno ili Neuspješno.
- **Uspješno:** zadatak je uspješno dovršen.
- **Preskočen:** Zadatak je preskočen. Jedan ili više postupaka u nastavku o kojima ovaj zadatak ovisi nisu uspjeli ili su preskočeni.
- **Neuspješno:** obrada zadatka nije uspjela.
- **Otkazano:** korisnik je otkazao obradu prije nego što je dovršena.
- **U redu čekanja:** obrada je u redu čekanja i započet će nakon dovršetka svih zadataka. Za dodatne informacije pogledajte [Pravila osvježavanja](#refresh-policies).

### <a name="refresh-policies"></a>Pravila osvježavanja

Ovaj popis prikazuje pravila osvježavanja za svaki od glavnih postupaka:

- **Izvori podataka:** pokreću se prema [konfiguriranom rasporedu](#schedule-tab). Ne ovisi ni o kojem drugom procesu. Podudaranje ovisi o uspješnom dovršetku ovog postupka.
- **Podudaranje:** pokreće se prema [konfiguriranom rasporedu](#schedule-tab). Ovisi o obradi izvora podataka koji se koriste u definiciji podudaranja. Spajanje ovisi o uspješnom dovršetku ovog postupka.
- **Spajanje**: pokreće se prema [konfiguriranom rasporedu](#schedule-tab). Ovisi o dovršetku postupka podudaranja. Segmenti, mjere, obogaćivanje, pretraživanje, aktivnosti, predviđanja i priprema podataka ovise o uspješnom dovršetku ovog procesa.
- **Segmenti**: pokreću se ručno (jednokratno osvježavanje) i u skladu s [konfiguriranim rasporedom](#schedule-tab). Ovise o spajanju. Uvidi ovise o njihovoj obradi.
- **Mjere**: pokreću se ručno (jednokratno osvježavanje) i u skladu s [konfiguriranim rasporedom](#schedule-tab). Ovise o spajanju.
- **Aktivnosti**: pokreću se ručno (jednokratno osvježavanje) i u skladu s [konfiguriranim rasporedom](#schedule-tab). Ovise o spajanju.
- **Obogaćivanje**: pokreće se ručno (jednokratno osvježavanje) i u skladu s [konfiguriranim rasporedom](#schedule-tab). Ovise o spajanju.
- **Pretraživanje**: pokreće se ručno (jednokratno osvježavanje) i u skladu s [konfiguriranim rasporedom](#schedule-tab). Ovise o spajanju.
- **Priprema podataka:** pokreće se prema [konfiguriranom rasporedu](#schedule-tab). Ovise o spajanju.
- **Uvidi**: pokreću se ručno (jednokratno osvježavanje) i u skladu s [konfiguriranim rasporedom](#schedule-tab). Ovise o segmentima.

Odaberite status zadatka da biste vidjeli pojedinosti o tijeku cijelog posla. Gore navedena pravila osvježavanja mogu vam pomoći da shvatite što možete učiniti za rješavanje zadatka **Preskočeno** ili **U redu čekanja**.

## <a name="schedule-tab"></a>Kartica Raspored

Upotrijebite karticu **Raspored** da biste zakazali automatsko osvježavanje svih vaših [unesenih izvora podataka](data-sources.md). Automatska osvježavanja pomažu osigurati da se ažuriranja iz vaših izvora podataka odražavaju na objedinjenim profilima klijenata.

1. U uvidima u ciljnu skupinu idite na **Admin** > **Sustav** i odaberite karticu **Raspored**.

2. Zadano je stanje za zakazano osvježavanje **Isključeno**. Da biste omogućili zakazana osvježavanja, promijenite gumb na vrhu zaslona na **Uključeno**.

3. Odaberite između osvježavanja **Tjedno** (zadano) i **Dnevno**. Ako namjeravate zakazati tjedna osvježavanja, odaberite jedan ili više dana u koje želite izvesti osvježavanje.

4. Postavite vrijednost **Vremenska zona**, a zatim upotrijebite padajući izbornik **Vrijeme** kako biste postavili vrijeme osvježavanja. Kada dovršite, odaberite **Postavi**. Ako želite zakazati više osvježavanja u jednom danu, odaberite **Dodavanje drugog vremena**.

5. Odaberite **Spremi** za primjenu izmjena.

## <a name="about-tab"></a>Kartica Pojedinosti

Kartica **O programu** sadrži podatke vaše tvrtke ili ustanove **Zaslonsko ime**, aktivni **ID okruženja**, **Regiju** i **ID sesije**. Ako imate više od jednog radnog okruženja, trebali biste svakome od njih dati lako prepoznatljiv zaslonsko ime.

## <a name="general-tab"></a>Kartica Općenito

Postoje dvije mogućnosti na karticama **Općenito**, **Jezik** i **Oblik države/regije**.

Aplikacija [podržava brojne jezike](supported-languages.md). Da biste promijenili željeni jezik, odaberite **Jezik** s padajućeg izbornika.

Da biste promijenili željeno oblikovanje za datum, vrijeme i brojeve, koristite padajući izbornik **Oblik države/regije**. Pod ovim se poljem prikazuje pretpregled oblikovanja. Sustav će automatski predložiti odabir kada odaberete novi jezik.

Odaberite **Spremi** kako biste potvrdili svoje odabire.

## <a name="api-usage-tab"></a>Kartica Upotreba API-ja

Pronađite pojedinosti o upotrebi API-ja u stvarnom vremenu i pogledajte koji su se događaji dogodili u određenom vremenskom rasponu. Za dodatne informacije pogledajte [Uvlačenje podataka u stvarnom vremenu](real-time-data-ingestion.md).
