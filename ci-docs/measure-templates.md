---
title: Stvaranje mjera iz predložaka
description: Definirajte mjere pomoću predložaka za slučajeve uobičajene uporabe.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170764"
---
# <a name="create-measures-from-templates"></a>Stvaranje mjera iz predložaka

Za njihovo stvaranje koristite unaprijed definirane predloške najčešće korištenih [mjera](measures.md). Predlošci se nadovezuju na mapirane podatke iz entiteta *Objedinjena aktivnost*. Stoga provjerite jeste li konfigurirali [aktivnosti klijenata](activities.md) prije nego što stvorite mjeru iz predloška.

Predlošci mjera podržani su samo u okruženjima za **pojedinačne kupce**. Upute za stvaranje prilagođenih mjera ili stvaranje mjera za B-do-B potražite u članku [Korištenje sastavljača mjera](measure-builder.md).

Dostupni predlošci mjera:
- Prosječna vrijednost transakcije (ATV)
- Ukupna vrijednost transakcije
- Prosječni dnevni prihod
- Prosječni mjesečni prihod
- Prosječni godišnji prihod
- Broj transakcija
- Zarađeni bodovi vjernosti
- Iskorišteni bodovi vjernosti
- Bilanca stanja bodova vjernosti
- Životni vijek aktivnog klijenta
- Trajanje članstva u programu vjernosti
- Vrijeme od zadnje kupnje

## <a name="build-a-new-measure-using-a-template"></a>Stvaranje nove mjere pomoću predloška

1. Idite na **Mjere**.

1. Odaberite **Novo**, a zatim odaberite **Odaberi predložak**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Snimka zaslona padajućeg izbornika prilikom izrade nove mjere s istaknutim predloškom.":::

1. Pronađite predložak koji odgovara vašim potrebama i odaberite **Odaberi predložak**.

1. Pregledajte potrebne podatke i odaberite **Započni** ako imate sve podatke na mjestu.

1. Uz **stavku Naziv mjere odaberite Uredi detalje**. Navedite naziv mjere. Po želji dodajte [oznake](work-with-tags-columns.md#manage-tags) mjeri.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dijaloški okvir Uređivanje detalja.":::

1. Odaberite **Gotovo**.

1. U sekciji **Postavljanje vremenskog razdoblja** definirajte vremenski okvir podataka. Odaberite želite li da nova mjera pokriva cijeli skup podataka odabirom **Cijelo vrijeme** ili ako želite da se mjera usredotoči na **Određeno vremensko razdoblje**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Snimka zaslona koja prikazuje odjeljak vremenskog razdoblja prilikom konfiguriranja mjere iz predloška.":::

1. U sljedećem odjeljku odaberite **Dodaj podatke** za odabir aktivnosti i mapiranje odgovarajućih podataka iz vašeg entiteta *Objedinjena aktivnost*.

    1. Korak 1 od 2: Pod **Vrsta aktivnosti** odaberite vrstu entiteta koju želite koristiti. U odjeljku **Aktivnosti odaberite entitete koje želite mapirati, a zatim dalje** **.**
    1. Korak 2 od 2: Odaberite atribut iz entiteta *Objedinjena aktivnost* za komponentu koju zahtijeva formula. Na primjer, za Prosječna vrijednost transakcije to je atribut koji predstavlja vrijednost Transakcije. Za **vremensku oznaku** aktivnosti odaberite atribut iz entiteta *Objedinjena aktivnost* koji predstavlja datum i vrijeme aktivnosti.
    1. Odaberite **Spremi**.

    Kada je mapiranje podataka uspješno, status prikazuje **Dovršeno** i prikaz naziva mapiranih aktivnosti i atributa.

1. Odaberite **Pokreni** da biste izračunali rezultate mjere. Odaberite **Spremi skicu** ako želite zadržati trenutnu konfiguraciju i kasnije pokrenuti mjeru. Prikazuje se **stranica Mjere**.

## <a name="next-step"></a>Sljedeći korak

Koristite postojeće mjere da biste kreirali [segment kupca](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
