---
title: Upravljanje zadanim pravilima pristanka na segmentima
description: Uz mogućnost upravljanja pristankom možete onemogućiti ili promijeniti zadana pravila pristanka ako su omogućena poništenja.
ms.date: 12/01/2021
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 43f03ea97765e112a8ea2a7da97cc548c8c84dfc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642242"
---
# <a name="disable-or-change-default-consent-rules"></a>Onemogućivanje ili promjena zadanih pravila pristanka

Ako vaša organizacija koristi [mogućnost](consent-management/overview.md) upravljanja pristankom s programom Dynamics 365 Customer Insights, [administratori mogu provoditi pravila](activate-consent.md) pristanka za segmente. 

Uz nametnuta pravila o suglasnosti u području segmenta, svaki segment obavještava o stanju provjere suglasnosti i pravilima. Ako su dopuštena poništenja, zadana pravila pristanka isključuju se za određene segmente. Svaki autor segmenta može dodati više pravila pristanka povrh zadanih pravila segmentu. 

## <a name="for-administrators"></a>Za administratore

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Sastavljač segmenata s mogućnostima pravila pristanka.":::

**Da biste deaktivirali zadana pravila pristanka:**

1. U obavijesti o **pravilima** pristanka odaberite **Pogledajte detalje**. 

1. Postavite prebacivanje zadanih **pravila** pristanka na **Isključeno**.

**Da biste dodali dodatna pravila o pristanku:**

1. U obavijesti o **pravilima** pristanka odaberite **Pogledajte detalje**. 

1. Odaberite **Dodaj pravila** pristanka i odaberite pravilo pristanka na **padajućem izborniku Odabir vrste** podataka pristanak.

1. Odaberite **Spremi** da biste primijenili novo pravilo na segment.

## <a name="for-contributors"></a>Za suradnike

Da biste stvorili segment bez nametnutih pravila pristanka, morate surađivati sa svojim administratorom da biste ga onemogućili u svom segmentu. Međutim, možete dodati vlastita pravila pristanka segmentima koje posjedujete i kojima upravljate.

To je proces u tri koraka: 
1. [Stvorite segment](segments.md) u customer insights i spremite ga. 

1. Podijelite naziv segmenta s administratorom i zatražite od njega da [omogući poništenja za vaš segment](activate-consent.md). 

1. Ponovno otvorite segmente. **U obavijesti o pravilima** pristanka odaberite **Pogledajte detalje** i dodajte pravila pristanka koja želite primijeniti. Zatim spremite **i** **pokrenite** svoj segment.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
