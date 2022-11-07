---
title: Izvoz segmenata u Klaviyo (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Klaviyo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 075e6758f2c6992a1185756f9beecf852fdd0a96
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724571"
---
# <a name="export-segments-to-klaviyo-preview"></a>Izvoz segmenata u Klaviyo (pretpregled)

Izvezite segmente objedinjenih profila kupaca u Klaviyo i upotrijebite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduvjeti

- [Klaviyo račun](https://www.klaviyo.com/) i odgovarajuće administratorske vjerodajnice.
- Klaviyo [API ključ](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- ID [Klaviyo liste](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [Konfigurirani segmenti](segments.md) u customer insights.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Privatna veza u kombinaciji s Donesite vlastitu pohranu (BYOS) nije podržana.
- Do milijun profila kupaca po izvozu u Klaviyo, što može potrajati i do 20 minuta. Broj profila kupaca koje možete izvesti u Klaviyo ovisi o vašem ugovoru s Klaviyom.
- Samo segmenti.

## <a name="set-up-connection-to-klaviyo"></a>Postavljanje veze sa servisom Klaviyo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Klaviyo**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite svoj ključ Klaviyo API-ja za nastavak prijave.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** da biste inicijalizirali vezu.

1. Odaberite **Provjera autentičnost sa servisom Klaviyo** i navedite svoje administratorske vjerodajnice za Klaviyo.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Klaviyo. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. Unesite svoj **ID** Klaviyo liste.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
