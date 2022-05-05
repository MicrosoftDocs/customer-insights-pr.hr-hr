---
title: Aktiviranje pravila pristanka za segmente
description: Slijedite ove korake kako biste povezali podatke o pristanku i aktivirali prijave privole Dynamics 365 Customer Insights. Administrator također može onemogućiti provjere pristanka.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bfa03f4b7b56b300a74ebd04721cd64b893879f1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642222"
---
# <a name="activate-consent-rules"></a>Aktiviranje pravila pristanka

Centar [za pristanak (pregled)](consent-management/overview.md) pomaže vam u usklađivanju podataka o pristanku iz različitih izvora. Upotrijebite jedinstveni *entitet privola* za primjenu zadanih provjera privole. Nakon uvoza podataka o pristanku u Centar za pristanak i konfiguriranja pravila za podatke, *entitet Privola* automatski se sinkronizira sa sustavom Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Omogući provjere pristanka

Uz podatke o pristanku uvezene u Centar za pristanak (pretpregled) i postavljena pravila možete omogućiti provjere pristanka. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Kartica Pristanak u postavkama customer insights s aktiviranim podacima o pristanku.":::

1. U aplikaciji Customer Insights idite na **Administrator** > **Sustav**.

1. Odaberite karticu **Privola (pretpregled).**

1. **U odjeljku Omogući provjere** pristanka postavite prekidač na **Uključeno** za sva područja koja želite omogućiti.

1. **Potvrdite okvir Dopusti nadjačavanje zadanih pravila** pristanka da biste uklonili zadane provjere pristanka koje se provode na određenom segmentu. 

1. Na padajućem izborniku odaberite mjesto na kojem želite dopustiti poništenja.     

1. U odjeljku Poveži **pristanak na korisničke** profile odaberite atribut koji se koristi kao identifikator za povezivanje podataka o pristanku s podacima o kupcima. To će vjerojatno biti telefonski broj ili adresa e-pošte. 

1. Odaberite **Spremi** da biste primijenili postavke.

## <a name="disable-consent-checks"></a>Onemogući provjere pristanka

Da bi prestao koristiti podatke o pristanku u Customer Insights, administrator mora u skladu s tim ažurirati postavke sustava.

1. U aplikaciji Customer Insights idite na **Administrator** > **Sustav**.

1. Odaberite karticu **Privola (pretpregled).**

1. **U odjeljku Omogući provjere** pristanka postavite prekidač na **Isključeno**.

> [!TIP]
> Da biste prestali koristiti mogućnost upravljanja pristankom, pročitajte članak [Postavke sustava u centru za pristanak (pretpregled)](consent-management/system-settings.md).
