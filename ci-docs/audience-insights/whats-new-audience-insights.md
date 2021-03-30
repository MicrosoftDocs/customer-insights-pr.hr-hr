---
title: Nove i nadolazeće značajke
description: Informacije o novim značajkama, poboljšanjima i ispravcima programskih pogrešaka.
ms.date: 03/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 96c0b871eeaaf0976e5c718f37f883f4410977dc
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598422"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Što je novo u mogućnosti uvida u ciljnu skupinu Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Sa zadovoljstvom objavljujemo naša najnovija ažuriranja! Ovaj članak daje javni pretpregled značajki, poboljšanja opće dostupnosti i ažuriranja značajki. Kako biste vidjeli dugoročne planove značajki, pogledajte članak [Raspored izdanja sustava Dynamics 365 i rješenje Power Platform](/dynamics365/release-plans/).

Također možete pogledati sljedeći videozapis da biste saznali više o mogućnostima planiranim u posljednjih šest mjeseci.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Ažuriranja unosimo po regijama. Tako bi neke regije mogle vidjeti značajke prije drugih. Ako nije drugačije određeno, ne morate poduzimati ništa i automatski ćemo ažurirati aplikaciju bez prekida u radu.

> [!TIP]
> Za kontakt i glasanje o zahtjevima za značajkama i prijedlozima o proizvodu idite na [portal sa zamislima za aplikacije Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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

  Administratori mogu kopirati konfiguracije okruženja u novo okruženje u istoj tvrtki ili ustanovi. Ova značajka proširuje funkcionalnost kopiranja okruženja za slučajeve u kojima se koriste izvori podataka na temelju jezera podataka Common Data Service ili mape Common Data Model.

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


## <a name="december-2020-updates"></a>Ažuriranja u prosincu 2020.

Ažuriranja u prosincu 2020. uključuju nekoliko značajki, nadogradnji performansi i ispravke programskih pogrešaka.

### <a name="new-and-updated-features-in-december-2020"></a>Nove i ažurirane značajke u prosincu 2020.

#### <a name="data-enrichment"></a>Obogaćivanje podataka

- **Poboljšana obogaćivanja afiniteta marke i interesa**
  
  Pojednostavili smo ocjene afiniteta kako bismo ih olakšali za razumijevanje i upotrebu. Sada možete brzo identificirati klijente na temelju toga koliko imaju afiniteta za marku ili interes.

  Uz to smo dodali nove mogućnosti konfiguracije kako bi se bolje kontroliralo kako želite da vaši profili klijenata budu obogaćeni. 

  Za više informacija pogledajte [Obogaćivanje profila klijenata afinitetima za robne marke i interese](enrichment-microsoft-graph.md).

- **Kontrolirajte koje ćete profile obogaćivati**

  Sada možete obogatiti samo podskup svojih profila klijenata s mogućnosti odabira entiteta segmenta umjesto zadanog entiteta klijenta. Stvorite segment s profilima klijenata koje biste željeli obogatiti i odaberite ga u konfiguraciji obogaćivanja za svoj skup podataka klijenta.
  Ova je značajka trenutno dostupna samo za obogaćivanja koja pružaju Experian i HERE Technologies. Uskoro ćemo ovu mogućnost omogućiti za više obogaćivanja.

  Dodatne informacije potražite u odjeljku [Obogaćivanje profila klijenata demografskim podacima tvrtke Experian](enrichment-experian.md) ili [Obogaćivanje profila klijenata putem tvrtke HERE Technologies](enrichment-here.md).

#### <a name="extensibility"></a>Proširivost

- **Aktivirajte svoje segmente putem sustava Autopilot**

  Izvezite segmente u Autopilot i upotrijebite ih u marketinške svrhe. Dodatne informacije potražite u odjeljku [Poveznik za Autopilot (pretpregled)](export-autopilot.md).

- **Aktivirajte svoje segmente putem servisa SendGrid**

  Izvezite segmente u SendGrid i upotrijebite ih u marketinške svrhe. Dodatne informacije potražite u odjeljku [Poveznik za SendGrid](export-sendgrid.md).

#### <a name="system-administration"></a>Administracija sustava

- **Ažurirano iskustvo upravljanja okruženjem**
  
  Sada možete stvarati, uređivati, brisati i vraćati okruženja izravno iz birača okruženja u zaglavlju aplikacije. 
  
  Osim toga, okruženje koje koristite prikvačit će se na vrhu panela okruženja, tako da ga više ne morate tražiti.

  Dodatne informacije potražite u odjeljku [Upravljanje okruženjima](manage-environments.md).

## <a name="november-2020-updates"></a>Ažuriranja obavljena u studenom 2020.

Ažuriranja u studenom 2020. uključuju nekoliko značajki, nadogradnji performansi i ispravke programskih pogrešaka.

### <a name="new-and-updated-features-in-november-2020"></a>Nove i ažurirane značajke u studenom 2020.

#### <a name="data-enrichment"></a>Obogaćivanje podataka

- **Donesite vlastite podatke o obogaćivanju putem prilagođenog uvoza protokola sigurnog prijenosa datoteka (SFTP)**
  
  SFTP prilagođeni uvoz omogućuje vam uvoz podataka obogaćivanja koji ne moraju proći kroz postupak objedinjavanja podataka. Saznajte više o prilagođenom uvozu SFTP.

  Više informacija pogledajte u [Obogatite profile kupaca prilagođenim podacima (pretpregled)](enrichment-SFTP-custom-import.md).
 
- **Obogatite svoje podatke o klijentima pomoću podataka o lokaciji tvrtke HERE Technologies**

  Pomoću usluga obogaćivanja podataka tvrtke HERE Technologies možete stvoriti preciznije razumijevanje lokacije svojih klijenata uz normalizaciju adrese, izvlačenje zemljopisne širine i dužine i još mnogo toga. Saznajte više o obogaćivanju uz tvrtku HERE Technologies.

  Više informacija pogledajte u [Obogatite profile klijenata uz tvrtku HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Objedinjavanje podataka

- **Fleksibilnost za omogućavanje profiliranja podataka na odabranim entitetima i poljima s vašeg računa za pohranu**

  Možete navesti koje entitete podataka i polja iz mape Common Data Model na vašem računu za pohranu Azure Data Lake želite omogućiti za profiliranje podataka kao dio postupka unosa podataka.

  Više informacija pogledajte u [Poveži s mapom Common Data Model ](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Proširivost

- **Aktivirajte svoje segmente putem usluge Google Ads**

  Izvezite segmente s popisa ciljne publike usluge Google Ads i upotrijebite te popise za oglašavanje na uslugama Google pretraživanje, Google prikazivačkoj mreži, kanalu YouTube i Gmail. Saznajte više o aktiviranju svojih segmenata putem usluge Google Ads.

  Više informacija pogledajte u [Konektor za Google Ads](export-google-ads.md).

- **Aktivirajte svoje segmente putem usluge Marketo**

  Izvozite segmente u ciljne skupine Marketo i koristite ih za automatizaciju marketinga. Saznajte više o aktiviranju svojih segmenata putem usluge Marketo. 

  Više informacija pogledajte u [Konektor za Marketo](export-marketo.md).

- **Aktivirajte svoje segmente putem usluge DotDigital**

  Izvezite segmente u DotDigital i upotrijebite ih u marketinške svrhe. Saznajte više o aktiviranju svojih segmenata putem usluge DotDigital. 

  Više informacija pogledajte u [Konektor za DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Predviđanja

- **Predvidite transakcijski gubitak**

  Značajka predviđanja transakcijskog gubitka omogućuje vam, bez pomoći istraživača podataka, predvidjeti vjerojatnost klijenta da prekine kupnju proizvoda ili usluga.  Koristeći rezultat predviđanja, možete kombinirati druge podatke o svojim klijentima, poput vrijednosti klijenta, kako biste stvorili segmente klijenta s visokim rizikom ili one velike vrijednosti. Koristite ovaj segment za izravno ciljanje klijenata putem marketinških aktivnosti, korisničke podrške i drugih scenarija kako biste smanjili rizik od gubitka.
 
  Konfigurirajte definiciju gubitka kao vremenski određen prozor specifičan za vaše poslovanje i definirajte kada se klijenti smatraju izgubljenima. Na primjer, trgovina mješovitom robom možda će htjeti razmotriti gubitak klijenta ako u zadnjih 30 dana nije ništa kupio.
 
  Kako nastavljate stvarati predviđanje, vodit ćemo vas kroz potrebne podatke i omogućiti vam mapiranje podataka o vašem poslovanju u polja potrebna za predviđanje gubitka klijenata. Također možete postaviti raspored za prekvalifikaciju modela na temelju novih podataka u vašem sustavu kako bi se prilagodio promjenjivim poslovnim okolnostima.
 
  Više informacija pogledajte u [Predviđanje transakcijskog gubitka (pretpregled)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Administracija sustava

- **Ponovno postavi okruženje**

  Ponovno postavite sve u okruženju odabrane instance da biste započeli iznova.

  Dodatne informacije potražite u odjeljku [Ponovno postavljanje postojećeg okruženja](manage-environments.md#reset-an-existing-environment).


- **Povežite se sa svojim računom za pohranu Azure Data Lake pomoću glavne usluge**

  Ispišite zapis podataka na svoj račun za pohranu i očitajte podatke s pomoću glavne usluge Azure. Postojeće veze računa za pohranu mogu i dalje upotrebljavati ključ računa. Oni također nude mogućnost nadogradnje za korištenje napredovanja glavne usluge. Nove veze temeljit će se na načinu provjere autentičnosti glavne usluge za vaš račun pohrane.

  Više informacija pogledajte u [Povezivanje uvida ciljne skupine računa Azure Data Lake Storage Gen2 s glavnom uslugom Azure](connect-service-principal.md).

## <a name="october-2020-updates"></a>Ažuriranja iz listopada 2020.

Ažuriranja u listopadu 2020. uključuju nekoliko značajki, nadogradnji performansi i ispravke programskih pogrešaka.

### <a name="new-and-updated-features-in-october-2020"></a>Nove i ažurirane značajke u listopadu 2020.

#### <a name="extensibility"></a>Proširivost

- **Izvoz u Mailchimp**

Izvezite segmente na postojeće popise ciljne skupine u Mailchimp kako biste svojim klijentima pružili personalizirano iskustvo e-pošte.

Više informacija pogledajte u [Konektor za Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Obogaćivanje podataka

- **Uklonite duplikate izvornih zapisa u entitetu podudaranja**

Navedite pravila uklanjanja duplikata za entitete koji se koriste u procesu podudaranja za identificiranje dupliciranih zapisa. Spojite ih u jedan zapis i povežite sve izvorne zapise s tim spojenim zapisom. Taj uklonjeni duplicirani zapis tada će se upotrijebiti u postupku podudaranja među entitetima.

Više informacija pogledajte u [Definirajte uklanjanje duplikata u entitetu podudarnosti](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Administracija sustava

- **Orkestracija: Nova opcija osvježavanja u Spajanju**

Do danas, kada pokrenete postupak spajanja, sustav je izvodio sve prethodne postupke koji ovise o spajanju i sljedećim postupcima. Sada možete provjeriti izlaz postupka spajanja (objedinjeni entitet klijenta) prije nego što ga upotrijebite u daljnjoj obradi poput segmenata ili mjera.
Na stranici spajanja sada možete odabrati pokretanje samo koraka spajanja i pokretanje samo ovog postupka. Da biste osvježili i sve prethodne postupke možete odabrati pokretanje spajanja i prethodne postupke. 

## <a name="september-2020-updates"></a>Ažuriranja u rujnu 2020.

Ažuriranja aplikacije u rujnu 2020. uključuju nekoliko značajki, nadogradnje performansi i ispravke programskih pogrešaka.

### <a name="new-and-updated-features-in-september-2020"></a>Nove i ažurirane značajke u rujnu 2020.

#### <a name="activities"></a>Aktivnosti

- **Inteligentno predviđanje semantike atributa**

Ova nova značajka predviđa semantičke vrste ulaznih atributa koji se prenose na postupak objedinjavanja podataka. Upotrebljava načine strojnog učenja koji poboljšavaju točnost i štede vrijeme.

#### <a name="enrichments"></a>Obogaćivanja

- **Demografski podaci obogaćeni od strane tvrtke Experian**

Obogaćivanje demografskih podataka od strane tvrtke Experian sada je dostupno u pretpregledu. Experian je svjetski predvodnik u izvješćivanju o potrošačkim i poslovnim kreditima i marketinškim uslugama. Uz [usluge tvrtke Experian za obogaćivanja podataka](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) možete izgraditi bolje temelje za razumijevanje svojih klijenata obogaćujući njihove profile demografskim podacima kao što su veličina kućanstva, prihod i još mnogo toga.

Za uporabu ove značajke, morate imati aktivnu pretplatu na Experian.

Dodatne informacija potražite u odjeljku [Obogaćivanje profila klijenata demografskim podacima tvrtke Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Administracija sustava

- **Okno pojedinosti zadatka**

Okno pojedinosti zadatka omogućuje vam prikaz pojedinosti zadataka koje pokreće sustav. To je praktičan način za prepoznavanje problema s konfiguracijom i pronalaženje rješenja.
Pregledajte poruke o pogreškama i vidite kako biste riješili moguće probleme.
 
- **Obrada podataka dodana na više stranica**

Ovo poboljšanje dodaje informacije o statusu vaših entiteta na stranice **Entiteti** i **Klijenti**.
 
Uz to, na obje ove stranice možete pronaći pojedinosti o napretku postupka, zajedno s pojedinostima zadatka.

- **Poboljšanja stranice statusa sustava**

Poboljšali smo strukturu tablice pojedinosti statusa na **Sustav** > **Status** tijekom pregleda izvoza podataka.
 
Uz to, pogreške u stupcu **Pojedinosti** sada su podrobniji i djelotvorniji. 
 
- **Otkazivanje vraća posao natrag u prethodno stanje**

Na primjer, kada otkažete zadatak u postupku podudaranja, on će se vratiti natrag u svoje najnovije stanje. Na primjer, ako je postupak podudaranja završen jučer, a vi ga otkažete danas, on se vraća u jučerašnje uspješno stanje.


## <a name="august-2020-updates"></a>Ažuriranja u kolovozu 2020.

Ažuriranja aplikacije u kolovozu 2020. uključuju nekoliko značajki, nadogradnje performansi i ispravke programskih pogrešaka.

### <a name="new-and-updated-features-in-august-2020"></a>Nove i ažurirane značajke u kolovozu 2020.

#### <a name="data-unification"></a>Objedinjavanje podataka

- **Poboljšano iskustvo u fazi mapiranja tijekom objedinjavanja podataka**

  Iskustvo do faze mapiranja u procesu objedinjavanja podataka omogućuje vam odabir entiteta, atributa i definiranje semantike na jednostavniji način.

  Promjene obuhvaćaju sljedeće:
  
  - potrebno je manje interakcija za dodavanje entiteta i polja
  - poboljšane su mogućnosti pretraživanja na stranici mapiranja
  - vizualna i laka identifikacija predložene vrste polja

#### <a name="enrichment"></a>Obogaćivanje

- **Obogaćivanje afiniteta interesa dostupno na više tržišta**

  Dostupnost obogaćivanja afiniteta interesa proširujemo izvan Sjedinjenih Država na pet drugih tržišta: Kanadu, Australiju, Ujedinjeno Kraljevstvo, Francusku i Njemačku. Ovim proširenjem možete obogatiti podatke o klijentima s više interesa koji se primjenjuju na tim tržištima. Također ćemo obogatiti profile klijenata koji se nalaze na tim tržištima korištenjem lokalnih osobnih podataka iz značajke Microsoftove Graph.
  Za više informacija pogledajte [Obogaćivanje profila klijenata afinitetima za robne marke i interese](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Ažuriranja za srpanj 2020.

Ažuriranja sustava u srpnju 2020. uključuju nekoliko značajki, nadogradnje performansi i ispravke programskih pogrešaka.

### <a name="new-and-updated-features-in-july-2020"></a>Nove i ažurirane značajke u srpnju 2020.

#### <a name="extensibility"></a>Rastezljivost

- **Power Automate okidač za dovršeni postupak objedinjavanja**

  Proširili smo svoje okidače za Power Automate i omogućili stvaranje obavijesti ili radnje kada se dovrši postupak objedinjavanja (karta, podudaranje, spajanje).    
  Za dodatne informacije pogledajte [Poveznik za Power Automate](export-power-automate.md)

#### <a name="enrichment"></a>Obogaćivanje

- **Obogaćivanje afiniteta marke dostupno na više tržišta**

  Dostupnost obogaćivanja afiniteta marke proširujemo izvan Sjedinjenih Država na pet drugih tržišta: Kanadu, Australiju, Ujedinjeno Kraljevstvo, Francusku i Njemačku. Ovim proširenjem možete obogatiti podatke klijenata lokalnim robnim markama na tim tržištima. Također ćemo obogatiti profile klijenata koji se nalaze na tim tržištima korištenjem lokalnih osobnih podataka iz značajke Microsoftove Graph.
  Za više informacija pogledajte [Obogaćivanje profila klijenata afinitetima za robne marke i interese](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Ažuriranja za lipanj 2020.

Ažuriranja sustava u lipnju 2020. uključuju nekoliko značajki, nadogradnje performansi i ispravke programskih pogrešaka.

### <a name="new-and-updated-features-in-june-2020"></a>Nove i ažurirane značajke u lipnju 2020.

#### <a name="enrichment"></a>Obogaćivanje

- **Obogaćivanje podacima tvrtke iz tvrtkeLeadspace**
  
  Odredite polja u objedinjenim profilima klijenata koja se koriste za traženje povezanih podataka o tvrtki iz tvrtke Leadspace. Nakon pokretanja postupka obogaćivanja, B2B profili obogaćuju se s više atributa, uključujući veličinu tvrtke, lokaciju, granu industrije i još mnogo toga.    
  Ova suradnja omogućava vam poboljšati kvalitetu podataka pomoću unosa usluga trećih strana. Za uporabu ovog obogaćenja potrebna vam je licenca tvrtke Leadspace za pristup podacima tvrtke B2B. Sustav će koristiti tu licencu za kontinuirano obogaćivanje vaših podataka.    
  Za više informacija pogledajte [Obogaćivanje profila tvrtke pomoću tvrtke Leadspace](enrichment-leadspace.md),

- **Stranica središta za obogaćivanje**

  Sva dostupna obogaćivanja podataka originalnih i drugih pružatelja usluga obogaćivanja konfiguriraju se na istom mjestu. Konfiguriranje obogaćivanja podataka besprijekoran je doživljaj kojim se upravlja iz uobičajenog mjesta.    
  Za više informacija pogledajte [Obogaćivanje za profile klijenata](enrichment-hub.md).

- **Odvojeno obogaćivanje afiniteta za robne marke i interese**

  Afiniteti za robne marke i interese sada su dostupni kao dva neovisna obogaćivanja. Odvojena obogaćenja daju vam fleksibilnost da ih pojedinačno konfigurirate i upravljate njima, ovisno o vašim poslovnim zahtjevima ili potrebama.    
  Za više informacija pogledajte [Obogaćivanje profila klijenata afinitetima za robne marke i interese](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Rastezljivost

- **URL-ovi koji se mogu kliknuti za objedinjene aktivnosti na dodatku kartice kartice sustava Dynamics 365**

  Objedinjene aktivnosti u programskom dodatku za korisničku karticu sada pokazuju URL-ove na koje je moguće kliknuti ako su takvi URL-ovi definirani tijekom konfiguracije aktivnosti.    
  Za dodatne informacije pogledajte [Dodatak za karticu klijenta](customer-card-add-in.md).

- **Afiniteti za robne marke i interese dostupni na dodatku kartice Klijent sustava Dynamics 365**

  Nova kontrola dodataka kartice Klijent sustava Dynamics 365 omogućava vam prikazivanje obogaćivanja robnih marki i interesa na svojim kontaktima u aplikacijama Customer Engagement u sustavu Dynamics 365.    
  Za dodatne informacije pogledajte [Dodatak za karticu klijenta](customer-card-add-in.md).

- **Više okidača za Power Automate**

  Proširili smo svoje okidače za Power Automate i dodali sljedeće okidače:
  - Ako primite obavijest ili izvršite radnju kada se dovrši automatsko potpuno osvježavanje (izvori podataka, objedinjavanje, segmenti, mjerila, izvoz).
  - Odredite graničnu vrijednost za poslovno mjerilo. Na primjer, možete stvoriti obavijest koja će biti poslana kad premaši definirani prag. Osim toga, okidač pruža informacije koje vam omogućuju stvaranje složenijih tijekova rada na usluzi Power Automate.    
  Za dodatne informacije pogledajte [Poveznik za Power Automate](export-power-automate.md)

- **Izvoz u Facebook upravitelja oglasa**
  
  Ova vam mogućnost omogućuje izvoz segmenata u Upravitelj oglasa za Facebook . Segmenti se izvoze kao prilagođena ciljna skupina za upotrebu objedinjenih profila u klijenata u marketinške kampanje i oglase za Facebook. Prilagođena publika također se može upotrijebiti za stvaranje kampanja na Instagramu pomoću Facebook upravitelja oglasa.    
  Za više informacija pogledajte [Poveznik za Facebook upravitelja oglasa](export-facebook.md).

#### <a name="predictions"></a>Predviđanja

- **Predviđanje gubitka pretplate**

  Slijedite vođeni doživljaj za stvaranje predviđanja gubitka pretplata u područjima pretplate, poput usluga oblaka, članstva klijenata i drugih sektora. 

  Značajka predviđanja gubitka pretplate omogućuje vam predvidjeti vjerojatnost da će klijent prestati upotrebljavati proizvode ili usluge koji se temelje na pretplati bez znanstvenika s podacima. Rezultati predviđanja omogućuju kombiniranje drugih podataka o svojim klijentima radi stvaranja segmenata visokog rizika gubitka pretplate. Pomoću ovog segmenta možete izravno ciljati klijente u marketingu, korisničkoj podršci i drugim scenarijima kako biste smanjili rizik od gubitka određenih klijenata radi poboljšanja prihoda i smanjenja troškova.

  Unutar doživljaja možete konfigurirati definiciju guitka pretplate kao vremenskog okvira specifičnog za vašu tvrtku. Na primjer, tvrtka za strujanje videozapisa koja ima postupak mjesečne pretplate možda bi željela uzeti u obzir da je klijent odustao od pretplate 15 dana nakon isteka njihove pretplate.

  Dok nastavljate kroz predviđanje, uputit ćemo vas kroz podatke koji su vam potrebni i omogućiti vam da preslikavate podatke o svojoj tvrtki u polja potrebna za predviđanje gubitka pretplate za vaše klijente. Kako se poslovne informacije mijenjaju, možete postaviti i raspored ponovnog usavršavanja za prikupljanje novih podataka u vašem sustavu kako biste se prilagodili promjenjivim poslovnim okolnostima.    
  Za više informacija pogledajte [Predviđanje gubitka pretplate (pretpregled)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmenti

- **Pronalaženje sličnih klijenata**
  
  Pronađite slične klijente svojoj bazi klijenata koristeći umjetnu inteligenciju. Model strojnog učenja binarne klasifikacije dodjeljuje rezultat sličnosti klijentima u proširenom segmentu. Ocjena se temelji na sličnosti s klijentima u izvornom segmentu. Ovisno o ocjeni sličnosti, profili klijenata dodaju se tek stvorenom segmentu.

  U digitalnom marketingu se to nekad zove modeliranje dvojnika koje koristi model umjetne inteligencije kao pomoć u pronalaženju klijenata koji su slični drugom segmentu vaših klijenata uzimajući u obzir više atributa. To ne samo da vam omogućuje odabir atributa, već vam omogućuje da odredite maksimalni broj klijenata koji bi trebao biti u ovom novom segmentu. Model umjetne inteligencije tada će izračunati rezultate sličnosti za svakog klijenta na temelju odabranih atributa i pronaći klijente s višom prosječnom ocjenom sličnosti. Rezultirajući segment uključuje klijente koji su slični klijentima u vašem izvornom segmentu.    
  Dodatne informacije potražite u članku [Slični klijenti](find-similar-customer-segments.md).

- **Preklapanje i razlikovanja segmenta**

  Preklapanje segmenata omogućava prikazati koliko i koji su klijenti slični za dva ili više segmenta. Na primjer, kako se segment s visokom potrošnjom preklapa s segmentom klijenata s velikim zadovoljstvom ili kako se segment gubitka klijenata preklapa sa segmentom klijenata s niskim zadovoljstvom. Pored toga, možete analizirati kako se preklapanje mijenja na temelju dodatnog atributa po vašem izboru.

  Razlikovanja segmenta otkrivaju što razlikuje jedan segment od ostalih klijenata ili od drugog segmenta. Sve što trebate učiniti je identificirati segment i sustav će prepoznati atribute profila i mjerila koja razlikuju segment u obrascu rangiranog popisa razlikovanja – od najjačeg razlikovanja do najslabijeg.    
  Za dodatne informacije pogledajt [Uvidi u segmente (pretpregled)](segment-insights.md).

- **Vijek trajanja segmenta**
  
  Definirajte raspored za aktiviranje ili deaktiviranje segmenta.    
  Dodatne informacije potražite u odjeljku [Upravljanje postojećim segmentima](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Ažuriranja za svibanj 2020.

Ažuriranja aplikacije u svibnju 2020. uključuju nekoliko značajki, nadogradnje performansi i ispravke programskih pogrešaka.

### <a name="new-and-updated-features-in-may-2020"></a>Nove i ažurirane značajke u svibnju 2020. godine

#### <a name="data-ingestion"></a>Obrada podataka

- **Unos podataka u stvarnom vremenu: prikazi povijesti**

  Kada koristite naš API za unos ažuriranja u stvarnom vremenu, možete vidjeti do 30 dana skupne povijesti tih ažuriranja. Imate pristup skupnim podacima svih uspješnih ili neuspjelih poziva API-a, u koje spadaju njihov ishod, izvorni sustav i drugi korisni metapodaci.    
  Za dodatne informacije pogledajte [Uvlačenje podataka u stvarnom vremenu](real-time-data-ingestion.md).

- **Unos podataka u stvarnom vremenu: ažuriranja profila**

  Ovo proširenje unosa podataka u stvarnom vremenu omogućuje vam da u roku od nekoliko sekundi vidite promjene u određenim poljima korisničkog profila.    
  Pored funkcionalnosti za aktivnosti u stvarnom vremenu, sustav podržava ažuriranje polja profila niske latencije. Ažuriranja polja profila u stvarnom vremenu imaju vrijeme isteka te stoga ne zamjenjuju planirana osvježavanja.    
  Za dodatne informacije pogledajte [Uvlačenje podataka u stvarnom vremenu](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Rastezljivost

- **Ažurirana vremenska traka i označavanje stranica u dodatku za karticu klijenta**

  Vremenska crta rješenja za programski dodatak za korisničke kartice podudara se s vremenskom linijom aktivnosti. Označavanje stranica vremenske trake poboljšano je i prikazuje do 50 aktivnosti odjednom. Također omogućuje učitavanje više aktivnosti na vremenskoj crti.    
  Za dodatne informacije pogledajte [Dodatak za karticu klijenta](customer-card-add-in.md).

- **Okidač servisa Power Automate za promjene segmenta**

  Okidači za Power Automate određuju iz čega možete graditi tok. Novododani okidač omogućuje vam odrediti prag za neki segment. Na primjer, možete stvoriti obavijest koja će biti poslana kad premaši definirani prag.    
  Za dodatne informacije pogledajte [Poveznik Power Automate](export-power-automate.md).

- **Multiklijentska podrška za prilagođene modele**

  Konfigurirajte tijekove rada za prilagođene modele s web-servisom drugog klijenta za Strojno učenje Azure. Možete se prijaviti na klijenta za strojno učenje Azure prilikom izrade novog tijeka rada za prilagođene modele. Ova je mogućnost dodatak postojećoj mogućnosti integriranja s vlastitim prilagođenim web-servisom Strojno učenje Azure.    
  Za dodatne informacije pogledajte [Prilagođeni modeli strojnog učenja](custom-models.md).

#### <a name="segments"></a>Segmenti

- **Automatizacija putanja entiteta**

  Prilikom stvaranja segmenta korisnici moraju definirati put entiteta. Ova sposobnost čini prvi korak u automatizaciji definicije putanje entiteta, tako da se možete usredotočiti na kriterije segmentacije koje imate na umu.    
  Ako je entitet pomoću kojeg želite segmentirati svoje kupce izravno povezan s objedinjenim entitetom kupca, više nećete trebati definirati putanju entiteta. Međutim, ako postoji više mogućih putanja entiteta, morate je i dalje definirati ručno.

- **Radnje na više segmenata**
  
  Korisnici mogu odabrati više segmenata i poduzimati radnje na njima, poput osvježavanja segmenata, jednim klikom.    

- **Osvježavanje segmenata**

  Korisnici mogu osvježiti jedan segment ili odabrati samo one segmente koje žele osvježiti.    

  
- **Poboljšanja složenih segmenata**

  Korisnici mogu stvarati, uređivati i brisati segmente koji se temelje na drugim segmentima. Na primjer, segment izgrađen na drugom segmentu koji je izgrađen na trećem segmentu.    

- **Stranica popisa segmenata**

  Novi dizajn stranice sa segmentima koristi oblik popisa koji vam omogućuje da vidite više segmenata odjednom. Za brzo pronalaženje segmenata dodaje se polje za pretraživanje. Korisnici sada mogu primijeniti radnje poput preuzimanja ili brisanja na više segmenata odjednom. Uvodi se trend kao novo iskustvo za brzo prepoznavanje značajnih promjena na segmentima.    
  Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).

#### <a name="system-administration"></a>Administracija sustava

- **Aplikacija Customer Insights dostupna u sustavu Microsoft Dynamics 365 Online Government**

  Zbog sve više kanala za interakcije, podaci o građanima raspršeni su na bezbroj sustava, što dovodi do razdvajanja podataka i fragmentiranog prikaza informacija o interakcijama građana. Bez cjelovitog pregleda interakcija svakog građanina na različitim kanalima, državne uprave ne mogu se modernizirati razmjerno. Microsoft je posvećen podršci tehnološkim potrebama državne uprave kako bi išao ukorak s očekivanjima građana za dosljednim i susretljivim iskustvima.    
  Uz 1. val izdanja za 2020., aplikacija Dynamics 365 Customer Insights bit će dostupna za Zajednicu državnih ustanova u oblaku (GCC), okruženje izgrađeno za zadovoljenje većih potreba državnih agencija Sjedinjenih Država. Agencije stječu objedinjen prikaz građana i koriste unaprijed izgrađenu umjetnu inteligenciju radi dobivanja uvida koji poboljšavaju interakcije, osnažuju zaposlenike i transformiraju zajednice, istovremeno smanjujući složenost IT-a i ispunjavajući standarde usklađenosti i sigurnosti Sjedinjenih Država. Dynamics 365 Government ispunjava zahtjevne uvjete američkog Saveznog programa za upravljanje rizicima i ovlaštenjima (FedRAMP), koji saveznim agencijama Sjedinjenih Država omogućavaju uštedu troškova i strogu sigurnost usluge Microsoft Cloud.

## <a name="april-2020-updates"></a>Ažuriranja za travanj 2020.

Ažuriranja aplikacije u travnju 2020. uključuju nekoliko značajki, nadogradnje performansi i ispravke programskih pogrešaka.

### <a name="new-and-updated-features-in-april-2020"></a>Nove i ažurirane značajke u travnju 2020. godine

#### <a name="activities"></a>Aktivnosti

- **Entitet aktivnosti mapiranja na standardnu vrstu aktivnosti**
  
  Konfiguracija i pohrana aktivnosti trenutačno se temelje na statičkom dizajnu kako biste ih vidjeli u vremenskoj traci. Semantičko značenje aktivnosti, koje ima potencijal za višestruke slučajeve upotrebe u modelima umjetne inteligencije, trenutačno se ne koristi u potpunosti. Planiramo poboljšati dinamiku vremena aktivnosti temeljenog na vrsti aktivnosti i boljem semantičkom razumijevanju aktivnosti. Ova značajka ima za cilj identificirati vrstu aktivnosti kako je definirana u Common Data Model za svaku unesenu aktivnost.
  Za dodatne informacije pogledajte [Aktivnosti klijenata](activities.md).

#### <a name="data-ingestion"></a>Obrada podataka

- **Unos podataka u stvarnom vremenu: aktivnosti**
  
  Funkcija unosa podataka u stvarnom vremenu odmah pruža podatke za potrošnju, sve dok ih naknadno zakazano osvježenje ne izbaci iz izvora podataka.    
  Za dodatne informacije pogledajte [Uvlačenje podataka u stvarnom vremenu](real-time-data-ingestion.md).

- **Poboljšanja pripreme podataka**
  
  Saznajte više o podacima unesenim u entitet. Pomoću sažetka podataka možete razumjeti karakteristike kvalitete podataka koje vam mogu pomoći da poduzmete odgovarajuće mjere.    
  Dodatne informacije potražite u odjeljku [Istraživanje podataka entiteta](entities.md#exploring-a-specific-entitys-data).

- **Unos analitičkih podataka iz sustava Dynamics 365 pomoću usluge Common Data Service**
  
  Common Data Service dostupan je kao način za stvaranje izvora podataka. Postojeći korisnici sustava Dynamics 365 mogu unositi analitičke entitete iz usluge Common Data Service u aplikaciju Customer Insights. Jedan izvor podataka može istovremeno koristiti isti Common Data Service – upravljano jezero u okruženju Customer Insights.    
  Za dodatne informacije pogledajte [Povezivanje s podacima u rješenju Data Lake kojim upravlja platforma Common Data Service](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Rastezljivost

- **Izvoz u LiveRamp**

  Aktivirajte svoje podatke u usluzi LiveRamp® da biste se povezali s preko 500 platformi u digitalnim, društvenim i TV ekosustavima. Upotrijebite svoje podatke na platformi LiveRamp za ciljanje, suzbijanje i personalizaciju oglasnih kampanja.    
  Za dodatne informacije pogledajte [Poveznik za LiveRamp&reg;](export-liveramp.md).

- **Dodatak za rad s Teamsom za aplikaciju Customer Insights**
  
  Bot pruža mogućnosti pretraživanja za objedinjene profile klijenata. Pokazat će karticu s do 15 polja iz rezultirajućeg profila kupca. Višestruka podudaranja vraćaju popis rezultata gdje možete odabrati profil.    
  Za dodatne informacije pogledajte [Bot za Teams za aplikaciju Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Mjerila

- **Stranica popisa mjera**
  
  U poboljšanja stranice mjera spada podrška za radnje na jednoj mjeri i na više mjera odjednom. Pored toga, pronaći ćete polje za brzo pretraživanje i praćenje mjera.    
  Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).

- **Poboljšanja složenih mjera**
  
  Korisnici mogu stvarati, uređivati i brisati mjere koje se temelje na drugim mjerama. Na primjer, mjera izgrađena na drugoj mjeri koja je izgrađena na trećoj mjeri.

#### <a name="segments"></a>Segmenti

- **Drugi operator**
  
  Operator „u skupu” omogućuje segmentaciju za klijente prema nekoliko mogućih vrijednosti nizova. Prije nego što je dodan ovaj operator, morali ste konstruirati takve segmente s više ILI uvjeta. Operator „u skupu” omogućuje vam to isto uz samo jedan uvjet.    
  Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).

#### <a name="system-administration"></a>Administracija sustava

- **Kopiranje konfiguracijskih postavki u novo okruženje**
  
  Kopirajte svoju konfiguraciju iz jednog okruženja u drugo. Tijekom stvaranja novog okruženja možete odabrati postojeće okruženje iz kojeg želite kopirati konfiguraciju. Trenutačno je moguće kopirati izvore podataka, objedinjavanje podataka, odnose, mjere i segmente. Vjerodajnice izvora podataka i stvarni podaci se ne kopiraju.    
  Dodatne informacije potražite u odjeljku [Upravljanje okruženjima](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]