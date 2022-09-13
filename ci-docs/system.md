---
title: Prikaz konfiguracije sustava
description: Saznajte više o postavkama sustava u sustavu Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 6e60bf7c18939a29f660e06989e262deeb59a39b
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395992"
---
# <a name="view-system-configuration"></a>Prikaz konfiguracije sustava

Prikažite informacije o sustavu, stanje sustava i korištenje API-ja.

## <a name="view-api-usage"></a>Prikaz korištenja API-ja

Pregledajte detalje o korištenju API-ja u stvarnom vremenu i pogledajte koji su se događaji dogodili u određenom vremenski okvir.

1. Otvorite **Administratorski** > **sustav** i odaberite karticu **Korištenje** API-ja.

1. **Odaberite vremenski okvir** za prikaz.

   Stranica za **korištenje** API-ja sadrži tri odjeljka:

   - **Pozivi API-ja** – grafikon koji prikazuje skupni broj poziva API-ju u odabranom vremenskom okviru.
   - **Prijenos podataka** – grafikon koji prikazuje količinu podataka koja je prenesena putem API-ja u odabranom vremenskom okviru.
   - **Operacije** – tablica s recima za svaku dostupnu operaciju API-ja i pojedinostima o korištenju operacija. Odaberite naziv operacije da biste prešli na [referencu](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) API-ja.

## <a name="view-system-information"></a>Prikaz informacija o sustavu

Prikažite zaslonsko ime okruženja, ID-a, regije, vrste i ID-a sesije.

1. Otvorite **Administratorski** > **sustav** i odaberite karticu **O programu**.

1. Da biste prikazali jezik i državu/regiju, odaberite karticu **Općenito**.

### <a name="update-preferred-language-or-countryregion"></a>Ažuriranje preferiranog jezika ili države/regije

Customer Insights [podržava mnoge jezike](/dynamics365/get-started/availability). Aplikacija upotrebljava vaše jezične postavke za prikaz elemenata poput izbornika, teksta oznake te poruka sustava na željenom jeziku.

Uvezeni podaci i informacije koje ste ručno unijeli se ne prevode.

1. Otvorite **Administratorski** > **sustav** i odaberite karticu **Općenito**.

1. Da biste promijenili željeni jezik, odaberite **Jezik** s padajućeg izbornika.

1. Da biste promijenili željeno oblikovanje za datum, vrijeme i brojeve, koristite padajući izbornik **Oblik države/regije**. Prikazuje se pretpregled oblikovanja. Sustav automatski predlaže odabir kada odaberete novi jezik.

1. Odaberite **Spremi**.

## <a name="view-system-status"></a>Prikaz statusa sustava

Pratite napredak zadataka, unos podataka, izvoz podataka i nekoliko drugih važnih procesa proizvoda. Pregledajte informacije kako biste osigurali potpunost aktivnih zadataka i procesa.

1. Otvorite **Administratorski** > **sustav** i odaberite karticu **Stanje**.

   Prikaz stanja i obrade informacija za različite procese. **Prikažite naziv** zadatka, **stanje** njegovog zadnjeg izvođenja i kada je **zadnji put ažuriran**.

1. Da biste vidjeli detalje posljednjih nekoliko pokretanja, odaberite naziv zadatka ili procesa.

1. Da biste vidjeli detalje o napretku zadatka, odaberite status. Prikazuje se **okno s detaljima o** napretku.

   :::image type="content" source="media/system-progress-details.png" alt-text="Okno s detaljima o tijeku sustava":::

1. Da biste prikazali detalje o napretku za sve zadatke, odaberite **Cijeli tijek rada**.

### <a name="status-definitions"></a>Definicije stanja

Sustav za zadatke i procese koristi sljedeće statuse:

|Stanje  |Definicija  |
|---------|---------|
|Otkazano |Korisnik je otkazao zadatak ili proces prije dovršetka.   |
|Neuspjelo   |Zadatak ili proces naišli su na pogreške.         |
|Nije uspjelo  |Zadatak ili proces nisu uspjeli.  |
|Nije pokrenuto   |Izvor podataka još nema unesenih podataka ili je zadatak još uvijek u načinu skice.         |
|Obrada u tijeku  |Zadatak ili proces su u tijeku.  |
|Osvježavanje    |Zadatak ili proces su u tijeku. Da biste prekinuli ovu operaciju, odaberite **Zadatak** osvježavanja **i** otkazivanja. Zaustavljanje osvježavanja zadatka ili procesa vratit će ga u posljednje stanje osvježavanja.       |
|Preskočeno  |Zadatak ili proces su preskočeni. Jedan ili više postupaka u nastavku o kojima ovaj zadatak ovisi nisu uspjeli ili su preskočeni.|
|Uspješno  |Zadatak ili proces uspješno su dovršeni. Za izvore podataka označava da su podaci uspješno uneseni ako je u stupcu **Osvježeno** navedeno vrijeme.|
|U redu čekanja | Obrada je u redu čekanja i započet će nakon dovršetka svih uzlaznih zadataka i procesa. Dodatne informacije potražite u članku [Osvježi procese](#refresh-processes).|

### <a name="refresh-processes"></a>Procesi osvježavanja

Osvježavanje zadataka i procesa pokreće se prema konfiguriranom [rasporedu](schedule-refresh.md).

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
