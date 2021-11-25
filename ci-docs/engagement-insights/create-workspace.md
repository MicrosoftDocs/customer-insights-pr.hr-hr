---
title: Stvaranje novog radnog prostora
description: Svrha radnog prostora i kako stvoriti novi.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f8922703af506974c8b5b24086b61f05a83609d
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673373"
---
# <a name="create-a-new-workspace-and-add-members"></a>Stvaranje novog radnog prostora i dodavanje članova

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Radni prostor je način na koji možete pregledati aktivnost klijenta u stvarnom vremenu radi boljeg razumijevanja ciljne skupine. Tu pohranjujete događaje i izvješća i upravljate njima.

Kada stvarate radni prostor, odabirete vrstu podataka na koje se želite usredotočiti. U svakom trenutku možete dodati druge korisnike ili članove u postojeći radni prostor. 

## <a name="create-a-new-workspace"></a>Stvaranje novog radnog prostora

Postupak stvaranja radnog prostora uključuje postavljanje *okruženja* za organiziranje radnog prostora. Okruženje je prostor koji može sadržavati jedan ili više radnih prostora. Okruženjem možete upravljati svojim radnim prostorima i vezama s mogućnošću uvida u publika.

1. Na **·** prekidaču radnog prostora odaberite +Novo.

   :::image type="content" source="media/new-workspace.png" alt-text="Stranica Uvidi u klijenta s oblačićim u navigacijskom oknu i opisu.":::

1. U okno **Radni prostor** unesite **Naziv radnog prostora**.

   :::image type="content" source="media/workspace-name.png" alt-text="Unesite naziv radnog prostora.":::

1. Odaberite vrstu platforme (web ili mobilnu) koju želite izmjeriti.

1. Odaberite **Prikaži napredne postavke** da biste omogućili ili onemogućili te izborne postavke:

   - Prebacite **Od nepoznatog do poznatog** na „omogućeno” kako biste povezali web-događaje s korisnicima čija je autentičnost prethodno provjerena. Dodatne informacije potražite u odjeljku [Prepoznajte web-događaje od prethodno provjerenih posjetitelja](unknown-to-known.md)
   - Prebacite **Filtriraj promet botova** na „omogućeno” za uklanjanje web-prometa botova za ovaj radni prostor. 

1. Odaberite **Dovršeno** kad završite. 

1. Instalirajte isječak koda da biste počeli primati podatke, a zatim odaberite **Završi** za stvaranje radnog prostora. Za dodatne informacije pogledajte [Pregled resursa za razvojne inženjere](developer-resources.md).

> [!NOTE]
> Sada možete dodati članove i dodijeliti im razinu dozvole s popisa **Uloga**. Za više informacija pogledajte [Uloge i dopuštenja](user-roles.md). 

Za više informacija pogledajte [Upravljanje okruženjima i radnim prostorima](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
