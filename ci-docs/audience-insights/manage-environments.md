---
title: Izrada okruženja i upravljanje njima
description: Saznajte kako se prijaviti za uslugu i kako upravljati okruženjima.
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376867"
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

Da biste koristili [gotove modele predviđanja](predictions-overview.md#out-of-box-models), konfigurirajte dijeljenje podataka s platformom Dataverse. Ili možete omogućiti uvoz podataka iz lokalnih izvora podataka, navodeći URL okruženja Microsoft Dataverse kojim upravlja vaša tvrtka ili ustanova.

> [!IMPORTANT]
> Uvidi u kupce i Dataverse moraju biti u istoj regiji kako biste omogućili dijeljenje podataka.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Mogućnosti konfiguracije za omogućavanje dijeljenja podataka uz Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights ne podržava sljedeće scenarije dijeljenja podataka:
> - Ako sve podatke spremite na vlastiti Azure Data Lake Storage, nećete moći omogućiti dijeljenje podataka s data lake kojim upravlja Dataverse.
> - Ako omogućite dijeljenje podataka s Dataverse, nećete moći [stvoriti predviđene ili nedostajuće vrijednosti u entitetu](predictions.md).

## <a name="copy-the-environment-configuration"></a>Kopiranje konfiguracije okruženja

Kada stvorite novo okruženje, možete odabrati kopiranje konfiguracije iz postojećeg okruženja. 

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

Sljedeći podaci *nisu* kopirani:

- Profili klijenata.
- Vjerodajnice izvora podataka. Morat ćete navesti vjerodajnice za svaki izvor podataka i ručno osvježiti izvore podataka.

- Izvori podataka iz mape Common Data Model i Dataverse – upravljano data lake. Te izvore podataka morat ćete stvoriti ručno s istim nazivom kao u izvornom okruženju.

Kad kopirate okruženje, vidjet ćete potvrdnu poruku da je stvoreno novo okruženje. Odaberite **Idi na izvore podataka** da biste vidjeli popis izvora podataka.

Svi će izvori podataka prikazati status **Potrebne su vjerodajnice**. Uredite izvore podataka i unesite vjerodajnice kako biste ih osvježili.

:::image type="content" source="media/data-sources-copied.png" alt-text="Popis izvora podataka koji su kopirani i potrebna im je provjera autentičnosti.":::

Nakon osvježenja izvora podataka, idite na **Podaci** > **Objedini**. Ovdje ćete pronaći postavke iz izvornog okruženja. Uredite ih po potrebi ili odaberite **Pokreni** za pokretanje postupka objedinjavanja podataka i stvaranje jedinstvenog entiteta klijenta.

Nakon završetka objedinjavanja podataka idite na **Mjere** i **Segmenti** da ih osvježite.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
