---
title: Upravljanje radnim prostorima i okruženjima
description: Kako stvoriti, preimenovati i izbrisati radne prostore i okruženja.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486026"
---
# <a name="manage-environments-and-workspaces"></a>Upravljajte okruženjima i radnim prostorima

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Pretpregled

Radni prostor prostor je za pohranu i upravljanje događajima i izvješćima. Tu možete pregledati korisničku aktivnost u stvarnom vremenu. Kada stvorite radni prostor, odaberite vrstu podataka koju želite poslati u radni prostor. Trenutačno su podržani web-podaci i mobilne aplikacije.

Okruženje je prostor u kojem upravljate svojim radnim prostorima i vezama. Način na koji koristite okruženja ovisi o vašoj tvrtki ili ustanovi i vašem slučaju korištenja. Primjerice, možete stvoriti:

-   Jedno okruženje.
-   Odvojena okruženja za ispitivanje i proizvodnju.
-   Odvojena okruženja za određene timove ili odjele u vašoj tvrtki ili ustanovi koja sadrže relevantne događaje za svaku ciljnu skupinu.
-   Odvojena okruženja za različite globalne podružnice vaše tvrtke.
-   Veze s mogućnošću uvida u ciljnu skupinu Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Odaberite okruženje i stvorite radni prostor 

Svaki radni prostor treba biti u okruženju. Možete odabrati već postojeće okruženje ili izraditi novo prilikom stvaranja radnog prostora. Tada možete odabrati dodavanje članova radnog prostora i započeti prikupljanje podataka.

**Stvaranje prvog radnog mjesta**

1. U uvidima u angažman odaberite **Novo** iz prebacivača radnog prostora. 

   :::image type="content" source="media/New-workspace.png" alt-text="Birač radnog prostora stranice Customer Insights.":::

1. Odaberite okruženje s popisa ili odaberite **Stvori novo okruženje**.

1. Unesite naziv pod **Naziv radnog prostora**. 

1. Odaberite vrstu okruženja koje želite stvoriti, ovisno o tome želite li mjeriti što se događa na web-mjestu ili u mobilnoj aplikaciji. 

1. Možete dodati članove i dodijeliti im razinu dopuštenja s popisa **Uloga**. Zatim odaberite **Završi** za stvaranje radnog prostora ili **Dalje** za instaliranje koda. 

1. Instalirajte isječak koda da biste počeli primati podatke, a zatim odaberite **Gotovo**. 

## <a name="manage-a-workspace"></a>Upravljanje radnim prostorom

Možete istovremeno održavati više radnih prostora u okruženju. Vaša [uloga](user-roles.md) određuje kako u njima možete raditi. 

 - Morate biti administrator okruženja ili administrator radnog prostora da biste upravljali radnim prostorom.
 - Kao administrator radnog prostora, možete preimenovati postojeće radne prostore ili ih izbrisati. 

### <a name="edit-a-workspace-name"></a>Uređivanje naziva radnog prostora

1. Idite na **Admin** > **Radni prostor** i odaberite **Postavke**.

1. U okvir **Naziv radnog prostora** unesite novi naziv.

1. Odaberite **Spremi** za primjenu izmjena.

### <a name="delete-a-workspace"></a>Brisanje radnog prostora

Brisanje radnog prostora trajno će se ukloniti sav njegov sadržaj, podatke, postavke i dozvole. To se ne može poništiti.

1. Idite na **Admin** > **Radni prostor** i odaberite **Postavke**.

1. Odaberite **Izbriši radni prostor**. 

1. U dijalogu **Izbriši radni prostor** unesite **POTVRDI BRISANJE**. 

1. Odaberite **Izbriši** da biste trajno izbrisali radni prostor.

### <a name="manage-workspace-members"></a>Upravljanje članovima radnog prostora

1. Idite na **Admin** > **Radni prostor** i odaberite **Članovi**.

1. Odaberite **Dodaj članove** da biste dali pristup i [dodijelili uloge](user-roles.md). Trenutno je dostupan samo **Administrator radnog prostora**.

1. Odaberite **Dodaj članove** da biste ih dodali u svoj radni prostor.

## <a name="manage-an-environment"></a>Upravljanje okruženjem

Kao administrator okruženja okruženju možete pristupiti iz lijevog navigacijskog okna. Možete konfigurirati postavke okruženja, druge administratore okruženja i radne prostore. Odaberite kartice za kretanje između različitih područja u centru za administratore.

:::image type="content" source="media/New-environment.png" alt-text="Centar za administratore okruženja.":::

### <a name="create-an-environment"></a>Stvaranje okruženja

1. U biraču radnog prostora odaberite **+Novo**.

1. U vođenom iskustvu otvorite padajući izbornik **Okruženje** i odaberite **Stvori novo okruženje**. 

1. Navedite **Naziv okruženja**.

   :::image type="content" source="media/create-environment.png" alt-text="Zakoračite u vođeno iskustvo kako biste naveli pojedinosti o okruženju.":::

1. Odaberite **Regija** i odaberite **Dalje**. 

1. Navedite naziv radnog prostora i odaberite vrstu radnog prostora koju želite stvoriti. 

1.  Neobavezno dodajte članove i kopirajte isječak koda da biste dovršili postupak stvaranja.

### <a name="rename-an-environment"></a>Preimenovanje okruženja

1. Idite na **Admin** > **Okruženje** i odaberite **Postavke**.

1. Ažurirajte **Naziv okruženja** i odaberite **Spremi** da biste primijenili svoje promjene.

### <a name="manage-environment-members"></a>Upravljanje članovima okruženja

1. Idite na **Admin** > **Okruženje** i odaberite **Članovi**.

1. Odaberite **Dodaj članove** da biste ažurirali članove i [dodijelili uloge](user-roles.md). Trenutno je dostupan samo **Administrator okruženja**.

1. Odaberite **Dodaj članove** da biste ih dodali u svoje okruženje.

### <a name="delete-an-environment"></a>Brisanje okruženja

Administratori okruženja mogu izbrisati okruženja. Prije nego što možete izbrisati okruženje, morate ukloniti sve radne prostore ispod njega.

1. Idite na **Admin** > **Okruženje** i odaberite **Postavke**.

1. Odaberite **Izbriši okruženje**. 

1. U dijalogu **Izbriši radni prostor** unesite **POTVRDI BRISANJE**. 

1. Odaberite **Izbriši** da biste trajno izbrisali okruženje.

## <a name="manage-connections"></a>Upravljanje vezama

Uspostavljanje veza s uvidima u ciljnu skupinu omogućuje vam da vidite izvješća u uvidima u angažman na temelju objedinjenih profila klijenata. 

Više informacija potražite u članku [Izrada veze između uvida u ciljnu skupinu i uvida u angažman](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Upravljanje osobnim podacima

Da biste zaštitili osobne podatke svojeg klijenta, možete izbrisati ili izvesti podatke koji mogu identificirati krajnjeg korisnika.

Za više informacija pogledajte [Brisanje i izvoz podataka o događajima koji sadrže osobne podatke](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
