---
title: Aktiviranje pravila pristanka za segmente
description: Slijedite ove korake da biste povezali podatke o pristanku i aktivirali provjere pristanka u publika uvidima. Administrator također može onemogućiti provjere pristanka.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 45899738d39bd5caa433e123f9fe59020e831998
ms.sourcegitcommit: 79b09498d1328e5551fb8684c44af1fb149f9881
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7815889"
---
# <a name="activate-consent-rules"></a>Aktiviranje pravila pristanka

[Centar za pristanak (pretpregled) pomaže vam](../consent-management/overview.md) uskladiti podatke o pristanku iz različitih izvora. Koristite entitet jedinstveni *pristanak* za primjenu zadanih provjera pristanka. Nakon uvoza podataka o suglasnosti u Centar za pristanak i konfiguriranja pravila za podatke, *entitet Pristanak automatski se sinkronizira s publika* uvidima.

## <a name="enable-consent-checks"></a>Omogući provjere pristanka

Uz podatke o pristanku uvezene u Centar za pristanak (pregled) i postavljena pravila, možete omogućiti provjere pristanka. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Kartica Pristanak u publika postavke uvida s aktiviranim podacima o pristanku.":::

1. U uvidima u ciljnu skupinu idite na **Administrator** > **Sustav**.

1. Odaberite **karticu Pristanak** (pretpregled).

1. U **odjeljku Omogući provjere** pristanka postavite preklopni gumb **Uključeno za sva područja koja** želite omogućiti.

1. Potvrdite **okvir Dopusti poništenje zadanih pravila pristanka** da biste uklonili zadane provjere privole koje se provode na određenom segmentu. 

1. Na padajućem izborniku odaberite mjesto na kojem želite dopustiti poništenja.     

1. U **odjeljku Privola veze na profile** korisnika odaberite atribut koji se koristi kao identifikator za povezivanje podataka o pristanku s korisničkim podacima. To će vjerojatno biti telefonski broj ili adresa e-pošte. 

1. Odaberite **Spremi** da biste primijenili postavke.

## <a name="disable-consent-checks"></a>Onemogući provjere pristanka

Da bi prestao koristiti podatke o pristanku u publika uvidima, administrator mora ažurirati postavke sustava u skladu s tim.

1. U uvidima u ciljnu skupinu idite na **Administrator** > **Sustav**.

1. Odaberite **karticu Pristanak** (pretpregled).

1. U **odjeljku Omogući provjere** pristanka postavite preklopni gumb na **Isključeno**.
