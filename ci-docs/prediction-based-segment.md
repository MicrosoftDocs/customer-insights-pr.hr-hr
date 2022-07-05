---
title: Stvaranje segmenta na temelju modela predviđanje
description: Stvorite segmente na temelju izlaznog entiteta modela predviđanja.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: d67594f2467c1a0fde84b1ba0bd1afa4025e7b71
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082424"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Stvaranje segmenta na temelju modela predviđanja (pretpregled)

Rezultati predviđanja ponekad se odnose samo na podskup vaših klijenata. Povećajte personalizaciju preporuka stvaranjem segmenata iz rezultata modela predviđanja. Na primjer, možda ćete htjeti dati određene preporuke klijentima koji preferiraju određenu vrstu usluge. 

## <a name="prerequisites"></a>Preduvjeti

- Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.

- Preporuka proizvoda, odbijanje transakcija, gubitak pretplate ili model trajne vrijednosti klijenta konfigurirani su u Customer Insights. Pregled zahtjeva za postavljanje različitih modela:

  - [Model preporuke proizvoda](predict-product-recommendation.md)
  - [Model gubitka pretplate](predict-subscription-churn.md)
  - [Model odbijanja transakcija](predict-transactional-churn.md)
  - [Model trajne vrijednosti klijenta](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Stvaranje segmenta klijenta na temelju predviđanja

1. Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.

1. Odaberite vertikalne elipse pored modela koji želite pregledati i odaberite **Prikaži**.

1. Na stranici s rezultatima odaberite **Stvori segment**. Za više informacija o stranici s rezultatima pregledajte članak o modelu.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Snimka zaslona stranice s rezultatima predviđanja s naglaskom na radnji Stvori segment.":::

1. Stvorite novi segment na temelju izlaznog entiteta odabranog modela. Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).