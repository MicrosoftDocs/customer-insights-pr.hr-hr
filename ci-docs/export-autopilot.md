---
title: Izvoz segmenata u Autopilot (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 449d2c5e32697e4a5d2c9dff4a5a1cbdb26aeb4d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195051"
---
# <a name="export-segments-to-autopilot-preview"></a>Izvoz segmenata u Autopilot (pretpregled)

Izvezite segmente objedinjenih profila klijenata u Autopilot i koristite ih za marketing putem e-pošte u usluzi Autopilot.

## <a name="prerequisites-for-a-connection"></a>Preduvjeti za vezu

- Račun [autopilota](https://www.autopilothq.com/) i odgovarajuće administratorske vjerodajnice.
- Ključ [autopilotskog API-ja](https://autopilot.docs.apiary.io/#)
- [Konfigurirani segmenti](segments.md) u customer insights.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 100.000 profila kupaca po izvozu u Autopilot, što može potrajati i do nekoliko sati. Broj profila kupaca koje možete izvesti u Autopilot ovisi o vašem ugovoru s Autopilotom.
- Samo segmenti.

## <a name="set-up-connection-to-autopilot"></a>Postavljanje veze s Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Autopilot**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj Ključ za API za Autopilot.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** da biste inicijalizirali vezu.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Autopilot. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta.

1. Po želji izvezite druga polja kao **što su ime** i **prezime**.

1. Odaberite segmente koje želite izvesti u skladu s poznatim ograničenjima.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
