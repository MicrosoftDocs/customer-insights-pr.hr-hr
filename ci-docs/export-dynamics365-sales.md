---
title: Izvoz segmenata u Dynamics 365 Sales (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: b8e756313ca037dca41cb25587229808f0c584c9
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082382"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Izvoz segmenata u Dynamics 365 Sales (pretpregled)

Upotrijebite podatke o klijentima za izradu popisa zainteresiranih, daljnje praćenje tijekova rada i slanje promocija pomoću aplikacije Dynamics 365 Sales.

## <a name="known-limitations"></a>Poznata ograničenja

- Izvoz u Dynamics 365 Prodaja ograničena je na 100'000 članova po segmentu.
- Izvoz segmenata u Dynamics 365 Prodaja može potrajati do 3 sata. 

## <a name="prerequisite-for-connection"></a>Preduvjet za vezu

1. Zapisi o kontaktima moraju biti prisutni u sustavu Dynamics 365 Sales prije nego što možete izvesti segment iz Customer Insights u Sales. Pročitajte više o tome kako unijeti kontakte iz [sustava Dynamics 365 Sales pomoću programa Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Izvoz segmenata iz uvida u kupce u prodaju neće kreirati nove zapise o kontaktima u instancama Prodaje. Zapisi o kontaktima iz prodaje moraju se progutati u uvidima kupaca i koristiti kao izvor podataka. Trebaju se uključiti i u objedinjeni entitet Klijent da bi mapirali ID-jeve klijenta u ID-jeve kontakta prije nego što se segmenti mogu izvesti.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
