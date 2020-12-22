---
title: Prikaz profila klijenata
description: Dobijte kombinirani prikaz svojih objedinjenih podataka o klijentima.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 13308c2f40cda0d7e813b4d94ab47d53b5ce2115
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653881"
---
# <a name="customer-profiles"></a>Profili klijenata

Na stranici **Klijenti** prikazuje se kombinirani prikaz vaših klijenata na temelju podataka profila prikupljenih iz [svih izvora podataka](data-sources.md). Profili klijenata dostupni su nakon što [izradite objedinjeni entitet klijenta](data-unification.md). Obavezno dovršite proces objedinjavanja podataka da biste stekli bogatije prikaze svojih klijenata. Stranica vam također omogućuje pretraživanje klijenata.

Klijenti mogu biti pojedinci ili organizacije (pretpregled). Svaki profil klijenta ili organizacije predstavljen je pločicom. Odaberite pločicu da biste vidjeli dodatne informacije o tom određenom klijentu ili organizaciji. Upotrijebite kontrole za postavljanje stranica na dnu stranice za prikaz dodatnih zapisa.

> [!div class="mx-imgBorder"] 
> ![B2C profili klijenata](media/profiles-customers.png "B2C profili klijenata")

Organizacije (pretpregled)
> [!div class="mx-imgBorder"] 
> ![B2B profili klijenata](media/profile-customers-b2b.png "B2B profili klijenata")

> [!NOTE]
> Ako ne možete vidjeti pločice kada odaberete **Klijenti** na navigacijskoj traci, vaš administrator treba [definirati barem jedan atribut koji se može pretraživati](search-filter-index.md) na **Indeksu pretraživanja i filtriranja**.

## <a name="search-for-customers"></a>Pretraživanje klijenata

Potražite klijente unosom imena ili nekog drugog atributa u okvir za pretraživanje. Pretraživanje funkcionira samo unutar entiteta Profil klijenta koji je izrađen tijekom procesa objedinjavanja podataka.

Kao administrator, možete konfigurirati atribute pretraživanja s pomoću stranice **Indeks Pretraži i filtriraj**. Za više informacija pogledajte [Upravljanje stranicom Indeks Pretraži i filtriraj](search-filter-index.md).

## <a name="filter-customers"></a>Filtriranje klijenata

Možete filtrirati klijente prema poljima entiteta Profil klijenta. Slično pretraživanju, vaš administrator najprije će morati definirati polja kao filtrirajuća s pomoću stranice **Indeks Pretraži i filtriraj**.

1. Odaberite **Filtar** na stranici **Klijenti**.

2. Potvrdite okvire pored atributa prema kojima želite filtrirati klijente.

   > [!div class="mx-imgBorder"] 
   > ![Profili klijenata](media/profiles-customers3.png "Profili klijenata")

3. Uklonite filtre odabirom opcije **Obriši filtre** na stranici **Klijenti**.

##  <a name="customer-details-page"></a>Stranica s pojedinostima o klijentu

Odaberite bilo koju pločicu klijenta da biste otvorili **Stranicu s pojedinostima o klijentu**. Ovaj prikaz sadrži objedinjene podatke za odabranog klijenta.

Pojedinosti o klijentu uključuju sljedeće:

-   **Pločica profila klijenta:** Ova pločica prikazuje različite vrijednosti iz entiteta jedinstvenog profila kupca. Te pojedinosti mogu uključivati adresu e-pošte, ime, grad itd. 

-   **Potencijalni interesi, potencijalni brendovi:** Pokazuje jeste li konfigurirali obogaćivanje prve strane. Predstavlja potencijalne interese i afinitete za brendove koje može imati klijent s profilom sličnim ovom klijentu. Za više informacija pogledajte [Obogaćivanje profila klijenata afinitetima za robne marke i interese](enrichment-microsoft-graph.md).

-   **Mjerenja:** Pokazuje jeste li konfigurirali jedno ili više mjerenja određene vrste: mjerenja korisničkih atributa. Uključuju izračunate KPI-jeve oko vaših klijenata na razini pojedinačnog klijenta. Za više informacija pogledajte [Definiranje i upravljanje mjerama](measures.md).

-   **Vremenska traka aktivnosti:** Pokazuje jeste li konfigurirali aktivnosti. Prikaz vremenske trake sadrži kronološki poredane aktivnosti ovog klijenta, počevši od najnovije aktivnosti. Za dodatne informacije pogledajte [Aktivnosti klijenata](activities.md).

Odaberite **Natrag na stranicu Klijenti** za povratak na stranicu za pretraživanje klijenata.

## <a name="next-steps"></a>Sljedeći koraci

[Dodajte više izvora podataka](data-sources.md) ili [stvorite segmente klijenta](segments.md).
