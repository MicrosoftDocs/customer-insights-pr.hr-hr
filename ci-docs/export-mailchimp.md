---
title: Izvoz segmenata u Mailchimp (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Mailchimp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 54aec10e24b6356e2e4317cf33e740a1a086a2dd
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196845"
---
# <a name="export-segments-to-mailchimp-preview"></a>Izvoz segmenata u Mailchimp (pretpregled)

Izvezite segmente objedinjenih profila klijenata u Mailchimp da biste stvorili biltene i kampanje e-pošte.

## <a name="prerequisites"></a>Preduvjeti

- [Mailchimp račun](https://mailchimp.com/) i odgovarajuće administratorske vjerodajnice.
- [Postojeća publika u Mailchimpu](https://mailchimp.com/help/create-audience/) i odgovarajući [ID-ovi publika](https://mailchimp.com/help/find-audience-id/).
- [Konfigurirani segmenti](segments.md).
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milijun korisničkih profila po izvozu u Mailchimp, što može potrajati i do tri sata. Broj korisničkih profila koje možete izvesti u Mailchimp ovisi o vašem ugovoru s Mailchimpom.
- Samo segmenti.

## <a name="set-up-connection-to-mailchimp"></a>Postavljanje veze s Mailchimp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Mailchimp**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** da biste inicijalizirali vezu.

1. Odaberite mogućnost **Provjera autentičnosti pomoću usluge Mailchimp** i unesite svoje vjerodajnice za Mailchimp.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Mailchimp. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. Unesite svoj **Mailchimp publika ID**.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta.

1. Po želji izvezite **ime** i **prezime** da biste stvorili personaliziranije poruke e-pošte. Odaberite **Dodavanje atributa** za mapiranje ovih polja.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
