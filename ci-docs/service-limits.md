---
title: Ograničenja usluge u sustavu Dynamics 365 Customer Insights
description: Razumjeti ograničenja i restrikcije.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641753"
---
# <a name="service-limits-in-customer-insights"></a>Ograničenja usluge u uvidima kupaca

U ovom se članku opisuju ugrađena ograničenja za uslugu Customer Insights koji su osmišljeni da bi osigurali pouzdanost i stabilnost usluge. Svi zahtjevi za promjenama mogu se izvršiti putem [Foruma s idejama](https://go.microsoft.com/fwlink/?linkid=2074172), 

## <a name="customer-insights"></a>Customer Insights

| Područje  | Limiti  | Bilješke |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, mjere i predviđanja | 300  | Ukupan broj segmenata [,](segments.md) mjera [i](measures.md) predviđanja [zajedno ne može biti veći od](predictions.md) 300.  |
| Odnosi | 20 razina dubine u odnosima na putanjama entiteta. | Prilikom stvaranja [segmenata](segments.md) ili [mjera](measures.md) pomoću sučelja graditelja, putanje entiteta mogu imati do 20 skokova odnosa između početnog entiteta i ciljnog entiteta.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
