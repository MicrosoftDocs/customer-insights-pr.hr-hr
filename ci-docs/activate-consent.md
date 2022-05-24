---
title: Aktiviranje pravila pristanka za segmente
description: Slijedite ove korake kako biste povezali podatke o pristanku i aktivirali prijave privole Dynamics 365 Customer Insights. Administrator također može onemogućiti provjere pristanka.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755161"
---
# <a name="activate-consent-rules"></a>Aktiviranje pravila pristanka

Centar [za pristanak (pregled)](consent-management/overview.md) pomaže vam u usklađivanju podataka o pristanku iz različitih izvora. Upotrijebite jedinstveni *entitet privola* za primjenu zadanih provjera privole. Nakon uvoza podataka o pristanku i konfiguriranja pravila karte, *entitet Pristanak* automatski se sinkronizira sa sustavom Dynamics 365 Customer Insights.

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
