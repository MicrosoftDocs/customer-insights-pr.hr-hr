---
title: Korištenje jedinstvenih profila u sustavu Dynamics 365 Marketing
description: Saznajte kako integrirati objedinjene profile i segmente sa sustavom Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4cc3cbde97d0f9da198652e86c0843476393b646
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833299"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Rad s jedinstvenim profilima klijenata u sustavu Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) povećava korisnička iskustva, omogućujući vam organiziranje personaliziranih putovanja na svim dodirnim točkama kako biste ojačali Odnosi i zaradili lojalnost. Aplikacija Dynamics 365 Marketing besprijekorno radi sa sustavom Dynamics 365 Sales, Dynamics 365 Customer Insights, i Microsoft Teams drugim proizvodima te vam omogućuje brže i bolje donošenje odluka pomoću snage podataka i umjetne inteligencije.

Povezivanjem podataka Customer Insights s marketingom možete:

- Ciljajte jedinstvene profile i segmente kupaca. To vam omogućuje da angažirate svakog kupca, bez obzira na lokaciju podataka kupca.
- Osnovni dinamički sadržaj (kao što su personalizirani tokeni) u porukama e-pošte, SMS-ovima i push obavijestima o mjerama kao što su status vjernosti, datum obnove pretplate, nadređeni račun ili bilo koja druga mjera koju ste zabilježili u jedinstvenom profilu customer insights.
- Učitajte podatke iz marketinga u Customer Insights i kombinirajte ih s podacima o kupcima iz drugih izvora.
- Primijenite korisničke uvide u alate za čišćenje, obogaćivanje i nejasno podudaranje podataka.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Koristite bogate profile kupaca u marketingu u stvarnom vremenu

Marketing u stvarnom vremenu omogućuje vam stvaranje [prilagođenih okidača](/dynamics365/marketing/real-time-marketing-custom-triggers) koji pokreću putovanja kupaca na temelju bilo koje akcije kupaca. Što su vaši podaci personaliziraniji, to će vaša putovanja biti relevantnija i personaliziranija. To je ono što kombiniranje marketinga i uvida u kupce čini tako moćnim. Možete [objediniti podatke](data-unification.md) iz bilo kojeg izvora, a zatim ih koristiti za poticanje hiper-personaliziranih putovanja kupaca.

Saznajte više: [Koristite profile i segmente customer insights u marketingu u stvarnom vremenu](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Korištenje jedinstvenih segmenata s odlaznim putovanjima kupaca

Customer Insights omogućuje vam da usavršite podatke iz mnogih izvora i kombinirate ih u agregirane segmente kupaca. Povezivanjem [Customer Insightsa s izlaznim marketingom](export-dynamics365-marketing.md) ti će se segmenti automatski pojaviti *i* automatski osvježiti u put klijenta dizajneru.

Dodatne informacije: [Korištenje segmenata iz Dynamics 365 Customer Insights sustava Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Izvlačenje podataka iz vlastitih Azure Data Lake Storage

Ako želite koristiti podatke customer insights s marketingom, niste ograničeni samo na pohranu u oblaku. Ako ste već sami Azure Data Lake Storage postavili, možete se povezati s Customer Insights, a zatim ih podijeliti s aplikacijom Marketing baš kao što biste to učinili s postavljanjem u oblaku.

Dodatne informacije: [Omogućivanje zajedničkog korištenja podataka s Dataverse vlastitim Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
