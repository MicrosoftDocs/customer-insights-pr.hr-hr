---
title: Izvoz segmenata u Campaign Monitor (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196293"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Izvoz segmenata u Campaign Monitor (pretpregled)

Izvezite segmente objedinjenih profila klijenata u Campaign Monitor i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduvjeti

- Račun [nadzora](https://www.campaignmonitor.com/) kampanje i odgovarajuće administratorske vjerodajnice.
- [ID popisa nadzornika kampanje](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Generirani [API ključ](https://www.campaignmonitor.com/api/getting-started/) iz **postavki** računa u nadzoru kampanje za dobivanje ID-ja popisa API-ja.
- [Konfigurirani segmenti](segments.md) u customer insights.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milijun profila kupaca po izvozu u Campaign Monitor, što može potrajati i do 20 minuta. Broj profila kupaca koje možete izvesti u nadzor kampanje ovisi o ugovoru s nadzorom kampanje.
- Samo segmenti.

## <a name="set-up-connection-to-campaign-monitor"></a>Postavljanje veze s Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Nadzor** kampanje.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** za inicijalizaciju veze s Campaign Monitor.

1. Odaberite **Provjeri autentičnost uz Campaign Monitor** i pružite svoje administratorske vjerodajnice za Campaign Monitor.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, ddaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Campaign Monitor. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. **Unesite ID** popisa nadzornika kampanje.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. Obavezno je izvoziti segmente u Campaign Monitor.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
