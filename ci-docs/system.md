---
title: Konfiguracija sustava u korisničkim uvidima
description: Saznajte više o postavkama sustava u sustavu Dynamics 365 Customer Insights.
ms.date: 04/21/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 3aa4c6529d705698e612adad86587e3c3a4db35b
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653607"
---
# <a name="system-configuration"></a>Konfiguracija sustava

Da biste pristupili konfiguracijama sustava, idite na **AdminSystem** > **da** biste pogledali popis sistemskih zadataka i procesa.

Stranica **Sustav** uključuje sljedeće kartice:
- [Stanje](#status-tab)
- [Raspored](#schedule-tab)
- [Upotreba API-ja](#api-usage-tab)
- [Više o](#about-tab)
- [Općenito](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Kartice postavki na stranici sustava.":::

## <a name="status-tab"></a>Kartica Status

Kartica **Stanje** omogućuje praćenje napretka zadataka, unosa podataka, izvoza podataka i nekoliko drugih važnih procesa proizvoda. Pregledajte informacije na ovoj kartici kako biste osigurali potpunost aktivnih zadataka i procesa.

Ova kartica uključuje tablice s informacijama o statusu i obradi za različite procese. Svaka tablica prati **Naziv** zadatka i odgovarajućeg entiteta, **Status** najnovijeg pokretanja i vrijeme za **Zadnje ažuriranje**. Detalje posljednjih nekoliko pokretanja možete pregledati odabirom naziva zadatka ili procesa. 

Odaberite status pokraj zadatka ili procesa u stupcu **Stanje** da biste otvorili okno s detaljima o **napretku**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Okno s detaljima o tijeku sustava":::

### <a name="status-definitions"></a>Definicije stanja

Sustav za zadatke i procese koristi sljedeće statuse:

|Stanje  |Definicija  |
|---------|---------|
|Otkazano |Korisnik je prekinuo obradu prije dovršetka.   |
|Neuspjelo   |Došlo je do pogreške pri unosu podataka.         |
|Nije uspjelo  |Obrada nije uspjela.  |
|Nije pokrenuto   |Izvor podataka još nema unesenih podataka ili je još uvijek u načinu skice.         |
|Obrada u tijeku  |Zadatak ili proces su u tijeku.  |
|Osvježavanje    |U tijeku je unos podataka. Ovu operaciju možete otkazati tako da odaberete **Prekini osvježavanje** u stupcu **Radnje**. Ako prekinete osvježavanje, izvor podataka vratit će se na posljednje stanje osvježavanja.       |
|Preskočeno  |Zadatak ili proces su preskočeni. Jedan ili više postupaka u nastavku o kojima ovaj zadatak ovisi nisu uspjeli ili su preskočeni.|
|Uspješno  |Zadatak ili proces uspješno su dovršeni. Za izvore podataka označava da su podaci uspješno uneseni ako je u stupcu **Osvježeno** navedeno vrijeme.|
|U redu čekanja | Obrada je u redu čekanja i započet će nakon dovršetka svih uzlaznih zadataka i procesa. Dodatne informacije potražite u članku [Osvježi procese](#refresh-processes).|

### <a name="refresh-processes"></a>Procesi osvježavanja

Osvježavanje zadataka i procesa pokreće se prema konfiguriranom [rasporedu](#schedule-tab). 

|Proces  |Opis  |
|---------|---------|
|Aktivnost  |Izvodi se ručno (jednokratno osvježavanje). Ovisi o procesu spajanja. Uvidi ovise o njihovoj obradi.|
|Povezivanje analize |Izvodi se ručno (jednokratno osvježavanje). Ovisi o segmentima.  |
|Priprema analize |Izvodi se ručno (jednokratno osvježavanje). Ovisi o segmentima.  |
|Priprema podataka   |Potreban je entitet za pokretanje. Izvor podataka entiteti ovise o gutanju. Obogaćeni subjekti ovise o obogaćivanju. Entitet Klijent ovisi o spajanju.  |
|Izvori podataka   |Ne ovisi ni o kojem drugom procesu. Podudaranje ovisi o uspješnom dovršetku ovog postupka.  |
|Obogaćivanja   |Izvodi se ručno (jednokratno osvježavanje). Ovisi o procesu spajanja. |
|Izvozi odredišta |Izvodi se ručno (jednokratno osvježavanje). Ovisi o segmentima.  |
|Uvidi |Izvodi se ručno (jednokratno osvježavanje). Ovisi o segmentima.  |
|Intelligence   |Ovisi o spajanju.   |
|Usklađivanje |Ovisi o obradi izvora podataka koji se koriste u definiciji podudaranja.      |
|Mjerila  |Izvodi se ručno (jednokratno osvježavanje). Ovisi o procesu spajanja.  |
|Spoji   |Ovisi o dovršetku postupka podudaranja. Segmenti, mjere, obogaćivanje, pretraživanje, aktivnosti, predviđanja i priprema podataka ovise o uspješnom dovršetku ovog procesa.   |
|Profili   |Izvodi se ručno (jednokratno osvježavanje). Ovisi o procesu spajanja. |
|Traži   |Izvodi se ručno (jednokratno osvježavanje). Ovisi o procesu spajanja. |
|Segmenti  |Izvodi se ručno (jednokratno osvježavanje). Ovisi o procesu spajanja. Uvidi ovise o njihovoj obradi.|
|Sustav   |Ovisi o dovršetku postupka podudaranja. Segmenti, mjere, obogaćivanje, pretraživanje, aktivnosti, predviđanja i priprema podataka ovise o uspješnom dovršetku ovog procesa.   |
|User  |Izvodi se ručno (jednokratno osvježavanje). Ovisi o entitetima.  |

Odaberite status procesa da biste vidjeli detalje o napretku cijelog posla u kojem se nalazio. Gore navedeni procesi osvježavanja mogu vam pomoći da shvatite što možete učiniti da biste riješili zadatak ili proces preskočenog **ili** **u redu čekanja**.

## <a name="schedule-tab"></a>Kartica Raspored

Upotrijebite karticu **Raspored** da biste zakazali automatsko osvježavanje svih vaših [unesenih izvora podataka](data-sources.md). Automatska osvježavanja pomažu osigurati da se ažuriranja iz vaših izvora podataka odražavaju na objedinjenim profilima klijenata.

> [!NOTE]
> Izvore podataka kojima upravljate osvježavate prema vlastitim rasporedima. Da biste zakazali osvježavanje izvora podataka kojima upravljate, konfigurirajte postavke osvježavanja na tom određenom izvor podataka sa **stranice Izvori** podataka.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Postavke osvježavanja tijeka podataka.":::

1. Otvorite **AdminSystem** > **i** odaberite karticu **Raspored**.

2. Zadano je stanje za zakazano osvježavanje **Isključeno**. Da biste omogućili zakazana osvježavanja, promijenite gumb na vrhu zaslona na **Uključeno**.

3. Odaberite između osvježavanja **Tjedno** (zadano) i **Dnevno**. Ako namjeravate zakazati tjedna osvježavanja, odaberite jedan ili više dana u koje želite izvesti osvježavanje.

4. Postavite vrijednost **Vremenska zona**, a zatim upotrijebite padajući izbornik **Vrijeme** kako biste postavili vrijeme osvježavanja. Kada dovršite, odaberite **Postavi**. Ako želite zakazati više osvježavanja u jednom danu, odaberite **Dodavanje drugog vremena**.

5. Odaberite **Spremi** za primjenu izmjena.

## <a name="about-tab"></a>Kartica Pojedinosti

Kartica **O programu** sadrži podatke vaše tvrtke ili ustanove **Zaslonsko ime**, aktivni **ID okruženja**, **Regiju** i **ID sesije**. Ako imate više od jednog radnog okruženja, trebali biste svakome od njih dati lako prepoznatljiv zaslonsko ime.

## <a name="general-tab"></a>Kartica Općenito

Možete promijeniti jezik i format zemlje/regije na kartici **Općenito**.

Customer Insights [podržava mnoge jezike](/dynamics365/get-started/availability). Aplikacija upotrebljava vaše jezične postavke za prikaz elemenata poput izbornika, teksta oznake te poruka sustava na željenom jeziku.

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

   Operacije koje koriste [unos podataka u](real-time-data-ingestion.md) stvarnom vremenu sadrže gumb s binokularnim simbolom za prikaz upotrebe API-ja u stvarnom vremenu. Odaberite gumb da biste otvorili bočno okno s detaljima o upotrebi API-ja u stvarnom vremenu u trenutačnom okruženju.   
   Koristite okvir **Grupiraj prema** u oknnu **Korištenje API-ja u stvarnom vremenu** da biste odabrali način kako najbolje predstaviti svoje interakcije u stvarnom vremenu. Možete grupirati podatke prema načinu rada API-ja, nazivu kvalificiranog entiteta (uvučeni entitet), kreatoru (izvor događaja), rezultatu (uspjeh ili neuspjeh) ili kodovima pogrešaka. Podaci su dostupni u vidu povijesnog grafikona i tablice.


[!INCLUDE [footer-include](includes/footer-banner.md)]
