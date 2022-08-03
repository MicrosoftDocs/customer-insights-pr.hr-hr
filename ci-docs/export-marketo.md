---
title: Izvoz segmenata u Marketo (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195235"
---
# <a name="export-segments-to-marketo-preview"></a>Izvoz segmenata u Marketo (pretpregled)

Izvezite segmente objedinjenih profila klijenata da biste generirali kampanje, pružili marketing putem e-pošte i koristili određene grupe klijenata pomoću usluge Marketo.

## <a name="prerequisites"></a>Preduvjeti

- [Marketo račun](https://login.marketo.com/) i odgovarajuće administratorske vjerodajnice.
- [Marketo ID klijenta, tajna klijenta i REST krajnja točka naziv glavnog računala](https://developers.marketo.com/rest-api/authentication/).
- [Postojeći popisi u Marketu](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) i odgovarajući ID-ovi.
- [Konfigurirani segmenti](segments.md).
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milijun profila kupaca po izvozu u Marketo, što može potrajati i do 3 sata. Broj profila kupaca koje možete izvesti u Marketo ovisi o vašem ugovoru s Marketom.
- Samo segmenti.

## <a name="set-up-connection-to-marketo"></a>Postavljanje veze s Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Marketo**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj **Marketo ID klijenta, tajnu klijenta i REST krajnja točka naziv glavnog računala**. Naziv glavnog računala krajnje točke za REST je samo naziv glavnog računala, bez https://. Primjer: xyz-abc-123.mktorest.com.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** da biste inicijalizirali vezu.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Marketo. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. Unesite svoj **ID Marketo liste**. ID popisa je čisto numerička vrijednost. Na primjer, ako je ID popisa Marketo ST12345A7, uklonite znak prije i poslije brojeva i unesite *12345*.

1. **U odjeljku Podudaranje** podataka odaberite barem jedno polje koje predstavlja korisnikovu adresu e-pošte ili korisnikov Marketo ID.

1. Po želji izvezite **ime**, **prezime**, **grada**, **države** i **države/regije da biste stvorili** personaliziranije e-poruke. Odaberite **Dodavanje atributa** za mapiranje ovih polja.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

U Marketu pronađite svoje segmente pod [Marketo popisima](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
