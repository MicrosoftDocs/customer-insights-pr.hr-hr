---
title: Izvoz podataka customer insights u HubSpot
description: Saznajte kako konfigurirati vezu i izvesti u HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725345"
---
# <a name="export-segments-to-hubspot-preview"></a>Izvoz segmenata u HubSpot (pretpregled)

Izvezite segmente jedinstvenih profila kupaca u HubSpot i koristite ih za marketing putem e-pošte.

## <a name="prerequisites-for-a-connection"></a>Preduvjeti za vezu

- [HubSpot račun](https://www.hubspot.com/) i odgovarajuće administratorske vjerodajnice.
- [API ključ](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) iz HubSpota.
- [Konfigurirani segmenti](segments.md) u customer insights.

## <a name="known-limitations"></a>Poznata ograničenja

- Privatna veza u kombinaciji s Donesite vlastitu pohranu (BYOS) nije podržana.
- Do 100'000 korisničkih profila po izvozu u HubSpot, što može potrajati i do 15 minuta. Broj korisničkih profila koje možete izvesti u HubSpot ovisi i ograničen je na vaš ugovor s HubSpotom.
- Samo segmenti.

## <a name="set-up-connection-to-hubspot"></a>Postavljanje veze s HubSpotom

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **HubSpot** da biste konfigurirali vezu.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite vjerodajnice hubSpota kada se to od vas zatraži.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** se da biste inicijalizirali vezu s HubSpotom.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, ddaberite **Dodaj izvoz**.

1. **U polju Veza za izvoz** odaberite vezu iz odjeljka HubSpot. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. Ponovite iste korake za druga neobavezna polja.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
