---
title: Stvaranje segmenta na temelju modela predviđanje
description: Stvorite segmente na temelju izlaznog entiteta modela predviđanja.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610411"
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

1. Odaberite model koji želite pregledati i odaberite **Prikaz**.

1. Na stranici s rezultatima odaberite **Stvori segment**. Za više informacija o stranici s rezultatima pregledajte članak o modelu.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Snimka zaslona stranice s rezultatima predviđanja s naglaskom na radnji Stvori segment.":::

1. Kreirajte novi segment pomoću atributa iz izlaznog entiteta odabranog modela. Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).

> [!TIP]
> Segment za model predviđanje možete stvoriti i na **stranici Segmenti** tako da odaberete **Novo** i odaberete **Stvori iz** > **inteligencije**. Dodatne informacije potražite u članku [Stvaranje novog segmenta s brzim segmentima](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
