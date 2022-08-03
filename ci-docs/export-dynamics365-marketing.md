---
title: Izvoz segmenata u Dynamics 365 Marketing (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Dynamics 365 Marketing.
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
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196615"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Izvoz segmenata u Dynamics 365 Marketing (pretpregled)

Segmente [koristite](segments.md) za generiranje kampanja i kontaktiranje određenih grupa kupaca pomoću [sustava Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Ako se koristite novim mogućnostima usluge Dynamics 365 Marketing za organizaciju puta klijenta u stvarnom vremenu u Dataverse organizaciji, ne morate izraditi standardni izvoz u uslugu Dynamics 365 Marketing. Kontakti i segmenti iz customer insights dostupni su izravno u sustavu Dynamics 365 Marketing nakon povezivanja marketinga i uvida u kupce. Prije brisanja postojećeg izvoza pregledajte dokumentaciju o [povezivanju Customer Insights i Dynamics 365 Marketing put klijenta orkestraciji](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Preduvjet

Zapisi o kontaktima moraju biti prisutni u sustavu Dynamics 365 Marketing prije nego što možete izvesti segment iz Customer Insights u Marketing. Pročitajte više o tome kako preuzeti kontakte u [Dynamics 365 Marketing pomoću Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Izvoz segmenata iz customer insights u Marketing neće stvoriti nove zapise o kontaktima u marketinškim instancama. Zapisi o kontaktima iz marketinga moraju se unijeti u Uvide u kupce i koristiti kao izvor podataka. Trebaju se uključiti i u objedinjeni entitet Klijent da bi mapirali ID-jeve klijenta u ID-jeve kontakta prije nego što se segmenti mogu izvesti.

## <a name="set-up-connection-to-marketing"></a>Postavljanje veze s Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Dynamics 365 Marketing**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite URL za Marketing vaše tvrtke ili ustanove u polje **Adresa poslužitelja**.

1. U odjeljku **Račun administratora poslužitelja** odaberite **Prijava** i odaberite račun usluge Dynamics 365 Marketing.

1. Mapirajte polje ID kontakta u entitetu Kupac na ID kontakta sustava Dynamics 365.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Dynamics 365 Marketing. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. Odaberite polje ID kontakta u entitetu Kupac koje odgovara ID-u kontakta sustava Dynamics 365.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
