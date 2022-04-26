---
title: Nove i nadolazeće značajke
description: Informacije o novim značajkama, poboljšanjima i ispravcima programskih pogrešaka.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547663"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Što je novo u mogućnosti uvida u ciljnu skupinu Dynamics 365 Customer Insights

Sa zadovoljstvom objavljujemo naša najnovija ažuriranja! Ovaj članak daje javni pretpregled značajki, poboljšanja opće dostupnosti i ažuriranja značajki. Kako biste vidjeli dugoročne planove značajki, pogledajte članak [Raspored izdanja sustava Dynamics 365 i rješenje Power Platform](/dynamics365/release-plans/).

Ažuriranja unosimo po regijama. Tako bi neke regije mogle vidjeti značajke prije drugih. Ako nije drugačije određeno, ne morate poduzimati ništa i automatski ćemo ažurirati aplikaciju bez prekida u radu.

> [!TIP]
> Za kontakt i glasanje o zahtjevima za značajkama i prijedlozima o proizvodu idite na [portal sa zamislima za aplikacije Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>Ažuriranja za ožujak 2022.

Ažuriranja u ožujku 2022. uključuju nove značajke, nadogradnje performansi i ispravke pogrešaka.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec obogaćivanje (Preview)

LiveRamp pruža razlučivost identiteta i konsolidaciju korisničkih podataka. Osobne identifikatore u svojim podacima o kupcima možete mapirati na grafikon identiteta tvrtke AbiliTec i primati AbiliTec ID-ove. Zatim možete koristiti te ID-ove za bolje ujedinjenje podataka o kupcima.

Dodatne informacije potražite u članku [Obogaćivanje korisničkih profila podacima o identitetu s LiveRampa (Pretpregled)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organiziranje segmenata i mjera pomoću oznaka i filtara
Ako vaša organizacija održava mnogo segmenata ili mjera, pronalaženje pravog ponekad se može osjećati izazovno. Ova nova značajka omogućuje organiziranje popisa pomoću oznaka i stupaca. Pomaže u brzom i jednostavnom pronalaženju podataka i prilagodbi prikaza.

Dodatne informacije potražite u članku [Rad s oznakama i stupcima](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Omogućivanje zajedničkog korištenja podataka s Dataverse pomoću vlastitog računa za pohranu

Ako se vaše okruženje koristi Azure Data Lake Storage za pohranu podataka Customer Insights, za dijeljenje Microsoft Dataverse podataka potrebna je dodatna konfiguracija.
Ranije ste mogli omogućiti dijeljenje podataka samo kada Dataverse su vaši podaci pohranjeni u našem upravljanom jezeru podataka. 

Dodatne informacije potražite u članku [Omogućivanje zajedničkog korištenja podataka s Dataverse pomoću vlastitog Azure Data Lake Storage (pretpregleda)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Nova izvozna odredišta: Iterable i Braze

Nastavljamo širiti naš ekosustav izvoznih odredišta novim vezama. Sada možete izvoziti segmente u Iterable i Braze kako biste koristili njihove usluge aktivacije.

Dodatne informacije potražite u člancima [Izvoz segmenata u segmente iterable (pretpregled)](export-iterable.md) i [Izvoz u braze (pretpregled)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Poboljšanja izvoza Marketa i Google Adsa

Promjena API-ja u povezanim uslugama dovodi do ažuriranja za pouzdano i glatko pokretanje poveznika. Objavili smo neka ažuriranja za izvoz u Marketo i Google Ads usluge:

- Google Ads: nova verzija Google Adsovog poveznika za izvoz pojednostavljuje doživljaj provjere autentičnosti i sada vam omogućuje automatsko stvaranje nove publike na Google Adsu. 
- Marketo: Nova verzija marketo izvoznog poveznika pruža podršku za Marketo ID, omogućujući vam da izbjegnete udvostručavanje podataka, ažurirate postojeće zapise i stvorite nove zapise u Marketu. 


## <a name="february-2022-updates"></a>Ažuriranja za veljaču 2022.

Ažuriranja u veljači 2022. uključuju nove značajke, nadogradnje performansi i ispravke pogrešaka.

### <a name="general-availability-for-prediction-models"></a>Opća dostupnost za predviđanje modele

Gotovi modeli predviđanje, uključujući **prijenos** pretplate, **transakcijski bućkuriš** i **vrijednost životnog vijeka korisnika (CLV)** postaju općenito dostupni kao dio Customer Insights. 

Dodatne informacije potražite u članku [Pregled](predictions-overview.md) predviđanja.

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Novi izvor podataka: integracija s (pretpregledom Azure Synapse Analytics)

Azure Synapse Analytics je usluga analitike poduzeća koja ubrzava vrijeme do uvida u skladišta podataka i big data sustava.

Organizacije koje već koriste Azure Synapse Analytics mogu unijeti te podatke u Customer Insights. 

Dodatne informacije potražite u članku [Povezivanje Azure Synapse izvor podataka (pretpregled)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp obogaćivanje (Preview)

LiveRamp pruža razlučivost identiteta i konsolidaciju korisničkih podataka. Osobne identifikatore u svojim podacima o kupcima možete mapirati na grafikon identiteta tvrtke AbiliTec i primati AbiliTec ID-ove. Zatim možete koristiti te ID-ove za bolje ujedinjenje podataka o kupcima.

Dodatne informacije potražite u članku [Obogaćivanje korisničkih profila podacima o identitetu s LiveRampa (Pretpregled)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Obogaćivanje za izvore podataka (Pretpregled)

Koristite podatke iz izvora kao što su Microsoft i drugi partneri da biste obogatili svoje korisničke podatke prije ujedinjenja podataka. Izvor podataka obogaćivanja pomažu u stvaranju veće cjelovitosti i kvalitete podataka koji mogu pomoći u postizanju boljih rezultata nakon što objedinite svoje podatke.

Dodatne informacije potražite u članku [Obogaćivanje izvora podataka (pretpregled)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Promijeni vlasnika okruženja

Iako nekoliko korisnika može imati administratorske dozvole u Customer Insights, samo je jedan korisnik vlasnik okruženja. Poboljšano iskustvo omogućuje vam promjenu vlasnika okruženja i preuzimanje vlasništva ako je bivši vlasnik napustio organizaciju. 

Dodatne informacije potražite u članku [Promjena vlasnika okruženja](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>U procesu pripreme podataka naveden je razlog oštećenja oštećenih zapisa

Priprema podataka sada prikazuje razlog oštećenja za sva polja s oštećenim podacima. Informacije se pružaju na pojedinačnoj razini evidencije radi lakše identifikacije. 

Dodatne informacije potražite u odjeljku [Oštećeni izvori](entities.md#corrupted-data-sources) podataka.

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Kraj pretpregleda za značajke izvješćivanja u mogućnosti uvida u angažman

Pregled Dynamics 365 Customer Insights sposobnosti uvida u angažman završio je 15. veljače 2022.  
Ta promjena znači da probno iskustvo Customer Insights više ne uključuje mogućnost stvaranja tokova niti drugih funkcija izvješćivanja.

Pozivamo vas da istražite i procijenite [mnoge druge značajke Customer Insights, Microsoftove platforme za korisničke](https://dynamics.microsoft.com/ai/customer-insights/) podatke (CDP).    
 
U prijelaznom razdoblju postojeći sudionici pretpregleda i dalje imaju pristup nekim mogućnostima i funkcijama pretpregleda:

- Dobijte kod za instrument web-mjesta ili mobilne aplikacije 
- Prikaz događaja i svojstava događaja 
- Poboljšajte jedinstvene profile s unesenim i rafiniranim događajima kako biste imali koristi od pune vrijednosti njihovih korisničkih podataka
  
Tijekom prijelaznog razdoblja zabilježeni događaji i dalje se prenose na povezano jezero podataka. Nakon što se ta funkcionalnost isključi, razmjena podataka između uvida u angažman i uvida u publika prestat će i neće se slati novi događaji u povezanu pohranu.
Ako imate pitanja o završetku pretpregleda mogućnosti, obratite se izravno timu za Microsoftov račun. Vaš tim računa obavještavat će vas o nadolazećim lansiranjima. 

## <a name="january-2022-updates"></a>Ažuriranja iz siječnja 2022.

Ažuriranja u siječnju 2022. uključuju nove značajke, nadogradnje performansi i ispravke pogrešaka.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analiza naklonosti povratnih informacija vašeg kupca

Customer Insights pruža novu značajku koju pokreće umjetna inteligencija kako bi sintetizirala raspoloženje kupaca i identificirala određene poslovne aspekte kao prilike za ciljana poboljšanja. Analizom pisanih povratnih informacija vaših kupaca možete dobiti točne uvide po niskoj cijeni. Analiza naklonosti koju pokreću modeli obrade prirodnog jezika (NLP) koji generiraju dva izvedena uvida za svaki ID kupca. Ocjena naklonosti (od –5 do 5) i popis primjenjivih poslovnih aspekata. 

Dodatne informacije potražite u članku [Analiza naklonosti u povratnim informacijama korisnika (Pretpregled)](sentiment-analysis.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]