---
title: Aktivnosti klijenta
description: Definirajte aktivnosti klijenta i prikažite ih na vremenskoj traci na profilima klijenata.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188130"
---
# <a name="customer-activities"></a>Aktivnosti klijenta

Aktivnosti kupaca su akcije ili događaji koje izvode kupci. Na primjer, transakcije, trajanje poziva za podršku, recenzije web stranice, kupnje ili povrati. Te su aktivnosti sadržane u jednom ili više izvora podataka. Uz Customer Insights objedinite svoje aktivnosti kupaca iz tih [izvora](data-sources.md) podataka i povežite ih s profilima kupaca. Te se aktivnosti pojavljuju kronološki u vremenskoj traci na profilu kupca. Uključite vremensku traku u aplikacije sustava Dynamics 365 pomoću [rješenja](customer-card-add-in.md) za dodatak Kartica kupca.

## <a name="define-an-activity"></a>Definiranje aktivnosti

Entitet mora imati barem jedan atribut vrste **Datum** da bi bio uključen u vremensku traku klijenta. Kontrola **Dodaj aktivnost** onemogućena je ako nije pronađen takav entitet.

1. Otvorite **Podatkovne** > **aktivnosti**.

1. Odaberite **Dodaj aktivnost** da biste započeli vođeno iskustvo.

1. U koraku **s podacima o** aktivnosti unesite sljedeće podatke:

   - **Naziv** aktivnosti: naziv vaše aktivnosti.
   - **Entitet** aktivnosti: entitet koji uključuje podatke o transakcijama ili aktivnostima.
   - **Primarni ključ**: polje koje jedinstveno identificira zapis. Ne smije sadržavati duplicirane vrijednosti, prazne vrijednosti ili vrijednosti koje nedostaju.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Postavite podatke o aktivnosti s nazivom, entitetom i primarnim ključem.":::

1. Odaberite **Dalje**.

1. U koraku **Odnos** odaberite **Dodaj odnos** da biste povezali podatke o aktivnostima s odgovarajućim zapisom o klijentu. Ovaj korak vizualizira vezu među entitetima.  

   - **Vanjski ključ iz entiteta**: polje u entitetu aktivnosti koje će se koristiti za uspostavljanje odnosa s drugim entitetom.
   - **Naziv entiteta**: Odgovarajući izvorni klijentski entitet s kojim će vaš entitet aktivnosti biti u odnosu. Možete se odnositi samo na izvorne entitete klijenata koji se koriste u procesu objedinjavanja podataka.
   - **Naziv** odnosa: Naziv koji identificira odnos između entiteta. Ako odnos između ovog entiteta aktivnosti i odabranog izvornog entiteta klijenta već postoji, naziv odnosa je samo za čitanje.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definirajte odnos entiteta.":::

   > [!TIP]
   > U B2B okruženjima možete birati između entiteta računa i ostalih entiteta. Ako odaberete entitet računa, automatski se postavlja putanja odnosa. Za druge entitete morate definirati putanju odnosa preko jednog ili više posrednih entiteta dok ne dođete do entiteta računa.

1. Odaberite **Primijeni** da biste stvorili odnos.

1. Odaberite **Dalje**.

1. U koraku **Objedinjavanje aktivnosti** odaberite događaj aktivnosti i vrijeme početka svoje aktivnosti.
   - **Obvezna polja**
      - **Aktivnost događaja**: Polje koje je događaj za ovu aktivnost.
      - **Vremenska oznaka**: Polje koje predstavlja vrijeme početka vaše aktivnosti.

   - **Neobvezna polja**
      - **Dodatna pojedinost**: Polje s relevantnim informacijama za ovu aktivnost.
      - **Ikona**: Ikona koja najbolje predstavlja ovu vrstu aktivnosti.
      - **Web-adresa**: Polje koje sadrži URL s informacijama o ovoj aktivnosti. Na primjer, transakcijski sustav iz kojega je potekla ova aktivnost. Ovaj URL može biti bilo koje polje iz izvor podataka ili se može konstruirati kao novo polje pomoću transformacije Power Query. Podaci o URL-u bit će pohranjeni u entitetu *Objedinjena aktivnost* koji se može konzumirati prema dolje pomoću [API-ja](apis.md).

   - **Prikaži na vremenskoj traci**
      - Odaberite želite li prikazati tu aktivnost na prikazu vremenske trake profila klijenta. Odaberite **Da** za prikaz aktivnosti na vremenskoj traci ili **Ne** za sakrivanje.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Navedite podatke o aktivnostima klijenta u entitetu Objedinjene aktivnosti.":::

1. Odaberite **Dalje** da biste odabrali vrstu aktivnosti ili Odaberite **Završi i pregledaj** da biste spremili aktivnost s vrstom aktivnosti postavljenom na **Ostalo**.

1. U koraku **Vrsta aktivnosti** odaberite vrstu aktivnosti i neobavezno odaberite želite li semantički mapirati neke od vrsta aktivnosti za korištenje u ostalim područjima Customer Insights. Trenutno, vrste aktivnosti povratnih informacija *,* *lojalnosti* *, salesoradera*, *salesorderlinea* i *pretplate* podržavaju semantiku nakon što pristanu na mapiranje polja. Ako vrsta aktivnosti nije relevantna za novu aktivnost, možete odabrati *Ostalo* ili *Stvori novo* za prilagođenu vrstu aktivnosti.

1. Odaberite **Dalje**.

1. U koraku **Pregled** provjerite svoje odabire. Vratite se na bilo koji od prethodnih koraka i ažurirajte podatke ako je potrebno.

1. Odaberite **Spremi aktivnost** da biste primijenili promjene i odaberite **Gotovo** da biste se vratili na **Podaci** > **Aktivnosti**. Prikazana je stvorena aktivnost.

1. Nakon stvaranja svih aktivnosti odaberite **Pokreni** da biste ih obradili.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Upravljanje postojećim aktivnostima

Idite na **Podatkovne** > **aktivnosti** da biste vidjeli spremljene aktivnosti, njihov izvorni entitet, vrstu aktivnosti i ako su uključene u vremensku traku klijenta. Popis aktivnosti možete sortirati po bilo kojem stupcu ili pomoću okvira za pretraživanje pronaći aktivnost kojom želite upravljati.

Odaberite aktivnost za prikaz dostupnih akcija.

- **Uredite** aktivnost da biste promijenili njezinu konfiguraciju. Konfiguracija se otvara u koraku pregleda. Nakon promjene konfiguracije odaberite **Spremi aktivnost**, a zatim odaberite **Pokreni** za obradu promjena.
- **Preimenujte** aktivnost. Odaberite **Spremi** za primjenu izmjena.
- **Izbrišite** aktivnost. Da biste izbrisali više aktivnosti odjednom, odaberite aktivnosti, a zatim **izbrišite**. Potvrdite brisanje.

## <a name="view-activity-timelines-on-customer-profiles"></a>Prikaz vremenskih traka aktivnosti na profilima klijenata

1. Ako ste u konfiguraciji aktivnosti odabrali **Prikaži vremensku traku** aktivnosti, idite na **Kupci i odaberite profil kupca** da biste vidjeli aktivnosti klijenta u odjeljku Vremenska **traka** Aktivnost.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Pregledajte konfigurirane aktivnosti u profilima klijenata.":::

1. Da biste filtrirali aktivnosti na vremenskoj traci aktivnosti:

   - Odaberite jednu ili više ikona aktivnosti da biste suzili rezultate tako da sadrže samo odabrane vrste.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrirajte aktivnosti prema vrsti s pomoću ikona.":::

   - Odaberite **Filtar** da biste otvorili ploču filtra da biste konfigurirali filtre vremenske trake. Filtrirajte prema *ActivityType* i/ili *Datumu*. Odaberite **Primijeni**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="S pomoću panela filtra konfigurirajte uvjete filtra.":::

1. Da biste uklonili filtre, odaberite **Očisti filtre** ili Potvrdite okvir **Filtriraj** i poništite okvir filtra.

> [!NOTE]
> Filtri aktivnosti uklanjaju se kada napustite profil klijenta. Morate ih primijeniti svaki put kada otvorite profil kupca.

[!INCLUDE [footer-include](includes/footer-banner.md)]
