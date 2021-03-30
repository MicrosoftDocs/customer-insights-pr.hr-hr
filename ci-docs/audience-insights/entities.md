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
ms.openlocfilehash: 383523bad5105e08e57758838e90a49e805b5f9b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596398"
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

## <a name="exploring-a-specific-entitys-data"></a>Istraživanje podataka određenog entiteta

Odaberite entitet za istraživanje različitih polja i zapisa koji su uključeni u taj entitet.

> [!div class="mx-imgBorder"]
> ![Odaberite entitet](media/data-manager-entities-data.png "Odaberite entitet")

- Kartica **Podaci** odabrana je prema zadanim postavkama i prikazuje tablicu s detaljima o pojedinačnim zapisima o entitetu.

> [!div class="mx-imgBorder"]
> ![Tablica polja](media/data-manager-entities-fields.PNG "Tablica polja")

- Kartica **Polja** prikazuje tablicu za pregled detalja za odabrani entitet, kao što su nazivi polja, vrste podataka i vrste. Stupac **Vrsta** prikazuje povezane vrste modela uobičajenih podataka, koji automatski identificira sustav ili [ručno mapiraju](map-entities.md) korisnici. To su semantičke vrste koje se mogu razlikovati ovisno o vrstama podataka atributa – primjerice polje *E-pošta* u nastavku ima vrstu podataka *Tekst*, ali njegova (semantička) vrsta modela uobičajenih podataka može biti *E-pošta* ili *Adresa e-pošte*.

> [!NOTE]
> Obje tablice prikazuju samo uzorak podataka entiteta. Za prikaz cijelog skupa podataka idite na stranicu **Izvori podataka**, odaberite entitet, nakon toga **Uredi** i zatim pregledajte podatke tog entiteta uz pomoć alata za uređivanje Power Query, kao što je objašnjeno u poglavlju [Izvori podataka](data-sources.md).

Da biste saznali više o podacima koji su uneseni u entitet, stupac **Sažetak** pruža vam neke važne karakteristike podataka, kao što su nule, vrijednosti koje nedostaju, brojevi i distribucije, kako je primjenjivo za vaše podatke.

Odaberite ikonu grafikona za prikaz sažetka podataka.

> [!div class="mx-imgBorder"]
> ![Simbol sažetka](media/data-manager-entities-summary.png "Tablica sažetka podataka")

### <a name="next-step"></a>Sljedeći korak

Pogledajte temu [Ujedinjavanje](data-unification.md) da biste saznali kako *mapirati*, *upariti* i *spojiti* unesene podatke.


[!INCLUDE[footer-include](../includes/footer-banner.md)]