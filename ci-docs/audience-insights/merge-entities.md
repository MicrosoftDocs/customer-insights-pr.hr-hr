---
title: Spajanje entiteta u objedinjavanju podataka
description: Spojite entitete da biste stvorili objedinjene profile klijenata.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 5d5ff4c6f091d1b50d0f6c8366bbe4f0e6428dac
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268493"
---
# <a name="merge-entities"></a>Spajanje entiteta

Faza spajanja zadnja je faza u procesu objedinjavanja podataka. Njezina je svrha usklađivanje zbunjujućih podataka. Primjeri sukobljenih podataka mogu uključivati ime klijenta koje se nalazi u dvama skupovima podataka, ali se malo drugačije prikazuje u svakome od njih („Grant Marshall” u odnosu na „Grant Marshal”) ili telefonski broj koji se razlikuje u obliku (617-803-091X u odnosu na 617803091X). Spajanje tih zbunjujućih podatkovnih točaka vrši se na osnovi atribut prema atributu.

Nakon dovršetka [faze uparivanja](match-entities.md) fazu spajanja možete započeti odabirom pločice **Spajanje** na stranici **Objedinjavanje**.

## <a name="review-system-recommendations"></a>Pregled preporuka sustava

Na stranici **Spajanje** možete odabrati i isključiti atribute koji će se spajati unutar vašeg objedinjenog entiteta profila klijenta (rezultat procesa konfiguracije). Sustav automatski spaja neke atribute.

### <a name="view-merged-attributes"></a>Prikaz spojenih atributa

Da biste prikazali atribute koji su uključeni u jedan od vaših automatski spojenih atributa, odaberite taj spojeni atribut. Dva atributa koja čine taj spojeni atribut prikazat će se u dva nova reda ispod spojenog atributa.

> [!div class="mx-imgBorder"]
> ![Odabir spojenog atributa](media/configure-data-merge-profile-attributes.png "Odabir spojenog atributa")

### <a name="separate-merged-attributes"></a>Odvajanje spojenih atributa

Da biste odvojili ili odspojili bilo koji od automatski spojenih atributa, pronađite atribut u tablici **Atributi profila**.

1. Odaberite gumb trotočke (...).
  
2. Na padajućem popisu odaberite **Odvoji polja**.

### <a name="remove-merged-attributes"></a>Uklanjanje spojenih atributa

Da biste atribut isključili iz konačnog entiteta profila klijenta, pronađite ga u tablici **Atributi profila**.

1. Odaberite gumb trotočke (...).
  
2. Na padajućem popisu odaberite **Nemoj spojiti**.

   Atribut je premješten u odjeljak **Uklonjeno iz zapisa klijenta**.

## <a name="manually-add-a-merged-attribute"></a>Ručno dodavanje spojenog atributa

Da biste dodali spojeni atribut, idite na stranicu **Spoji**.

1. Odaberite **Dodaj spojeni atribut**.

2. Unesite **Naziv** da biste ga kasnije identificirali na stranici **Spoji**.

3. Ako želite, unesite **Zaslonski naziv** koji će se pojaviti u objedinjenom entitetu profila klijenta.

4. Konfigurirajte **Odaberi duplicirane atribute** da biste odabrali atribute koje želite spojiti iz uparenih entiteta. Također možete tražiti atribute.

5. Postavite **Poredak po značaju** da biste dali prednost jednom atributu iznad ostalih. Na primjer, ako *WebAccountCSV* entitet uključuje najtočnije podatke o atributu *Puni nazivi*, možete dati prednost ovom entitetu iznad *ContactCSV* odabirom *WebAccountCSV*. Kao rezultat, *WebAccountCSV* prelazi na prvi prioritet, dok *ContactCSV* prelazi na drugi prioritet pri povlačenju vrijednosti za atribut *Puni naziv*.

## <a name="run-your-merge"></a>Pokretanje spajanja

Bilo da ručno spajate atribute ili da ih spaja sustav, uvijek možete pokrenuti spajanje. Odaberite **Pokreni** na stranici **Spoji** da biste pokrenuli proces.

> [!div class="mx-imgBorder"]
> ![Spremi i pokreni spajanje podataka](media/configure-data-merge-save-run.png "Spremi i pokreni spajanje podataka")

Da biste napravili dodatne promjene i ponovo pokrenuli korak, možete otkazati slaganje u tijeku. Odaberite **Osvježavanje...** i odaberite **Otkaži posao**  na bočnom oknu koje se pojavljuje.

Nakon što se tekst **Osvježavanje...** promijeni u **Uspješno**, spajanje se dovršilo i riješilo kontradikcije u podacima prema pravilima koje ste definirali. Spojeni i nespojeni atributi uključeni su u objedinjeni entitet profila. Isključeni atributi nisu uključeni u objedinjeni entitet profila.

Ako nije prvi put da ste uspješno pokrenuli spajanje, svi postupci, uključujući obogaćivanje, segmentaciju i mjere, automatski će se ponovno pokrenuti. Nakon što su se svi postupci ponovno pokrenuli, profili klijenta odražavaju sve promjene.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies). Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla. Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.

## <a name="next-step"></a>Sljedeći korak

Konfigurirajte [aktivnosti](activities.md), [obogaćivanje](enrichment-microsoft-graph.md) ili [odnose](relationships.md) za više uvida u svoje klijente.

Ako ste već konfigurirali aktivnosti, obogaćivanje ili odnose ili ako ste definirali segmente, oni će se automatski obraditi kako bi se upotrijebili najnoviji podaci o klijentima.




[!INCLUDE[footer-include](../includes/footer-banner.md)]