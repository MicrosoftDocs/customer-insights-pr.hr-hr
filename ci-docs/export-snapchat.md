---
title: Izvoz segmenata u Snapchat (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195373"
---
# <a name="export-segments-to-snapchat-preview"></a>Izvoz segmenata u Snapchat (pretpregled)

Izvezite segmente objedinjenih profila klijenata u Snapchat i koristite ih za oglašavanje.

## <a name="prerequisites"></a>Preduvjeti

- [Snapchat poslovni račun](https://business.snapchat.com/), [Snapchat Ads račun](https://ads.snapchat.com/) i odgovarajuće administratorske vjerodajnice. Morate barem biti član poslovnog subjekta tvrtke ili ustanove i upravitelj podataka određenog oglasnog računa.
- Najmanje jedan publika u Snapchatu publika menadžer tipa SAM (Snap publika Match).
- [Snapchat segment / publika ID](https://businesshelp.snapchat.com/s/article/custom-audiences). ID publika može se naći u URL-u nakon odabira publika u Snapchat publika Manageru.
- [Konfigurirani segmenti](segments.md) u customer insights.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milijun korisničkih profila, što može potrajati i do 15 minuta.
- Samo segmenti.

## <a name="set-up-connection-to-snapchat"></a>Postavljanje veze za Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Snapchat**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** da biste inicijalizirali vezu.

1. Odaberite **Provjeri autentičnost uz Snapchat** i pružite svoje administratorske vjerodajnice za Snapchat.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Snapchat. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. **Unesite Snapchat segment / publika ID**.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
