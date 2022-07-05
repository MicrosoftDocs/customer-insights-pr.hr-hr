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
ms.openlocfilehash: 880c06bffcfa269151d96cb4c597eed4832fc61b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083117"
---
# <a name="measures-overview"></a>Pregled mjera

Mjere vam pomažu da bolje razumijete ponašanja klijenata i poslovne performanse. Gledaju na relevantne vrijednosti iz [objedinjenih profila](data-unification.md). Na primjer poduzeće želi vidjeti *ukupnu potrošnju po kupcu* za razumijevanje povijesti kupca pojedinog kupca ili mjerenje *ukupne prodaje društva* kako bi se razumio ukupni prihod u cijelom poslovanju.  

Mjere se stvaraju [pomoću sastavljača](measure-builder.md) mjera, platforme za podatkovne upite s različitim operatorima i jednostavnim mogućnostima mapiranja. Omogućuje vam filtriranje podataka, grupiranje rezultata, otkrivanje [putanja odnosa entiteta](relationships.md) i pretpregled izlazne vrijednosti. Unaprijed definirane predloške [možete](measure-templates.md) koristiti za učinkovito konfiguriranje najčešće korištenih mjera.

Koristite alat za izradu mjera za planiranje poslovnih aktivnosti ispitivanjem podataka o klijentima i izvozom uvida. Na primjer, stvaranje mjere *ukupna potrošnja po klijentu* i *ukupan povrat po klijentu* pomaže identificirati grupu klijenata s visokom potrošnjom, ali i visokim povratom. Na temelju tih mjera možete [kreirati segment](segments.md) za pokretanje sljedećih najboljih akcija.

## <a name="manage-your-measures"></a>Upravljanje mjerama

Popis mjera možete pronaći na stranici **Mjere**.

Pronaći ćete informacije o vrsti mjere, autoru, datumu stvaranja, statusu i stanju. Kada odaberete mjeru s popisa, možete pretpregledati izlaz i preuzeti CSV datoteku.

:::image type="content" source="media/measures-actions.png" alt-text="Radnje za upravljanje jedinstvenim mjerama."lightbox="media/measures-actions.png":::

Kada odaberete mjeru, dostupne su sljedeće akcije:

- Odaberite **Uredi** konfiguraciju mjere.
- **Dupliciranje** mjere. Možete odmah urediti njegova svojstva ili jednostavno spremiti duplikat.
- **Osvježi** mjeru na temelju najnovijih podataka. Da biste istovremeno osvježili sve mjere, odaberite sve mjere, a zatim **Osvježi**.
- Odaberite **Preimenuj** mjeru.
- **Aktiviraj** ili **Deaktiviraj**. Neaktivne mjere neće se osvježavati tijekom [zakazanog osvježavanja](system.md#schedule-tab).
- **Oznaka** za [upravljanje strukturnim oznakama](work-with-tags-columns.md#manage-tags) za segment.
- Odaberite **Izbriši** mjeru.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Sljedeći korak

Možete koristiti postojeće mjere za stvaranje [segmenta klijenta](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
