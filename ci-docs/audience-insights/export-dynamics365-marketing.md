---
title: Izvoz podataka usluge Customer Insights u Dynamics 365 Marketing
description: Saznajte kako konfigurirati vezu s uslugom Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269045"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Poveznik za Dynamics 365 Marketing (pretpregled)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Upotrijebite [segmente](segments.md) za stvaranje kampanja i kontaktiranje određenih grupa klijenata koristeći Dynamics 365 Marketing. Za dodatne informacije pogledajte [Korištenje segmenata iz sustava Dynamics 365 Customer Insights s uslugom Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Preduvjet

- Zapisi o kontaktima moraju biti prisutni u sustavu Dynamics 365 Marketing prije nego što možete izvesti segment iz Customer Insights u Marketing. Pročitajte više o tome kako preuzeti kontakte u [Dynamics 365 Marketing pomoću Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Izvoz segmenata iz uvida u ciljnu skupinnu u Marketing neće stvoriti nove zapise o kontaktima u instancama programa Marketing. Zapisi o kontaktima iz programa Marketing moraju se preuzeti u uvide u ciljnu skupinu i koristiti kao izvor podataka. Trebaju se uključiti i u objedinjeni entitet Klijent da bi mapirali ID-jeve klijenta u ID-jeve kontakta prije nego što se segmenti mogu izvesti.

## <a name="configure-the-connector-for-marketing"></a>Konfiguracija poveznika za Marketing

1. U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.

1. U odjeljku **Dynamics 365 Marketing** odaberite **Postavljanje**.

1. Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.

1. Unesite URL za Marketing vaše tvrtke ili ustanove u polje **Adresa poslužitelja**.

1. U odjeljku **Račun administratora poslužitelja** odaberite **Prijava** i odaberite račun usluge Dynamics 365 Marketing.

1. Mapirajte polje ID-a klijenta na ID kontakta sustava Dynamics 365.

1. Odaberite **Dalje**.

1. Odaberite jedan segment ili više njih.

1. Odaberite **Spremi**.

## <a name="export-the-data"></a>Izvoz podataka

Možete [izvesti podatke na zahtjev](export-destinations.md). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]