---
title: Stvaranje jednostavnih segmenata s brzim segmentima
description: Stvorite jednostavne segmente kupaca kako biste ih grupirali na temelju različitih atributa.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171153"
---
# <a name="create-simple-segments-with-quick-segments"></a>Stvaranje jednostavnih segmenata s brzim segmentima

Brzi segmenti omogućuju vam brzu izgradnju jednostavnih segmenata s jednim operatorom za brži uvid. Brzi segmenti podržani su samo u okruženjima za **pojedinačne klijente**.

## <a name="create-a-new-segment-with-quick-segments"></a>Stvaranje novog segmenta s brzim segmentima

1. Idite na **Segmenti**.

1. Odaberite **Novo** > **stvaranje iz**.
   - Odaberite mogućnost **Profili** za stvaranje segmenta koji se temelji na entitetu *jedinstvenog klijenta*.
   - Odaberite mogućnost **Mjere** za stvaranje segmenta prema mjerama koje ste prethodno stvorili.
   - Odaberite mogućnost **Inteligencija** za izgradnju segmenta oko jednog od izlaznih entiteta koje ste generirali pomoću mogućnosti **Predviđanja** ili **Prilagođeni modeli**.

1. U dijaloškom okviru **Novi brzi segment** odaberite atribut iz padajućeg izbornika **Polje**. Na temelju vašeg odabira, sustav pruža različite vrijednosti.
   - Za kategorička polja prikazuje se 10 najboljih brojeva kupaca. Odaberite **Vrijednost** te **Pregled**.
   - Za numerički atribut sustav pokazuje koja vrijednost atributa spada pod percentil svakog kupca. Odaberite **Operator** i **Vrijednost**, a zatim odaberite **Pregled**.

1. Sustav pruža procijenjenu **veličinu segmenta**. Odaberite želite li generirati segment koji ste definirali ili se vratiti da biste odabrali drugo polje.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Naziv i procjena brzog segmenta.":::

1. Navedite naziv i **naziv izlaznog** **entiteta** za svoj segment. Po želji dodajte [oznake](work-with-tags-columns.md#manage-tags).

1. Odaberite **Spremi** kako biste stvorili segment. Prikazuje se **stranica Segmenti**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Sljedeći koraci

[Izvezite segment](export-destinations.md) i istražite [integraciju usluge Customer Card](customer-card-add-in.md) za upotrebu segmenata u drugim aplikacijama.

[!INCLUDE [footer-include](includes/footer-banner.md)]
