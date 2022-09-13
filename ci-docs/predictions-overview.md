---
title: Pregled predviđanja
description: Scenariji i mogućnosti predviđanja koje obuhvaća aplikacija Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 32240c8c43751d8514d38b392f23ef4138d50ee2
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411822"
---
# <a name="predictions-overview"></a>Pregled predviđanja

Dynamics 365 Customer Insights dolazi s raznim mogućnostima koje koriste umjetnu inteligenciju i strojno učenje za predviđanje podataka. 

## <a name="out-of-box-models"></a>Gotovi modeli

Najlakši način za početak s predviđanjem podataka su unaprijed definirani modeli, koji se često nazivaju gotovi modeli. Potrebni su im samo određeni podaci i struktura za brzo stvaranje uvida. Trenutno su dostupni sljedeći modeli: 

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- [Doživotna vrijednost klijenta](predict-customer-lifetime-value.md): predviđa potencijalni prihod klijenta tijekom čitave interakcije s tvrtkom.
- [Preporuka proizvoda](predict-product-recommendation.md): predlaže skupove prediktivnih preporuka za proizvode na temelju ponašanja pri kupnji i klijenata sa sličnim obrascima kupnje.
- [Gubitak pretplaćenih klijenata](predict-subscription-churn.md): predviđa postoji li opasnost da će klijent prestati koristiti pretplatu na proizvode ili usluge vaše tvrtke.
- [Transakcijski gubitak klijenata](predict-transactional-churn.md): predviđa hoće li klijent prestati kupovati vaše proizvode ili usluge u određenom vremenskom okviru.
- [Analiza](sentiment-analysis.md) naklonosti: Analizirajte sentimentalnost povratnih informacija kupaca i identificirajte poslovne aspekte koji se često spominju.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

- [Transakcijski gubitak klijenata](predict-transactional-churn.md): predviđa hoće li klijent prestati kupovati vaše proizvode ili usluge u određenom vremenskom okviru.

---

> [!TIP]
> Preporučujemo da redovito osvježavate modele izvan okvira ažuriranim podacima kako biste bili sigurni da točno obavještavaju o slučaju vaše poslovne upotrebe. Podaci se osvježavaju ad hoc kada sustav proguta nove ili ažurirane izvore podataka. Međutim, modeli će se u ovom slučaju tek ponovno uključiti i nastaviti upotrebljavati postojeće podatke o osposobljavanju.
>
> Raspored **ažuriranja možete konfigurirati** postavljanjem rasporeda prekvalifikacije modela u konfiguracijskom iskustvu. Model će se prekvalificirati i ponovno uključiti u ovaj raspored, koji možete promijeniti u bilo kojem trenutku.

## <a name="azure-machine-learning-integration"></a>Integracija Strojnog učenja Azure

Ako tvrtka ili ustanova već koristi scenarije strojnog učenja na temelju eksperimenata Strojnog učenja Azure, značajka prilagođenih modela u rješenju Customer Insights pomaže spojiti točkice. Stvorite tijekove rada koji vam pomažu u odabiru podataka od kojih želite stvoriti uvide i mapiranju rezultata u vaše objedinjene profile klijenata. Za dodatne informacije pogledajte [Prilagođeni modeli strojnog učenja](custom-models.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
