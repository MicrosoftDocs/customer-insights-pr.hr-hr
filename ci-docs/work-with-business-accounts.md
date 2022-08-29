---
title: Rad s poslovnim računima
description: Informirajte se o poslovnim računima kao primarnim ciljnim publika u sustavu Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: abb77a720ab737520a905b0c93b65573e669109f
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303907"
---
# <a name="work-with-business-accounts"></a>Rad s poslovnim računima

Omogućuje Dynamics 365 Customer Insights vam konfiguriranje okruženja za različite primarne ciljne publike: pojedinačne potrošače (B-do-C) i poslovne račune (B-do-B). U B2C scenarijima podaci su usmjereni na pojedince. Za B2B primarne ciljne skupine su računi – organizacije ili tvrtke – i kontakti. Ovaj vam članak pomaže započeti raditi s okruženjem za poslovne račune. U njemu su navedene razlike za područja značajki u odjeljku Customer Insights, ovisno o fokusu na vaše okruženje. Za dodatne informacije o razlikama pregledajte dokumente područja značajki. 

## <a name="create-an-environment-for-business-accounts"></a>Stvaranje okruženja za poslovne račune

Administratori mogu [stvoriti okruženje u postojećoj tvrtki ili ustanovi](create-environment.md). Korak u procesu stvaranja novog okruženja traži od administratora primarnu ciljnu skupinu okruženja. U slučaju da se radi o početnom postavljanju nakon kupnje licence, vođeno iskustvo pomaže u stvaranju prvog okruženja.

Tada možete [uvesti podatke](data-sources.md) za poslovne račune i povezane kontakte kao izvore podataka iz svih podržanih izvora.

 [Objedinite podatke](data-unification.md) o računu nakon kojih slijede podaci za kontakt da biste povezali entitete kontakata i računa.

## <a name="switch-between-primary-target-audience"></a>Prebacivanje između primarne ciljne skupine

Ako vaša tvrtka ili ustanova održava okruženja za pojedinačne klijente i poslovne račune, možete upotrijebiti preglednik u lijevom oknu za odabir primarne ciljne skupine.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Preglednik za promjenu primarne ciljne skupine između pojedinačnih klijenata i poslovnih računa.":::

## <a name="supported-feature-areas"></a>Podržana područja značajke

- [Aktivnosti](activities.md): Podrška za račune i povezane kontakte za stvaranje aktivnosti i njihovo prikazivanje na vremenskoj traci.
- [Odnosi](relationships.md): Čarobnjak za aktivnosti pomaže u stvaranju odnosa između entiteta, tako da prikaz računa može prikazati sve aktivnosti iz kontakata. Kontakti se mogu detaljno pregledati za prikaz kontakata, a hijerarhije se mogu koristiti za agregaciju aktivnosti računa.
- [Mjere](measures.md) : Podržava mjere stvorene od graditelja mjera s jednim izračunom. Neobvezna postavka omogućuje dodavanje podračuna pri stvaranju mjera.
- [Segmenti](segments.md): Podržava segmente koji su stvoreni od nule s pomoću sastavljača segmenata. Segmenti se mogu temeljiti na poslovnim subjektima ili kontaktima.
- [Unos podataka](data-sources.md): Sve značajke u ovom području iste su za poslovne račune i pojedinačne klijente.
- Objedinjavanje podataka od B do B vrlo je slično ujedinjenju podataka B-to-C, ali ima dodatni korak za objedinjavanje kontakata nakon ujedinjenja računa. Pogledajte [Poslovni računi (od B do B)](data-unification.md).
- [Obogaćivanje](enrichment-hub.md): Neke vrste obogaćivanja dostupne su samo za scenarije pojedinačnih klijenata, dok su druge dostupne samo za poslovne račune.
- [Predviđanja i gotovi modeli](predictions-overview.md): Predviđanje gubitka transakcije sadrži dodatne korake za poslovne račune. Ostala predviđanja dostupna su samo za pojedinačne klijente.
- [Aktivacija i izvoz](export-destinations.md): Izvozi su dostupni za poslovne račune i pojedinačne klijente. Neki izvozi zahtijevaju dodatnu konfiguraciju i podatke za kontakt projicirane u pozadinskim segmentima kako bi bili valjani za poslovne račune.
- [Postavke sustava](system.md) i [upravljanje korisnicima](permissions.md): Sve značajke u ovom području iste su za poslovne račune i pojedinačne klijente.

[!INCLUDE [footer-include](includes/footer-banner.md)]
