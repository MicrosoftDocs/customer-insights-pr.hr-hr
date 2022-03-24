---
title: Nove i nadolazeće značajke
description: Informacije o novim značajkama, poboljšanjima i ispravcima programskih pogrešaka.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 9195770255bd798636b9532d6e1ca928345b3708
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376453"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Što je novo u mogućnosti uvida u ciljnu skupinu Dynamics 365 Customer Insights

Sa zadovoljstvom objavljujemo naša najnovija ažuriranja! Ovaj članak daje javni pretpregled značajki, poboljšanja opće dostupnosti i ažuriranja značajki. Kako biste vidjeli dugoročne planove značajki, pogledajte članak [Raspored izdanja sustava Dynamics 365 i rješenje Power Platform](/dynamics365/release-plans/).

Ažuriranja unosimo po regijama. Tako bi neke regije mogle vidjeti značajke prije drugih. Ako nije drugačije određeno, ne morate poduzimati ništa i automatski ćemo ažurirati aplikaciju bez prekida u radu.

> [!TIP]
> Za kontakt i glasanje o zahtjevima za značajkama i prijedlozima o proizvodu idite na [portal sa zamislima za aplikacije Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="february-2022-updates"></a>Ažuriranja za veljaču 2022.

Ažuriranja u veljači 2022. uključuju nove značajke, nadogradnje performansi i ispravke pogrešaka.

### <a name="general-availability-for-prediction-models"></a>Opća dostupnost za predviđanje modele

Gotovi modeli predviđanje, uključujući **prijenos** pretplate, **transakcijski bućkuriš** i **vrijednost životnog vijeka korisnika (CLV)** postaju općenito dostupni kao dio Customer Insights. 

Dodatne informacije potražite u članku [Pregled predviđanja](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Novi izvor podataka: integracija s (pretpregledom Azure Synapse Analytics)

Azure Synapse Analytics je usluga analitike poduzeća koja ubrzava vrijeme do uvida u skladišta podataka i big data sustava.

Ako vaša tvrtka ili ustanova već koristi za napredne analitičke Azure Synapse Analytics mogućnosti i pohranjuje izlaz u bazama podataka servisa Data Lake, te podatke možete jednostavno unijeti u Customer Insights. Dodatne informacije potražite u članku [Povezivanje Azure Synapse izvor podataka (pretpregled)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp obogaćivanje (Preview)

LiveRamp pruža determinističko izvanmrežno rješavanje identiteta i konsolidaciju korisničkih podataka. Osobne identifikatore u svojim podacima o kupcima možete mapirati na grafikon identiteta tvrtke AbiliTec i primati AbiliTec ID-ove. Zatim možete koristiti te ID-ove za bolje ujedinjenje podataka o kupcima.

Dodatne informacije potražite u članku [Obogaćivanje korisničkih profila podacima o identitetu s LiveRampa (Pretpregleda)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Obogaćivanje za izvore podataka (Pretpregled)

Koristite podatke iz izvora kao što su Microsoft i drugi partneri da biste obogatili svoje korisničke podatke prije ujedinjenja podataka. Izvor podataka obogaćivanja pomažu u stvaranju veće cjelovitosti i kvalitete podataka koji mogu pomoći u postizanju boljih rezultata nakon što objedinite svoje podatke.

Dodatne informacije potražite u članku [Obogaćivanje izvora podataka (pretpregled)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Promijeni vlasnika okruženja

Iako nekoliko korisnika može imati administratorske dozvole u Customer Insights, samo je jedan korisnik vlasnik okruženja. Poboljšano iskustvo omogućuje vam promjenu vlasnika okruženja i preuzimanje vlasništva ako je bivši vlasnik napustio organizaciju. 

Dodatne informacije potražite u članku [Promjena vlasnika okruženja](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>U procesu pripreme podataka naveden je razlog oštećenja oštećenih zapisa

Postupak pripreme podataka sada prikazuje razlog korupcije za sva polja s oštećenim podacima na pojedinačnoj razini zapisa radi lakše identifikacije. 

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

Dodatne informacije potražite u članku [Analiza naklonosti u povratnim informacijama klijenta (Pretpregled)](sentiment-analysis.md).


## <a name="december-2021-updates"></a>Ažuriranja u prosincu 2021.

Ažuriranja u prosincu 2021. uključuju nove značajke, nadogradnje performansi i ispravke pogrešaka.

### <a name="forward-customer-insights-logs-to-azure-monitor"></a>Prosljeđivanje zapisnika korisničkih uvida u Azure Monitor

Customer Insights omogućuje izravnu integraciju s azure monitorom. Ova značajka uključuje revizijske događaje i operativne događaje. Zapisnici resursa azure monitora omogućuju vam praćenje i slanje zapisnika u Azure Storage, Azure Log Analytics ili njihovo strujanje na Azure Središta događaja.

Dodatne informacije potražite u [članku Dynamics 365 Customer Insights Prijava prosljeđivanja pomoću servisa Azure Monitor (Pretpregled)](diagnostics.md).

### <a name="enrich-customer-profiles-with-engagement-data"></a>Obogatite profile kupaca podacima o angažmanu

Koristite podatke iz Microsoft Office 365 da biste obogatili profile svojih korisničkih računa uvidima u angažmane putem Office 365 aplikacija. Podaci o angažmanu sastoje se od aktivnosti e-pošte i sastanka, koja se agregira na razini računa. Na primjer, broj e-poruka s poslovnog računa ili broj sastanaka s računom. Ne dijele se podaci o pojedinačnim korisnicima. Ovo obogaćivanje dostupno je u sljedećim regijama: Velika Britanija, Europa, Sjeverna Amerika.

Dodatne informacije potražite u članku [Obogaćivanje profila korisnika podacima o angažmanu (pretpregled)](enrichment-office.md).

### <a name="advanced-data-unification-features"></a>Dodatne značajke objedinjavanja podataka

#### <a name="enable-conflict-resolution-policies-at-the-individual-attribute-level"></a>Omogućivanje pravila za rješavanje sukoba na razini pojedinačnog atributa

Prilikom dedupliciranja zapisa o klijentima unutar entiteta, možda nećete htjeti odabrati cijeli zapis kao pobjednika. Sada vam omogućujemo spajanje najboljih polja iz različitih zapisa na temelju pravila za svaki atribut. Na primjer, možete odabrati zadržavanje najnovije e-pošte I najcjelovitije adrese iz različitih zapisa. 

Sada možete definirati zasebna pravila spajanja za pojedinačne atribute dok deduplicirate i spajate zapise unutar jednog entiteta. Prethodno smo vam omogućili da odaberete samo jedno pravilo spajanja (vođenje evidencije na temelju cjelovitosti podataka o recesiji) i to se pravilo primijenilo na razini zapisa na sve atribute. To nije idealno kada se neki podaci koje želite zadržati nađu u evidenciji A i drugi dobri podaci koji se nalaze u zapisu B.

Više informacija pogledajte u [Definirajte uklanjanje duplikata u entitetu podudarnosti](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="custom-rules-for-matching"></a>Prilagođena pravila za podudaranje

Postoje slučajevi kada trebate navesti iznimku od općih pravila kako ne biste odgovarali zapisima. To se može dogoditi kada više pojedinaca podijeli dovoljno informacija kako bi ih sustav odgovarao kao jednu osobu. Na primjer, blizanci s istim prezime, žive u istom gradu i dijele datum rođenja.

Iznimkama se osigurava da se u pravilima ujedinjenja može riješiti netočno ujedinjenje podataka. Pravilu možete dodati više iznimaka.

Dodatne informacije potražite u članku [Dodavanje iznimaka pravilu](match-entities.md#add-exceptions-to-a-rule).

#### <a name="provide-additional-conflict-resolution-policies-and-enable-grouping-of-attributes"></a>Navedite dodatna pravila za rješavanje sukoba i omogućite grupiranje atributa

Ova značajka omogućuje vam da grupu polja tretirate kao jednu jedinicu. Na primjer, kada naši zapisi sadrže polja Adresa1, Adresa2, Grad, Država i Zip. Vjerojatno se ne želimo spojiti u adresu drugog zapisa2, misleći da će to učiniti naše podatke potpunijima.

Sada možete kombinirati grupu povezanih polja i primijeniti jedno pravilo spajanja na grupu. 

Dodatne informacije potražite u članku [Kombiniranje grupe polja](merge-entities.md#combine-a-group-of-fields).


## <a name="november-2021-updates"></a>Ažuriranja obavljena u studenom 2021.

Ažuriranja u studenom 2021. uključuju nove značajke, nadogradnje performansi i ispravke pogrešaka.

### <a name="segment-membership-now-available-in-dataverse"></a>Članstvo u segmentu sada je dostupno u programu Dataverse

Podaci o članstvu u Dataverse segmentu za korisničke profile sada su dostupni zajedno s profilima i uvidima kupaca. Akcijske aplikacije sustava Dynamics 365 i aplikacije stvorene prema modelu mogu koristiti te podatke za traženje podataka o članstvu u segmentu za određenog kupca.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>Aktivnosti podržavaju detalje na razini kontakta za poslovne račune

Sada možete konfigurirati, prikazati i filtrirati aktivnosti za kontakte na vremenskim crtama aktivnosti vašeg poslovnog računa kako biste bolje razumjeli koji su kontakti poslovnog subjekta sudjelovali u određenim aktivnostima.

## <a name="october-2021-updates"></a>Ažuriranja iz listopada 2021.

Ažuriranja u listopadu 2021. uključuju nove značajke, nadogradnje performansi i ispravke pogrešaka.

### <a name="b-to-b"></a>B-do-B

Počevši od listopada 2021., možete raditi s poslovnim računima i njihovim povezanim kontaktima u customer insights. Prije je aplikacija uglavnom bila prilagođena pojedinačnim potrošačima. Nekoliko područja značajki ažurirano je kako bi podržalo scenarije B-do-B povrh nove vrste okruženja. Pregled podržanih značajki od B do točke B potražite u članku [Rad s poslovnim računima u publika uvidima](work-with-business-accounts.md).

U sljedećim se odjeljcima ističu neka od ključnih područja prilagođenih za podršku poslovnim računima i pojedinačnim potrošačima.

#### <a name="export-segments-based-on-business-accounts"></a>Izvoz segmenata na temelju poslovnih računa

Sav izvoz segmenata u publika uvidima dostupan je u kontekstu poslovnih računa. Većina izvoza segmenata zahtijeva dodatnu konfiguraciju i [podatke za kontakt projicirane](segment-builder.md#create-a-new-segment) u temeljnim segmentima kako bi bili valjani za poslovne račune. Dodatne informacije potražite u odjeljku [Izvoz segmenata](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>Korištenje izvoza LinkedIn Adsa s poslovnim računima

Izvoz LinkedIn Adsa sada je dostupan za ciljanje kontakata i tvrtki u kontekstu poslovnih računa. Prilikom odabira ciljanja tvrtke kao primarnog fokusa izvoza linkedina, možete izvesti segmente izgrađene na poslovnim računima bez potrebe za projiciranjem podataka za kontakt. Dodatne informacije potražite u dokumentima o [izvozu](export-linkedin-ads.md) LinkedIn Adsa i razlici između [ciljanja](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) kontakata i [ciljanja](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) tvrtke. 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Stvaranje mjera na temelju poslovnih računa i njihove hijerarhije

Sastavljač mjera omogućuje vam stvaranje mjera oko poslovnih računa i po želji korištenje informacija o hijerarhiji. Informacije o hijerarhiji koriste se za kumulativnu analizu mjere na cijelom računu i svim povezanim podračunima. Na primer, možete kreirati mjere kao što su ukupni prihodi za svaku grupu poslovnih računa označenu njihovom hijerarhijom. Za više informacija pogledajte [Definiranje i upravljanje mjerama](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Stvaranje segmenata na temelju poslovnih računa i njihove hijerarhije

Sastavljač segmenata omogućuje kreiranje segmenata poslovnih računa koji po želji uključuju podatke za kontakt za svaki poslovni subjekt u segmentu. Ako ste postavili hijerarhiju računa, u kreiranju segmenata možete koristiti informacije o hijerarhiji računa. Dodatne informacije potražite u članku [Stvaranje novog segmenta](segment-builder.md#create-a-new-segment).

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Zadržite svoje poslovne račune s dubokim uvidima u njihovu tendenciju bućkanja

Model predviđanje kupca sada podržava i poslovne račune. Možete procijeniti rizik od bućkanja ne samo za račun, već i za kombinaciju računa i kategorije proizvoda ili usluge koju kupuju od vas. Ovaj dodatak pomaže vam da shvatite je li vjerojatnije da će račun prestati kupovati od vas općenito ili samo za određenu kategoriju robe ili usluga. Da bi vam dodatno pomogao u korištenju ovog modela umjetne inteligencije, navodi i razloge zbog kojih će se račun vjerojatno bućkati. Dodatne informacije potražite u odjeljku [Transakcijski skup predviđanje (pretpregled)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Prikaz kontakata poslovnog računa u prikazu kupca

Ako su poslovni računi mapirani na povezane račune, aplikacija Customer Insights prikazuje te povezane kontakte kao dio prikaza pojedinosti o kupcima. Dodatne informacije potražite u odjeljku [Profili](customer-profiles.md) kupaca.


## <a name="september-2021-updates"></a>Ažuriranja u rujnu 2021.

Ažuriranja u rujnu 2021. uključuju nove značajke, nadogradnje performansi i ispravke programskih pogrešaka.

### <a name="activities"></a>Aktivnosti

- **Poboljšanja vremenske trake aktivnosti** Proširili smo filtre za vremensku traku aktivnosti na profilima klijenata. Osim toga, možete koristiti novo okno filtra za filtriranje prema vrsti aktivnosti i prema datumu. Datumi se mogu filtrirati pod različitim uvjetima. Dodatne informacije potražite u odjeljku [Prikaz vremenskih traka aktivnosti na profilima klijenata](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Odnosi

- **Podrška za odnos s više preskoka** Koristite odnose s više preskoka pri konfiguriranju aktivnosti i definiranju odnosa između entiteta. Odnosi s više preskoka koriste posrednički entitet za povezivanje dva entiteta. Prilikom konfiguriranja aktivnosti možete koristiti odnos s više preskoka za povezivanje entiteta aktivnosti s posredničkim entitetom, a zatim s entitetom klijenta. Možete kombinirati odnose s više preskoka s odnosima s više putanja. Dodatne informacije potražite u odjeljku [Odnos s više preskoka](relationships.md#multi-hop-relationship).

- **Podrška za odnos s više putanja** Koristite odnose s više putanja pri konfiguriranju aktivnosti i definiranju odnosa između entiteta. Odnosi s više putanja povezuju izvorni entitet s više od jednog entiteta. Prilikom konfiguriranja aktivnosti možete koristiti odnos s više putanja za povezivanje entiteta aktivnosti s više od jednog entiteta klijenta. Možete kombinirati odnose s više putanja s odnosima s više preskoka. Dodatne informacije potražite u odjeljku [Odnos s više putanja](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Ažuriranja u kolovozu 2021.

Ažuriranja u srpnju i kolovozu 2021. uključuju novu značajku, nadogradnje performansi i ispravke programskih pogrešaka.

### <a name="extensibility"></a>Proširivost

- **Izvoz segmenata u Klaviyo** Proširili smo svoja [izvozna odredišta tako da uključuju Klaviyo](export-klaviyo.md). Sada možete izvesti segmente da biste stvorili kampanje, pokrenuli marketing putem e-pošte i koristili određene grupe klijenata uz Klaviyo. 


## <a name="june-2021-updates"></a>Ažuriranja za lipanj 2021.

Ažuriranja sustava u lipnju 2021. uključuju nekoliko značajki, nadogradnje performansi i ispravke programskih pogrešaka.

### <a name="data-ingestion"></a>Obrada podataka

- **Poboljšana ažuriranja napretka objedinjavanja podataka** Sada možete vidjeti detaljnija, poboljšana dinamička ažuriranja statusa u koracima [procesa objedinjavanja podataka](data-unification.md). Ova vam značajka omogućuje praćenje detaljnog napretka kako biste razumjeli tijek procesa i poduzeli radnje ako bilo koji korak zahtijeva pozornost.

### <a name="extensibility"></a>Proširivost

- **Izvoz segmenata i ostalih podataka u Salesforce Marketing Cloud** Proširili smo svoja izvozna odredišta tako da uključuju [Salesforce Marketing Cloud](export-salesforce.md). Sada možete izvesti segmente i ostale vrste podataka u Salesforce Marketing Cloud putem brendiranog SFTP izvoza. Uvoz podataka može se potpuno automatizirati u Salesforce i koristiti za stvaranje učinkovitijih marketinških kampanja.  
 
- **Izvoz segmenata u ActiveCampaign** Proširili smo svoja izvozna odredišta tako da uključuju [Active Campaign](export-active-campaign.md). Sada možete izvesti segmente da biste generirali kampanje, pokrenuli marketing putem e-pošte i radili s određenim grupama klijenata u ActiveCampaign.
 
- **Izvoz segmenata u Sendinblue** Proširili smo svoja izvozna odredišta tako da uključuju [Sendinblue](export-sendinblue.md). Sada možete izvesti segmente da biste generirali kampanje, pokrenuli marketing putem e-pošte i radili s određenim grupama klijenata uz Sendinblue.
 
### <a name="ux-updates"></a>Ažuriranja korisničkog iskustva 

- **Nova i poboljšana stranica klijenata i stranica s pojedinostima o profilu** Redizajnirali smo stranicu Klijenti i stranice s pojedinostima profila radi poboljšanja korisničkog iskustva i boljih performansi. Ove vam promjene omogućuju pregled, sortiranje, pretraživanje i filtriranje klijenata. Filtri su sada predstavljeni u URL -u za besprijekorno dijeljenje rezultata pretraživanja s ostalim korisnicima. Rezultati pretraživanja mogu se spremiti i kao segment.    
  Stranica s pojedinostima za profile klijenata sada grupira podatke u različitim pododjeljcima, kao što su demografski podaci, ID-jevi i ostali atributi profila radi bolje čitljivosti. Ostali odjeljci na stranici s pojedinostima o profilu sada su interaktivniji. Na primjer, odjeljak aktivnosti sada omogućuje filtriranje i sortiranje.


## <a name="may-2021-updates"></a>Ažuriranja za svibanj 2021.

Ažuriranja u svibnju 2021. uključuju nekoliko značajki, nadogradnje performansi i ispravke pogrešaka.

### <a name="data-ingestion"></a>Obrada podataka

- **Pregledajte ili izmijenite metapodatke ili definiciju entiteta tijekom prilaganja podataka iz vašeg spremišta Azure Data Lake Storage**. Sada možete pregledavati i uređivati metapodatke ili definiciju entiteta u uvidima u ciljne skupine tijekom prilaganja podataka iz mape Common Data Model u vašem spremištu Azure Data Lake Storage. Ova mogućnost pruža povratne informacije u stvarnom vremenu, provjeru valjanosti modela i provjeru pogrešaka. Omogućuje vam uređivanje modela.json i manifest.json bez problema.

### <a name="extensibility"></a>Proširivost

- **Poboljšani izvoz segmenata, prilagođeni raspored i dupliciranje** Sada možete [vidjeti sve izvoze za određeni segment](export-destinations.md#view-exports-and-export-details) na popisu. Ovaj novi prikaz olakšava upravljanje načinom na koji se koristi određeni segment i prilagođavanje postojećih ili stvaranje novih izvoza.    
  Možete [definirati prilagođene rasporede osvježavanja](export-destinations.md#schedule-and-run-exports) za pojedinačne izvoze ili više izvoza odjednom. Do sada su se svi izvozi pokretali sa svakim osvježavanjem sustava.    
  Umjesto da stvarate novi izvoz od početka, možete započeti na temelju postojećeg kako biste uštedjeli dio vremena.

- **Izvoz segmenata u Microsoftovo oglašavanje** Proširili smo naša izvozna odredišta tako da uključuju i Microsoftovo oglašavanje. Pomoću objedinjenih podataka profila klijenata stvorite ciljne skupine Podudaranje klijenata u Microsoftovom oglašavanju te ih upotrijebite za svoje kampanje za oglašavanje. Dodatne informacije potražite u odjeljku [Izvoz segmenata u Microsoftovo oglašavanje](export-microsoft-advertising.md).

- **Izvoz segmenata u LinkedIn Ads** Proširili smo naša izvozna odredišta tako da uključuju LinkedIn Ads i omogućuju vam da otključate Ciljanje kontakata, kao i Ciljanje tvrtki putem servisa LinkedIn pomoću izvoza vaših objedinjenih podataka profila klijenata. Dodatne informacije potražite u odjeljku [Izvoz segmenata u LinkedIn Ads](export-linkedin-ads.md).


- **Izvoz segmenata u Omnisend** Proširili smo naša izvozna odredišta tako da uključuju i Omnisend. Segmente stvorene u uvidima u ciljne skupine upotrebljavajte za generiranje kampanja, pružanje marketinga putem e-pošte i upotrebu određenih grupa klijenata uz Omnisend. Dodatne informacije potražite u odjeljku [Izvoz segmenata u Omnisend](export-omnisend.md)

### <a name="predictions"></a>Predviđanja

- **Izvješće o upotrebljivosti ulaznih podataka** Izvješće o upotrebljivosti ulaznih podataka pruža pročišćen prikaz pogrešaka i upozorenja koja mogu proizvesti vaša gotova predviđanja. Također daje preporuke kako poboljšati izvedbu modela.    
  Izvješće je dostupno nakon što model završi svoj proces obuke. Stvara se za svaki model zasebno, bez obzira je li uspješno dovršen ili ne.
  Trenutno je ova značajka dostupna samo za model Transakcijski gubitak klijenata. Dodatne informacije potražite u odjeljku [Izvješće o upotrebljivosti ulaznih podataka](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Odnosi

- **Vizualizator odnosa** Prikaz vizualizatora odnosa omogućuje vam da vidite sve postojeće odnose između entiteta i njihove kardinalnosti. Odnosi su sada organizirani u grupe: odnosi koje je stvorio korisnik, sustav i naslijeđeni odnosi. Prikaz možete izvesti i kao sliku. Dodatne informacije potražite u odjeljku [Prikaz odnosa](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Ažuriranja za travanj 2021.

Ažuriranja u travnju 2021. uključuju nekoliko značajki, nadogradnje performansi i ispravke pogrešaka.

### <a name="data-unification"></a>Objedinjavanje podataka
 
- **Poboljšano iskustvo spajanja za objedinjavanje podataka**    
  
   Sada imamo poboljšano korisničko iskustvo u konfiguraciji spajanja u postupku objedinjavanja podataka. Promjene uključuju intuitivno slaganje spojenih polja i detaljne statistike o kombiniranim i pojedinačnim poljima.

- **Promjena rasporeda entiteta i konfiguriranje svih izvornih zapisa u entitetu Klijent**  
      
   Sada u postupku objedinjavanja podataka možete promijeniti raspored entiteta i ukloniti entitete iz postojećeg plana spajanja. Omogućuje fleksibilnu promjenu rasporeda entiteta u postupku uparivanja prema poslovnim potrebama. Uz to, omogućujemo uključivanje svih neuparenih zapisa u završni entitet *Klijent* koji im omogućuje definiranje njihove definicije skupa podataka o profilu klijenta.

### <a name="enrichments"></a>Obogaćivanja

 - **Novo obogaćivanje: Poboljšane adrese**    
  
   Uzbuđeni smo što vam predstavljamo novo obogaćivanje za poboljšanje adresa u vašim podacima o klijentima. Adrese u vašim podacima mogu biti nestrukturirane, nepotpune ili netočne. Ova značajka koristi Microsoftove modele za normalizaciju i obogaćivanje adresa u format Common Data Model radi veće preciznosti i uvida.
 
   Dodatne informacije potražite u odjeljku [Obogaćivanje profila klijenata s poboljšanim adresama](enrichment-enhanced-addresses.md).

- **Vođeno iskustvo konfiguracije za obogaćivanja**    
  
   Ponovno smo razmotrili iskustvo konfiguracije radi obogaćivanja s jednostavnim, vođenim iskustvom. Sada imate jasan postupak korak-po-korak za stvaranje i uređivanje obogaćivanja.
 
   Osim toga, odvojili smo konfiguraciju veza za obogaćivanja treće strane kako bismo omogućili da se ista veza koristi u više obogaćivanja. Samo administratori mogu konfigurirati nove veze, ali stvorene veze su dostupne i administratorima i suradnicima.    

   Dodatne informacije potražite u odjeljku [Pregled veza](connections.md).

- **Višestruka obogaćivanja iste vrste**    
  
   Sada korisnicima dopuštamo stvaranje i upravljanje višestrukih obogaćivanja iste vrste obogaćivanja. Na primjer, sada možete stvoriti dva odvojena obogaćivanja adresa kako biste obogatili dva različita segmenta klijenta. Ograničenja se primjenjuju na to koliko se obogaćivanja iste vrste može stvoriti i razlikuju se ovisno o vrsti obogaćivanja.
  
   Za više informacija pogledajte [Obogaćivanje za profile klijenata](enrichment-hub.md).

## <a name="march-2021-updates"></a>Ažuriranja za ožujak 2021.

Ažuriranja u ožujku 2021. uključuju nekoliko značajki, nadogradnje performansi i ispravke pogrešaka.

### <a name="activities"></a>Aktivnosti

- **Čarobnjak aktivnosti i semantičke vrste**

   Poboljšali smo i ažurirali naše iskustvo mapiranja aktivnosti kako bismo usmjerili i pojednostavili stvaranje mapiranja aktivnosti. U ovom novom iskustvu korisnici dobivaju vođeno iskustvo koje pomaže u dovršenju svakog koraka postupka. U koraku mapiranja aktivnosti, osim odabira između mnogih vrsta aktivnosti, korisnik može odabrati i semantičko mapiranje podataka za *Pretplatu* i/ili *SalesOrderLine* prema industrijskim standardnim shemama koje se mogu koristiti za pojednostavljenu potrošnju.   

   Za dodatne informacije pogledajte [Aktivnosti klijenata](activities.md).

### <a name="data-ingestion"></a>Obrada podataka

- **Povežite se s lokalnim izvorima podataka pomoću Power Platform tijekova podataka i pristupnika** Zadovoljstvo nam je objaviti pretpregled Power Platform tijekova podataka i lokalne povezivosti pomoću pristupnika u Customer Insights s pridruženim okruženjem Power Platform ili Dataverse. Svi novi izvori podataka stvoreni u okruženju Customer Insights s povezanim okruženjem Dataverse bit će zadani na Power Platform tijekovima podataka donoseći lokalnu podatkovnu povezivot i bogat skup poveznika i mogućnosti transformacije.

### <a name="extensibility"></a>Proširivost

- **Izvozi organizirani u vezama i izvozima** Promijenili smo naziv stranice **Izvozna odredišta** u **Veze** i dodali zasebnu stranicu za **Izvoze**. Kao dio ovog ažuriranja prebacit ćemo postojeće izvoze u parove veze i izvoz pomoću te veze. Administratori sada imaju više jasnoće u odnosu na odlazne podatke na stranici **Veze**. Sve korisničke uloge imaju pristup stranici **Izvozi**, ali samo administratori mogu odabrati dopustiti suradnicima uređivanje određenih izvoza pomoću dijeljenih veza.     
  Za više informacija pogledajte [Pregled veza](connections.md) i [Pregled izvoza](export-destinations.md).

- **Izvoz segmenata u Campaign Monitor** Proširili smo naša izvozna odredišta tako da uključuju i Campaign Monitor. Sada možete izvesti segmente iz Customer Insights na popise Campaign Monitor i koristiti ih kao polaznu osnovu za vaše marketinške kampanje.    
   Za više informacija pogledajte [Izvoz u Campaign Monitor](export-campaign-monitor.md).

- **Izvoz segmenata u Constant Contact** Proširili smo naša izvozna odredišta tako da uključuju i Constant Contact. Sada možete izvesti segmente iz Customer Insights na popise Constant Contact i koristiti ih kao polaznu osnovu za vaše marketinške kampanje.   
   Za više informacija pogledajte [Izvoz u Constant Contact](export-constant-contact.md).

- **Izvoz segmenata u RollWorks** Proširili smo naša izvozna odredišta tako da uključuju i RollWorks. Sada možete izvesti segmente iz Customer Insights u ciljanu publiku RollWorks i koristiti ih kao osnovu za svoje B2B oglašavanje.    
   Za više informacija pogledajte [Izvoz u RollWorks ](export-rollworks.md).

- **Izvoz segmenata u Snapchat** Proširili smo naša izvozna odredišta tako da uključuju i Snapchat. Sada možete izvesti segmente iz Customer Insights u ciljne skupine Snapchat i koristiti ih kao polaznu osnovu za vaše oglašavanje.     
   Za više informacija pogledajte [Izvoz u Snapchat](export-snapchat.md).

### <a name="predictions"></a>Predviđanja

- **Koristite filtre proizvoda u prediktivnim preporukama proizvoda** U naš model preporuke proizvoda dodali smo mogućnost korištenja filtara proizvoda. Sada možete stvoriti predviđanje koje koristi samo podskup vaših proizvoda.    
   Za više informacija pogledajte [Konfiguracija filtara proizvoda](predict-product-recommendation.md#configure-product-filters).

- **Stvorite segmente iz predviđanja modela** Dodali smo brzi način za stvaranje segmenata pomoću rezultata modela predviđanja. Na stranici rezultata modela jednostavno možete stvoriti novi segment odabirom nove mogućnosti **Stvori segment**.    
  Za više informacija pogledajte [Stvaranje segmenta na temelju modela predviđanja](prediction-based-segment.md).

- **Objašnjenja za preporuke proizvoda** Dodali smo informaciju koja objašnjava ključne čimbenike naučene modelom umjetne inteligencije za generiranje preporuka proizvoda i stupanj u kojem ti čimbenici doprinose preporukama proizvoda. Te se informacije dodaju na zaslon rezultata modela.    
   Više informacija pogledajte u [Pregledaj stanje i rezultate predviđanje](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Ažuriranja za veljaču 2021.

Ažuriranja u veljači 2021. uključuju nekoliko značajki, nadogradnje performansi i ispravke programskih pogrešaka.

#### <a name="extensibility"></a>Proširivost

- **Izvoz segmenata u AdRoll**

  Proširili smo naša odredišta izvoza tako da uključuju AdRoll. Sada možete izvesti segmente iz Customer Insights u ciljne publike AdRoll i koristiti ih kao osnovnu vrijednost za svoje oglašavanje. Dodatne informacije potražite u odjeljku [Poveznik za AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmenti
 
- **Dupliciranje segmenta**
  
  Da biste stvorili novi segment na temelju postojećeg, sada možete duplicirati segment i urediti duplicirani segment da biste ga dodatno pročistili. 

- **Dodavanje dodatnih atributa segmentu**

  Sada atribute možete uključiti u izlaz svog segmenta, čak i ako ti atributi nisu dio profila klijenta. Na primjer, uključite pretplatničke ID-ove u segment iako je dio pretplatničkog entiteta koji ima odnos M:1 s entitetom klijenta. Sve dok atribut pripada entitetu povezanom s entitetom klijenta, sada možete uključiti te atribute.  

#### <a name="predictions"></a>Predviđanja

- **Stvaranje prediktivnih preporuka proizvoda**

  Razumijevanje onoga što klijente zanima za kupnju jedan je od prvih koraka potrebnih za poboljšanje poslovnog prihoda i izgradnju odanosti klijenata kroz personalizaciju i angažman. Davanje preporuka za proizvode koji nisu usklađeni s interesima vaših klijenata može stvoriti osjećaj nepovezanosti između klijenta i vaše tvrtke te u konačnici ograničiti ukupni potencijalni prihod i iskustvo klijenta. 

  Pomoću vlastitih podataka sada možete stvoriti predviđanja za proizvode koje će vaši klijenti vjerojatno kupiti u budućnosti. Dodatne informacije potražite u odjeljku [Predviđanje preporuka proizvoda](predict-product-recommendation.md).

#### <a name="system-administration"></a>Administracija sustava

- **Okruženje za kopiranje podržava više vrsta izvora podataka**

  Administratori mogu kopirati konfiguracije okruženja u novo okruženje u istoj tvrtki ili ustanovi. Ova značajka proširuje funkcionalnost okruženja za kopiranje u slučajevima u kojima se izvori podataka temelje na data lake kojim upravlja Microsoft Dataverse ili se koristi mapa Common Data Model.

## <a name="january-2021-updates"></a>Ažuriranja iz siječnja 2021.

Ažuriranja u siječnju 2021. uključuju nekoliko značajki, nadogradnje performansi i ispravke programskih pogrešaka.

#### <a name="extensibility"></a>Proširivost

- **Proširena funkcionalnost i poboljšane performanse za SFTP izvoz** Sada možete izvesti sve izlazne entitete iz servisa Customer Insights na SFTP glavno računalo. Prije je izvoz bio ograničen na entitete segmenata. Osim toga, izvedba SFTP izvoza omogućuje veću količinu podataka za manje vremena, ovisno o izvedbi vašeg SFTP glavnog računala.    
  Dodatne informacije potražite u odjeljku [Poveznik za SFTP (pretpregled)](export-sftp.md).  

#### <a name="segments"></a>Segmenti

- **Strojno učenje omogućuje predložene segmente za poboljšanje metrike** Postoji novi način otkrivanja i stvaranja segmenata. Sustav koristi model umjetne inteligencije za predlaganje segmenata koji mogu pomoći u poboljšanju KPI-ja (mjere) koji već pratite. Prikazujemo opseg utjecaja atributa koje ćete odabrati za mjeru ili neki drugi primarni atribut. Ove informacije pomažu u pronalaženju potencijalnih segmenata koji predstavljaju prilike.    
  Dodatne informacije potražite u odjeljku [Predloženi segmenti (pretpregled)](suggested-segments.md).

#### <a name="data-unification"></a>Objedinjavanje podataka

- **Poboljšano iskustvo podudaranja** U području objedinjavanja podataka ažurirano je iskustvo podudaranja. Omogućuje vam konfiguriranje i pregled pravila podudaranja, uključujući detaljnu statistiku za daljnje objašnjenje kako funkcionira podudaranje. Postoje mogućnosti za onemogućivanje pravila podudaranja, tako da više ne bude aktivno, a da zadrži konfiguraciju, pravila podudaranja za povlačenje i ispuštanje i još mnogo toga.
  Dodatne informacije potražite u odjeljku [Podudaranje entiteta](match-entities.md).

- **Rezultat uklanjanja duplikata iz postupka podudaranja dostupan je kao entitet** Rezultat postupka uklanjanja duplikata iz postupka podudaranja sada se zapisuje u zasebni entitet za daljnju analizu. Ovaj se entitet sastoji od polja koja se koriste u postupku uklanjanja duplikata i pobjedničkog zapisa i odgovarajućih zamjenskih zapisa koji se spajaju s pobjedničkim zapisom.
  Dodatne informacije potražite u odjeljku [Rezultat uklanjanja duplikata kao entitet](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Administracija sustava

- **Lako dijeljenje podataka s platformom Microsoft Dataverse** Sada možete dijeliti rezultat servisa Customer Insights s aplikacijama platforme Microsoft Dataverse pomoću upravljanog jezera podataka Microsoft Dataverse Data Lake. Kada povežete okruženje platforme Dataverse sa servisom Customer Insights, dobit ćete mogućnost za omogućivanje dijeljenja podataka.
  Dodatne informacije potražite u odjeljku [Upravljanje okruženjima](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]