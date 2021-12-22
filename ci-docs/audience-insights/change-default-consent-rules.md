---
title: Upravljanje zadanim pravilima pristanka za segmente
description: Pomoću mogućnosti upravljanja pristankom možete onemogućiti ili promijeniti zadana pravila pristanka ako su omogućena poništenja.
ms.date: 12/01/2021
ms.service: customer-insights
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28c9ea49b1f3aebd3abd7d4de58fe61e6474158b
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884161"
---
# <a name="disable-or-change-default-consent-rules"></a>Onemogućivanje ili promjena zadanih pravila pristanka

Ako vaša tvrtka ili ustanova koristi [mogućnost upravljanja](../consent-management/overview.md) pristankom u kombinaciji s publika uvidima, [administratori mogu nametnuti pravila](activate-consent.md) pristanka za segmente. 

Uz provedena pravila o suglasnosti u području segmenta, svaki segment informira o stanju provjere suglasnosti i pravila. Ako su dopuštena nadjačavanja, pravila zadanog pristanka isključena su za određene segmente. Svaki autor segmenta segmentu može dodati više pravila o pristanku povrh zadanih pravila. 

## <a name="for-administrators"></a>Za administratore

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Sastavljač segmenata s mogućnostima pravila pristanka.":::

**Da biste deaktivirali zadana pravila o pristanku:**

1. U **obavijesti o pravilima** suglasnosti odaberite **Pogledaj detalje**. 

1. Postavite **preklopni gumb Zadana pravila** pristanka na **Isključeno**.

**Da biste dodali još pravila o pristanku:**

1. U **obavijesti o pravilima** suglasnosti odaberite **Pogledaj detalje**. 

1. Odaberite **Dodaj pravila** pristanka i odaberite pravilo privole na **padajućem izborniku Odabir vrste podataka** pristanka.

1. Odaberite **Spremi da biste novo pravilo** primijenili na segment.

## <a name="for-contributors"></a>Za suradnike

Da biste stvorili segment bez nametnutih pravila pristanka, morate surađivati s administratorom da biste ih onemogućili u segmentu. Međutim, možete dodati vlastita pravila pristanka segmentima koje posjedujete i kojima upravljate.

To je proces u tri koraka: 
1. [Stvorite segment](segments.md) u publika uvidima i spremite ga. 

1. Podijelite naziv segmenta s administratorom i zatražite da [omogući poništenja za vaš segment](activate-consent.md). 

1. Ponovno otvorite segmente. U **obavijesti o pravilima** pristanka odaberite **Pogledajte detalje** i dodajte pravila o pristanku koja želite primijeniti. Zatim **spremite** i **pokrenite** segment.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
