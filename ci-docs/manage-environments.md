---
title: Izrada okruženja i upravljanje njima
description: Saznajte kako se prijaviti za uslugu i kako upravljati okruženjima.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: fcdb7f073ff73322ff69d0a8684391819a809d00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642361"
---
# <a name="manage-environments"></a>Upravljanje okruženjima

## <a name="switch-environments"></a>Prebacivanje okruženja

Odaberite kontrolu **Okruženje** u gornjem desnom kutu stranice kako biste se prebacili između okruženja.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Snimka zaslona kontrole za promjenu okruženja.":::

Administratori mogu [stvarati](create-environment.md) i upravljati okruženjima.

## <a name="edit-an-existing-environment"></a>Uređivanje postojećeg okruženja

Možete urediti neke pojedinosti postojećih okruženja.

1.  Odaberite birač **Okruženja** u zaglavlju aplikacije.

2.  Odaberite ikonu **Uredi**.

3. U okviru **Uredi okruženje** možete ažurirati postavke okruženja.

Dodatne informacije o postavkama okruženja potražite u odjeljku [Stvaranje novog okruženja](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Povezivanje sa sustavom Microsoft Dataverse
   
Korak **Microsoft Dataverse** omogućuje vam da povežete Customer Insights s okruženjem Dataverse. 

Pružite vlastito Microsoft Dataverse okruženje za dijeljenje podataka (profila i uvida) s poslovnim aplikacijama koje se temelje na, kao što su Dynamics 365 Marketing ili aplikacije temeljene na Dataverse modelu u Power Apps sustavu.

Da biste koristili [gotove modele predviđanja](predictions-overview.md#out-of-box-models), konfigurirajte dijeljenje podataka s platformom Dataverse. Ili možete omogućiti uvoz podataka iz lokalnih izvora podataka, navodeći URL okruženja Microsoft Dataverse kojim upravlja vaša tvrtka ili ustanova.

Omogućavanje dijeljenja podataka odabirom Microsoft Dataverse potvrdnog okvira za dijeljenje podataka pokrenut će jednokratno potpuno osvježavanje izvora podataka i svih drugih procesa.

> [!IMPORTANT]
> 1. Uvidi u kupce i Dataverse moraju biti u istoj regiji kako biste omogućili dijeljenje podataka.
> 1. Morate imati globalnu administratorsku ulogu u Dataverse okruženju. Provjerite je li ovo [Dataverse okruženje povezano](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) s određenim sigurnosnim grupama i provjerite jeste li dodani tim sigurnosnim grupama.
> 1. Nijedno postojeće okruženje Customer Insights već nije povezano s tim Dataverse okruženjem. Saznajte kako [ukloniti postojeću vezu s okruženjem Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Mogućnosti konfiguracije za omogućavanje dijeljenja podataka uz Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Omogućivanje zajedničkog korištenja podataka s Dataverse vlastitim Azure Data Lake Storage (pretpregled)

Ako je vaše okruženje konfigurirano za upotrebu vlastitog Azure Data Lake Storage za pohranu podataka Customer Insights, omogućavanje dijeljenja podataka s Microsoft Dataverse potrebama dodatne konfiguracije.

1. Stvorite dvije sigurnosne grupe na pretplati na Azure – jednu **Čitatelj** sigurnosnu grupu i jednu **suradnik** sigurnosnu grupu Microsoft Dataverse te postavite uslugu kao vlasnika za obje sigurnosne grupe.
2. Upravljajte popisom kontrole pristupa (ACL) u spremniku CustomerInsights na računu za pohranu putem tih sigurnosnih grupa. Microsoft Dataverse Dodajte servis i sve Dataverse poslovne aplikacije temeljene na sustavu Dynamics 365 Marketing u sigurnosnu grupu **Čitatelj** s **dozvolama samo** za čitanje. Dodajte *samo* aplikaciju Customer Insights u sigurnosnu grupu **suradnik** da biste dodijelili **dozvole za čitanje i pisanje** profila i uvida.
   
#### <a name="prerequisites"></a>Preduvjeti

Da biste izvršili skripte komponente PowerShell, morate uvesti sljedeća tri modula. 

1. Instalirajte najnoviju verziju ljuske [Azure Active Directory PowerShell za grafikon](/powershell/azure/active-directory/install-adv2).
   1. Na računalu pritisnite tipku Windows na tipkovnici, potražite **Windows PowerShell** i odaberite **Pokreni kao administrator**.
   1. U prozoru PowerShell koji se otvori unesite `Install-Module AzureAD`.
2. Uvezite tri modula.
    1. U prozoru ljuske PowerShell unesite `Install-Module -Name Az.Accounts` korake i slijedite ih. 
    1. Ponovite za `Install-Module -Name Az.Resources` i `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Koraci konfiguriranja

1. Preuzmite dvije PowerShell skripte koje su vam potrebne za pokretanje iz GitHub repo našeg [inženjera](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Za pokretanje ove skripte komponente PowerShell potrebne su vam *administratorske* dozvole klijenta. 
       - Ova skripta komponente PowerShell stvara dvije sigurnosne grupe u pretplati na Azure. Jedan za Čitatelj grupu, a drugi za suradnik grupu i pružit Microsoft Dataverse će uslugu kao vlasnik za obje ove sigurnosne grupe.
       - Izvršite ovu powershell skriptu u komponenti Windows PowerShell pružanjem ID-ja pretplate na Azure koji sadrži vaš Azure Data Lake Storage. Otvorite skriptu komponente PowerShell u uređivaču da biste pregledali dodatne informacije i implementiranu logiku.
       - Spremite obje vrijednosti ID-a sigurnosne grupe generirane ovom skriptom jer ćemo ih koristiti u skripti `ByolSetup.ps1`.
       
        > [!NOTE]
        > Stvaranje sigurnosne grupe može se onemogućiti na klijentu. U tom bi slučaju bilo potrebno ručno postavljanje i vaš Azure AD bi administrator morao [omogućiti stvaranje](/azure/active-directory/enterprise-users/groups-self-service-management) sigurnosne grupe.

    2. `ByolSetup.ps1`
        - Za pokretanje ove skripte potrebne su vam *dozvole vlasnika* blob podataka za pohranu na razini računa/spremnika za pohranu ili će vam je ova skripta stvoriti. Dodjela uloge može se ukloniti ručno nakon uspješnog pokretanja skripte.
        - Ova skripta ljuske PowerShell dodaje potrebnu kontrolu pristupa temeljenu na toleu (RBAC) za uslugu Microsoft Dataverse i sve Dataverse poslovne aplikacije koje se temelje na njima. Također ažurira Popis kontrole pristupa (ACL) u spremniku CustomerInsights za sigurnosne grupe stvorene skriptom `CreateSecurityGroups.ps1`. Grupa suradnik imat *će rwx* dozvolu, a grupa Readers imat *će samo r-x* dozvolu.
        - Izvršite ovu skriptu komponente PowerShell u komponenti Windows PowerShell tako da navedete ID pretplate na Azure koji sadrži naziv računa Azure Data Lake Storage za pohranu, naziv grupe resursa te vrijednosti ID-a Čitatelj i suradnik sigurnosne grupe. Otvorite skriptu komponente PowerShell u uređivaču da biste pregledali dodatne informacije i implementiranu logiku.
        - Kopirajte izlazni niz nakon uspješnog pokretanja skripte. Izlazni niz izgleda ovako: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Unesite izlazni niz kopiran odozgo u **polje identifikatora** dozvola koraka konfiguracije okruženja za Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Mogućnosti konfiguracije za omogućavanje zajedničkog korištenja podataka s vlastitog Azure Data Lake Storage pomoću programa Microsoft Dataverse.":::

Customer Insights ne podržava sljedeće scenarije dijeljenja podataka:
- Ako omogućite dijeljenje podataka s Dataverse, nećete moći [stvoriti predviđene ili nedostajuće vrijednosti u entitetu](predictions.md).
- Ako omogućite zajedničko korištenje podataka s programom Dataverse, nećete moći vidjeti opcionalna izvješća dodatka PowerBI Embedded u okruženju customer insights.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Uklanjanje postojeće veze s okruženjem Dataverse

Kada se povezujete s okruženjem Dataverse, poruka **o pogrešci Ova cds organizacija već je priložena drugoj instanci** Customer Insights znači da Dataverse se okruženje već koristi u okruženju Customer Insights. Postojeću vezu možete ukloniti kao globalni administrator u Dataverse okruženju. Može potrajati nekoliko sati da se popune promjene.

1. Idite na [Power Apps](https://make.powerapps.com).
1. Odaberite okruženje iz birača okruženja.
1. Idi na **rješenja**
1. Deinstalirajte ili izbrišite rješenje pod nazivom **Dynamics 365 Customer Insights Dodatak za karticu kupca (pretpregled)**.

ILI 

1. Otvorite okolinu Dataverse.
1. Otvorite **Dodatne postavkeSolutions** > **·**.
1. **Deinstalirajte rješenje CustomerInsightsCustomerCard**.

## <a name="copy-the-environment-configuration"></a>Kopiranje konfiguracije okruženja

Kao administrator možete odabrati kopiranje konfiguracije iz postojećeg okruženja kada stvorite novu. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Snimka zaslona mogućnosti postavki u postavkama okruženja.":::

Vidjet ćete popis svih dostupnih okruženja u svojoj tvrtki ili ustanovi iz kojih možete kopirati podatke.

Kopirane su sljedeće postavke konfiguracije:

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

## <a name="set-up-a-copied-environment"></a>Postavljanje kopiranog okruženja

Kada kopirate konfiguraciju okruženja, sljedeći se *podaci ne* kopiraju:

- Profili klijenata.
- Vjerodajnice izvora podataka. Morat ćete navesti vjerodajnice za svaki izvor podataka i ručno osvježiti izvore podataka.
- Izvori podataka iz mape Common Data Model i Dataverse – upravljano data lake. Te izvore podataka morat ćete stvoriti ručno s istim nazivom kao u izvornom okruženju.
- Tajne povezivanja koje se koriste za izvoz i obogaćivanje. Morate ponovno uspostaviti veze, a zatim ponovno aktivirati obogaćivanja i izvoz. 

Kad kopirate okruženje, vidjet ćete potvrdnu poruku da je stvoreno novo okruženje. Odaberite **Idi na izvore podataka** da biste vidjeli popis izvora podataka.

Svi će izvori podataka prikazati status **Potrebne su vjerodajnice**. Uredite izvore podataka i unesite vjerodajnice kako biste ih osvježili.

:::image type="content" source="media/data-sources-copied.png" alt-text="Popis izvora podataka koji su kopirani i potrebna im je provjera autentičnosti.":::

Nakon osvježenja izvora podataka, idite na **Podaci** > **Objedini**. Ovdje ćete pronaći postavke iz izvornog okruženja. Uredite ih po potrebi ili odaberite **Pokreni** za pokretanje postupka objedinjavanja podataka i stvaranje jedinstvenog entiteta klijenta.

Nakon završetka objedinjavanja podataka idite na **Mjere** i **Segmenti** da ih osvježite.

Prije nego što ponovno aktivirate izvoz i obogaćivanja, idite na **AdminConnections** > **da** biste ponovno uspostavili veze u novom okruženju.

## <a name="change-the-owner-of-an-environment"></a>Promjena vlasnika okruženja

Iako nekoliko korisnika može imati administratorske dozvole u Customer Insights, samo je jedan korisnik vlasnik okruženja. Prema zadanim postavkama administrator je taj koji u početku stvara okruženje. Kao administrator okruženja možete dodijeliti vlasništvo drugom korisniku s administratorskim dozvolama.

1. Odaberite birač **Okruženja** u zaglavlju aplikacije.

1. Odaberite ikonu **Uredi**.

1. U okviru Uređivanje okruženja **idite** na **korak Osnovne informacije**.

1. **U polju Promjena vlasnika okruženja** odaberite novog vlasnika okruženja.  

1. Odaberite **Pregled i završi**, a zatim **Ažuriraj** da biste primijenili promjene. 

## <a name="claim-ownership-of-an-environment"></a>Potraživanje vlasništva nad okruženjem

Ako vlasnik okruženja napusti organizaciju ili se njegov korisnički račun izbriše, okruženje neće imati vlasnika. Korisnik s administratorskim dozvolama može preuzeti vlasništvo i postati novi vlasnik. Oni mogu nastaviti posjedovati okoliš ili [promijeniti vlasništvo u drugog administratora](#change-the-owner-of-an-environment). 

Da biste preuzeli vlasništvo, odaberite **gumb Preuzimanje vlasništva** koji se prikazuje pri vrhu svake stranice u korisničkom uvidu kada je izvorni vlasnik napustio tvrtku ili ustanovu.

## <a name="reset-an-existing-environment"></a>Ponovno postavljanje postojećeg okruženja

Kao vlasnik okruženja možete vratiti okruženje u prazno stanje ako želite izbrisati sve konfiguracije i ukloniti unesene podatke.

1.  Odaberite birač **Okruženja** u zaglavlju aplikacije. 

2.  Odaberite okruženje koje želite ponovno postaviti i odaberite trotočje (**...**). 

3. Odaberite mogućnost **Ponovno postavi**. 

4.  Da biste potvrdili brisanje, unesite naziv okruženja i odaberite **Ponovno postavi**.

## <a name="delete-an-existing-environment"></a>Brisanje postojećeg okruženja

Kao vlasnik okruženja možete izbrisati okruženje kojim upravljate.

1.  Odaberite birač **Okruženja** u zaglavlju aplikacije.

2.  Odaberite okruženje koje želite ponovno postaviti i odaberite trotočje (**...**). 

3. Odaberite mogućnost **Izbriši**. 

4.  Da biste potvrdili brisanje, unesite naziv okruženja i odaberite **Izbriši**.

> [!NOTE]
> Brisanjem okruženja ne uklanja se Dataverse pridruživanje okruženju. Saznajte kako [ukloniti postojeću vezu s okruženjem Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE [footer-include](includes/footer-banner.md)]
