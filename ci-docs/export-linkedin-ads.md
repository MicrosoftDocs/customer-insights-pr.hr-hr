---
title: Izvoz segmenata u LinkedIn Ads (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u LinkedIn Ads.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d1a9ae985043398f4bc38163be26ecf0c3c8e2ba
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196799"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Izvoz segmenata u LinkedIn Ads (pretpregled)

Izvezite segmente objedinjenih profila klijenata u LinkedIn Ads kako biste stvorili podudarne ciljne skupine. Upotrijebite podudarne ciljne publike za ciljanje tvrtki i ciljanje kontakata.

## <a name="prerequisites"></a>Preduvjeti

- Račun [LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) i odgovarajuće administratorske vjerodajnice.
- ID [LinkedIn Campaign Manager računa](https://www.linkedin.com/help/lms/answer/a424270).
- [Konfigurirani segmenti](segments.md) u customer insights.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 100 000 korisničkih profila po izvozu na LinkedIn Ads, što može potrajati i do 10 minuta.
- Samo segmenti. Segment mora sadržavati najmanje 300 jedinstvenih profila.

## <a name="set-up-connection-to-linkedin-ads"></a>Postavljanje veze sa servisom LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **LinkedIn Ads**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite svoj LinkedIn Campaign Manager ID računa.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži** da biste inicijalizirali vezu.

1. Odaberite **Provjeri autentičnost uz LinkedIn** i pružite svoje administratorske vjerodajnice za LinkedIn Campaign Manager.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka LinkedIn Ads. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. Odaberite želite li izvesti podatke radi [ciljanja kontakata](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ili [ciljanja tvrtki](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) u usluzi LinkedIn.

1. U odjeljku **Podudaranje podataka** za ciljanje kontakata odaberite barem jedno polje koje predstavlja adresu e-pošte klijenta, ID za Apple Ad, ID za Google Ad, ID korisnika tražilice Google ili ime i prezime. Ako odaberete ciljanje tvrtke, odaberite barem jedno polje koje predstavlja naziv tvrtke, domenu e-pošte, URL stranice LinkedIn, simbol Stock ili web-mjesto.

1. Po želji dodajte polja da biste dodatno definirali izvoz. Odaberite **Dodavanje atributa** za mapiranje ovih polja.

1. Odaberite segmente koje želite izvesti. Podudarne ciljne skupine u alatu LinkedIn Campaign Manager automatski će se stvoriti s nazivom segmenata koje ste odabrali za izvoz. Svaki će segment rezultirati zasebnom podudarnom ciljnom skupinom.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
