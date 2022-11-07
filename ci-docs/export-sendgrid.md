---
title: Izvoz segmenata u SendGrid (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724839"
---
# <a name="export-segments-to-sendgrid-preview"></a>Izvoz segmenata u SendGrid (pretpregled)

Izvezite segmente objedinjenih profila klijenata u popise kontakata usluge SendGrid i koristite ih za kampanje i marketing putem e-pošte u usluzi SendGrid.

## <a name="prerequisites"></a>Preduvjeti

- SendGrid [račun](https://sendgrid.com/) i odgovarajuće administratorske vjerodajnice.
- [Postojeći popisi kontakata u SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) i odgovarajući ID-ovi.
- SendGrid [API ključ](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Konfigurirani segmenti](segments.md) u customer insights.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Privatna veza u kombinaciji s Donesite vlastitu pohranu (BYOS) nije podržana.
- SendGridu ukupno do 100.000 profila kupaca, što može potrajati i do nekoliko sati. Broj profila kupaca koje možete izvesti u SendGrid ovisi o vašem ugovoru s SendGrid-om.
- Samo segmenti.

## <a name="set-up-connection-to-sendgrid"></a>Postavljanje veze sa SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **SendGrid**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite tipku **SendGrid API**.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** da biste inicijalizirali vezu.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka SendGrid. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. **Unesite ID** popisa SendGrid.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta.

1. Po želji odaberite polja kao **što su ime**, **prezime**, **Država/regija**, **Država**, **Grad** i **Poštanski broj**.

1. Odaberite segmente koje želite izvesti slijedeći poznata ograničenja.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
