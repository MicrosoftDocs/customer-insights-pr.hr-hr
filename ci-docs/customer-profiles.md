---
title: Prikaz profila klijenata
description: Prikaz jedinstvenih podataka o klijentima, uključujući korištenje pretraživanja i filtriranja
ms.date: 06/08/2022
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
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188084"
---
# <a name="view-customer-profiles"></a>Prikaz profila klijenata

Profili kupaca dostupni su nakon što [stvorite jedinstveni *entitet Klijent*](data-unification.md). Kombinirani prikaz vaših jedinstvenih profila kupaca prikazuje se na **stranici Kupci**. Klijenti mogu biti pojedinci ili tvrtke ili ustanove.

Idite na **stranicu Kupci** da biste vidjeli svoje klijente i njihove profile. Svaki profil klijenta predstavljen je pločicom. Za dobivanje više zapisa koristite kontrole označavanja stranica. Kartica prikazuje polja iz entiteta *Klijent* kako je definirano u opciji **Pretraži i filtriraj indeks**. Redoslijed polja unutar svake kartice odabire sustav.

> [!NOTE]
> Ako pločice ne vidite kada odaberete **Kupci**, administrator mora definirati barem jedan atribut [koji se](search-filter-index.md) može pretraživati u indeksu **pretraživanja** i filtriranja.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Stranica kupci na kojoj se prikazuju pločice rezultata.":::

Odaberite neku od sljedećih akcija:
- [Prikaz detalja o klijentu](#view-customer-details)
- [Upravljanje indeksom](search-filter-index.md) pretraživanja i filtriranja (samo za administratore)
- [Filtriranje klijenata](#filter-customers)
- **Proširivanje kartica** ili **sažimanje kartica** radi proširenja ili sažimanja podataka prikazanih na pločici kupca
- **Sortiranje po** određenom atributu
- [Pretraživanje klijenata](#search-for-customers)

  > [!NOTE]
  > Da bi koristio pretraživanje i filtriranje, administrator mora konfigurirati atribute koji se mogu pretraživati i definirati polja koja se mogu filtrirati pomoću indeksa pretraživanja i filtra.

## <a name="search-for-customers"></a>Pretraživanje klijenata

Potražite klijente unosom imena ili nekog drugog atributa u **korisničke korisnike** pretraživanja. Atribute koji se mogu pretraživati definira administrator i dolaze iz jedinstvenog *entiteta Klijent*.

> [!NOTE]
> **Niz** je jedina vrsta podataka koja je uključena u pretraživanje. Koristite ga u **polju Pretraži kupce** na stranici Kupci da biste potražili kupce.

## <a name="filter-customers"></a>Filtriranje klijenata

Filtrirajte kupce prema poljima entiteta *Kupac*. Polja koja se mogu filtrirati definira administrator.

1. **Na stranici Kupci** odaberite **Pokaži filtre**. Prikazuje se okno Filtar.

1. Potvrdite okvire pored atributa prema kojima želite filtrirati klijente.

1. Uklonite sve filtre tako da odaberete **Očisti filtre ili poništite** potvrdni okvir pokraj odabranog atributa.

1. Odaberite **Sakrij filtre** da biste zatvorili okno filtra.

1. Da biste rezultate filtra spremili kao [segment](segments.md), odaberite **Spremi filtre kao segment**.
   1. Unesite naziv segmenta.
   1. Odaberite **Spremi** da biste spremili segment.
   1. Odaberite želite li sada pokrenuti segment tako **da odaberete Aktiviraj** ga ili pokrenite **kasnije**.

## <a name="view-customer-details"></a>Prikaz detalja o klijentu

**Na stranici Kupci** odaberite pločicu kupca da biste vidjeli detalje za odabranog kupca.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Stranica s detaljima o kupcu.":::

Pojedinosti o klijentu uključuju sljedeće:

**Pločica** profila klijenta prikazuje različite vrijednosti od objedinjenog *entiteta Klijent*. Ako polje nema vrijednost za odabrani profil kupca, neće se prikazati osim polja adrese. Pločica je strukturirana u dijelove:

- Prvi odjeljak prikazuje unaprijed definirani skup polja, nakon kojih slijede sva polja koja su dio opcije pretraživanja i filtriranja indeksa. Sva polja povezana s adresom kombinirana su u jedan redak, što pokazuje čak i ako profil ne sadrži podatke o adresi.
- **Kontakti za ovog klijenta** prikazuju se u okruženjima za poslovne račune. Svaki kontakt prikazan je sa svojim poljima. Prazna polja su skrivena.
- **Dodatna polja** prikazuju preostala polja odabranog kupca, osim ID-ova.
- **ID-ovi** navode sve ID-ove pod odgovarajućim nazivom entiteta. Polja su identificirana kao ID-ovi po njihovoj semantici.

**Vremenska traka** aktivnosti prikazuje podatke ako ste konfigurirali [aktivnosti](activities.md). Prikaz vremenske trake sadrži kronološki razvrstane aktivnosti odabranog klijenta, počevši od najnovije aktivnosti.

**Uvidi**:

- **Mjere** pokazuju jeste li konfigurirali mjere atributa [kupca](measures.md). Uključuju izračunate KPI-jeve oko vaših klijenata na razini pojedinačnog klijenta.

- **Potencijalni interesi, potencijalne marke** pokazuju jeste li konfigurirali marku [ili obogaćivanje](enrichment-microsoft.md) afiniteta interesa. Predstavlja potencijalne interese i afinitete za robne marke na temelju drugih klijenata čiji je profil sličan profilu odabranog klijenta.

Da biste se vratili na **stranicu Kupci**, odaberite **Povratak kupcima**.

## <a name="next-steps"></a>Sljedeći koraci

[Dodati više izvora podataka](data-sources.md), [obogatiti objedinjene profile](enrichment-hub.md) ili [stvoriti segmente](segments.md) za rad s objedinjenim profilima klijenata u drugim aplikacijama.

[!INCLUDE [footer-include](includes/footer-banner.md)]
