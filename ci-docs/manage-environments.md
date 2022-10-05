---
title: Upravljanje okruženjima
description: Saznajte kako upravljati postojećim okruženjima Customer Insights kao administrator.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 6d48f7088d722b27ca69cd591178651bdb6e2c23
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588803"
---
# <a name="manage-environments"></a>Upravljanje okruženjima

Administratori stvaraju [okruženja](create-environment.md) i upravljaju njima. Neke postavke mogu promijeniti u postojećim okruženjima. Poslovne postavke, vrsta, regija, mogućnost pohrane i Dataverse postavke popravljaju se nakon stvaranja okruženja. Ako želite promijeniti te postavke, [resetirajte okruženje](#reset-an-existing-environment-preview) ili [stvorite novo okruženje](create-environment.md).

## <a name="edit-an-existing-environment"></a>Uređivanje postojećeg okruženja

Uredite detalje postojećeg okruženja, kao što su naziv ili postavljanje zadanog okruženja.

1. Odaberite birač **Okruženja** u zaglavlju aplikacije.

1. Odaberite ikonu **Uredi**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikona za uređivanje postavki okruženja.":::

1. U oknu Uređivanje okruženja **ažurirajte** postavke okruženja.

1. Odaberite **Pregled i završi**, a zatim **Ažuriraj** da biste primijenili promjene.

## <a name="change-the-owner-of-an-environment"></a>Promjena vlasnika okruženja

Nekoliko korisnika može imati administratorske dozvole, ali samo je jedan korisnik vlasnik okruženja. Prema zadanim postavkama administrator je taj koji u početku stvara okruženje. Kao administrator okruženja možete dodijeliti vlasništvo drugom korisniku s administratorskim dozvolama.

1. Odaberite birač **Okruženja** u zaglavlju aplikacije.

1. Odaberite ikonu **Uredi**.

1. U oknu Uređivanje okruženja **idite** na **korak Osnovne informacije**.

1. **U polju Promjena vlasnika okruženja** odaberite novog vlasnika okruženja.  

1. Odaberite **Pregled i završi**, a zatim **Ažuriraj** da biste primijenili promjene.

## <a name="claim-ownership-of-an-environment"></a>Potraživanje vlasništva nad okruženjem

Ako se korisnički račun vlasnika izbriše ili obustavi, okruženje neće imati vlasnika. Svaki korisnik administratora može preuzeti vlasništvo i postati novi vlasnik. Administrator vlasnika može nastaviti posjedovati okruženje ili [promijeniti vlasništvo u drugog administratora](#change-the-owner-of-an-environment).

Da biste preuzeli vlasništvo, odaberite **gumb Preuzimanje vlasništva** koji se prikazuje pri vrhu svake stranice u korisničkom uvidu kada je izvorni vlasnik napustio tvrtku ili ustanovu.

## <a name="reset-an-existing-environment-preview"></a>Ponovno postavljanje postojećeg okruženja (pretpregled)

Kao vlasnik okruženja, vratite okruženje u prazno stanje ako želite izbrisati sve konfiguracije i ukloniti unesene podatke.

1. Odaberite birač **Okruženja** u zaglavlju aplikacije.

1. Odaberite okruženje koje želite vratiti na izvorno i odaberite okomitu trotočje (&vellip;).

1. Odaberite **Vrati izvorno (pretpregled)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontrola za resetiranje okruženja.":::

1. Odaberite želite li resetirati cijelo okruženje, sve osim izvora podataka ili bilo što što je konfigurirano povrh jedinstvenog korisničkog profila.

1. Da biste potvrdili, unesite naziv okruženja i odaberite **Vrati izvorno**.

## <a name="delete-an-existing-environment"></a>Brisanje postojećeg okruženja

Kao vlasnik okruženja možete ga izbrisati.

> [!IMPORTANT]
> Brisanjem okruženja ne uklanja se veza s okruženjem Dataverse. Ako ubuduće planirate povezati isto Dataverse okruženje s novim okruženjem Customer Insights, morate [ukloniti tu vezu s okolinom Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Odaberite birač **Okruženja** u zaglavlju aplikacije.

1. Odaberite okruženje koje želite izbrisati i odaberite okomitu trotočje (&vellip;). 

1. Odaberite **Izbriši**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kontrola za brisanje okruženja.":::

1. Da biste potvrdili brisanje, unesite naziv okruženja i odaberite **Izbriši**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
