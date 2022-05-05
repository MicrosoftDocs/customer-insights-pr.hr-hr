---
title: Izvoz podataka usluge Customer Insights u Dynamics 365 Marketing
description: Saznajte kako konfigurirati vezu i izvesti u Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 7227f3f9e7699a9b5ad546789de5e568b56da579
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642190"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Korištenje segmenata u Dynamics 365 Marketing (pretpregled)



Upotrijebite [segmente](segments.md) za stvaranje kampanja i kontaktiranje određenih grupa klijenata koristeći Dynamics 365 Marketing. Više informacija potražite u članku [Upotreba segmenata iz usluge Dynamics 365 Customer Insights s uslugom Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Ako se koristite novim mogućnostima usluge Dynamics 365 Marketing za organizaciju puta klijenta u stvarnom vremenu u Dataverse organizaciji, ne morate izraditi standardni izvoz u uslugu Dynamics 365 Marketing. Kontakti i segmenti iz customer insights dostupni su izravno u sustavu Dynamics 365 Marketing nakon povezivanja marketinga i uvida u kupce. Prije brisanja postojećeg izvoza pregledajte dokumentaciju o [povezivanju Customer Insights i Dynamics 365 Marketing put klijenta orkestraciji](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Preduvjet za vezu

- Zapisi o kontaktima moraju biti prisutni u sustavu Dynamics 365 Marketing prije nego što možete izvesti segment iz Customer Insights u Marketing. Pročitajte više o tome kako preuzeti kontakte u [Dynamics 365 Marketing pomoću Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > Izvoz segmenata iz customer insights u Marketing neće stvoriti nove zapise o kontaktima u marketinškim instancama. Zapisi o kontaktima iz marketinga moraju se unijeti u Uvide u kupce i koristiti kao izvor podataka. Trebaju se uključiti i u objedinjeni entitet Klijent da bi mapirali ID-jeve klijenta u ID-jeve kontakta prije nego što se segmenti mogu izvesti.

## <a name="set-up-connection-to-marketing"></a>Postavljanje veze s Marketing

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **Dynamics 365 Marketing** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite URL za Marketing vaše tvrtke ili ustanove u polje **Adresa poslužitelja**.

1. U odjeljku **Račun administratora poslužitelja** odaberite **Prijava** i odaberite račun usluge Dynamics 365 Marketing.

1. Mapirajte polje ID kontakta u entitetu Kupac na ID kontakta sustava Dynamics 365.

1. Odaberite **Spremi** da biste završili vezu. 

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Dynamics 365 Marketing. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Odaberite jedan segment ili više njih.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]