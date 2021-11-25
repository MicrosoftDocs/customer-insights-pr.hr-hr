---
title: Zahtjevi subjekta podataka (ZSP) za prava pod OUZP-om | Microsoft Docs
description: Odgovorite na zahtjeve ispitanika za Dynamics 365 Customer Insights publika mogućnosti uvida.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732671"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahtjevi subjekta podataka (ZSP) za prava pod OUZP-om

Opća uredba o zaštiti podataka Europske unije (OUZP) na snazi je od 25. svibnja 2018. Pruža značajna prava pojedincima u vezi s njihovim podacima. Cilj OUZP-a je zaštita i omogućavanje prava na privatnost pojedinaca. Možete pročitati više o Microsoftovoj predanosti sigurnosti i usklađenosti u [Microsoftovom centru za pouzdanost](https://www.microsoft.com/trust-center).

Posvećeni smo pomaganju našim klijentima u ispunjavanju njihovih zahtjeva u vezi s OUZP-om. Sadrži pravo brisanja i izvoza podataka koji uključuju osobne podatke, poput korisničkih ID-ova, telefonskih brojeva i adresa e-pošte. Administratori mogu implementirati zahtjeve korisnika za brisanje ili izvoz osobnih podataka.

## <a name="audience-insights"></a>Uvidi u ciljne skupine

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odgovaranje na GDPR podatke subjekt izbrisati zahtjeve za Dynamics 365 Customer Insights publika uvida sposobnost

"Pravo na zaborav" brisanjem osobnih podataka iz korisničkih podataka organizacije ključna je zaštita u Općoj uredbi o zaštiti podataka (OUZP). Uklanjanje osobnih podataka uključuje uklanjanje svih osobnih podataka i dnevnika koje generira sustav, osim informacija iz dnevnika revizije.

#### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtjevima za brisanje subjekta podataka

Uvidi u ciljnu skupinu nude sljedeća iskustva u proizvodu za brisanje osobnih podataka za specifičnog klijenta ili korisnika:

- **Upravljanje zahtjevima za brisanje za podatke o klijentu**: podaci o klijentu u stavci Customer Insights unose se iz izvornih izvora podataka koji su izvan stavke Customer Insights. Svi OUZP zahtjevi za brisanje moraju se provesti u originalnom izvoru podataka.
- **Upravljaj zahtjevima za brisanje korisničkih podataka u sustavu Customer Insights**: podatke za korisnike stvara Customer Insights. Svi OUZP zahtjevi za brisanje moraju se provesti unutar stavke Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Upravljanje zahtjevima za brisanje podataka o klijentima

Administrator za Customer Insights može slijediti ove korake kako bi uklonio korisničke podatke koji su izbrisani u izvoru podataka:

1. Prijavite se u Dynamics 365 Customer Insights.
2. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**
3. Za svaki izvor podataka na popisu koji sadrži izbrisane podatke o klijentu:
   1. Odaberite (...), a zatim odaberite **Osvježi**.
   2. Provjerite status izvora podataka pod **Status**. Oznaka kvačice znači da je osvježavanja bilo uspješno. Trokut upozorenja znači da je došlo do pogreške. Ako se prikaže znak upozorenja, kontaktirajte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Upravljanje zahtjevima za brisanje OUZP-a za podatke o klijentima.](audience-insights/media/gdpr-data-sources.png "Upravljanje zahtjevima za brisanje OUZP-a za podatke o klijentima")

##### <a name="manage-delete-requests-for-user-data"></a>Upravljanje zahtjevima za brisanje za podatke o korisniku

Administrator za Customer Insights može poduzeti ove korake za brisanje podataka o klijentu za Customer Insights:

1. Prijavite se u Dynamics 365 Customer Insights.
2. U uvidima u ciljnu skupinu idite na **Admin** > **Dozvole**.
3. Potvrdite okvir korisnika kojeg želite izbrisati.
4. Odaberite mogućnost **Ukloni**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odgovaranje na OUZP zahtjeve ispitanika za izvoz

Kao dio naše obveze za sklapanje partnerstva s vama na vašem putu prema Općoj uredbi o zaštiti podataka (OUZP-u), razvili smo dokumentaciju kako bismo vam pomogli da se pripremite. Ova dokumentacija opisuje korake koje danas možete poduzeti da biste podržali usklađenost s GDPR-om kada koristite uvide u ciljnu skupinu.

#### <a name="manage-export-and-view-requests"></a>Upravljanje izvozom i pregledavanjem zahtjeva

Pravo na prenosivost podataka omogućuje subjektima podataka da zatraže kopiju svojih osobnih podataka u elektroničkom obliku ("strukturirani, uobičajeno korišten, strojno čitljiv i interoperabilni format") koji se može prenijeti drugom kontroloru podataka.

##### <a name="export-customer-data-tenant-admin"></a>Izvoz podataka klijenta (administrator klijenta)

Administrator klijenta može pratiti ove korake za izvoz podataka:

1. Pošaljite e-poštu na D365CI@microsoft.com i u zahtjevu navedite adresu e-pošte klijenta. Tim Customer Insights poslat će poruku e-pošte na registriranu adresu e-pošte administratora klijenta i zatražiti potvrdu za izvoz podataka.
2. Potvrdite zahtjev za izvozom podataka za zatraženog klijenta.
3. Primite izvezene podatke putem adrese e-pošte administratora klijenta.

##### <a name="export-user-data-tenant-admin"></a>Izvoz podataka o korisniku (administrator klijenta)

1. Pošaljite e-poštu na D365CI@microsoft.com i u zahtjevu navedite adresu e-pošte korisnika. Tim Customer Insights poslat će poruku e-pošte na registriranu adresu e-pošte administratora klijenta i zatražiti potvrdu za izvoz podataka.
2. Potvrdite zahtjev za izvozom podataka za zatraženog korisnika.
3. Primite izvezene podatke putem adrese e-pošte administratora klijenta.

## <a name="consent-management-preview"></a>Upravljanje pristankom (pretpregled)

Mogućnost upravljanja pristankom ne prikuplja izravno korisničke podatke. Uvozi i obrađuje samo podatke o pristanku koje pružaju korisnici u drugim aplikacijama.

Da biste uklonili podatke o pristanku o određenim korisnicima, uklonite ih u izvorima podataka koji se unose u sposobnost upravljanja pristankom. Nakon osvježavanja izvor podataka, uklonjeni podaci izbrisat će se i u Centru za pristanak. Aplikacije koje koriste entitet privole također će izbrisati podatke koji su uklonjeni na izvoru nakon [osvježavanja](audience-insights/system.md#refresh-processes). Preporučujemo brzo osvježavanje izvora podataka nakon odgovora na zahtjev ispitanika za uklanjanje korisničkih podataka iz svih drugih procesa i aplikacija.


## <a name="engagement-insights-preview"></a>Uvidi u angažman (pretpregled)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Brisanje i izvoz podataka o događajima koji sadrže podatke koji mogu otkriti identitet krajnjeg korisnika

Sljedeći odjeljci opisuju kako brisati i izvoziti podatke o događajima koji mogu sadržavati osobne podatke.

Brisanje ili izvoz podataka:

1. Označite svojstva događaja koja sadrže osobne podatke.
2. Izbrišite ili izvezite podatke povezane s određenim vrijednostima (na primjer: navedeni korisnički ID).

#### <a name="tag-and-update-event-properties"></a>Označivanje i ažuriranje svojstava događaja

Osobni podaci označeni su na razini svojstva događaja. Prvo označite svojstva koja se razmatraju za brisanje ili izvoz.

Slijedite ove korake da biste svojstvo događaja označili kao svojstvo koje sadrži osobne podatke:

1. Otvorite radni prostor koji sadrži događaj.

1. Idite na **Podaci** > **Događaji** da biste vidjeli popis događaja u odabranom radnom prostoru.
  
1. Odaberite događaj koji želite označiti.

1. Odaberite **Uredi svojstva** za otvaranje okna s popisom svih svojstava odabranog događaja.
     
1. Odaberite **...**, a zatim odaberite **Uredi** da biste dospjeli do dijaloškog okvira **Ažuriraj svojstvo**.

   ![Uredite događaj.](engagement-insights/media/edit-event.png "Uređivanje događaja")

1. U prozoru **Ažuriraj svojstvo** odaberite **...** u gornjem desnom kutu, a zatim odaberite okvir **Sadrži EUII**. Odaberite **Ažuriraj** da biste spremili promjene.

   ![Spremite promjene.](engagement-insights/media/update-property.png "Spremite promjene")

   > [!NOTE]
   > Svaki put kada se shema događaja promijeni ili kad stvorite novi događaj, preporučuje se da procijenite pridružena svojstva događaja i po potrebi ih označite ili odznačite kao svojstva koja sadrže osobne podatke.

#### <a name="delete-or-export-tagged-event-data"></a>Brisanje ili izvoz označenih podataka o događajima

Ako su sva svojstva događaja označena na odgovarajući način kako je opisano u prethodnom koraku, administrator okruženja može izdati zahtjev za brisanje označenih podataka o događaju.

Za upravljanje zahtjevima za brisanje ili izvoz EUII

1. Idite na **Administrator** > **Okruženje** > **Postavke**.

1. U odjeljku **Upravljanje podacima koji otkrivaju identitet krajnjeg korisnika (EUII)** odaberite **Upravljanje EUII**.

##### <a name="deletion"></a>Brisanje

Za brisanje možete unijeti popis korisničkih ID-ova odvojenih zarezom u odjeljku **Brisanje podataka koji mogu otkriti identitet krajnjeg korisnika (EUII)**. Ti će se ID-ovi zatim usporediti sa svim označenim svojstvima događaja svih projekata u trenutačnom okruženju s pomoću točnog podudaranja nizova. 

Ako se vrijednost svojstva podudara s jednim od navedenih ID-ova, pridruženi događaj trajno će se izbrisati. Zbog nepovratnosti te radnje, morate potvrditi brisanje nakon odabira opcije **Izbriši**.

##### <a name="export"></a>Export

Postupak izvoza identičan je postupku brisanja kada je riječ o definiranju vrijednosti svojstava događaja u odjeljku **Izvoz podataka koji mogu otkriti identitet krajnjeg korisnika (EUII)**. Uz to ćete morati navesti **URL za pohranu Azure bloba** da biste odredili odredište izvoza. URL za Azure blob mora sadržavati [Potpis za dijeljeni pristup (SAS)](/azure/storage/common/storage-sas-overview).

Nakon što odaberete **Izvoz**, svi događaji trenutačnog tima koji sadrže odgovarajuća označena svojstva izvest će se u CSV formatu na odredište za izvoz.

### <a name="good-practices"></a>Dobre prakse

* Pokušajte izbjegavati slanje događaja koji sadrže osobne podatke.
* Ako trebate poslati događaje koji sadrže EUII podatke, ograničite broj događaja i svojstava događaja koji sadrže EUII podatke. U idealnom slučaju, ograničite se na jedan takav događaj.
* Osigurajte da što manje ljudi ima pristup poslanim osobnim podacima.
* Za događaje koji sadrže osobne podatke obavezno postavite jedno svojstvo koje će slati jedinstveni identifikator koji se lako može povezati s određenim korisnikom (na primjer, ID korisnika). Time se olakšava odvajanje podataka i izvoz ili brisanje odgovarajućih podataka.
* Označite samo jedno svojstvo po događaju kao ono koje sadrži osobne podatke. Po mogućnosti, svojstvo koje sadrži samo jedinstveni identifikator.
* Nemojte označavati svojstva koja sadrže opširne vrijednosti (na primjer, cijelo tijelo zahtjeva). Mogućnost uvida u angažman koristi točno podudaranje nizova prilikom odlučivanja koje ćete događaje izbrisati ili izvesti.

[!INCLUDE[footer-include](includes/footer-banner.md)]