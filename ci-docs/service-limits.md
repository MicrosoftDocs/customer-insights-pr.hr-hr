---
title: Ograničenja usluge u uvidima kupaca
description: Shvatite ograničenja i ograničenja u usluzi Customer Insights SaaS.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940659"
---
# <a name="service-limits-in-customer-insights"></a>Ograničenja usluge u uvidima kupaca

U ovom se članku opisuju ugrađena ograničenja za uslugu Customer Insights koji su osmišljeni da bi osigurali pouzdanost i stabilnost usluge. Svi zahtjevi za promjenama mogu se izvršiti putem [Foruma s idejama](https://go.microsoft.com/fwlink/?linkid=2074172),

## <a name="customer-insights"></a>Customer Insights

| Područje  | Limiti  | Bilješke |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, mjere i predviđanja | 300  | Ukupan broj segmenata [,](segments.md) mjera [i](measures.md) predviđanja [zajedno ne može biti veći od](predictions.md) 300.  |
| Odnosi | 20 razina dubine u odnosima na putanjama entiteta. | Prilikom stvaranja [segmenata](segments.md) ili [mjera](measures.md) pomoću sučelja graditelja, putanje entiteta mogu imati do 20 skokova odnosa između početnog entiteta i ciljnog entiteta.  |

## <a name="fair-scheduling-of-jobs"></a>Pošteno raspoređivanje radnih mjesta

Customer Insights je SaaS usluga koja koristi zajedničke resurse servisa Azure. Kupci imaju tendenciju da imaju radno opterećenje promjenjivog intenziteta i po različitim rasporedima. Kako bismo osigurali pravedan pristup temeljnim resursima, osiguravamo da se procesi sustava izvršavaju pravednim redoslijedom. Primjeri sistemskih procesa su poslovi povezani s objedinjavanjem podataka, ažuriranjima segmenata ili izračunom mjera. Pošteno raspoređivanje štiti vas od čekanja u redu za resurse ako dođe do skoka traženih poslova. Istodobno, Customer Insights ne jamči da se svi poslovi koje čekate u redu obrađuju paralelno.

[!INCLUDE [footer-include](includes/footer-banner.md)]
