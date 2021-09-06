---
title: Entiteti i skupovi podataka
description: Pogledajte podatke na stranici Entiteti.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 137de726b243b501491fcbe7866820aaee26097fcf379270c423c277374ae9a4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033806"
---
# <a name="entities-in-audience-insights"></a>Entiteti u uvidima u ciljnu skupinu

Nakon [konfiguriranja izvora podataka](data-sources.md) otvorite stranicu **Entiteti** za evaluaciju kvalitete unesenih podataka. Entiteti se smatraju skupovima podataka. Više mogućnosti servisa Dynamics 365 Customer Insights izgrađeno je oko ovih entiteta. Ako ih pažljivo pregledate, mogli biste provjeriti rezultate tih mogućnosti.

Stranica **Entiteti** navodi entitete i uključuje nekoliko stupaca:

- **Naziv**: naziv entiteta podatka. Ako vidite znak upozorenja pored naziva entiteta to znači da se podaci za taj entitet nisu uspješno učitali.
- **Izvor**: vrsta izvora podataka koji su uneseni za entitet
- **Autor**: ime osobe koja je izradila entitet
- **Izrađeno**: datum i vrijeme izrade entiteta
- **Ažurirao**: ime osobe koja je ažurirala entitet
- **Posljednji put ažurirano**: datum i vrijeme posljednjeg ažuriranja entiteta
- **Posljednji put osvježeno**: datum i vrijeme posljednjeg osvježavanja podataka

## <a name="explore-a-specific-entitys-data"></a>Istraživanje podataka određenih entiteta

Odaberite entitet za istraživanje različitih polja i zapisa koji su uključeni u taj entitet.

> [!div class="mx-imgBorder"]
> ![Odaberite entitet.](media/data-manager-entities-data.png "Odabir entiteta")

- Kartica **Podaci** prikazuje tablicu s popisom pojedinosti o pojedinačnim zapisima entiteta.

> [!div class="mx-imgBorder"]
> ![Tablica polja.](media/data-manager-entities-fields.PNG "Tablica polja")

- Kartica **Atributi** je odabrana prema zadanim postavkama i prikazuje tablicu za pregled pojedinosti za odabrani entitet, kao što su nazivi polja, vrste podataka i vrste. Stupac **Vrsta** prikazuje povezane vrste modela uobičajenih podataka, koji automatski identificira sustav ili [ručno mapiraju](map-entities.md) korisnici. Te su vrste semantičke vrste koje se mogu razlikovati od vrsta podataka atributa. Na primjer, polje *E -pošta* u nastavku ima vrstu podataka *Tekst*, ali bi njegova (semantička) vrsta Common Data Model mogla biti *E -pošta* ili *Adresa e-pošte*.

> [!NOTE]
> Obje tablice prikazuju samo uzorak podataka entiteta. Za prikaz cijelog skupa podataka idite na stranicu **Izvori podataka**, odaberite entitet, nakon toga **Uredi** i zatim pregledajte podatke tog entiteta uz pomoć alata za uređivanje Power Query, kao što je objašnjeno u poglavlju [Izvori podataka](data-sources.md).

Da biste saznali više o podacima koji su uneseni u entitet, stupac **Sažetak** pruža vam neke važne karakteristike podataka, kao što su nule, vrijednosti koje nedostaju, brojevi i distribucije, kako je primjenjivo za vaše podatke.

Odaberite ikonu grafikona za prikaz sažetka podataka.

> [!div class="mx-imgBorder"]
> ![Simbol sažetka.](media/data-manager-entities-summary.png "Tablica sažetka podataka")

## <a name="entity-specific-information"></a>Informacija za određeni entitet

Sljedeći odjeljak pruža informacije o nekim entitetima koje je stvorio sustav.

### <a name="corrupted-data-sources"></a>Oštećeni izvori podataka

Polja iz obrađenog izvora podataka mogu sadržavati oštećene podatke. Zapisi s oštećenim poljima izloženi su u entitetima koje je stvorio sustav. Poznavanje oštećenih zapisa pomaže vam identificirati koje podatke pregledati i ažurirati u izvornom sustavu. Nakon sljedećeg osvježavanja izvora podataka ispravljeni zapisi unose se u Customer Insights i prosljeđuju nizvodnim procesima. 

Na primjer, stupac 'rođendan' ima vrstu podataka postavljenu kao „datum”. U zapisu klijenta rođendan je unesen kao '01/01/19777'. Sustav će označiti ovaj zapis kao oštećen. Netko sada može promijeniti rođendan u izvornom sustavu na '1977'. Nakon automatskog osvježavanja izvora podataka polje sada ima valjani format i zapis će biti uklonjen iz oštećenog entiteta. 

Idite na **Podaci** > **Entiteti** i potražite oštećene entitete u odjeljku **Sustav**. Shema imenovanja oštećenih entiteta: 'DataSourceName_EntityName_corrupt'.

Customer Insights i dalje obrađuje oštećene zapise. Međutim, mogu uzrokovati probleme prilikom rada s objedinjenim podacima.

Sljedeće provjere izvode se na unesenim podacima kako bi se otkrili oštećeni zapisi: 

- Vrijednost polja ne podudara se s vrstom podataka njegova stupca.
- Polja sadrže znakove koji uzrokuju da stupci ne odgovaraju očekivanoj shemi. Na primjer: pogrešno oblikovane ponude, neprespojne ponude ili znakovi novog retka.
- Ako postoje stupci datetime/date/datetimeoffset, njihov format treba navesti u modelu ako ne slijedi standardni ISO format.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
