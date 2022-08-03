---
title: Izvoz segmenata u Dynamics 365 Sales (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Dynamics 365 Sales.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195972"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Izvoz segmenata u Dynamics 365 Sales (pretpregled)

Upotrijebite podatke o klijentima za izradu popisa zainteresiranih, daljnje praćenje tijekova rada i slanje promocija pomoću aplikacije Dynamics 365 Sales.

## <a name="prerequisites"></a>Preduvjeti

Zapisi o kontaktima moraju biti prisutni u sustavu Dynamics 365 Sales prije nego što možete izvesti segment iz Customer Insights u Sales. Pročitajte više o tome kako unijeti kontakte iz [sustava Dynamics 365 Sales pomoću programa Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Izvoz segmenata iz uvida u kupce u prodaju neće kreirati nove zapise o kontaktima u instancama Prodaje. Zapisi o kontaktima iz prodaje moraju se progutati u uvidima kupaca i koristiti kao izvor podataka. Trebaju se uključiti i u objedinjeni entitet Klijent da bi mapirali ID-jeve klijenta u ID-jeve kontakta prije nego što se segmenti mogu izvesti.

## <a name="known-limitations"></a>Poznata ograničenja

Izvoz u Dynamics 365 Prodaja je ograničena na 100.000 po segmentu, što može potrajati i do 3 sata.

## <a name="set-up-connection-to-sales"></a>Postavljanje veze s prodajom

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Dynamics 365 Sales**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite URL za Sales vaše tvrtke ili ustanove u polje **Adresa poslužitelja**.

1. U odjeljku **Račun administratora poslužitelja** odaberite **Prijava** i odaberite račun usluge Dynamics 365 Sales.

1. Mapirajte polje ID-a klijenta na ID kontakta sustava Dynamics 365.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Dynamics 365 Sales. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. Odaberite polje ID kontakta u entitetu Kupac koje odgovara ID-u kontakta sustava Dynamics 365.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
