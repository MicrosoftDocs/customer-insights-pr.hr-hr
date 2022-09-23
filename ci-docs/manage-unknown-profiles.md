---
title: Upravljanje nepoznatim profilima pomoću uvida u klijenta
description: Rad s nepoznatim profilima klijenata koji su kreirani i kojima se upravlja u sustavu Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: d7e5050ee5832df5ecf40a352f7ea8d42830fa45
ms.sourcegitcommit: f6b6a4c4ce9cf12e449488b24aab80a2cbfe0c47
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/21/2022
ms.locfileid: "9556387"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Upravljanje nepoznatim profilima pomoću uvida u klijenta

Korisnici Interneta često su neidentificirani i anonimni na mreži. Ako nisu prijavljeni jer koriste različite uređaje ili kanale, to vrijedi čak i za najvjernije kupce. Budući da kolačići trećih strana vjerojatno uskoro nestaju, upravljanje korisničkim preferencijama na temelju podataka prve strane ključno je za postizanje diferenciranih personaliziranih iskustava. Za mnoge marke poznati ili autentificirani korisnici su manjina unatoč rastućim očekivanjima kupaca oko personalizacije. Izvrsno je da tvrtke znaju tko su njihovi kupci na temelju pouzdanih, detaljnih i jedinstvenih podataka.

Nezaboravna personalizacija ovisi o bogatstvu i cjelovitosti vaših korisničkih podataka, a Customer Insights pomaže vam u postizanju tih ciljeva. Ne morate ograničavati ili zaustavljati upotrebu podataka prikupljenih na početku put klijenta. Customer Insights omogućuje vam da donesete vlastite podatke kako biste stvorili korisnički profil za nepoznate korisnike. Zatim taj profil možete koristiti za daljnje radnje, unatoč tome što nedostaju podaci za kontakt. Uvezite podatke prve strane iz izvora kao što su web, mobilni ili CRM sustavi u Customer Insights kako biste kontinuirano obogaćivali profile kupaca. Kako objedinjujete više interakcija, [pretvorite nepoznatog *kupca* u poznatog *kupca*](unknown-to-known.md).

## <a name="sample-scenario"></a>Ogledni scenarij

E-trgovina je najbrže rastući kanal u posljednjem desetljeću. Pretpostavimo da korisnik koristi svoj mobilni uređaj za pregledavanje vaše web-lokacije za e-trgovinu. Web stranica posjetitelju dodjeljuje "mobile_guest123" kao jedinstveni identifikator i počinjete prikupljati aktivnosti ponašanja na temelju njihove mrežne aktivnosti. Na primjer, koje su stranice posjetili, koliko su vremena proveli na tim stranicama ili koje su veze kliknuli. Ne znate njihovo ime ili adresu e-pošte, ali ti podaci mogu pomoći u pružanju smislenih uvida robnim markama o tom određenom korisniku. S druge strane, te uvide možete staviti na posao sljedeći put kada korisnik posjeti web mjesto. Upitajte Customer Insights za "mobile_guest123" kako biste dohvatili popis segmenata korisnika, kao što su "organski", "korisnici mobilnih predbilježbi", "kupci visoke vrijednosti" itd., ili dohvatili profil za stvaranje personaliziranih web iskustava. Također možete izvesti podatke u bilo koji sustav aktivacije da biste učinili isto.

## <a name="prerequisites"></a>Preduvjeti

- Unos podataka prve strane u Uvide kupaca
- Svaki entitet ima jedinstveni ID koji je postavljen kao primarni ključ
- Svaki entitet s primarnim ključem za personalizaciju je ujedinjen
- Sustav upravljanja sadržajem vaše web stranice sposoban je koristiti API-je (za web personalizaciju temeljenu na izravnoj komunikaciji s Customer Insights)

Sljedeća tablica prikazuje pojednostavljeni primjer kako se web-događaji visoke vrijednosti mogu snimiti.

|ID događaja|EventTimeStamp|ID korisnika|Primarni ključ|Naziv događaja|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Prikaz proizvoda|
|2|09-18-2022 10:05:00|abc123|CookieID1|Prikaz proizvoda|
|3|09-18-2022 10:10:00|abc123|CookieID1|Dodaj u košaricu|
|4|09-21-2022 09:05:00|abc123|CookieID1|Prikaz proizvoda|

## <a name="data-ingestion"></a>Obrada podataka

Dodatne informacije o dostupnim mogućnostima gutanja podataka potražite u članku [Pregled izvora podataka](data-sources.md).

## <a name="data-unification"></a>Objedinjavanje podataka

Dodatne informacije o objedinjavanju profila korisnika potražite u članku [Pregled](data-unification.md) ujedinjenja podataka.

## <a name="get-insights"></a>Nabavi uvide

[Obogatite](enrichment-hub.md) svoje podatke, izradite [mjere](measures.md) i stvorite [segmente](segments.md) za daljnju aktivaciju.

Na primjer, možete stvoriti segmente nepoznatih korisnika koji su pregledavali iste stranice proizvoda, ali nikada nisu dovršili naplatu.

## <a name="activation"></a>Aktivacija

Sa svojim podacima u customer insights i vašim uvidima spremnim za početak rada, možete koristiti Customer Insights za personalizaciju:

1. [Korištenje OData API-ja](apis.md) za dohvaćanje članstva u segmentu ili korisničkog profila Za više primjera pogledajte [primjere upita OData za API-je customer insights](odata-examples.md).

1. [Izvezite](export-destinations.md) svoje podatke u aktivacijske sustave.

Primjer: nepoznati korisnik više puta posjećuje web stranicu i posjećuje stranice proizvoda za različite modele kožnih cipela. S tim podacima dostupnim u Customer Insights, nepoznatog korisnika možete uključiti u segment ljudi koji su zainteresirani za kožne cipele. Koristite ovaj segment kako biste informirali personalizaciju izrade web stranice za posjetitelje koji se vraćaju. Prilikom sljedećeg posjeta stranica prepoznaje nepoznatog korisnika i mogla bi im ponuditi 10% kupona na kožnim cipelama.

[!INCLUDE [footer-include](includes/footer-banner.md)]
