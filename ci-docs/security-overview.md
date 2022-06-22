---
title: Sigurnosne postavke u odjeljku Uvidi kupaca
description: Informirajte se o sigurnosnim postavkama u sustavu Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947406"
---
# <a name="security-settings-in-customer-insights"></a>Sigurnosne postavke u odjeljku Uvidi kupaca

Na **stranici Sigurnost** navedene su mogućnosti konfiguriranja korisničkih dozvola i značajki koje pomažu u zaštiti Dynamics 365 Customer Insights. Samo administratori mogu pristupiti ovoj stranici.

Idite na **Sigurnost** > **administratora** da biste konfigurirali postavke.

Stranica **Sigurnost** sadrži sljedeće kartice:

- [Korisnici](#users-tab)
- [API-ji](#apis-tab)
- [Privatne veze](#private-links-tab)
- [Sef za ključeve](#key-vault-tab)
- [Siguran pristup podacima o klijentima pomoću Customer Lockboxa (Pretpregled)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Kartica Korisnici

Pristup uvidima u korisnike ograničen je na korisnike u vašoj tvrtki ili ustanovi koje je administrator dodao u aplikaciju. Kartica **Korisnici** omogućuje upravljanje korisničkim pristupom i njihovim dozvolama. Dodatne informacije potražite u odjeljku [Korisničke](permissions.md) dozvole.

## <a name="apis-tab"></a>Kartica API-ji

Pregledajte ključeve za korištenje [API-ja](apis.md) customer insights i upravljajte njima s podacima vašeg okruženja.

Nove primarne i sekundarne tipke možete stvoriti tako **da odaberete Regenerate primary** ili **Regenerate sekundarni**. 

Da biste blokirali pristup API-ju okolišu, odaberite **Onemogući**. Ako su API-ji onemogućeni, možete odabrati **Omogući** ponovno odobravanje pristupa.

## <a name="private-links-tab"></a>Kartica Privatne veze

[Azure Private Link](/azure/private-link/private-link-overview) omogućuje uvidima u korisnike da se povežu s vašim Azure Data Lake Storage računom putem privatnog krajnja točka u vašoj virtualnoj mreži. Za podatke na računu za pohranu, koji nije izložen javnom internetu, Private Link omogućuje vezu s tom ograničenom mrežom.

> [!IMPORTANT]
> Minimalni preduvjet za ulogu za postavljanje veze privatne veze:
>
> - Uvidi kupaca: administrator
> - Azure built-in role: [Storage Account suradnik](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Dozvole za prilagođenu ulogu servisa Azure: [Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Postavljanje privatne veze u uvidima kupaca postupak je u dva koraka. Najprije pokrećete stvaranje privatne veze iz **privatnih veza** > **za sigurnost** > **administratora** u korisničkim uvidima. U **oknu Dodavanje privatne veze** navedeni su računi za pohranu klijenta za koje imate dozvole. Odaberite račun za pohranu i dajte pristanak za stvaranje privatne veze.

Zatim morate odobriti privatnu vezu na strani računa data lake pohrane. Otvorite vezu prikazanu na zaslonu da biste odobrili novu Privatnu vezu.

## <a name="key-vault-tab"></a>Kartica Trezor ključeva

Kartica **Trezor ključeva** omogućuje povezivanje i upravljanje vlastitim [trezorom](/azure/key-vault/general/basic-concepts) za ključeve servisa Azure s okolinom.
Namjenski sef za ključeve može se koristiti za postavljanje i korištenje tajni u granicama usklađenosti tvrtke ili ustanove. Customer Insights može koristiti tajne u trezoru ključeva servisa Azure za [postavljanje veza sa](connections.md) sustavima drugih proizvođača.

Za više informacija pogledajte [Donesite svoj vlastiti sef za ključeve servisa Azure](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Siguran pristup podacima o klijentima pomoću Customer Lockboxa (Pretpregled)

Customer Insights koristi Power Platform mogućnost Customer Lockbox. Customer Lockbox pruža sučelje za pregled i odobravanje (ili odbijanje) zahtjeva za pristup podacima. Ti se zahtjevi javljaju kada je za rješavanje slučaja podrške potreban pristup podacima o klijentima. Da biste koristili ovu značajku, Uvidi kupaca moraju imati postojeću vezu s okruženjem u vašem klijentu Microsoft Dataverse.

Dodatne informacije o Customer Lockboxu potražite u [sažetku](/power-platform/admin/about-lockbox#summary) customer lockboxa Power Platform. U članku se opisuje i tijek rada [i potrebna](/power-platform/admin/about-lockbox#workflow) postavka [za omogućivanje](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) customer lockboxa.

> [!IMPORTANT]
> Globalni administratori ili Power Platform Power Platform administratori mogu odobriti zahtjeve Customer Lockbox izdane za Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
