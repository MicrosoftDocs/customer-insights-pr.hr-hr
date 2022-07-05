---
title: 'Kako: upravljati okruženjima'
description: Saznajte kako upravljati postojećim okruženjima Customer Insights kao administrator."
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: fc3b3f404cf0ac84c782778414494289c803babe
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083054"
---
# <a name="how-to-manage-environments"></a>Kako: upravljati okruženjima

Administratori stvaraju [okruženja](create-environment.md) i upravljaju njima. Neke postavke mogu promijeniti u postojećim okruženjima. Poslovne postavke, vrsta, regija, mogućnost pohrane i Dataverse postavke popravljaju se nakon stvaranja okruženja. Ako želite promijeniti te postavke, resetirajte okruženje ili stvorite novo okruženje.

## <a name="edit-an-existing-environment"></a>Uređivanje postojećeg okruženja

Možete urediti neke pojedinosti postojećih okruženja.

1. Odaberite birač **Okruženja** u zaglavlju aplikacije.

1. Odaberite ikonu **Uredi**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikona za uređivanje postavki okruženja.":::

1. U okviru **Uredi okruženje** možete ažurirati postavke okruženja.

Upute za početak rada sa svježim okruženjem potražite u članku [Stvaranje novog okruženja](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Promjena vlasnika okruženja

Nekoliko korisnika može imati administratorske dozvole, ali samo je jedan korisnik vlasnik okruženja. Prema zadanim postavkama administrator je taj koji u početku stvara okruženje. Kao administrator okruženja možete dodijeliti vlasništvo drugom korisniku s administratorskim dozvolama.

1. Odaberite birač **Okruženja** u zaglavlju aplikacije.

1. Odaberite ikonu **Uredi**.

1. U okviru Uređivanje okruženja **idite** na **korak Osnovne informacije**.

1. **U polju Promjena vlasnika okruženja** odaberite novog vlasnika okruženja.  

1. Odaberite **Pregled i završi**, a zatim **Ažuriraj** da biste primijenili promjene.

## <a name="claim-ownership-of-an-environment"></a>Potraživanje vlasništva nad okruženjem

Ako se korisnički račun vlasnika izbriše ili obustavi, okruženje neće imati vlasnika. Svaki korisnik administratora može preuzeti vlasništvo i postati novi vlasnik. Oni mogu nastaviti posjedovati okoliš ili [promijeniti vlasništvo u drugog administratora](#change-the-owner-of-an-environment).

Da biste preuzeli vlasništvo, odaberite **gumb Preuzimanje vlasništva** koji se prikazuje pri vrhu svake stranice u korisničkom uvidu kada je izvorni vlasnik napustio tvrtku ili ustanovu.

## <a name="reset-an-existing-environment-preview"></a>Ponovno postavljanje postojećeg okruženja (pretpregled)

Kao vlasnik okruženja možete vratiti okruženje u prazno stanje ako želite izbrisati sve konfiguracije i ukloniti unesene podatke.

1. Odaberite birač **Okruženja** u zaglavlju aplikacije.

1. Odaberite okruženje koje želite vratiti na izvorno i odaberite okomitu trotočje (&vellip;).

1. Odaberite mogućnost **Ponovno postavi**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontrola za resetiranje okruženja.":::

1. Odaberite želite li resetirati cijelo okruženje, sve osim izvora podataka ili bilo što što je konfigurirano povrh jedinstvenog korisničkog profila.

1. Da biste potvrdili, unesite naziv okruženja i odaberite **Vrati izvorno**.

## <a name="delete-an-existing-environment"></a>Brisanje postojećeg okruženja

Kao vlasnik okruženja možete izbrisati okruženje kojim upravljate.

1. Odaberite birač **Okruženja** u zaglavlju aplikacije.

1. Odaberite okruženje koje želite vratiti na izvorno i odaberite okomitu trotočje (&vellip;). 

1. Odaberite mogućnost **Izbriši**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kontrola za brisanje okruženja.":::

1. Da biste potvrdili brisanje, unesite naziv okruženja i odaberite **Izbriši**.

> [!IMPORTANT]
> Brisanjem okruženja ne uklanja se veza s okruženjem Dataverse. Ako ubuduće planirate povezati isto Dataverse okruženje s novim okruženjem Customer Insights, morate ukloniti tu vezu Saznajte kako [ukloniti postojeću vezu s okruženjem Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
