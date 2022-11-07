---
title: Izvoz segmenata u ActiveCampaign
description: Saznajte kako konfigurirati vezu i izvesti u ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725391"
---
# <a name="export-segments-to-activecampaign-preview"></a>Izvoz segmenata u ActiveCampaign (pretpregled)

Izvezite segmente objedinjenih profila kupaca u ActiveCampaign i upotrijebite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduvjeti

- ActiveCampaign [račun](https://www.activecampaign.com/) i odgovarajuće administratorske vjerodajnice.
- [ID popisa ActiveCampaign](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- [ActiveCampaign API ključ](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) i REST krajnja točka naziv glavnog računala.
- [Konfigurirani segmenti](segments.md) u customer insights.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Privatna veza u kombinaciji s Donesite vlastitu pohranu (BYOS) nije podržana.
- Do milijun korisničkih profila po izvozu na ActiveCampaign, što može potrajati i do 90 minuta. Broj profila klijenata koje možete izvesti u ActiveCampaign ovisi o ugovoru s uslugom ActiveCampaign.
- Samo segmenti.

## <a name="set-up-connection-to-activecampaign"></a>Postavljanje veze na ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **ActiveCampaign**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj ključ API-ja za ActiveCampaign i naziv hosta REST krajnje točke. Naziv glavnog računala krajnje točke za REST je samo naziv glavnog računala, bez https://.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** da biste inicijalizirali vezu.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka ActiveCampaign. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. Unesite ID **popisa** ActiveCampaign.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta.

1. Po želji izvezite **ime**, **prezime** i **telefon** da biste stvorili personaliziranije poruke e-pošte. Odaberite **Dodavanje atributa** za mapiranje ovih polja.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
