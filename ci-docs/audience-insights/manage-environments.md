---
title: Izrada okruženja i upravljanje njima
description: Saznajte kako se prijaviti za uslugu i kako upravljati okruženjima.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598284"
---
# <a name="manage-environments"></a>Upravljanje okruženjima

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Ovaj članak objašnjava kako stvoriti novu tvrtku ili ustanovu i kako pripremiti okruženje.

## <a name="sign-up-and-create-an-organization"></a>Prijavite se i stvorite tvrtku ili ustanovu

1. Idi na web-mjesto aplikacije [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Odaberite **Početak rada**.

3. Odaberite željeni scenarij prijave i odgovarajuću vezu.

4. Prihvatite uvjete i odredbe te odaberite **Nastavi** kako biste započeli stvaranje tvrtke ili ustanove.

5. Nakon stvaranja okruženja bit ćete preusmjereni na aplikaciju [Customer Insights](https://home.ci.ai.dynamics.com).

6. Koristite demo okruženje da biste istražili aplikaciju ili stvorite novo okruženje slijedeći korake iz sljedećeg odjeljka.

7. Nakon što odredite postavke okruženja, odaberite **Stvaranje**.

8. Bit ćete prijavljeni nakon što je okruženje uspješno stvoreno.

## <a name="create-an-environment-in-an-existing-organization"></a>Stvaranje okruženja u postojećoj tvrtki ili ustanovi

Novo okruženje moguće je stvoriti na dva načina. Možete odrediti potpuno novu konfiguraciju ili kopirati neke postavke konfiguracije iz postojećeg okruženja.

Da biste stvorili okruženje:

1. Odaberite birač **Okruženja** u zaglavlju aplikacije.

1. Odaberite **Novo**.

   > [!div class="mx-imgBorder"]
   > ![Postavke okruženja](media/environment-settings-dialog.png)

1. U dijaloškom okviru **Stvori novo okruženje** odaberite **Novo okruženje**.

   Ako želite [kopirati podatke iz trenutačnog okruženja](#additional-considerations-for-copy-configuration-preview), odaberite mogućnnost **Kopiraj iz postojećeg okruženja**. Vidjet ćete popis svih dostupnih okruženja u svojoj tvrtki ili ustanovi iz kojih možete kopirati podatke.

1. Navedite sljedeće pojedinosti:
   - **Naziv**: Naziv za ovo okruženje. Ovo je polje već popunjeno ako ste kopirali iz postojećeg okruženja, ali to možete promijeniti.
   - **Regija**: Regija u kojoj je usluga uvedena i udomaćena.
   - **Tip**: Odaberite želite li stvoriti proizvodno okruženje ili okruženje sigurnosne ograde.

2. Po želji, možete odabrati **Napredne postavke**:

   - **Spremi sve podatke u**: Određuje gdje želite pohraniti izlazne podatke generirane iz aplikacije Customer Insights. Imat ćete dvije mogućnosti: **Pohrana aplikacije Customer Insights** (pohrana Azure Data Lake kojom upravlja tim za Customer Insights) i **Azure Data Lake Storage Gen2** (vaša vlastita pohrana Azure Data Lake Storage). Prema zadanome je odabrana mogućnost pohrane aplikacije Customer Insights.

   > [!NOTE]
   > Pohranjivanjem podataka u Azure Data Lake Storage slažete se s prijenosom podataka na odgovarajuću geografsku lokaciju za taj račun za pohranu za Azure te s njihovom pohranom na toj lokaciji. Ta lokacija može se razlikovati od lokacije za pohranu podataka u aplikaciji Dynamics 365 Customer Insights. [Saznajte više u Microsoftom centru za pouzdanost.](https://www.microsoft.com/trust-center)
   >
   > Trenutno se korišteni entiteti uvijek pohranjuju u rješenju Data Lake kojim upravlja Customer Insights.
   > Podržavamo samo račune za pohranu Azure Data Lake Gen2 iz iste Azure regije koju ste odabrali prilikom stvaranja okruženja.
   > Podržavamo samo račune za pohranu Azure Data Lake Gen2 s omogućenom značajkom hijerarhijskog prostora za naziv (HNS).

   - Za mogućnost Azure Data Lake Storage Gen2 možete birati između mogućnosti koja se temelji na resursima i mogućnosti koja se temelji na pretplati za provjeru autentičnosti. Za više informacija pogledajte [Povezivanje uvida ciljne skupine s računom servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure](connect-service-principal.md). Naziv **spremnika** ne može se promijeniti i bit će „customerinsights”.
   
   - Ako želite koristiti [predviđanja](predictions.md) ili konfigurirati dijeljenje podataka s aplikacijama i rješenjima na temelju Microsoft Dataverse, navedite URL okruženja Microsoft Dataverse pod **Konfiguriraj dijeljenje podataka pomoću Microsoft Dataverse i omogući dodatne mogućnosti**. Odaberite **Omogući dijeljenje podataka** za dijeljenje izlaznih podataka usluge Customer Insights pomoću Microsoft Dataverse Managed Data Lake.

     > [!NOTE]
     > - Dijeljenje podataka pomoću Microsoft Dataverse Managed Data Lake trenutno nije podržano kada sve podatke spremite u vlastiti Azure Data Lake Storage.
     > - [Predviđanje vrijednosti koje nedostaju u entitetu](predictions.md) trenutno nije podržano kada omogućite dijeljenje podataka pomoću Microsoft Dataverse Managed Data Lake.

     > [!div class="mx-imgBorder"]
     > ![Mogućnosti konfiguracije za omogućavanje dijeljenja podataka pomoću Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)

   Kada pokrenete procese, kao što su obrada podataka ili stvaranje segmenta, na računu za pohranu koji ste gore odredili stvorit će se odgovarajuće mape. Stvorit će se podatkovne datoteke i datoteke model.json i dodati u odgovarajuće podmape na temelju procesa koji pokrećete.

   Ako stvorite više okruženja značajke Customer Insights i odaberete spremiti izlazne entitete iz tih okruženja na svoj račun za pohranu, za svako će se okruženje stvoriti zasebne mape s ci_<environmentid> u spremniku.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Dodatna razmatranja o konfiguraciji kopije (pretpregled)

Kopirane su sljedeće postavke konfiguracije:

- Najvažnije konfiguracije
- Uneseni/uvezeni izvori podataka
- Konfiguracija objedinjavanja podataka (mapiranje, podudaranje, spajanje)
- Segmenti
- Mjerila
- Odnosi
- Aktivnosti
- Pretraži i filtriraj indeks
- Odredišta izvoza
- Zakazano osvježavanje
- Obogaćivanja
- Upravljanje modelom
- Dodjele uloga

Sljedeće postavke *nisu* kopirane:

- Profili klijenata.
- Vjerodajnice izvora podataka. Morat ćete navesti vjerodajnice za svaki izvor podataka i ručno osvježiti izvore podataka.
- Izvori podataka iz mape Common Data Model i jezera za upravljanje Common Data Service. Te izvore podataka morat ćete stvoriti ručno s istim nazivom kao u izvornom okruženju.

Kad kopirate okruženje, vidjet ćete potvrdnu poruku da je stvoreno novo okruženje. Odaberite **Idi na izvore podataka** da biste vidjeli popis izvora podataka.

Svi će izvori podataka prikazati status **Potrebne su vjerodajnice**. Uredite izvore podataka i unesite vjerodajnice kako biste ih osvježili.

> [!div class="mx-imgBorder"]
> ![Kopirani izvori podataka](media/data-sources-copied.png)

Nakon osvježenja izvora podataka, idite na **Podaci** > **Objedini**. Ovdje ćete pronaći postavke iz izvornog okruženja. Uredite ih po potrebi ili odaberite **Pokreni** za pokretanje postupka objedinjavanja podataka i stvaranje jedinstvenog entiteta klijenta.

Nakon završetka objedinjavanja podataka idite na **Mjere** i **Segmenti** da ih osvježite.

## <a name="edit-an-existing-environment"></a>Uređivanje postojećeg okruženja

Možete urediti neke pojedinosti postojećih okruženja.

1.  Odaberite birač **Okruženja** u zaglavlju aplikacije.

2.  Odaberite ikonu **Uredi**.

3. U okviru **Uredi okruženje** možete ažurirati **Zaslonski naziv** okruženja, ali ne možete promijeniti svojstva **Regija** ili **Vrsta**.

4. Ako je okruženje konfigurirano za pohranu podataka u pohrani Azure Data Lake Storage Gen2, možete ažurirati **Ključ računa**. Međutim, ne možete promijeniti **Naziv računa** ili naziv **Spremnik**.

5. Ako želite, možete ažurirati vezu koja se temelji na ključu računa na vezu koja se temelji na resursima ili pretplati. Nakon nadogradnje i nakon ažuriranja ne možete se vratiti na prethodni ključ računa. Za više informacija pogledajte [Povezivanje uvida ciljne skupine s računom servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure](connect-service-principal.md). Ne možete promijeniti podatke za **Spremnik** prilikom ažuriranja veze.

## <a name="reset-an-existing-environment"></a>Ponovno postavljanje postojećeg okruženja

Kao administrator možete ponovno postaviti okruženje u prazno stanje ako želite izbrisati sve konfiguracije i ukloniti unesene podatke.

1.  Odaberite birač **Okruženja** u zaglavlju aplikacije. 

2.  Odaberite okruženje koje želite ponovno postaviti i odaberite trotočje **...**. 

3. Odaberite mogućnost **Ponovno postavi**. 

4.  Da biste potvrdili brisanje, unesite naziv okruženja i odaberite **Ponovno postavi**.

## <a name="delete-an-existing-environment-available-only-for-admins"></a>Brisanje postojećeg okruženja (dostupno samo za administratore)

Kao administrator možete izbrisati okruženje koje administrirate.

1.  Odaberite birač **Okruženja** u zaglavlju aplikacije.

2.  Odaberite okruženje koje želite ponovno postaviti i odaberite trotočje **...**. 

3. Odaberite mogućnost **Izbriši**. 

4.  Da biste potvrdili brisanje, unesite naziv okruženja i odaberite **Izbriši**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]