---
title: Dodjela korisničkih dozvola
description: Saznajte više o dozvolama i korisničkim ulogama.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245410"
---
# <a name="assign-user-permissions"></a>Dodjela korisničkih dozvola

Pristup korisničkim uvidima ograničen je na korisnike u vašoj tvrtki ili ustanovi koje je administrator dodao u aplikaciju. Administrator može dodavati, uređivati ili uklanjati korisnike. Korisnik može biti jedan korisnik, grupa ili aplikacija. Postoje tri vrste uloga koje korisnik može imati:

## <a name="viewer"></a>Gledatelj

- Istražite uvide i segmente unutar stranica **Početna stranica** i **Segmenti**.
- Pretražite i filtrirajte profile klijenata s pomoću stranice **Klijenti**. Polja moraju biti pretraživa.
- Prikaži i istraži stranicu **Obogaćivanje**.
- Istražujte i izvozite entitete s pomoću stranice **Entiteti**.
- Pregledajte status procesnih sustava s pomoću stranice **Sustav**.
- Prikaži izvoze na stranici **Izvozi**.
- Instalirajte i koristite nadzornu ploču **Power BI Customer Insights**.

## <a name="contributor"></a>Suradnik

- Sve dozvole koje su dostupne Gledatelju.
- Učitavajte i pretvarajte podatke pomoću stranice **Izvori podataka**.
- Dovršite **objedinjavanje** podataka koje rezultira jedinstvenim entitetom korisničkog profila.
- Definirajte **Odnosi** i **Aktivnosti**.
- Stvorite segmente pomoću stranice **Segmenti**.
- Izradite mjere s pomoću stranice **Mjere**.
- Upravljajte konfiguracijom i obogaćujte korisničke profile sa stranice **Obogaćivanje** (samo za obogaćivanja prve strane).
- Upravljajte izvozom i stvarajte ih na [temelju veza koje se zajednički koriste sa suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administrativna cjelina

- Sve dozvole koje su dostupne Suradniku.
- Promijenite postavke na **stranici Sustav**, uključujući radni jezik, raspored osvježavanja sistemskih procesa i izvoz dijagnostičkih zapisnika.
- Promijenite postavke na **stranici Sigurnost**, uključujući korisnike, API ključeve, privatne veze i trezor ključeva.
- Postavite definicije pretraživanja i filtriranja za stranicu Klijenti pomoću stranice **Indeks pretraživanja i filtriranja** (dostupna putem stranice **Klijenti**).
- Upravljajte vezama i dopustite im ostale korisničke uloge na stranici **Veze**.
- Upravljajte konfiguracijom i obogaćujte korisničke profile sa stranice **Obogaćivanje** (za sva obogaćivanja).
- Upravljajte i stvarajte izvoze na stranici **Izvozi**.
- Instalirajte i koristite **Dodatak za karticu klijenta**.
- Dodajte i koristite **Power Apps poveznik**.
- Omogućite korištenje [API-jeva za Customer Insights](apis.md).
- [Dodijelite vlasništvo nad](manage-environments.md#change-the-owner-of-an-environment) okolišem drugom administratoru.

## <a name="admin-owner"></a>Administrator (vlasnik)

- Sve dozvole dostupne administratoru.
- [Resetirajte i izbrišite](manage-environments.md#reset-an-existing-environment-preview) okruženje.

## <a name="add-users"></a>Dodavanje korisnika

1. Otvorite **Sigurnost administratora** > **i** odaberite karticu **Korisnici**.

1. Odaberite **Dodaj korisnike** da biste otvorili okno **Dodaj/uredi dozvole**.

1. **Pomoću polja Pretraživanje** pronađite korisnika ili grupu Azure Active Directory koju želite dodati. Odaberite mogućnost **Uloga** za dodjelu tom korisniku ili grupi.

1. Odaberite **Spremi**. Trenutno okruženje automatski se dijeli s korisnikom ili članovima grupe. Korisnici mogu pristupiti aplikaciji Customer Insights i raditi u skladu s njihovom zadanom ulogom.

## <a name="view-current-permissions"></a>Pregledaj trenutačne dozvole

Otvorite **Sigurnost administratora** > **i odaberite karticu** Korisnici **da biste pogledali popis aktivnih korisnika i njihove** dodjele uloga. Popis korisnika možete sortirati po bilo kojem stupcu ili pomoću okvira za pretraživanje pronaći određenog korisnika.

## <a name="manage-current-users"></a>Upravljanje trenutnim korisnicima

Otvorite **Sigurnost administratora** > **i** odaberite karticu **Korisnici**. Popis korisnika možete sortirati po bilo kojem stupcu ili pomoću okvira za pretraživanje pronaći korisnika kojim želite upravljati.

Odaberite korisnika da biste vidjeli dostupne akcije.

- **Uredite** da biste uredili ulogu korisnika u odjeljku Uvidi kupaca. Odaberite **Spremi** da biste potvrdili promjenu.
- **Uklonite** da biste uklonili korisnika iz pristupa uvidima u kupca. Odaberite **Izbriši** da biste potvrdili brisanje.

[!INCLUDE [footer-include](includes/footer-banner.md)]
