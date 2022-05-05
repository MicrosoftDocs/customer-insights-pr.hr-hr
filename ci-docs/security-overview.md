---
title: Sigurnosne postavke u sustavu Dynamics 365 Customer Insights
description: Informirajte se o sigurnosnim postavkama u sustavu Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653775"
---
# <a name="security-overview-page"></a>Stranica pregleda sigurnosti

Na **stranici Sigurnost** navedene su mogućnosti konfiguriranja korisničkih dozvola i značajki koje pomažu u zaštiti Dynamics 365 Customer Insights. Samo administratori mogu pristupiti ovoj stranici. 

Idite na **AdminSecurity** > **da** biste konfigurirali postavke.

Stranica **Sigurnost** sadrži sljedeće kartice:
- [Korisnici](#users-tab)
- [API-ji](#apis-tab)
- [Sef za ključeve](#key-vault-tab)

## <a name="users-tab"></a>Kartica Korisnici

Pristup uvidima u korisnike ograničen je na korisnike u vašoj tvrtki ili ustanovi koje je administrator dodao u aplikaciju. Kartica **Korisnici** omogućuje upravljanje korisničkim pristupom i njihovim dozvolama. Dodatne informacije potražite u odjeljku [Korisničke](permissions.md) dozvole.

## <a name="apis-tab"></a>Kartica API-ji

Pregledajte ključeve za korištenje [API-ja](apis.md) customer insights i upravljajte njima s podacima vašeg okruženja.

Nove primarne i sekundarne tipke možete stvoriti tako **da odaberete Regenerate primary** ili **Regenerate sekundarni**. 

Da biste blokirali pristup API-ju okolišu, odaberite **Onemogući**. Ako su API-ji onemogućeni, možete odabrati **Omogući** ponovno odobravanje pristupa.

## <a name="key-vault-tab"></a>Kartica Trezor ključeva

Kartica **Trezor ključeva** omogućuje povezivanje i upravljanje vlastitim [trezorom](/azure/key-vault/general/basic-concepts) za ključeve servisa Azure s okolinom.
Namjenski sef za ključeve može se koristiti za postavljanje i korištenje tajni u granicama usklađenosti tvrtke ili ustanove. Customer Insights može koristiti tajne u trezoru ključeva servisa Azure za [postavljanje veza sa](connections.md) sustavima drugih proizvođača.

Za više informacija pogledajte [Donesite svoj vlastiti sef za ključeve servisa Azure](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
