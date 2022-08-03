---
title: Izvoz segmenata u Iterable (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ccf10b6e3a28a75f9d1bd3d8da3bf870ebc2b1b2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195420"
---
# <a name="export-segments-to-iterable-preview"></a>Izvoz segmenata u Iterable (pretpregled)

Izvezite segmente jedinstvenih profila kupaca u Iterable i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduvjeti

- Račun [koji](https://iterable.com/) se može iterirati i odgovarajuće administratorske vjerodajnice.
- API ključ koji [se može iterirati](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Konfigurirani segmenti](segments.md) u customer insights.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milijun korisničkih profila za Iterable, što može potrajati i do 30 minuta. Broj korisničkih profila koje možete izvesti u Iterable ovisi o vašem ugovoru s programom Iterable.
- Samo segmenti.

## <a name="set-up-connection-to-iterable"></a>Postavljanje veze s programom Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Iterable**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite svoj API ključ koji se može iterirati da biste se nastavili prijavljivati.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** da biste inicijalizirali vezu.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. **U polju Veza za izvoz** odaberite vezu iz odjeljka Iterable ( Iterable). Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. Popis kreiran u programu Iterable dobit će potpuno isti naziv kao i naziv vašeg segmenta u sustavu Dynamics 365 Customer Insights.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
