---
title: Izvoz podataka usluge Customer Insights u Dynamics 365 Sales
description: Saznajte kako konfigurirati vezu i izvesti u Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759582"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Korištenje segmenata u Dynamics 365 Sales (pretpregled)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Upotrijebite podatke o klijentima za izradu popisa zainteresiranih, daljnje praćenje tijekova rada i slanje promocija pomoću aplikacije Dynamics 365 Sales.

## <a name="prerequisite-for-connection"></a>Preduvjet za vezu

1. Zapisi o kontaktima moraju biti prisutni u sustavu Dynamics 365 Sales prije nego što možete izvesti segment iz Customer Insights u Sales. Pročitajte više o tome kako preuzeti kontakte u [Dynamics 365 Sales pomoću Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Izvoz segmenata iz uvida u ciljnu skupinnu u Sales neće stvoriti nove zapise o kontaktima u instancama programa Sales. Zapisi o kontaktima iz programa Sales moraju se preuzeti u uvide u ciljnu skupinu i koristiti kao izvor podataka. Trebaju se uključiti i u objedinjeni entitet Klijent da bi mapirali ID-jeve klijenta u ID-jeve kontakta prije nego što se segmenti mogu izvesti.

## <a name="set-up-the-connection-to-sales"></a>Postavite vezu sa Sales

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **Dynamics 365 Sales** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite URL za Sales vaše tvrtke ili ustanove u polje **Adresa poslužitelja**.

1. U odjeljku **Račun administratora poslužitelja** odaberite **Prijava** i odaberite račun usluge Dynamics 365 Sales.

1. Mapirajte polje ID-a klijenta na ID kontakta sustava Dynamics 365.

1. Odaberite **Spremi** da biste završili vezu. 

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Dynamics 365 Sales. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Odaberite jedan segment ili više njih.

1. Odaberite **Spremi**

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
