---
title: Što je novo u sustavu Dynamics 365 Customer Insights
description: Informacije o novim značajkama, poboljšanjima i ispravcima programskih pogrešaka.
ms.date: 06/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: f3ae0fe6631ee7c8d79664528be383ec53e93fe8
ms.sourcegitcommit: 92e5a798ca75c7f10aa5025a9bbd2ffb4d4ae7d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/05/2022
ms.locfileid: "9114237"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Što je novo u sustavu Dynamics 365 Customer Insights

Sa zadovoljstvom objavljujemo naša najnovija ažuriranja! Ovaj članak daje javni pretpregled značajki, poboljšanja opće dostupnosti i ažuriranja značajki. Kako biste vidjeli dugoročne planove značajki, pogledajte članak [Raspored izdanja sustava Dynamics 365 i rješenje Power Platform](/dynamics365/release-plans/).

Ažuriranja unosimo po regijama. Tako bi neke regije mogle vidjeti značajke prije drugih. Ako nije drugačije navedeno, ne morate poduzimati nikakve radnje, automatski ćemo ažurirati aplikaciju bez zastoja.

> [!TIP]
> Za kontakt i glasanje o zahtjevima za značajkama i prijedlozima o proizvodu idite na [portal sa zamislima za aplikacije Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="june-2022-updates"></a>Ažuriranja za lipanj 2022.

Ažuriranja u lipnju 2022. uključuju nove značajke, nadogradnje performansi i ispravke pogrešaka.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Ažurirano korisničko iskustvo za izvore podataka i unos podataka

Uvoz podataka iz širokog spektra izvora podataka temelj je konsolidacije podataka o klijentima u sustavu Dynamics 365 Customer Insights. Ponovno smo pregledali korisničko iskustvo za uvoz i povezivanje izvora podataka. Ovo ažuriranje ima za cilj olakšati vam unos podataka u Customer Insights.

Dodatne informacije potražite u članku [Pregled izvora podataka](data-sources.md).

### <a name="export-to-inmobi"></a>Izvoz u InMobi

InMobi pomaže robnim markama da razumiju, identificiraju, angažiraju i steknu potrošače. Segmente i druge podatke možete izvesti u uslugu InMobi putem računa servisa Azure Blob Storage.

Dodatne informacije potražite u članku [Izvoz u InMobi (pretpregled)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>Podrška za Lockbox u odjeljku Customer Insights

Customer Lockbox pruža sučelje za pregled i odobravanje (ili odbijanje) zahtjeva za pristup podacima. Ti se zahtjevi javljaju kada je za rješavanje slučaja podrške potreban pristup podacima o klijentima.

Dodatne informacije potražite u članku [Siguran pristup podacima o klijentima pomoću značajke Customer Lockbox (Pretpregled)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview).

### <a name="connect-to-your-data-using-azure-private-link"></a>Povezivanje s podacima pomoću veze servisa Azure Private Link

Azure Private Link omogućuje uvidima u korisnike da se povežu s vašim Azure Data Lake Storage računom putem privatnog krajnja točka u vašoj virtualnoj mreži. Za podatke na računu za pohranu, koji nije izložen javnom internetu, Private Link omogućuje vezu s tom ograničenom mrežom.

Dodatne informacije potražite u članku [Korištenje privatne veze u odjeljku Uvidi](security-overview.md#private-links-tab) kupaca.

## <a name="may-2022-updates"></a>Ažuriranja za svibanj 2022.

Ažuriranja u svibnju 2022. uključuju nove značajke, nadogradnje performansi i ispravke pogrešaka.

### <a name="updated-data-unification-experience"></a>Ažurirano iskustvo objedinjavanja podataka

 Objedinjavanje podataka omogućuje vam objedinjavanje jednom različitih izvora podataka u jedan skup glavnih podataka koji pruža jedinstveni prikaz tih podataka. Podaci se mogu objediniti u jednom entitetu ili više entiteta. Najprije odabirete entitete i izvorišna polja, uklanjate duplicirane zapise [, određujete pravila za](map-entities.md) podudarne uvjete [i definirate koja](remove-duplicates.md) polja želite uključiti u objedinjene [profile klijenata.](match-entities.md)[...](merge-entities.md)

Dodatne informacije potražite u članku [Pregled](data-unification.md) ujedinjenja podataka.

### <a name="refreshed-home-page-in-customer-insights"></a>Osvježena početna stranica u odjeljku Uvidi kupaca

**Home** vas vodi kroz postupak konfiguracije ključnih značajki i pruža pregled podataka o segmentima, mjerama i obogaćivanju. Osvježili smo doživljaj kako bismo pružili relevantnije informacije na prvi pogled.

Dodatne informacije potražite u članku [Istraživanje uvida](home.md) kupaca.

### <a name="track-usage-of-a-segment"></a>Praćenje korištenja segmenta

Sada [možete pratiti upotrebu segmenta](segments.md#track-usage-of-a-segment) u aplikacijama koje se temelje na organizaciji koja je povezana Dataverse s Customer Insights. Za [segmente Customer Insights koji se koriste u korisničkim putovanjima sustava Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), sustav vas informira o korištenju tog segmenta.

### <a name="export-to-criteo"></a>Izvoz u Criteo

Criteo je internetska platforma koja pomaže korisnicima u upravljanju digitalnim oglašavanjem. Sada možete izvesti segmente jedinstvenih profila kupaca za generiranje kampanja, pružanje marketinga putem e-pošte i korištenje određenih grupa kupaca s Criteom.

Dodatne informacije potražite u članku [Izvoz segmenata u Criteo (pretpregled)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Rafinirana struktura dokumentacije za stvaranje okruženja

Ponovno smo razmotrili dokumente pomoći povezane sa stvaranjem okruženja i upravljanjem okruženjima u customer insights. Članci su sada grupirani pod čvorom Okruženja u tablici sadržaja. Restrukturirani članci pružaju više smjernica za različite načine postavljanja okruženja i jasniju strukturu. Ako imate povratne informacije za dijeljenje, javite nam putem kontrola pred kraj članaka pomoći.

Dodatne informacije potražite pod [Kako: stvoriti novo okruženje](create-environment.md).

## <a name="april-2022-updates"></a>Ažuriranja za travanj 2022.

Ažuriranja u travnju 2022. uključuju nove značajke, nadogradnje performansi i ispravke pogrešaka.

### <a name="dun--bradstreet-enrichment-preview"></a>Obogaćivanje Dun & Bradstreeta (Preview)

Dun & Bradstreet pruža komercijalne podatke, analitiku i uvide za tvrtke. Klijentima pruža objedinjene korisničke profile kako bi tvrtke obogatile svoje podatke. Obogaćivanja uključuju atribute kao što su DUNS broj, veličina tvrtke, lokacija, industrija i još mnogo toga.

Više informacija potražite u odjeljku [Obogaćivanje profila tvrtke dun & bradstreet (preview)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Definiranje vrste mjere prilikom kreiranja nove mjere

Sada možete razlikovati mjere za pojedinačne profile i mjere u cijelom poslovanju. Iako se poslovne mjere prikazuju na početnoj stranici Customer Insights, mjere kupaca izložene su detaljnim prikazima kupaca.

Dodatne informacije potražite u članku [Stvaranje mjera pomoću sastavljača mjera od nule](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Konsolidacija dokumentacije customer insights

Ponovno smo pregledali članke o dokumentaciji i uklonili spominjanja uvida u angažman i mogućnosti uvida u publika. Napredujući, dosljedno ćemo se pozivati na naziv proizvoda Customer Insights kada budemo pisali o osnovnim značajkama aplikacije. Ova promjena također dovodi do značajnog restrukturiranja tablice sadržaja, strukture URL-a i putova datoteka u repozitoriju temeljne dokumentacije. Sve vaše knjižne oznake ili postojeće veze nastavljaju raditi i preusmjeravati ih na ažurirane URL-ove.

Ako nas želite obavijestiti kako doživljavate tu promjenu ili uočite da nešto ne radi kako se očekivalo, recite nam slanjem [povratnih informacija za ovu stranicu](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Ažuriranja za ožujak 2022.

Ažuriranja u ožujku 2022. uključuju nove značajke, nadogradnje performansi i ispravke pogrešaka.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec obogaćivanje (Preview)

LiveRamp pruža razlučivost identiteta i konsolidaciju korisničkih podataka. Osobne identifikatore u svojim podacima o kupcima možete mapirati na grafikon identiteta tvrtke AbiliTec i primati AbiliTec ID-ove. Zatim možete koristiti te ID-ove za bolje ujedinjenje podataka o kupcima.

Dodatne informacije potražite u članku [Obogaćivanje korisničkih profila podacima o identitetu s LiveRampa (Pretpregleda)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organiziranje segmenata i mjera pomoću oznaka i filtara

Ako vaša organizacija održava mnogo segmenata ili mjera, pronalaženje pravog ponekad se može osjećati izazovno. Ova nova značajka omogućuje organiziranje popisa pomoću oznaka i stupaca. Pomaže u brzom i jednostavnom pronalaženju podataka i prilagodbi prikaza.

Dodatne informacije potražite u članku [Rad s oznakama i stupcima](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Omogućivanje zajedničkog korištenja podataka s Dataverse pomoću vlastitog računa za pohranu

Ako se vaše okruženje koristi Azure Data Lake Storage za pohranu podataka Customer Insights, za dijeljenje Microsoft Dataverse podataka potrebna je dodatna konfiguracija.
Ranije ste mogli omogućiti dijeljenje podataka samo kada Dataverse su vaši podaci pohranjeni u našem upravljanom jezeru podataka.

Dodatne informacije potražite u članku [Omogućivanje zajedničkog korištenja podataka s Dataverse pomoću vlastitog Azure Data Lake Storage (pretpregleda)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

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

Dodatne informacije potražite u članku [Obogaćivanje korisničkih profila podacima o identitetu s LiveRampa (Pretpregleda)](enrichment-liveramp.md).

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
  
Tijekom prijelaznog razdoblja zabilježeni događaji i dalje se prenose na povezano jezero podataka. Nakon što se ta funkcija isključi, dijeljenje podataka će se zaustaviti i nijedan novi događaj neće se slati u povezanu pohranu.
Ako imate pitanja o završetku pretpregleda mogućnosti, obratite se izravno timu za Microsoftov račun. Vaš tim računa obavještavat će vas o nadolazećim lansiranjima. 

## <a name="january-2022-updates"></a>Ažuriranja iz siječnja 2022.

Ažuriranja u siječnju 2022. uključuju nove značajke, nadogradnje performansi i ispravke pogrešaka.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analiza naklonosti povratnih informacija vašeg kupca

Customer Insights pruža novu značajku koju pokreće umjetna inteligencija kako bi sintetizirala raspoloženje kupaca i identificirala određene poslovne aspekte kao prilike za ciljana poboljšanja. Analizom pisanih povratnih informacija vaših kupaca možete dobiti točne uvide po niskoj cijeni. Analiza naklonosti koju pokreću modeli obrade prirodnog jezika (NLP) koji generiraju dva izvedena uvida za svaki ID kupca. Ocjena naklonosti (od –5 do 5) i popis primjenjivih poslovnih aspekata. 

Dodatne informacije potražite u članku [Analiza naklonosti u povratnim informacijama klijenta (Pretpregled)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]