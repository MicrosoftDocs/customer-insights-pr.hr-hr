---
title: Segmenti koji se temelje na izlazu predviđanja
description: Stvorite segmente na temelju izlaznog entiteta modela predviđanja.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b89754aea2b0da33f27dea5b26d212920f0c090885f951a37cf42ff11c7b6e93
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036410"
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