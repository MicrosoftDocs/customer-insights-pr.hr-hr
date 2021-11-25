---
title: Ograničenja servisa u Dynamics 365 Customer Insights
description: Razumjeti ograničenja i restrikcije.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7815900"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Ograničenja usluge u sposobnostima Customer Insights

U ovom se članku opisuju ugrađena ograničenja za uslugu Customer Insights koji su osmišljeni da bi osigurali pouzdanost i stabilnost usluge. Svi zahtjevi za promjenama mogu se izvršiti putem [Foruma s idejama](https://go.microsoft.com/fwlink/?linkid=2074172), 

## <a name="audience-insights"></a>Uvidi u ciljne skupine

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ograničenja servisa u mogućnosti uvida u Dynamics 365 Customer Insights publika

| Područje  | Limiti  | Bilješke |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, mjere i predviđanja | 300  | Ukupan broj [segmenata](audience-insights/segments.md), mjera [i](audience-insights/measures.md)[predviđanja](audience-insights/predictions.md) zajedno ne može biti veći od 300.  |
| Odnosi | 20 razina dubine u odnosima na putanjama entiteta. | Prilikom stvaranja [segmenata](audience-insights/segments.md) ili [mjera](audience-insights/measures.md) pomoću sučelja graditelja, putanje entiteta mogu imati do 20 skokova odnosa između početnog entiteta i ciljnog entiteta.  |


## <a name="engagement-insights"></a>Uvidi u angažman

### <a name="workspace-and-event-quotas"></a>Kvote za radni prostor i događaje

Uvidi u angažman vrlo je skalabilna aplikacija koja može podržati milijune događaja u sekundi. Tijekom javnog pretpregleda događaji imaju prag glasnoće. Također postoji ograničenje broja radnih mjesta u tvrtki ili ustanovi.

### <a name="engagement-insights-limits"></a>Ograničenja uvida u angažman

- Maksimalni volumen događaja po radnom prostoru = 100 događaja u sekundi

- Maksimalni broj radnih prostora po tvrtki/ustanovi = 100

Kada događaji prijeđu prag, to može dovesti do gubitka podataka u izvješćima na temelju tih događaja. Možete se [obratiti podršci](https://go.microsoft.com/fwlink/?linkid=2145734) da biste zatražili povećanje volumena prije nego što prekoračite ograničenja. Surađivat ćemo s vama kako bismo utvrdili vašu potrebu za povećanjem volumena i podržali vaš zahtjev.


[!INCLUDE[footer-include](includes/footer-banner.md)]
