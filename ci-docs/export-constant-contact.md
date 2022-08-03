---
title: Izvoz segmenata u Constant Contact (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4d2ec29c194dc481ee40048b8ecbed813291b4d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196477"
---
# <a name="export-segments-to-constant-contact-preview"></a>Izvoz segmenata u Constant Contact (pretpregled)

Izvezite segmente objedinjenih profila klijenata u Constant Contact i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduvjeti

- Račun [stalnog](https://www.constantcontact.com/account-home) kontakta i odgovarajuće administratorske vjerodajnice.
- ID [popisa stalnih kontakata](https://app.constantcontact.com/pages/contacts/ui#lists). Otvorite popis u Constant Contact da biste pronašli ID popisa u URL-u.
- [Konfigurirani segmenti](segments.md) u customer insights.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milijun profila kupaca po izvozu u Constant Contact, što može potrajati i do jednog sata. Broj profila kupaca koje možete izvesti u Stalni kontakt ovisi o vašem ugovoru s stalnim kontaktom.
- Samo segmenti.

## <a name="set-up-connection-to-constant-contact"></a>Postavljanje veze s Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Stalni kontakt**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** da biste inicijalizirali vezu.

1. Odaberite **Provjeri autentičnost stalnim kontaktom** i dostavite svoje administratorske vjerodajnice za stalni kontakt.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Constant Contact. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. **Unesite ID** popisa stalnih kontakata.

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta.

1. Po želji izvezite **ime** i **prezime** kao dodatna polja za stvaranje personaliziranijih poruka e-pošte. Odaberite **Dodavanje atributa** za mapiranje ovih polja.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
