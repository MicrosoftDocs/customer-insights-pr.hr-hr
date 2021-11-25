---
title: Izrada okruženja i upravljanje njima
description: Saznajte kako se prijaviti za uslugu i kako upravljati okruženjima.
ms.date: 11/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 65c6a68f550c2873ec30c6ac54f1752d880ce12c
ms.sourcegitcommit: fb9f118b4e16b5aabb3e503463efca21718f5d72
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/12/2021
ms.locfileid: "7815895"
---
# <a name="manage-environments"></a>Upravljanje okruženjima

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

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

## <a name="connect-to-microsoft-dataverse"></a>Povezivanje s Microsoft Dataverse
   
Korak **Microsoft Dataverse omogućuje vam povezivanje** uvida u korisnike s Dataverse okruženjem.

Da biste [koristili gotove predviđanje modele](predictions-overview.md#out-of-box-models), konfigurirajte zajedničko korištenje podataka pomoću Dataverse. Ili možete omogućiti unos podataka iz lokalno izvora podataka, pružajući URL Microsoft Dataverse okruženja kojim upravlja vaša tvrtka ili ustanova. Odaberite **Omogući zajedničko korištenje podataka da biste** izlazne podatke customer insights zajednički koristili s podatkovnim jezerom kojim upravlja Dataverse.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Mogućnosti konfiguracije za omogućavanje zajedničkog korištenja podataka s Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights ne podržava sljedeće scenarije dijeljenja podataka:
> - Ako sve podatke spremite u vlastitu Azure Data Lake Storage, nećete moći omogućiti dijeljenje podataka s podatkovnim jezerom kojim upravlja Dataverse.
> - Ako omogućite zajedničko korištenje podataka sa Dataverse, nećete moći [stvarati predviđene ili nedostajuće vrijednosti u entitetu](predictions.md).

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

- Izvori podataka iz mape Zajednički podatkovni model i podatkovnog jezera s upravljanjem dataverse. Te izvore podataka morat ćete stvoriti ručno s istim nazivom kao u izvornom okruženju.

Kad kopirate okruženje, vidjet ćete potvrdnu poruku da je stvoreno novo okruženje. Odaberite **Idi na izvore podataka** da biste vidjeli popis izvora podataka.

Svi će izvori podataka prikazati status **Potrebne su vjerodajnice**. Uredite izvore podataka i unesite vjerodajnice kako biste ih osvježili.

:::image type="content" source="media/data-sources-copied.png" alt-text="Popis izvora podataka koji su kopirani i potrebna im je provjera autentičnosti.":::

Nakon osvježenja izvora podataka, idite na **Podaci** > **Objedini**. Ovdje ćete pronaći postavke iz izvornog okruženja. Uredite ih po potrebi ili odaberite **Pokreni** za pokretanje postupka objedinjavanja podataka i stvaranje jedinstvenog entiteta klijenta.

Nakon završetka objedinjavanja podataka idite na **Mjere** i **Segmenti** da ih osvježite.

## <a name="reset-an-existing-environment"></a>Ponovno postavljanje postojećeg okruženja

Kao administrator možete ponovno postaviti okruženje u prazno stanje ako želite izbrisati sve konfiguracije i ukloniti unesene podatke.

1.  Odaberite birač **Okruženja** u zaglavlju aplikacije. 

2.  Odaberite okruženje koje želite ponovno postaviti i odaberite trotočje (**...**). 

3. Odaberite mogućnost **Ponovno postavi**. 

4.  Da biste potvrdili brisanje, unesite naziv okruženja i odaberite **Ponovno postavi**.

## <a name="delete-an-existing-environment"></a>Brisanje postojećeg okruženja

Kao administrator možete izbrisati okruženje koje administrirate.

1.  Odaberite birač **Okruženja** u zaglavlju aplikacije.

2.  Odaberite okruženje koje želite ponovno postaviti i odaberite trotočje (**...**). 

3. Odaberite mogućnost **Izbriši**. 

4.  Da biste potvrdili brisanje, unesite naziv okruženja i odaberite **Izbriši**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
