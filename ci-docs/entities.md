---
title: Entiteti u aplikaciji Customer Insights
description: Pogledajte podatke na stranici Entiteti.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183533"
---
# <a name="entities-in-customer-insights"></a>Entiteti u aplikaciji Customer Insights

Nakon [konfiguriranja izvora podataka](data-sources.md) otvorite stranicu **Entiteti** za evaluaciju kvalitete unesenih podataka. Entiteti se smatraju skupovima podataka. Više mogućnosti servisa Dynamics 365 Customer Insights izgrađeno je oko ovih entiteta. Ako ih pažljivo pregledate, mogli biste provjeriti rezultate tih mogućnosti.

Dok radite u customer insights obogaćujući vaše podatke ili stvarajući segmente, mjere i aktivnosti, entiteti stvoreni iz tih akcija prikazuju se na **stranici Entiteti**.

## <a name="view-a-list-of-entities"></a>Prikaz popisa entiteta

Idite na **Podatkovni** > **entiteti** da biste prikazali popis entiteta. Za svaki entitet prikazuju se sljedeće informacije.

- **Naziv**: naziv podatkovnog entiteta. Ako vidite znak upozorenja pored naziva entiteta to znači da se podaci za taj entitet nisu uspješno učitali.
- **Izvor**: vrsta izvor podataka koja je progutala entitet.
- **Ažurirano**: vrijeme zadnjeg ažuriranja entiteta.
- **Stanje**: pojedinosti o posljednjem ažuriranju entiteta.

## <a name="explore-a-specific-entitys-data"></a>Istraživanje podataka određenih entiteta

1. Otvorite **Podatkovni** > **entiteti**.
1. Odaberite entitet da biste otvorili stranicu s detaljima.  
1. Istražite različita polja i zapise uključene u taj entitet.

- Kartica Atributi odabrana **je** prema zadanim postavkama i prikazuje detalje za odabrani entitet, kao što su nazivi polja, vrste podataka i vrste. Stupac **Vrsta** prikazuje povezane vrste modela uobičajenih podataka, koji automatski identificira sustav ili [ručno mapiraju](map-entities.md) korisnici. Te su vrste semantičke vrste koje se mogu razlikovati od vrsta podataka atributa. Na primjer, polje *E-pošta* u nastavku ima niz vrste *podataka,* ali njegova (semantička) vrsta uobičajenog podatkovnog modela može biti *e-pošta*, *Adresa e-pošte* ili *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tablica polja.":::

   > [!NOTE]
   > Ova stranica prikazuje samo uzorak podataka vašeg entiteta. Da biste prikazali cijeli skup podataka, idite na **stranicu Izvori** podataka, odaberite entitet, odaberite **Uredi**, a zatim prikažite podatke tog entiteta pomoću Power Query uređivača kako je objašnjeno u [izvorima](data-sources.md) podataka.

   Da biste saznali više o podacima unesenima u entitet, **stupac Sažetak** sadrži neke važne karakteristike podataka, kao što su null, vrijednosti koje nedostaju, jedinstvene vrijednosti, brojanje i distribucije, sve što se primjenjuje na vaše podatke. Odaberite ikonu grafikona za prikaz sažetka podataka.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Tablica sažetka podataka.":::

- Kartica **Podaci** prikazuje detalje o pojedinačnim zapisima entiteta. Navedeni detalji ovise o vrsti podataka entiteta.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Odaberite entitet.":::

- Kartica **Izvješća** (dostupna za neke entitete) omogućuje vizualizaciju podataka stvaranjem izvješća koje sadrži ove stupce:

  - **Naziv** izvješća: Naziv izvješća.
  - **Stvorio:** Ime osobe koja je stvorila entitet.
  - **Kreirano**: datum i vrijeme stvaranja entiteta.
  - **Uredio**: Ime osobe koja je izmijenila entitet.
  - **Uređeno**: datum i vrijeme izmjene entiteta.

## <a name="entity-specific-information"></a>Informacija za određeni entitet

Sljedeći odjeljak pruža informacije o nekim entitetima koje je stvorio sustav.

### <a name="corrupted-data-sources"></a>Oštećeni izvori podataka

Polja iz obrađenog izvora podataka mogu sadržavati oštećene podatke. Zapisi s oštećenim poljima izloženi su u entitetima koje je stvorio sustav. Poznavanje oštećenih zapisa pomaže vam identificirati koje podatke pregledati i ažurirati u izvornom sustavu. Nakon sljedećeg osvježavanja izvora podataka ispravljeni zapisi unose se u Customer Insights i prosljeđuju nizvodnim procesima. 

Na primjer, stupac 'rođendan' ima vrstu podataka postavljenu kao „datum”. U zapisu klijenta rođendan je unesen kao '01/01/19777'. Sustav će označiti ovaj zapis kao oštećen. Netko sada može promijeniti rođendan u izvornom sustavu na '1977'. Nakon automatskog osvježavanja izvora podataka polje sada ima valjani format i zapis će biti uklonjen iz oštećenog entiteta.

Idite na **Podaci** > **Entiteti** i potražite oštećene entitete u odjeljku **Sustav**. Shema imenovanja oštećenih entiteta: 'DataSourceName_EntityName_corrupt'. Odaberite oštećeni entitet da biste identifikovali oštećena polja i razlog na pojedinačnoj razini zapisa.

   :::image type="content" source="media/corruption-reason.png" alt-text="Razlog korupcije.":::

Customer Insights i dalje obrađuje oštećene zapise. Međutim, mogu uzrokovati probleme prilikom rada s objedinjenim podacima.

Sljedeće provjere izvode se na unesenim podacima kako bi se otkrili oštećeni zapisi:

- Vrijednost polja ne podudara se s vrstom podataka njegova stupca.
- Polja sadrže znakove koji uzrokuju da stupci ne odgovaraju očekivanoj shemi. Na primjer: pogrešno oblikovane ponude, neprespojne ponude ili znakovi novog retka.
- Ako postoje stupci datetime/datetime/datetimeoffset, njihov oblik mora biti naveden u modelu ako ne slijedi standardni ISO format.

[!INCLUDE [footer-include](includes/footer-banner.md)]
