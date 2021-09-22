---
title: Započnite s mogućnošću uvida u angažman
description: Pregled resursa za pomoć za brzi početak.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405349"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Započnite s mogućnošću uvida u angažman sustava Dynamics 365 Customer Insights (javni pretpregled)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Mogućnost uvida u angažman omogućuje vam prikupljanje i mjerenje ponašanja klijenata na vašoj web-stranici. Integrira se s mogućnošću uvida u ciljnu skupinu, tako da možete vidjeti bogatu analitiku ponašanja u stvarnom vremenu zajedno s izvješćima o profilima klijenata. Veze u ovom članku pomažu vam da brzo konfigurirate i postavite svoje okruženje.

## <a name="step-1-review-prerequisites"></a>1. korak: pregled preduvjeta

Najprije morate imati aktivan Microsoft Azure Active Directory korisnički račun. Zatim pročitajte sljedeće članke prije postavljanja radnog prostora za uvide u angažmane.

- Pregledajte i složite se s Microsoftovim [Uvjetima pružanja usluge](terms-of-service.md).  
- Pročitajte članak [Upravljanje kolačićima i pristankom korisnika](user-consent-storage.md). Nakon što pregledate ovaj članak, procijenite trebate li ažurirati obavijest o pristanku korisnika. Ako prije niste imali „neosnovne” kolačiće, vjerojatno ćete trebati ažurirati pravila svojeg web-mjesta.
- Pregledajte [pojmovnik](glossary.md) za brzo upoznavanje s ključnim pojmovima i konceptima.

## <a name="step-2-explore-engagement-insights"></a>Korak 2: Istraživanje uvida o angažmanu

Kada prvi put posjetite uvide o angažmanu, možete konfigurirati postavke, pregledati pravila i istražiti proizvod.

1. Prijavite se na [portal za mogućnost uvida u angažman](https://pi.dynamics.com) pomoću svojeg Microsoft Azure Active Directory korisničkog računa. (To može biti vaš školski ili poslovni račun.)

1. Odaberite svoju regiju i pomoću potvrdnog okvira naznačite želite li se uključiti u primanje ažuriranja i ponuda putem e-pošte.

1. Pregledajte **Uvjete korištenja uvida u angažman (pretpregled)** i **Izjavu o zaštiti privatnosti**, a zatim odaberite **Istraži pokaznu verziju** da biste ih prihvatili.

1. Istražite proizvod pomoću skupa uzoraka podataka.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Korak 3: Postavljanje radnog prostora i dodavanje koda na svoje web-mjesto

Radni prostor mjesto je na kojem možete pregledavati aktivnost korisnika u stvarnom vremenu te pohranjivati i upravljati izvješćima. Dodajte kod na svoje web-mjesto da biste započeli prikupljati *događaje*, podatke o aktivnostima koji dolaze od korisnika.

1. [Stvorite radni prostor](create-workspace.md) i dodajte članove.

1. [Dodajte kod na svoje web-mjesto](instrument-website.md) ili [mobilnu aplikaciju](developer-resources.md#capture-events-from-mobile-apps) da biste vidjeli aktivnosti korisnika kako stižu u vaš radni prostor.

1. Pregledajte [izvješće u stvarnom vremenu](view-reports.md) koje prikazuje aktivne korisnike prema pregledniku, uređaju, operacijskom sustavu, mjestu i jeziku. Možete stvarati i [prilagođena izvješća](custom-reports.md) da biste stvorili vlastite vizualizacije.
    
## <a name="step-4-export-data-to-other-channels"></a>Korak 4: Izvoz podataka na ostale kanale

Možete stvoriti *pročišćene događaje* (virtualni prikaz) vaših podataka web-analitike. Zatim filtrirajte i izvezite podatke u Azure Data Lake Storage. Izvezene podatke možete unijeti kao izvor podataka. Više informacija potražite u članku [Izrada veze između uvida u ciljnu skupinu i uvida u angažman](integrate-audience-insights-engagement-insights.md).

1. [Stvorite pročišćene događaje](refined-events.md) za izvoz.

1. [Izvezite podatke](export-events.md) u Data Lake Storage.

1. Saznajte kako [izbrisati i izvesti podatke o događajima koji sadrže osobne podatke](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Korak 5: Ostanite povezani

Cijenimo vaše aktivno sudjelovanje i planiramo razmotriti sve relevantne povratne informacije u razvoju budućih izdanja. Podijelite svoje povratne informacije i prijavite probleme na jednom od ovih kanala:
- [Zajednica](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Pošaljite povratne informacije](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Zahtjev za podršku](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
