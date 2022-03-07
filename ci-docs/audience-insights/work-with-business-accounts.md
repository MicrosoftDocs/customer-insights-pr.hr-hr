---
title: Početak rada s poslovnim računima kao primarnom ciljnom skupinom
description: Saznajte više o poslovnim računima kao primarnoj ciljnoj skupini Dynamics 365 Customer Insights.
ms.date: 09/30/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea036cf3a3623a314a6d0d7da85b2c30c030ccea
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/15/2021
ms.locfileid: "7644979"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Rad s poslovnim računima u uvidima u ciljne skupine

Mogućnost uvida u ciljne skupine Dynamics 365 Customer Insights omogućuje vam da konfigurirate okruženje za različite primarne ciljne skupine: pojedinačne klijente (B2C) i poslovne račune (B2B). U B2C scenarijima, podaci su usmjereni na pojedince. Za B2B, primarna ciljna skupina su računi – organizacije ili tvrtke – i kontakti. Ovaj vam članak pomaže započeti raditi s okruženjem za poslovne račune. Navodi razlike za područja značajki u uvidima ciljnih skupina, ovisno o fokusu na vaše okruženje. Za dodatne informacije o razlikama pregledajte dokumente područja značajki. 

## <a name="create-an-environment-for-business-accounts"></a>Stvaranje okruženja za poslovne račune

Administratori mogu [stvoriti okruženje u postojećoj tvrtki ili ustanovi](create-environment.md). Korak u procesu stvaranja novog okruženja traži od administratora primarnu ciljnu skupinu okruženja. U slučaju da se radi o početnom postavljanju uvida u ciljnu skupinu nakon kupnje licence, vođeno iskustvo pomaže u stvaranju prvog okruženja.

Tada možete [uvesti podatke](data-sources.md) za poslovne račune i povezane kontakte kao izvore podataka iz svih podržanih izvora.

Nakon objedinjavanja podataka [navedite hijerarhije računa](relationships.md#set-up-account-hierarchies) kao dio konfiguracije odnosa. Također možete [konfigurirati semantička mapiranja](semantic-mappings.md) za povezivanje kontakata i entiteta računa. 

## <a name="switch-between-primary-target-audience"></a>Prebacivanje između primarne ciljne skupine

Ako vaša tvrtka ili ustanova održava okruženja za pojedinačne klijente i poslovne račune, možete upotrijebiti preglednik u lijevom oknu za odabir primarne ciljne skupine.

:::image type="content" source="media/switch-primary-target-audience.PNG" alt-text="Preglednik za promjenu primarne ciljne skupine između pojedinačnih klijenata i poslovnih računa.":::

## <a name="supported-feature-areas"></a>Podržana područja značajke

- [Aktivnosti](activities.md): Podrška za račune i povezane kontakte za stvaranje aktivnosti i njihovo prikazivanje na vremenskoj traci.
- [Odnosi](relationships.md): Čarobnjak za aktivnosti pomaže u stvaranju odnosa između entiteta, tako da prikaz računa može prikazati sve aktivnosti iz kontakata. Kontakti se mogu detaljno pregledati za prikaz kontakata, a hijerarhije se mogu koristiti za agregaciju aktivnosti računa.
- [Mjere](measures.md) : Podržava mjere stvorene od graditelja mjera s jednim izračunom. Neobvezna postavka omogućuje dodavanje podračuna pri stvaranju mjera.
- [Segmenti](segments.md): Podržava segmente koji su stvoreni od nule s pomoću sastavljača segmenata. Novi operatori omogućuju uključivanje hijerarhije računa pri sastavljanju segmenata.
- [Unos podataka](data-sources.md): Sve značajke u ovom području iste su za poslovne račune i pojedinačne klijente.
- [Objedinjavanje podataka](data-unification.md): Sve značajke u ovom području iste su za poslovne račune i pojedinačne klijente.
- [Obogaćivanje](enrichment-hub.md): Neke vrste obogaćivanja dostupne su samo za scenarije pojedinačnih klijenata, dok su druge dostupne samo za poslovne račune.
- [Predviđanja i gotovi modeli](predictions-overview.md): Predviđanje gubitka transakcije sadrži dodatne korake za poslovne račune. Ostala predviđanja dostupna su samo za pojedinačne klijente.
- [Aktivacija i izvoz](export-destinations.md): Izvozi su dostupni za poslovne račune i pojedinačne klijente. Neki izvozi zahtijevaju dodatnu konfiguraciju i podatke za kontakt projicirane u pozadinskim segmentima kako bi bili valjani za poslovne račune.
- [Postavke sustava](system.md) i [upravljanje korisnicima](permissions.md): Sve značajke u ovom području iste su za poslovne račune i pojedinačne klijente.

