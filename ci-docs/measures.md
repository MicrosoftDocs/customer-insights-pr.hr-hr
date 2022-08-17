---
title: Pregled mjera
description: Saznajte kako mjere pomažu u analizi i odražavanju uspješnosti vašeg poslovanja.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245364"
---
# <a name="measures-overview"></a>Pregled mjera

Mjere vam pomažu da bolje razumijete ponašanja klijenata i poslovne performanse. Gledaju na relevantne vrijednosti iz [objedinjenih profila](data-unification.md). Na primjer poduzeće želi vidjeti *ukupnu potrošnju po kupcu* za razumijevanje povijesti kupca pojedinog kupca ili mjerenje *ukupne prodaje društva* kako bi se razumio ukupni prihod u cijelom poslovanju.

Stvorite mjere za planiranje poslovnih aktivnosti pretraživanjem podataka o klijentima i izdvajanjem uvida. Na primjer, stvorite mjeru ukupne potrošnje po kupcu *i* ukupnog povrata *po kupcu* kako biste lakše identificirali grupu kupaca s visokom potrošnjom, ali visokim povratom. [Zatim stvorite segment](segments.md) na temelju tih mjera kako biste pokrenuli sljedeće najbolje akcije.

## <a name="create-a-measure"></a>Izrada mjere

Odaberite način stvaranja mjere na temelju ciljnog publika.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- Od nule s sastavljačem mjera: [Izgradite vlastiti](measure-builder.md).
- Od najčešće korištenih mjera: [koristite unaprijed definirane predloške](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

Od nule s sastavljačem mjera: [Izgradite vlastiti](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Upravljanje postojećim mjerama

Idite na **stranicu Mjere** da biste vidjeli mjere koje ste stvorili, njihov status, vrstu mjere i posljednji put kada su podaci osvježeni. Popis mjera možete sortirati po bilo kojem stupcu ili pomoću okvira za pretraživanje pronaći mjeru kojom želite upravljati.

Odaberite pokraj mjere da biste vidjeli dostupne akcije. Odaberite naziv mjere za pretpregled izlaza i preuzmite CSV datoteku.

:::image type="content" source="media/measures-actions.png" alt-text="Radnje za upravljanje jedinstvenim mjerama."lightbox="media/measures-actions.png":::

- **Uredite** mjeru da biste promijenili njezina svojstva.
- **Osvježite** mjeru tako da uključuje najnovije podatke.
- Odaberite **Preimenuj** mjeru.
- **Aktiviranje** ili **deaktiviranje** mjere. Neaktivne mjere neće se osvježiti tijekom zakazanog [osvježavanja](schedule-refresh.md) i status je **naveden** kao **Preskočen**, što znači da osvježavanje nije ni pokušano.
- **Oznaka** za [upravljanje oznakama](work-with-tags-columns.md#manage-tags) za mjeru.
- Odaberite **Izbriši** mjeru.
- **Stupci** za [prilagodbu stupaca](work-with-tags-columns.md#customize-columns) koji se prikazuju.
- **Filtrirajte** za filtriranje [na strukturnim oznakama](work-with-tags-columns.md#filter-on-tags).
- **Naziv** za pretraživanje radi pretraživanja po nazivu mjere.

## <a name="refresh-measures"></a>Mjere osvježavanja

Mjere se mogu osvježiti prema automatskom rasporedu ili ručno osvježiti na zahtjev. Da biste ručno osvježili jednu ili više mjera, odaberite ih i odaberite **Osvježi**. Da biste [zakazali automatsko osvježavanje](schedule-refresh.md), idite na **Raspored** > **administratorskih** > **sustava**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
