---
title: Ograničenja usluge u sustavu Dynamics 365 Customer Insights
description: Razumjeti ograničenja i restrikcije.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483651"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Ograničenja usluge u sposobnostima Customer Insights

U ovom se članku opisuju ugrađena ograničenja za uslugu Customer Insights koji su osmišljeni da bi osigurali pouzdanost i stabilnost usluge. Svi zahtjevi za promjenama mogu se izvršiti putem [Foruma s idejama](https://go.microsoft.com/fwlink/?linkid=2074172), 

## <a name="audience-insights"></a>Uvidi u ciljne skupine

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ograničenja usluge u mogućnosti uvida u ciljnu skupinu Dynamics 365 Customer Insights

| Područje  | Limiti  | Bilješke |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti i mjere | 100 segmenata ili mjera. | Kombinirani ukupni broj aktivnih [segmenata](audience-insights/segments.md) i [mjera](audience-insights/measures.md) ne može premašiti 100.  |
| Odnosi | 20 razina dubine u odnosima na putanjama entiteta. | Prilikom stvaranja [segmenata](audience-insights/segments.md) ili [mjera](audience-insights/measures.md) pomoću sučelja graditelja, putanje entiteta mogu imati do 20 skokova odnosa između početnog entiteta i ciljnog entiteta.  |


## <a name="engagement-insights"></a>Uvidi u angažman

### <a name="workspace-and-event-quotas"></a>Kvote za radni prostor i događaje

Uvidi u angažman vrlo je skalabilna aplikacija koja može podržati milijune događaja u sekundi. Tijekom javnog pretpregleda događaji imaju prag glasnoće. Također postoji ograničenje broja radnih mjesta u tvrtki ili ustanovi.

### <a name="engagement-insights-limits"></a>Ograničenja uvida u angažman

- Maksimalni volumen događaja po radnom prostoru = 100 događaja u sekundi

- Maksimalni broj radnih prostora po tvrtki/ustanovi = 100

Kada događaji prijeđu prag, to može dovesti do gubitka podataka u izvješćima na temelju tih događaja. Možete se [obratiti podršci](https://go.microsoft.com/fwlink/?linkid=2145734) da biste zatražili povećanje volumena prije nego što prekoračite ograničenja. Surađivat ćemo s vama kako bismo utvrdili vašu potrebu za povećanjem volumena i podržali vaš zahtjev.


[!INCLUDE[footer-include](includes/footer-banner.md)]