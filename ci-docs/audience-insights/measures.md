---
title: Razumijevanje mjera i upravljanje njima
description: Saznajte kako mjere pomažu u analizi i odražavanja rezultata vaše tvrtke.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359764"
---
# <a name="measures-overview"></a>Pregled mjera

Mjere vam pomažu da bolje razumijete ponašanja klijenata i poslovne performanse. Gledaju na relevantne vrijednosti iz [objedinjenih profila](data-unification.md). Na primjer poduzeće želi vidjeti *ukupnu potrošnju po kupcu* za razumijevanje povijesti kupca pojedinog kupca ili mjerenje *ukupne prodaje društva* kako bi se razumio ukupni prihod u cijelom poslovanju.  

Mjere se stvaraju [pomoću sastavljača](measure-builder.md) mjera, platforme za podatkovne upite s različitim operatorima i jednostavnim mogućnostima mapiranja. Omogućuje vam filtriranje podataka, grupiranje rezultata, otkrivanje [putanja odnosa entiteta](relationships.md) i pretpregled izlazne vrijednosti. Unaprijed definirane predloške [možete](measure-templates.md) koristiti za učinkovito konfiguriranje najčešće korištenih mjera.

Koristite alat za izradu mjera za planiranje poslovnih aktivnosti ispitivanjem podataka o klijentima i izvozom uvida. Na primjer, stvaranje mjere *ukupna potrošnja po klijentu* i *ukupan povrat po klijentu* pomaže identificirati grupu klijenata s visokom potrošnjom, ali i visokim povratom. Segment možete [kreirati na temelju](segments.md) tih mjera da biste potaknuli sljedeće najbolje akcije. 

## <a name="manage-your-measures"></a>Upravljanje mjerama

Popis mjera možete pronaći na stranici **Mjere**.

Pronaći ćete informacije o vrsti mjere, autoru, datumu stvaranja, statusu i stanju. Kada odaberete mjeru s popisa, možete pretpregledati izlaz i preuzeti CSV datoteku.

Da biste istovremeno osvježili sve svoje mjere, odaberite **Osvježi sve** bez odabiranja određene mjere.

:::image type="content" source="media/measure-actions.png" alt-text="Radnje za upravljanje jedinstvenim mjerama.":::

Odaberite mjeru s popisa za sljedeće mogućnosti:

- Odaberite naziv mjere da biste vidjeli njezine pojedinosti.
- Odaberite **Uredi** konfiguraciju mjere.
- **Osvježi** mjeru na temelju najnovijih podataka.
- Odaberite **Preimenuj** mjeru.
- Odaberite **Izbriši** mjeru.
- **Aktiviraj** ili **Deaktiviraj**. Neaktivne mjere neće se osvježavati tijekom [zakazanog osvježavanja](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Sljedeći korak

Možete koristiti postojeće mjere za stvaranje [segmenta klijenta](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
