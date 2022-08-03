---
title: Izvoz segmenata u MoEngage
description: Saznajte kako konfigurirati vezu i izvesti u MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199188"
---
# <a name="export-segments-to-moengage-preview"></a>Izvoz segmenata u MoEngage (pretpregled)

Izvezite segmente jedinstvenih profila kupaca u MoEngage i koristite ih za marketing putem e-pošte u MoEngageu.

## <a name="prerequisites-for-a-connection"></a>Preduvjeti za vezu

- [MoEngage račun](https://www.moengage.com/) i odgovarajuće administratorske vjerodajnice.
- MoEngage API ključ iz settings > API u MoEngageu.
- [Konfigurirani segmenti](segments.md) u customer insights.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 100'000 korisničkih profila po izvozu u MoEngage, što može potrajati i do 15 minuta. Broj korisničkih profila koje možete izvesti u MoEngage ovisi o vašem ugovoru s tvrtkom MoEngage.
- Samo segmenti.

## <a name="set-up-connection-to-moengage"></a>Postavljanje veze s MoEngageom

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **MoEngage** da biste konfigurirali vezu.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj [MoEngage Data API ID i API ključ](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** se da biste inicijalizirali vezu s tvrtkom MoEngage.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, ddaberite **Dodaj izvoz**.

1. **U polju Veza za izvoz** odaberite vezu iz odjeljka MoEngage. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. Ponovite iste korake za druga neobavezna polja.

1. Odaberite segmente koje želite izvesti. Stvorit ćemo jedan ili više segmenata s istim nazivom kao i odabrani segmenti u odjeljku MoEngage u odjeljku **Segmenti** > **prilagođenih segmenata**.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
