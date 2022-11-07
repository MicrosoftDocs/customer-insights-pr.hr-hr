---
title: Izvoz segmenata u Google Ads (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725069"
---
# <a name="export-segments-to-google-ads-preview"></a>Izvoz segmenata u Google Ads (pretpregled)

Izvezite segmente objedinjenih korisničkih profila na popis publike servisa Google Ads i upotrijebite ih za oglašavanje na servisima Google Search, Gmail, YouTube i Google Display Network.

## <a name="prerequisites"></a>Preduvjeti

- [Google Ads račun](https://ads.google.com/) i odgovarajuće administratorske vjerodajnice.
- Google [Adsov korisnički ID](https://support.google.com/google-ads/answer/1704344).
- Ispunjeni su zahtjevi Pravila podudaranja [s kupcima](https://support.google.com/adspolicy/answer/6299717).
- Ispunjeni su zahtjevi [veličina](https://support.google.com/google-ads/answer/7558048) popisa za remarketing.
- [Konfigurirani segmenti](segments.md).
- Jedinstveni profili kupaca u izvezenim segmentima sadrže polja koja predstavljaju adresu e-pošte, telefon, ID mobilnog oglašivača, korisnički ID treće strane ili adresu.

## <a name="known-limitations"></a>Poznata ograničenja

- Privatna veza u kombinaciji s Donesite vlastitu pohranu (BYOS) nije podržana.
- Izvezite milijun korisničkih profila po izvozu u Google Ads, što može potrajati i do 30 minuta zbog ograničenja na strani pružatelja usluga.
- Samo segmenti.
- Podudaranje u Google Adsu može potrajati do 48 sati.

## <a name="set-up-connection-to-google-ads"></a>Postavljanje veze s Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Google Ads**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj Google Ads korisnički ID.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite mogućnost **Provjera autentičnosti pomoću usluge Google Ads** i unesite svoje vjerodajnice za Google Ads.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Google Ads. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. Odaberite želite li koristiti postojeću publika ili stvoriti novu:
   - Da biste ažurirali postojeći Google Ads publika, unesite svoj [Google Ads publika ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Da biste stvorili novu publika, polje Google publika ID ostavite prazno. Customer Insights automatski će izraditi novu publika na vašem Google Ads računu i upotrijebiti naziv izvezenog segmenta.

1. **U odjeljku Podudaranje** podataka odaberite jedno ili više podatkovnih polja za izvoz i odaberite polje koje predstavlja odgovarajuća podatkovna polja u odjeljku Customer Insights.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
