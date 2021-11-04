---
title: Konfiguracija sustava u uvidima u ciljnu skupinu
description: Saznajte više o postavkama sustava u mogućnosti uvidi u ciljnu skupinu Dynamics 365 Customer Insights.
ms.date: 10/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3ce767939b8fedf676dc569ede47104ecfe930dd
ms.sourcegitcommit: cd9f9a9d3da71c5420ef5c4c6ead91bc820d17a9
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/19/2021
ms.locfileid: "7651831"
---
# <a name="system-configuration"></a>Konfiguracija sustava

Stranica **Sustav** uključuje sljedeće kartice:
- [Stanje](#status-tab)
- [Raspored](#schedule-tab)
- [Upotreba API-ja](#api-usage-tab)
- [Više o](#about-tab)
- [Općenito](#general-tab)
- [Sigurnost](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Kartice postavki na stranici sustava.":::

## <a name="status-tab"></a>Kartica Status

**Kartica statusa** omogućuje vam praćenje napretka unosa podataka, izvoza podataka i nekoliko drugih važnih procesa proizvoda. Pregledajte podatke na ovoj kartici da biste osigurali dovršetak aktivnih procesa.

Ova kartica uključuje tablice s informacijama o statusu i obradi za različite procese. Svaka tablica prati **Naziv** zadatka i odgovarajućeg entiteta, **Status** najnovijeg pokretanja i vrijeme za **Zadnje ažuriranje**.

Prikažite pojedinosti o posljednjih nekoliko pokretanja zadatka odabirom njegova naziva.

### <a name="status-types"></a>Vrste statusa

Postoji šest vrsta stanja za zadatke. Sljedeće vrste statusa prikazuju se i na stranicama *Podudaranje*, *Spajanje*, *Izvori podataka*, *Segmenti*, *Mjere*, *Obogaćivanje*, *Aktivnosti* i *Predviđanja*:

- **Obrada:** zadatak je u tijeku. Status se može promijeniti u Uspješno ili Neuspješno.
- **Uspješno:** zadatak je uspješno dovršen.
- **Preskočen:** Zadatak je preskočen. Jedan ili više postupaka u nastavku o kojima ovaj zadatak ovisi nisu uspjeli ili su preskočeni.
- **Neuspješno:** obrada zadatka nije uspjela.
- **Otkazano:** korisnik je otkazao obradu prije nego što je dovršena.
- **U redu čekanja:** Obrada je u redu čekanja i započet će nakon dovršetka svih zadataka. Za dodatne informacije pogledajte [Pravila osvježavanja](#refresh-policies).

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

Možete promijeniti jezik i format zemlje/regije na kartici **Općenito**.

Customer Insights [podržava brojne jezike](/dynamics365/get-started/availability). Aplikacija upotrebljava vaše jezične postavke za prikaz elemenata poput izbornika, teksta oznake te poruka sustava na željenom jeziku.

Uvezeni podaci i informacije koje ste ručno unijeli se ne prevode.

### <a name="update-the-settings"></a>Ažuriraj postavke

Da biste promijenili željeni jezik, odaberite **Jezik** s padajućeg izbornika.

Da biste promijenili željeno oblikovanje za datum, vrijeme i brojeve, koristite padajući izbornik **Oblik države/regije**. Pod ovim se poljem prikazuje pretpregled oblikovanja. Sustav će automatski predložiti odabir kada odaberete novi jezik.

Odaberite **Spremi** kako biste potvrdili svoje odabire.

## <a name="api-usage-tab"></a>Kartica Upotreba API-ja

Pronađite pojedinosti o korištenju API-ja u stvarnom vremenu i pogledajte koji su se događaji dogodili u danom vremenskom okviru. Vremenski okvir odabirete u padajućem izborniku **Odabir vremenskog okvira**. 

**Korištenje API-ja** sadrži tri odjeljka: 
- **Pozivi API-ja** – grafikon koji prikazuje skupni broj poziva API-ju u odabranom vremenskom okviru.

- **Prijenos podataka** – grafikon koji prikazuje količinu podataka koja je prenesena putem API-ja u odabranom vremenskom okviru.

-  **Operacije** – tablica s recima za svaku dostupnu operaciju API-ja i pojedinostima o korištenju operacija. Možete odabrati naziv operacije na koju želite ići [referenca za API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operacije koje koriste [unos podataka u stvarnom vremenu](real-time-data-ingestion.md) sadrže gumb sa simbolom dalekozora za prikaz korištenja API-ja u stvarnom vremenu. Odaberite gumb da biste otvorili bočno okno s detaljima o upotrebi API-ja u stvarnom vremenu u trenutačnom okruženju.   
   Koristite okvir **Grupiraj prema** u oknnu **Korištenje API-ja u stvarnom vremenu** da biste odabrali način kako najbolje predstaviti svoje interakcije u stvarnom vremenu. Možete grupirati podatke prema načinu rada API-ja, nazivu kvalificiranog entiteta (uvučeni entitet), kreatoru (izvor događaja), rezultatu (uspjeh ili neuspjeh) ili kodovima pogrešaka. Podaci su dostupni u vidu povijesnog grafikona i tablice.

## <a name="security-tab"></a>Kartica Sigurnost

Kartica **Sigurnost** omogućuje vam povezivanje i upravljanje vlastitim [sefom za ključeve servisa Azure](/azure/key-vault/general/basic-concepts) u okruženju.
Namjenski sef za ključeve može se koristiti za postavljanje i korištenje tajni u granicama usklađenosti tvrtke ili ustanove. Uvidi u ciljne skupine mogu koristiti tajne u sefu za ključeve platforme Azure za [uspostavu veza](connections.md) sa sustavima trećih strana.

Za više informacija pogledajte [Donesite svoj vlastiti sef za ključeve servisa Azure](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]