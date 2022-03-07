---
title: Započnite s mogućnošću uvida u angažman
description: Pregled resursa za pomoć za brzi početak.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: c435810e712bbbf69f8f1cfb582fc0a971566de6
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225535"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Započnite s mogućnošću uvida u angažman sustava Dynamics 365 Customer Insights (javni pretpregled)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Mogućnost uvida u angažman omogućuje vam prikupljanje i mjerenje ponašanja klijenata na vašoj web-stranici. Integrira se s mogućnošću uvida u ciljnu skupinu, tako da možete vidjeti bogatu analitiku ponašanja u stvarnom vremenu zajedno s izvješćima o profilima klijenata. Veze u ovom članku pomažu vam da brzo konfigurirate i postavite svoje okruženje.

## <a name="step-1-review-prerequisites"></a>1. korak: pregled preduvjeta

Najprije morate imati aktivan korisnički račun Microsoft Azure Active Directory (AAD). Zatim pročitajte sljedeće članke prije postavljanja radnog prostora za uvide u angažmane.

- Pregledajte i složite se s Microsoftovim [Uvjetima pružanja usluge](terms-of-service.md).  
- Pročitajte članak [Upravljanje kolačićima i pristankom korisnika](user-consent-storage.md). Nakon toga procijenite trebate li ažurirati obavijest o pristanku korisnika. Ako prije niste imali „neosnovne” kolačiće, vjerojatno ćete trebati ažurirati pravila svojeg web-mjesta.
- Pregledajte [pojmovnik](glossary.md) za brzo upoznavanje s ključnim pojmovima i konceptima.

## <a name="step-2-explore-engagement-insights"></a>Korak 2: Istraživanje uvida o angažmanu

Prilikom prvog posjeta uvidima u angažman, možete konfigurirati postavke, pregledati pravila i istražiti mogućnost.

1. Prijavite se u [portal sposobnosti uvida u angažman](https://home.ci.ai.dynamics.com/app/engagement-insights) koristeći svoj Microsoftov korisnički račun AAD (školski ili poslovni).

1. Odaberite svoju regiju i potvrdite okvir ako se želite uključiti u primanje ažuriranja i ponuda putem e-pošte.

1. Pregledajte **Uvjete korištenja** uvida u angažman (pretpregled) i **Izjavu o zaštiti privatnosti**, a zatim odaberite **Istraži demo verziju** da biste prihvatili ove postavke.

1. Istražite proizvod pomoću skupa uzoraka podataka.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>3. korak: Postavite radni prostor i stvorite izvješća

Radni prostor mjesto je gdje možete vidjeti aktivnosti korisnika u stvarnom vremenu te pohraniti izvješća i upravljati njima. Dodajte kod na svoje web-mjesto da biste započeli prikupljati *događaje*, podatke o aktivnostima koji dolaze od korisnika.

1. [Stvorite radni prostor](create-workspace.md) i dodajte članove.

1. Dodajte kod na svoje [web-mjesto](instrument-website.md) ili [mobilnu aplikaciju](developer-resources.md#capture-events-from-mobile-apps) da biste vidjeli aktivnosti korisnika kako stižu u vaš radni prostor.

1. Pogledajte [izvješće u stvarnom vremenu](view-reports.md) koje prikazuje aktivne korisnike prema pregledniku, uređaju, operacijskom sustavu, lokaciji i jeziku. Možete stvarati i [prilagođena izvješća](custom-reports.md) da biste stvorili vlastite vizualizacije.

1. Stvorite [dimenzije](dimensions.md) da biste razvrstali posjetitelje prema novim i korisnicima koji se vraćaju, [metriku](metrics.md) radi boljeg razumijevanja ponašanja korisnika i [segmente](segments.md) da biste identificirali podskup posjetitelja na temelju karakteristika ili interakcija s web-mjestom.
    
## <a name="step-4-export-data-to-other-channels"></a>Korak 4: Izvoz podataka na ostale kanale

Možete stvoriti *pročišćene događaje* (virtualni prikaz) vaših podataka web-analitike. Zatim filtrirajte i izvezite podatke u Azure Data Lake Storage. Izvezene podatke možete unijeti kao izvor podataka.

1. [Stvorite pročišćene događaje](refined-events.md) za izvoz.

1. [Izvezite podatke](export-events.md) u Azure Data Lake Storage.

1. [Stvorite vezu između uvida u ciljnu skupinu i uvida u angažman](integrate-audience-insights-engagement-insights.md) za dijeljenje podataka između dviju mogućnosti.

1. [Prepoznajte web-događaje od prethodno provjerenih korisnika](unknown-to-known.md) uz značajku **od nepoznatog do poznatog**.

1. Saznajte kako [izbrisati i izvesti podatke o događajima koji sadrže osobne podatke](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>5. korak: Stvorite izvješća o kanalu i upravljajte njima

Izvješće o kanalu prikuplja informacije o koracima koji se događaju tijekom puta klijenta kroz vašu web stranicu ili mobilnu aplikaciju. Osim što možete stvoriti gotova izvješća o profilima i prilagođena izvješća, možete stvoriti i izvješće o kanalu kako biste identificirali putanje koje vaši klijenti prolaze prije nego što izvrše kupnju. 

1. [Stvorite izvješće o kanalu](funnel-reports.md) da biste donijeli informirane odluke i identificirali područja za optimizaciju i poboljšanja procesa.

1. Stvorite izvješća o višekanalnim tokovima nakon što svoju mobilnu aplikaciju upoznate s uvidima u angažman [Android SDK](get-started-android.md) ili [iOS SDK](get-started-ios.md).

1. Koristite [uvide u kanal](funnel-reports.md#funnel-insights) kako biste stekli dublji uvid u ponašanje klijenta o koracima u izvješću o kanalu.
 
## <a name="step-6-stay-connected"></a>Korak 6: Ostanite povezani

Cijenimo vaše aktivno sudjelovanje i razmatramo sve relevantne povratne informacije u razvoju budućih izdanja. Podijelite svoje povratne informacije i prijavite probleme na jednom od ovih kanala:
- [Zajednica](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Pošaljite povratne informacije](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Zahtjev za podršku](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
