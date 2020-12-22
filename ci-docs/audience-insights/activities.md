---
title: Aktivnosti klijenta
description: Definirajte aktivnosti kupaca i pregledajte ih na vremenskoj traci klijenta.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667220"
---
# <a name="customer-activities"></a>Aktivnosti klijenta

Kombinirajte aktivnosti klijenata iz [raznih izvora podataka](data-sources.md) u značajci Dynamics 365 Customer Insights kako biste stvorili vremensku crtu klijenta koja navodi aktivnosti kronološkim redoslijedom. Vremensku traku možete dodati u aplikacije Customer Engagement u sustavu Dynamics 365 putem [dodatka za korisničku karticu](customer-card-add-in.md) ili na nadzornoj ploči usluge Power BI.

## <a name="define-an-activity"></a>Definiranje aktivnosti

Vaši izvori podataka uključuju entitete s podacima o transakcijama i aktivnostima iz više izvora. Identificirajte te entitete i odaberite aktivnosti koje želite prikazati na vremenskoj traci klijenta. Odaberite entitet koji uključuje vašu ciljanu aktivnost ili aktivnosti.

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Aktivnosti**.

1. Odaberite **Dodaj aktivnost**.

   > [!NOTE]
   > Entitet mora imati najmanje jedan atribut vrste **Datum** da bi se uključio u vremensku traku klijenta i ne možete dodavati entitete bez polja **Datum**. Kontrola **Dodaj aktivnost** onemogućena je ako nije pronađen takav entitet.

1. U oknu **Dodavanje aktivnosti** okno postavite vrijednosti za sljedeća polja:

   - **Entitet**: odaberite entitet koji uključuje podatke o transakcijama ili aktivnostima.
   - **Primarni ključ**: odaberite polje koje jedinstveno identificira zapis. Ne smije sadržavati duplicirane vrijednosti, prazne vrijednosti ili vrijednosti koje nedostaju.
   - **Vremenska oznaka**: odaberite polje koje predstavlja vrijeme početka vaše aktivnosti.
   - **Događaj**: odaberite polje koje je događaj za aktivnost.
   - **Web-adresa**: Odaberite polje koje predstavlja URL koji pruža dodatne informacije o ovoj aktivnosti. Na primjer, transakcijski sustav iz kojega je potekla ova aktivnost. Ovaj URL može biti bilo koje polje iz izvora podataka ili se može konstruirati kao novo polje s pomoću transformacije Power Query. Podaci ovog URL-a bit će pohranjeni u entitetu Jedinstvena aktivnost, koji se može koristiti nizvodno pomoću API-ja.
   - **Pojedinosti**: prema želji odaberite polje koje se dodaje za dodatne pojedinosti.
   - **Ikona**: prema želji odaberite ikonu koja predstavlja navedenu aktivnost.
   - **Vrsta aktivnosti**: Definirajte referencu vrste aktivnosti prema modelu Common Data Model koji najbolje opisuje semantičku definiciju aktivnosti.

1. U odjeljku **Postavi odnos** konfigurirajte pojedinosti da biste povezali podatke o aktivnosti s odgovarajućim klijentom.

   > [!div class="mx-imgBorder"]
   > ![Definiranje odnosa entiteta](media/activities-entities-define.png "Definiranje odnosa entiteta")

    - **Polje entiteta aktivnosti**: odaberite polje u svojem entitetu aktivnosti koje će se koristiti za uspostavljanje odnosa s drugim entitetom.
    - **Entitet klijenta**: odaberite odgovarajući izvorni entitet klijenta s kojim će entitet aktivnosti biti u odnosu. Možete se povezati samo s onim izvornim entitetima klijenta koji se koriste u postupku objedinjavanja podataka.
    - **Polje entiteta klijenta**: ovo polje pokazuje primarni ključ izvornog entiteta klijenta kao odabranog u postupku mapiranja. Ovo polje primarnog ključa u izvornom entitetu klijenta koristi se za uspostavljanje odnosa s entitetom aktivnosti.
    - **Naziv**: ako odnos između ovog entiteta aktivnosti i odabranog izvornog entiteta klijenta već postoji, naziv odnosa bit će u načinu rada samo za čitanje. Ako takav odnos ne postoji, stvorit će se novi odnos s ovdje navedenim nazivom.

1. Odaberite **Spremi** za primjenu izmjena.

1. Na stranici **Aktivnosti** odaberite **Pokreni**.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies). Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla. Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.

## <a name="edit-an-activity"></a>Uređivanje aktivnosti

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Aktivnosti**.

2. Odaberite entitet aktivnosti koji želite urediti i odaberite **Uredi**. Ili možete držati pokazivač iznad retka entiteta i odabrati ikonu **Uredi**.

3. Kliknite na ikonu **Uredi**.

4. U oknu **Uređivanje aktivnosti** ažurirajte vrijednosti i odaberite **Spremi**.

5. Na stranici **Aktivnosti** odaberite **Pokreni**.

## <a name="delete-an-activity"></a>Brisanje aktivnosti

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Aktivnosti**.

2. Odaberite entitet aktivnosti koji želite ukloniti i odaberite **Izbriši**. Ili možete držati pokazivač iznad retka entiteta i odabrati ikonu **Izbriši**. Usto možete odabrati više entiteta aktivnosti koje ćete istovremeno izbrisati.
   > [!div class="mx-imgBorder"]
   > ![Uređivanje ili brisanje odnosa među entitetima](media/activities-entities-edit-delete.png "Uređivanje ili brisanje odnosa među entitetima")

3. Odaberite ikonu **Izbriši**.

4. Potvrdite brisanje.
