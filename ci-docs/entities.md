---
title: Entiteti u aplikaciji Customer Insights
description: Pogledajte podatke na stranici Entiteti.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610089"
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

[!INCLUDE [footer-include](includes/footer-banner.md)]
