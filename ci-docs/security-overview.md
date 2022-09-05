---
title: Konfiguriranje sigurnosnih postavki
description: Informirajte se o sigurnosnim postavkama u sustavu Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387240"
---
# <a name="configure-security-settings"></a>Konfiguriranje sigurnosnih postavki

Upravljajte API ključevima, pristupite podacima o klijentima i postavite privatnu vezu za Azure.

## <a name="manage-api-keys"></a>Upravljanje API ključevima

Pregledajte ključeve za korištenje [API-ja](apis.md) customer insights i upravljajte njima s podacima u vašem okruženju.

1. Otvorite **Sigurnost administratora** > **i** odaberite karticu **API-ji**.

1. Ako API pristup okolišu nije postavljen, odaberite **Omogući**. Ili, da biste blokirali pristup API-ja okolišu, odaberite **Onemogući** i potvrdi.

1. Upravljajte primarnim i sekundarnim API ključevima:

   1. Da biste prikazali primarni ili sekundarni API ključ, odaberite **simbol Pokaži**.

   1. Da biste kopirali primarni ili sekundarni API ključ, odaberite **simbol Kopiraj**.

   1. Da biste stvorili nove primarne ili sekundarne API tipke, odaberite **Obnovi primarni** ili **Regeneriraj sekundarni**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Siguran pristup podacima o klijentima pomoću Customer Lockboxa (Pretpregled)

Customer Insights koristi Power Platform mogućnost Customer Lockbox. Customer Lockbox pruža sučelje za pregled i odobravanje (ili odbijanje) zahtjeva za pristup podacima. Ti se zahtjevi javljaju kada je za rješavanje slučaja podrške potreban pristup podacima o klijentima. Da biste koristili ovu značajku, Uvidi kupaca moraju imati postojeću vezu s okruženjem u vašem klijentu Microsoft Dataverse.

Dodatne informacije o Customer Lockboxu potražite u [sažetku](/power-platform/admin/about-lockbox#summary) customer lockboxa Power Platform. U članku se opisuje i tijek rada [i potrebna](/power-platform/admin/about-lockbox#workflow) postavka [za omogućivanje](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) customer lockboxa.

> [!IMPORTANT]
> Globalni administratori ili Power Platform Power Platform administratori mogu odobriti zahtjeve Customer Lockbox izdane za Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Postavljanje veze servisa Azure Private Link

[Azure Private Link](/azure/private-link/private-link-overview) omogućuje uvidima u korisnike da se povežu s vašim Azure Data Lake Storage računom putem privatnog krajnja točka u vašoj virtualnoj mreži. Za podatke na računu za pohranu, koji nije izložen javnom internetu, Private Link omogućuje vezu s tom ograničenom mrežom.

> [!IMPORTANT]
> Minimalni preduvjet za ulogu za postavljanje veze privatne veze:
>
> - Uvidi kupaca: administrator
> - Azure built-in role: [Storage Account suradnik](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Dozvole za prilagođenu ulogu servisa Azure: [Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. U odjeljku Uvidi u klijente otvorite **Sigurnost administratora** > **i** odaberite karticu **Privatne veze**.

1. Odaberite **Dodaj privatnu vezu**.

   U **oknu Dodavanje privatne veze** navedeni su računi za pohranu klijenta za koje imate dozvole.

1. Odaberite pretplatu, grupu resursa i račun za pohranu.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Spremi**.

1. Idite na svoj račun za pohranu na servisu Data Lake i otvorite vezu prikazanu na zaslonu.

1. Odobrite privatnu vezu.


[!INCLUDE [footer-include](includes/footer-banner.md)]
