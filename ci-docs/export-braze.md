---
title: Izvoz segmenata u Braze (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Braze.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 84dc7f13f30e0334d431fe5b5866c7f87e82ab27
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195098"
---
# <a name="export-segments-to-braze-preview"></a>Izvoz segmenata u Braze (pretpregled)

Izvezite segmente jedinstvenih profila kupaca u Braze i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduvjeti

- [Braze račun](https://www.braze.com/) i odgovarajuće administratorske vjerodajnice.
- Braze [API ključ](https://www.braze.com/docs/api/basics/)
- [Konfigurirani segmenti](segments.md) u customer insights.
- Jedinstveni profili kupaca u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte i Brazeov ID kupca.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milijun korisničkih profila za Braze, što može potrajati i do 40 minuta. Broj profila kupaca koje možete izvesti u Braze ovisi o vašem ugovoru s Brazeom.
- Samo segmenti.

## <a name="set-up-connection-to-braze"></a>Postavljanje veze s Brazeom

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Braze**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite ključ Braze API-ja da biste se nastavili prijavljivati.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** da biste inicijalizirali vezu.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. **U polju Veza za izvoz** odaberite vezu iz odjeljka Braze. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. **U polju ID** kupca odaberite polje koje predstavlja korisnikov ID braze. Segmenti u Brazama nastaju s istim nazivom segmenta kao i u Dynamics 365 Customer Insights. Možete odabrati više neobaveznih polja za podudarne podatke.

1. Odaberite entitete ili segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
