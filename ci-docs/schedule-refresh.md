---
title: Zakazivanje osvježavanja sustava
description: Zakazivanje vremena osvježavanja sustava
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 949ea071ca41127b0c45488d5d7af3f6aa4e1c35
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395947"
---
# <a name="schedule-system-refresh"></a>Zakazivanje osvježavanja sustava

Zakažite automatsko osvježavanje svih [unesenih izvora podataka](data-sources.md). Automatska osvježavanja pomažu osigurati da se ažuriranja iz vaših izvora podataka odražavaju na objedinjenim profilima klijenata.

> [!NOTE]
> Power Query izvore podataka kojima upravljate osvježavate prema vlastitim rasporedima. Da biste zakazali osvježavanje tih Power Query izvora podataka, konfigurirajte postavke osvježavanja na tom određenom izvor podataka sa **stranice Izvori** podataka.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Postavke osvježavanja tijeka podataka.":::

## <a name="set-system-refresh-schedule"></a>Postavljanje rasporeda osvježavanja sustava

1. Otvorite **Administratorski** > **sustav** i odaberite karticu **Raspored**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Zakazivanje kartice osvježavanja sa stranice Sustav.":::

1. Zadano je stanje za zakazano osvježavanje **Isključeno**. Da biste omogućili zakazana osvježavanja, promijenite gumb na vrhu zaslona na **Uključeno**.

1. Odaberite između osvježavanja **Tjedno** (zadano) i **Dnevno**. Ako namjeravate zakazati tjedna osvježavanja, odaberite jedan ili više dana u koje želite izvesti osvježavanje.

1. Postavite vrijednost **Vremenska zona**, a zatim upotrijebite padajući izbornik **Vrijeme** kako biste postavili vrijeme osvježavanja. Ako želite zakazati više osvježavanja u jednom danu, odaberite **Dodavanje drugog vremena**. Možete dodati do četiri osvježavanja.

1. Odaberite **Spremi** za primjenu izmjena.

[!INCLUDE [footer-include](includes/footer-banner.md)]