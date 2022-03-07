---
title: Pregled podržanih scenarija predviđanja
description: Scenariji i mogućnosti predviđanja koje obuhvaća aplikacija Dynamics 365 Customer Insights.
ms.date: 12/21/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: c692785c7d81ab660ba2e07411e986c67c1a5d0a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228235"
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
- [Analiza](sentiment-analysis.md) raspoloženja: Analizirajte sentiment povratnih informacija kupaca i identificirajte poslovne aspekte koji se često spominju.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

- [Transakcijski gubitak klijenata](predict-transactional-churn.md): predviđa hoće li klijent prestati kupovati vaše proizvode ili usluge u određenom vremenskom okviru.

---


## <a name="azure-machine-learning-integration"></a>Integracija Strojnog učenja Azure

Ako tvrtka ili ustanova već koristi scenarije strojnog učenja na temelju eksperimenata Strojnog učenja Azure, značajka prilagođenih modela u rješenju Customer Insights pomaže spojiti točkice. Stvorite tijekove rada koji vam pomažu u odabiru podataka od kojih želite stvoriti uvide i mapiranju rezultata u vaše objedinjene profile klijenata. Za dodatne informacije pogledajte [Prilagođeni modeli strojnog učenja](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder predviđanje

Ponekad su skupovi podataka nepotpuni, a neke vrijednosti nedostaju. Customer Insights može vam pomoći u predviđanju vrijednosti koje nedostaju za entitet Klijent i segmente. Dodatne informacije potražite u odjeljku [Dopunite svoje djelomične podatke predviđanjima](predictions.md).
