---
title: Personalizirajte svoja iskustva podacima o poznatim i nepoznatim korisnicima
description: Uključite podatke o ranije nepoznatim korisnicima kada znate njihov identitet.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: ff99721bef0004bc8cae1ec14ff9df16cbb0682e
ms.sourcegitcommit: ece8ff732490ecd3b3421ab273f331e6fd46a7f7
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/19/2022
ms.locfileid: "9173813"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Personalizirajte svoja iskustva podacima o poznatim i nepoznatim korisnicima

Upravljanje podacima o kupcima nije novi izazov, ali postaje sve teže kako se korisnici kreću raznim ponudama robnih marki digitalnih kanala. Korisnik koji je poznat (autentificiran) na jednom kanalu postaje nepoznat (neprovjeren) u drugom ako nije prijavljen. Problem je često u tome što neprovjereni (nepoznati) korisnici nemaju zajednički ID. Može se koristiti za povezivanje značajnih atributa profila i generiranje jedinstvenih profila kupaca. Customer Insights pomaže u rješavanju ovog problema unoseći podatke iz metoda praćenja na izvornim sustavima. Konsolidirani nepoznati i poznati profili pružaju organizacijama potpuni prikaz ažurnih profila i njihovih povijesnih transakcija, ponašanja i demografskih podataka. Čak ide korak dalje pružajući razlučivost identiteta koja vam omogućuje objedinjavanje aktivnosti kupaca na više kanala, uključujući vašu web stranicu, kupnju u trgovini, programe vjernosti itd.

## <a name="sample-scenario"></a>Primjer scenarija

Razmislimo o lancu kave, koji ima široku bazu kupaca koja kupuje kavu i hranu u trgovinama i naručuje proizvode putem interneta. Često se internetskim posjetiteljima ne provjerava autentičnost prilikom pregledavanja proizvoda, što ih čini "nepoznatim korisnicima". Lancu kave teško je isporučiti personalizirane ponude i iskustva ako su korisnici nepoznati. S druge strane, kupci se mogu prijaviti na svoj račun i postati "poznati korisnici" tvrtke pridruživanjem sustavu vjernosti, što zauzvrat omogućuje personaliziranija iskustva. Customer Insights može pomoći lancu kave da dobije uvid u poznate i dosad nepoznate korisnike.

Uz Customer Insights, tvrtka može kombinirati korisničke profile s podacima o aktivnostima iz neprovjerenih (nepoznatih) sesija nakon što se korisnik prijavi i postane poznat. Lanac kave može donijeti podatke iz drugih izvora podataka pomoću ugrađenih konektora u Customer Insights za spajanje identiteta za kupce s različitih kanala.

## <a name="prerequisites"></a>Preduvjeti

- Web podaci se prikupljaju i sadrže "ID-ove posjetitelja" za sve posjetitelje.
- Web-podaci sadrže "provjerene korisničke ID-ove" za prijavljene posjetitelje. Ove osobne iskaznice povezane su sa sustavom vjernosti.
- Podaci o događajima visoke vrijednosti kao što su "Prikaz proizvoda" i "Odjava" definirani su i uključeni u izvorišne podatke zajedno s vremenskom oznakom događaja i ID-om događaja.

Sljedeća tablica prikazuje pojednostavljeni primjer kako se web-događaji visoke vrijednosti mogu snimiti.

|ID događaja|EventTimeStamp|ID korisnika|ID Lojalnosti|Naziv događaja|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Prikaz proizvoda|
|2|07-23-2022 10:05:00|abc123|707|Prijava lojalnosti|
|3|07-23-2022 10:10:00|abc123|707|Završetak plaćanja|
|4|07-23-2022 10:20:00|xyz789|--|Prikaz proizvoda|

## <a name="data-ingestion"></a>Obrada podataka

Podaci o korisnicima mogu potjecati s vaše web stranice kao podaci o događajima i mogu se pohraniti u vašim internim ili trećim uslugama analitike podataka. Web-podaci sadrže poznate i nepoznate korisnike ako web-mjesto ima tijek provjere autentičnosti koji se integrira s uslugom provjere autentičnosti. Na primjer, sustav e-trgovine koji zahtijeva od korisnika da dostave svoje potpune podatke kako bi dovršili transakciju kupnje. Ili sustav vjernosti koji zahtijeva provjeru autentičnosti kako bi potvrdio valjanog primatelja popusta na nagrade.

Podaci o događaju u našem gornjem primjeru sadrže različite ID-ove profila poznatih i nepoznatih korisnika. U slučaju 1 i 4 korisnici su nepoznati dok se u slučaju 2 i 3 korisnik s ID-om abc123 prijavljuje na program vjernosti.

:::image type="content" source="media/website-data-source.png" alt-text="Izvori podataka, uključujući web stranicu Contoso.":::

Dodatne informacije o dostupnim mogućnostima gutanja podataka potražite u članku [Pregled izvora podataka](data-sources.md).

## <a name="data-unification"></a>Objedinjavanje podataka

Konvergencija nepoznatih identiteta s poznatim identitetima pomaže u omogućavanju personalizacije na temelju ponašanja korisnika, bez obzira na njihovo stanje profila (poznato ili nepoznato). Personalizirani sadržaj za sve korisnike pomaže korisnicima da brzo dođu do najrelevantnijih proizvoda ili usluga koji ih u tom trenutku zanimaju.

Budući da su neki od korisnika u našim podacima poznati, možemo koristiti Customer Insights za kombiniranje tih podataka s korisničkim profilom. Dodatne informacije o objedinjavanju profila korisnika potražite u članku [Pregled ujedinjenja podataka](data-unification.md).

1. Odaberite izvorišna polja iz entiteta web-podataka. Koristite podatke profila pohranjene u vašim web-podacima i odaberite polja koja predstavljaju ID-ove s demografskim podacima.

   :::image type="content" source="media/website-source-fields.png" alt-text="Izvorišna polja za web-izvor podataka.":::

1. Dodajte pravila za spajanje dupliciranih zapisa. Za web-podatke odaberite najpotpunjenije podatke.

1. Konfigurirajte pravila i uvjete podudaranja. Podaci događaja web-profila u ovom primjeru podudarat će se na ID-ovima s profilima iz drugih izvora podataka koji sadrže podatke o kupcu. Postavite pravila točnog podudaranja na ID-ovima kao zasebna pravila sa svakim od ostalih entiteta profila koji imaju odgovarajući primarni ključ ili podudaranje ID-a. U primjeru se podaci profila web-događaja koriste kao posljednji podudarni entitet tako da se prvo kombiniraju drugi podaci profila.
   1. Ne provjeravaj **Uključi sve zapise** stvara jedinstvene profile za poznate korisnike i uključuje njihove odgovarajuće nepoznate korisničke ID-ove. Korisno je u scenarijima kada ste zainteresirani za pregled prošlih aktivnosti ponašanja poznatih korisnika dok su još bili nepoznati.
   1. Provjerom **Uključi sve zapise** stvara se zasebni zapisi profila za nepoznate korisnike. Nepoznati korisnici dobivaju jedinstveni ID klijenta. U budućnosti kada je poznati profil povezan s podacima profila web događaja, tada se putovanje novo poznatog korisnika može pregledati i koristiti za personalizaciju na temelju prošlih nepoznatih podataka o ponašanju.

:::image type="content" source="media/website-match-rule.png" alt-text="Pravilo podudaranja za web-mjesto izvor podataka entitet.":::

## <a name="get-insights"></a>Nabavi uvide

Ako su profili korisnika stvoreni za nepoznate i poznate korisnike, podaci web-događaja visoke vrijednosti mogu se koristiti kao [aktivnosti](activities.md). Te se aktivnosti mogu koristiti za stvaranje više uvida. Na primjer, korisnici koji su posjetili web stranicu prije šest mjeseci (dok su još bili nepoznati) ili korisnici koji nemaju ID vjernosti nikada nisu dovršili naplatu.

:::image type="content" source="media/website-known-unknown.png" alt-text="Snimka zaslona stranice kupca s poznatim i nepoznatim kupcima.":::

[Obogatite](enrichment-hub.md) svoje podatke, izradite [mjere](measures.md) i stvorite [segmente](segments.md) za daljnju aktivaciju.

Na primjer, možete stvoriti segmente poznatih korisnika koji su pregledali neke proizvode, ali nikada nisu dovršili naplatu.

Dodatne informacije potražite u odjeljku [Pregled](segments.md) segmenata.

## <a name="activate-insights"></a>Aktiviranje uvida

Postoji nekoliko načina za izvoz podataka i poduzimanje radnji na temelju temeljnih uvida.

Dodatne informacije potražite u članku [Pregled](export-destinations.md) izvoza.
