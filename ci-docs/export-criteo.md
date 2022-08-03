---
title: Izvoz segmenata u Criteo (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d7c8d6f0121fe18a6c886ba3776109a1a592ef33
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195327"
---
# <a name="export-segments-to-criteo-preview"></a>Izvoz segmenata u Criteo (pretpregled)

Izvoz segmenata jedinstvenih korisničkih profila za generiranje kampanja, pružanje marketinga putem e-pošte i korištenje određenih grupa kupaca s Criteom.

## <a name="prerequisites"></a>Preduvjeti

- Criteo [Dynamics Retargeting račun](https://www.criteo.com/login/) i odgovarajuće administratorske vjerodajnice.
- [Konfigurirani segmenti](segments.md).
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milijun profila kupaca po izvozu u Criteo, što može potrajati i do 30 minuta. Broj korisničkih profila koje možete izvesti u Criteo ovisi o vašem ugovoru s Criteom.
- Samo segmenti.

## <a name="set-up-connection-to-criteo"></a>Postavljanje veze s Criteom

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Criteo**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** da biste inicijalizirali vezu.

1. Odaberite **Autentifikaciju pomoću tvrtke Criteo** i navedite korisničko ime i vjerodajnice administratora za Criteo.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. **U polju Veza za izvoz** odaberite vezu iz sekcije Criteo. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta.

1. Po želji izvezite **ID** i **ime oglašivača**.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
