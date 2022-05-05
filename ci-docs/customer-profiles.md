---
title: Prikaz profila klijenata
description: Dobijte kombinirani prikaz svojih objedinjenih podataka o klijentima.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 45ef6abcd612178a097569825e32ff9ac779de01
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642211"
---
# <a name="customer-profiles"></a>Profili klijenata

Stranica **Klijenti** prikazuje kombinirani prikaz objedinjenih profila klijenata. Profili klijenata dostupni su nakon što [stvorite objedinjeni entitet klijenta](data-unification.md). Stranica vam omogućuje pretraživanje klijenata i definiranje indeksa za pretraživanje.

Klijenti mogu biti pojedinci ili tvrtke ili ustanove. Svaki profil klijenta predstavljen je pločicom. Za dobivanje više zapisa koristite kontrole označavanja stranica. Kartica prikazuje polja iz entiteta *Klijent* kako je definirano u opciji **Pretraži i filtriraj indeks**. Redoslijed polja unutar svake kartice odabire sustav.

Odaberite pločicu da biste vidjeli podatke o odabranom klijentu na namjenskoj stranici pod nazivom [Stranica s pojedinostima o klijentu](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Stranica klijenata prikazuje pločice rezultata](media/customers-page-result-tiles-B2C.png "Stranica klijenata prikazuje pločice rezultata")

> [!NOTE]
> Ako ne vidite pločice prilikom odabira opcije **Klijenti** u navigaciji, administrator mora [definirati barem jedan atribut koji se može pretraživati](search-filter-index.md) u opciji **Pretraži i filtriraj indeks**.

## <a name="search-for-customers"></a>Pretraživanje klijenata

Potražite klijente unosom imena ili nekog drugog atributa u okvir za pretraživanje. Pretraživanje radi samo unutar entiteta _Klijent_ koji je stvoren tijekom procesa objedinjavanja podataka.

Kao administrator, možete konfigurirati atribute pretraživanja s pomoću stranice **Indeks Pretraži i filtriraj**. Dodatne informacije potražite u odjeljku [Upravljanje pretraživanjem i filtriranjem indeksa](search-filter-index.md).

## <a name="filter-customers"></a>Filtriranje klijenata

Klijente možete filtrirati prema poljima entiteta _Klijent_. Slično pretraživanju, vaš administrator najprije će morati definirati polja kao filtrirajuća s pomoću stranice **Indeks Pretraži i filtriraj**.

1. Odaberite **Prikaži filtre** na stranici **Klijenti**.

1. Potvrdite okvire pored atributa prema kojima želite filtrirati klijente.

1. Uklonite filtre odabirom opcije **Obriši filtre** na stranici **Klijenti**.

## <a name="customer-details-page"></a>Stranica s pojedinostima o klijentu

Odaberite bilo koju pločicu klijenta da biste otvorili **Stranicu s pojedinostima o klijentu**. Ovaj prikaz sadrži objedinjene podatke za odabranog klijenta. Pojedinosti o klijentima uključuju sljedeći sadržaj:

**Pločica profila klijenta**: Ova pločica prikazuje različite vrijednosti od objedinjenog entiteta _Klijent_. Ako polje nema vrijednost za odabrani profil klijenta, neće se prikazati. Pločica je strukturirana u dijelove:  
  - Prvi odjeljak prikazuje unaprijed definirani skup polja, nakon kojih slijede sva polja koja su dio opcije pretraživanja i filtriranja indeksa. Sva polja povezana s adresom kombiniraju se u jedan redak ako profil sadrži takva polja. 
  - **Kontakti za ovog klijenta**: U okruženjima za poslovne račune kao drugi odjeljak vidjet ćete sve povezane kontakte za ovog klijenta. Svaki kontakt prikazan je sa svojim poljima. Prazna polja su skrivena.
  - **Dodatna polja**: Prikazuje preostala polja odabranog klijenta, osim ID-ova. 
  - **ID-ovi**: Navodi sve ID-ove pod odgovarajućim nazivom entiteta. Polja su identificirana kao ID-ovi svojom semantikom, koja ih kategorizira kao takve.

**Vremenska traka aktivnosti**: Prikazuje podatke ako ste konfigurirali aktivnosti. Prikaz vremenske trake sadrži kronološki razvrstane aktivnosti odabranog klijenta, počevši od najnovije aktivnosti. Dodatne informacije potražite u odjeljku [Aktivnosti klijenta](activities.md).

**Uvidi**:  
  - **Mjere**: Prikazuje ako ste konfigurirali jednu ili više mjera atributa klijenta. Uključuju izračunate KPI-jeve oko vaših klijenata na razini pojedinačnog klijenta. Dodatne informacije potražite u odjeljku [Definiranje i upravljanje mjerama](measures.md).

  - **Potencijalni interesi, potencijalne robne marke**: Prikazuje ako ste konfigurirali obogaćivanje afiniteta prema robnoj marki ili interesu. Predstavlja potencijalne interese i afinitete za robne marke na temelju drugih klijenata čiji je profil sličan profilu odabranog klijenta. Dodatne informacije potražite u odjeljku [Obogaćivanje profile klijenata afinitetima prema robnim markama i interesima](enrichment-microsoft.md).

Za povratak na stranicu za pretraživanje klijenata odaberite **Povratak klijentima**.

## <a name="next-steps"></a>Sljedeći koraci

[Dodati više izvora podataka](data-sources.md), [obogatiti objedinjene profile](enrichment-hub.md) ili [stvoriti segmente](segments.md) za rad s objedinjenim profilima klijenata u drugim aplikacijama.


[!INCLUDE [footer-include](includes/footer-banner.md)]
