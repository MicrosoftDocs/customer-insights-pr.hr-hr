---
title: Stvaranje novog okruženja
description: Svrha okruženja i kako stvoriti novo.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 8ff04a6b2ffbd513a77f7f8a33358f3d8f559c7e
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673633"
---
# <a name="create-a-new-environment"></a>Stvaranje novog okruženja 

## <a name="overview"></a>Pretpregled

Okruženje je prostor u kojem upravljate svojim radnim prostorima i vezama. Način na koji koristite okruženja ovisi o vašoj tvrtki ili ustanovi i vašem slučaju korištenja. Primjerice, možete stvoriti:

- Jedno okruženje.
- Odvojena okruženja za ispitivanje i proizvodnju.
- Odvojena okruženja za određene timove ili odjele u vašoj tvrtki ili ustanovi koja sadrže relevantne događaje za svaku ciljnu skupinu.
- Odvojena okruženja za različite globalne podružnice vaše tvrtke.
- Veze s mogućnošću uvida u ciljnu skupinu Customer Insights.

## <a name="create-a-new-environment"></a>Stvaranje novog okruženja

1. Na desnoj strani glavnog natpisa odaberite birač okruženja, a zatim **+Novo**.

   :::image type="content" source="media/environment-picker.png" alt-text="Odaberite birač okruženja.":::

1. U oknu **Postavljanje** unesite **Naziv okruženja**.

1. Odaberite **Vrstu** računa, ovisno o vrsti plana.

1. Odaberite **Regija** i odaberite **Dalje**. 

1. Upišite **naziv radnog prostora** koji vam omogućuje prikupljanje podataka za određena web-mjesta ili aplikacije. Dodatne informacije potražite u odjeljku [Stvaranje radnog prostora](create-workspace.md).

1. Odaberite **vrstu radnog prostora** (web ili mobilni) koju želite stvoriti. 

1. Odaberite **Prikaži napredne postavke** da biste omogućili ili onemogućili te izborne postavke:

   - Prebacite **Od nepoznatog do poznatog** na „omogućeno” kako biste povezali web-događaje s korisnicima čija je autentičnost prethodno provjerena. Dodatne informacije potražite [u članku Prepoznavanje web-događaja od prethodno provjerenih posjetitelja](unknown-to-known.md).
   - Prebacite **Filtriraj promet botova** na „omogućeno” za uklanjanje web-prometa botova za ovaj radni prostor. 

1. Odaberite **Dovršeno** kad završite. 

1. Instalirajte isječak koda da biste počeli primati podatke, a zatim odaberite **Završi** za stvaranje radnog prostora. Za dodatne informacije pogledajte [Pregled resursa za razvojne inženjere](developer-resources.md).

> [!NOTE]
> Sada možete dodati članove i dodijeliti im razinu dozvole s popisa **Uloga**. Za više informacija pogledajte [Uloge i dopuštenja](user-roles.md). 

Za više informacija pogledajte [Upravljanje okruženjima i radnim prostorima](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Rad s novim okruženjem

- [Stvorite radni prostor](../engagement-insights/create-workspace.md) i dodajte članove.
- [Dodajte kôd na web-mjesto](../engagement-insights/instrument-website.md) ili [mobilnu aplikaciju](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Prikažite [izvješće u stvarnom vremenu](../engagement-insights/view-reports.md) ili stvorite [prilagođena izvješća](../engagement-insights/custom-reports.md).
- [Stvorite pročišćene događaje](../engagement-insights/refined-events.md) za izvoz.
- [Izvezite podatke](../engagement-insights/export-events.md) u Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
