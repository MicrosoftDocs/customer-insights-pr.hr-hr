---
title: Nove i nadolazeće značajke
description: Informacije o novim značajkama, poboljšanjima i ispravcima programskih pogrešaka.
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988911"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Što je novo u mogućnosti uvida u ciljnu skupinu Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Sa zadovoljstvom objavljujemo naša najnovija ažuriranja! Ovaj članak daje javni pretpregled značajki, poboljšanja opće dostupnosti i ažuriranja značajki. Kako biste vidjeli dugoročne planove značajki, pogledajte članak [Raspored izdanja sustava Dynamics 365 i rješenje Power Platform](/dynamics365/release-plans/).

Ažuriranja unosimo po regijama. Tako bi neke regije mogle vidjeti značajke prije drugih. Ako nije drugačije određeno, ne morate poduzimati ništa i automatski ćemo ažurirati aplikaciju bez prekida u radu.

> [!TIP]
> Za kontakt i glasanje o zahtjevima za značajkama i prijedlozima o proizvodu idite na [portal sa zamislima za aplikacije Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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

- **Izvoz segmenata u RollWorks** Proširili smo naša izvozna odredišta tako da uključuju i RollWorks. Sada možete izvesti segmente iz Customer Insights u ciljne skupine RollWorks i koristiti ih kao polaznu osnovu za vaše B2B oglašavanje.    
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




[!INCLUDE[footer-include](../includes/footer-banner.md)]