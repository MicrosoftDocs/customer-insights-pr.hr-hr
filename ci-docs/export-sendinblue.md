---
title: Izvoz segmenata u Sendinblue (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 816a3b242fadaa5a75db878adf0a76baf638e41c
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196937"
---
# <a name="export-segments-to-sendinblue-preview"></a>Izvoz segmenata u Sendinblue (pretpregled)

Segmente objedinjenih klijenskih profila izvezite za generiranje kampanja, pružanje marketinga putem e-pošte i iskorištavanje određenih grupa klijenata uz Sendinblue.

## <a name="prerequisites"></a>Preduvjeti

- Sendinblue [račun](https://www.sendinblue.com/) i odgovarajuće administratorske vjerodajnice.
- Tipka [SendinBlue API](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Postojeći popisi u sendinblue i odgovarajući ID-ovi.
- [Konfigurirani segmenti](segments.md).
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milijun profila kupaca po izvozu u SendinBlue, što može potrajati i do 90 minuta. Broj profila kupaca koje možete izvesti u SendinBlue ovisi o ugovoru s sendinblueom.
- Samo segmenti.

## <a name="set-up-connection-to-sendinblue"></a>Postavljanje veze na Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **SendinBlue**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite tipku **SendinBlue** API.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** da biste inicijalizirali vezu.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Sendinblue. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. **Unesite ID** popisa SendinBlue.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta.

1. Po želji izvezite **ime**, **prezime** i **telefon** da biste stvorili personaliziranije poruke e-pošte. Odaberite **Dodavanje atributa** za mapiranje ovih polja.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
