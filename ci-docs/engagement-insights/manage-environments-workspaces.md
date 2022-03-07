---
title: Upravljanje radnim prostorima i okruženjima
description: Kako stvoriti, preimenovati i izbrisati radne prostore i okruženja.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ded9e98f06109b7cdc27f449455b7f58d633722f
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350628"
---
# <a name="manage-environments-and-workspaces"></a>Upravljajte okruženjima i radnim prostorima

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Pretpregled

U ovoj se temi raspravlja o upravljanju radnim prostorima i okruženjima nakon što su već stvoreni. 

- *Radni prostor* prostor je za pohranu i upravljanje događajima i izvješćima. Tu možete pregledati korisničku aktivnost u stvarnom vremenu. Kada stvorite radni prostor, odaberite vrstu podataka koju želite poslati u radni prostor. Trenutačno su podržani web-podaci i mobilne aplikacije. Dodatne informacije potražite u članku [Stvaranje novog radnog prostora i dodavanje članova](create-workspace.md).

- *Okruženje* je prostor u kojem upravljate svojim radnim prostorima i vezama. Dodatne informacije potražite u odjeljku [Stvaranje novog okruženja](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Upravljanje postojećim radnim prostorom

Možete istovremeno održavati više radnih prostora u okruženju. Vaša [uloga](user-roles.md) određuje kako u njima možete raditi. 

 - Morate biti administrator okruženja ili administrator radnog prostora da biste upravljali radnim prostorom.
 - Kao administrator radnog prostora, možete preimenovati postojeće radne prostore ili ih izbrisati. 

:::image type="content" source="media/workspace-edit.png" alt-text="Centar za administratore radnog prostora.":::

### <a name="edit-a-workspace-name"></a>Uređivanje naziva radnog prostora

1. Idite na **Admin** > **Radni prostor** i odaberite **Postavke**.

1. U okvir **Naziv radnog prostora** unesite novi naziv.

1. Odaberite **Spremi** za primjenu izmjena.

### <a name="delete-a-workspace"></a>Brisanje radnog prostora

Brisanjem radnog prostora trajno se uklanjaju sav njegov sadržaj, podaci, postavke i dozvole. To se ne može poništiti.

1. Idite na **Admin** > **Radni prostor** i odaberite **Postavke**.

1. Odaberite **Izbriši radni prostor**. 

1. U dijaloškom okviru **Izbriši radni prostor** unesite **POTVRDI BRISANJE** velikim slovima. 

1. Odaberite **Izbriši** da biste trajno izbrisali radni prostor.

### <a name="manage-workspace-members"></a>Upravljanje članovima radnog prostora

1. Idite na **Admin** > **Radni prostor** i odaberite **Članovi**.

1. Odaberite **Dodaj članove** da biste dali pristup i [dodijelili uloge](user-roles.md). Trenutno je dostupan samo **Administrator radnog prostora**.

1. Odaberite **Dodaj članove** da biste ih dodali u svoj radni prostor.

## <a name="manage-an-existing-environment"></a>Upravljanje postojećim okruženjem

Kao administrator okruženja, okruženju možete pristupiti iz lijevog navigacijskog okna. Možete konfigurirati postavke okruženja, druge administratore okruženja i radne prostore. Odaberite kartice za kretanje između različitih područja u centru za administratore.

:::image type="content" source="media/environment-edit.png" alt-text="Centar za administratore okruženja.":::

### <a name="edit-an-environment-name"></a>Uređivanje naziva okruženja

1. Idite na **Admin** > **Okruženje** i odaberite **Postavke**.

1. Ažurirajte **Naziv okruženja** i odaberite **Spremi** da biste primijenili svoje promjene.

### <a name="delete-an-environment"></a>Brisanje okruženja

Administratori okruženja mogu izbrisati okruženja. Prije nego što možete izbrisati okruženje, morate ukloniti sve radne prostore ispod njega.

1. Idite na **Admin** > **Okruženje** i odaberite **Postavke**.

1. Odaberite **Izbriši okruženje**. 

1. U dijaloškom okviru **Izbriši radni prostor** unesite **POTVRDI BRISANJE** velikim slovima. 

1. Odaberite **Izbriši** da biste trajno izbrisali okruženje.

### <a name="manage-environment-members"></a>Upravljanje članovima okruženja

1. Idite na **Admin** > **Okruženje** i odaberite **Članovi**.

1. Odaberite **Dodaj članove** da biste ažurirali članove i [dodijelili uloge](user-roles.md). Trenutno je dostupan samo **Administrator okruženja**.

1. Odaberite **Dodaj članove** da biste ih dodali u svoje okruženje.

## <a name="manage-connections"></a>Upravljanje vezama

Uspostavljanje veza s uvidima u ciljnu skupinu omogućuje vam da vidite izvješća u uvidima u angažman na temelju objedinjenih profila klijenata. 

Više informacija potražite u članku [Izrada veze između uvida u ciljnu skupinu i uvida u angažman](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Upravljanje osobnim podacima

Da biste zaštitili osobne podatke svojeg klijenta, možete izbrisati ili izvesti podatke koji mogu identificirati krajnjeg korisnika.

Za više informacija pogledajte [Brisanje i izvoz podataka o događajima koji sadrže osobne podatke](../dsr-rights-requests.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
