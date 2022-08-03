---
title: Izvoz segmenata u DotDigital (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196063"
---
# <a name="export-segments-to-dotdigital-preview"></a>Izvoz segmenata u DotDigital (pretpregled)

Izvezite segmente objedinjenih profila klijenata u adresare usluge DotDigital i koristite ih za kampanje, marketing putem e-pošte i za izgradnju segmenata klijenata pomoću usluge DotDigital.

## <a name="prerequisites"></a>Preduvjeti

- [DotDigital račun](https://dotdigital.com/) i korisnik API-ja [...](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- DotDigital ID iz [novog](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) ili postojećeg adresara u DotDigitalu. ID se može pronaći u URL-u kada odaberete i otvorite adresar.
- [Konfigurirani segmenti](segments.md) u customer insights.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milijun profila kupaca po izvozu u DotDigital, što može potrajati i do tri sata zbog ograničenja na strani pružatelja usluga. Broj profila kupaca koje možete izvesti u DotDigital ovisi o vašem ugovoru s DotDigitalom.
- Samo segmenti.

## <a name="set-up-connection-to-dotdigital"></a>Postavljanje veze s DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **DotDigital**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **korisničko ime i lozinku API-ja za DotDigital**.

1. **Unesite svoj DotDigital ID** adresara.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** da biste inicijalizirali vezu.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka DotDigital. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta.

1. Po želji izvezite **ime**, **prezime**, **puno ime**, **spol** i **poštanski broj**.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

U DotDigitalu pronađite svoje segmente u [DotDigital adresarima](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
