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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350398"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Ograničenja usluge u sposobnostima Customer Insights

U ovom se članku opisuju ugrađena ograničenja za uslugu Customer Insights koji su osmišljeni da bi osigurali pouzdanost i stabilnost usluge. Svi zahtjevi za promjenama mogu se izvršiti putem [Foruma s idejama](https://go.microsoft.com/fwlink/?linkid=2074172), 

## <a name="audience-insights"></a>Uvidi u ciljne skupine

| Područje  | Limiti  | Bilješke |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, mjere i predviđanja | 300  | Ukupan broj kombiniranih [segmenata](audience-insights/segments.md)[, mjera](audience-insights/measures.md) i [predviđanja](audience-insights/predictions.md) ne može premašiti 300.  |
| Odnosi | 20 razina dubine u odnosima na putanjama entiteta. | Prilikom stvaranja [segmenata](audience-insights/segments.md) ili [mjera](audience-insights/measures.md) pomoću sučelja graditelja, putanje entiteta mogu imati do 20 skokova odnosa između početnog entiteta i ciljnog entiteta.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
