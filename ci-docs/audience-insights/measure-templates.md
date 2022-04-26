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
ms.openlocfilehash: eeabd889f7b694f8d809894169a3cdc068acc340
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529392"
---
# <a name="use-a-template-to-build-a-measure"></a>Korištenje predloška za izradu mjera

Za njihovo stvaranje možete koristiti unaprijed definirane predloške najčešće korištenih [mjera](measures.md). Detaljni opisi predložaka i vođeno iskustvo pomažu vam u učinkovitom stvaranju mjera. Predlošci se nadovezuju na mapirane podatke iz entiteta *Objedinjena aktivnost*. Stoga provjerite jeste li konfigurirali [aktivnosti klijenata](activities.md) prije nego što stvorite mjeru iz predloška.

Upute za stvaranje prilagođenih mjera potražite u članku [Stvaranje mjera pomoću sastavljača mjera od nule](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

Dostupni predlošci mjera: 
- Prosječna vrijednost transakcije (ATV)
- Ukupna vrijednost transakcije
- Prosječni dnevni prihod
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

1. U odjeljku **Postavi vremensko razdoblje** definirajte vremenski okvir podataka koji će se koristiti. Odaberite želite li da nova mjera pokriva cijeli skup podataka odabirom **Cijelo vrijeme** ili ako želite da se mjera usredotoči na **Određeno vremensko razdoblje**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Snimka zaslona koja prikazuje odjeljak vremenskog razdoblja prilikom konfiguriranja mjere iz predloška.":::

1. U sljedećem odjeljku odaberite **Dodaj podatke** za odabir aktivnosti i mapiranje odgovarajućih podataka iz vašeg entiteta *Objedinjena aktivnost*.

    1. Korak 1 od 2: Pod **Vrsta aktivnosti** odaberite vrstu entiteta koju želite koristiti. Za **Aktivnosti** odaberite entitete koje želite mapirati.
    1. Korak 2 od 2: Odaberite atribut iz entiteta *Objedinjena aktivnost* za komponentu koju zahtijeva formula. Na primjer, za Prosječna vrijednost transakcije to je atribut koji predstavlja vrijednost Transakcije. Za **Vremenska oznaka aktivnosti** odaberite atribut iz entiteta Objedinjena aktivnost koji predstavlja datum i vrijeme aktivnosti.
   
1. Nakon što mapiranje podataka bude uspješno, možete vidjeti status kao **Dovršeno** te naziv mapiranih aktivnosti i atributa.

1. Sada možete odabrati **Pokreni** za izračunavanje rezultata mjere. Da biste je kasnije pročistili, odaberite **Spremi nacrt**.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

Ova je značajka dostupna samo za mjere stvorene u okruženjima s pojedinačnim klijentima kao primarnom ciljnom skupinom.

---
