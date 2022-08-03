---
title: Izvoz segmenata u Microsoftovo oglašavanje (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Microsoftovo oglašavanje.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196523"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Izvoz segmenata u Microsoftovo oglašavanje (pretpregled)

Izvezite segmente usluge Customer Insights u Microsoftovo oglašavanje da biste stvorili ciljne skupine Podudaranje klijenta. Upotrijebite ove ciljne skupine za svoje reklamne kampanje.

## <a name="prerequisites"></a>Preduvjeti

- Račun [za Microsoftovo oglašavanje](https://ads.microsoft.com/) i odgovarajuće administratorske vjerodajnice.
- Microsoft Advertising Korisnički ID i ID računa. Pronađite ID klijenta (`cid`) i ID računa (`aid`) u parametrima URL-a kada ste prijavljeni u Microsoft Advertising.
- Prihvaćaju se uvjeti korištenja Customer Match.
- [Konfigurirani segmenti](segments.md) u customer insights.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 500 000 korisničkih profila po izvozu u Microsoft Advertising, što može potrajati i do 10 minuta.
- Samo segmenti.

## <a name="set-up-connection-to-microsoft-advertising"></a>Postavljanje veze s Microsoftovim oglašavanjem

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Microsoftovo oglašavanje**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Zadana postavka su administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Unesite Microsoft Advertising Customer ID**.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** da biste inicijalizirali vezu.

1. Odaberite **Provjeri autentičnost uz Microsoftovo oglašavanje** i pružite svoje administratorske vjerodajnice za Microsoftovo oglašavanje.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Microsoftovo oglašavanje. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. Odaberite segmente za izvoz. Ciljne skupine Podudaranje klijenata u Microsoftovom oglašavanju stvaraju se automatski s nazivom segmenata odabranih za izvoz. Svaki će segment rezultirati zasebnom ciljnom skupinom Podudaranje klijenata.

1. Unesite svoj **ID klijenta Microsoftova oglašavanja i ID računa**.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje s adresom e-pošte klijenta.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
