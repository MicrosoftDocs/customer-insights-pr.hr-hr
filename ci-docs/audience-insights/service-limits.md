---
title: Ograničenja usluge
description: Razumjeti ograničenja i restrikcije.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 81253332cbea3110c0b3804db3a4d03b514f92d4
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604360"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ograničenja usluge u mogućnosti uvida u ciljnu skupinu Dynamics 365 Customer Insights

U ovom se članku opisuju ugrađena ograničenja za uslugu Customer Insights koji su osmišljeni da bi osigurali pouzdanost i stabilnost usluge. Svi zahtjevi za promjenama mogu se izvršiti putem [Foruma s idejama](https://go.microsoft.com/fwlink/?linkid=2074172), 
 
| Područje  | Limiti  | Bilješke |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti i mjere | 100 segmenata ili mjera. | Kombinirani ukupni broj aktivnih [segmenata](segments.md) i [mjera](measures.md) ne može premašiti 100.  |
| Odnosi | 20 razina dubine u odnosima na putanjama entiteta. | Prilikom stvaranja [segmenata](segments.md) ili [mjera](measures.md) pomoću sučelja graditelja, putanje entiteta mogu imati do 20 skokova odnosa između početnog entiteta i ciljnog entiteta.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]