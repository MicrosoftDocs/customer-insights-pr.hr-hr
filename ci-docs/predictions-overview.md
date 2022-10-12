---
title: Pregled predviđanja
description: Scenariji i mogućnosti predviđanja koje obuhvaća aplikacija Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610181"
---
# <a name="predictions-overview"></a>Pregled predviđanja

Dynamics 365 Customer Insights dolazi s raznim mogućnostima koje koriste umjetnu inteligenciju i strojno učenje za predviđanje podataka.

## <a name="out-of-box-models"></a>Gotovi modeli

Najlakši način za početak s predviđanjem podataka su unaprijed definirani modeli, koji se često nazivaju gotovi modeli. Potrebni su im samo određeni podaci i struktura za brzo stvaranje uvida. Dostupni su sljedeći modeli:

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- [Doživotna vrijednost klijenta](predict-customer-lifetime-value.md): predviđa potencijalni prihod klijenta tijekom čitave interakcije s tvrtkom.
- [Preporuka proizvoda](predict-product-recommendation.md): predlaže skupove prediktivnih preporuka za proizvode na temelju ponašanja pri kupnji i klijenata sa sličnim obrascima kupnje.
- [Gubitak pretplaćenih klijenata](predict-subscription-churn.md): predviđa postoji li opasnost da će klijent prestati koristiti pretplatu na proizvode ili usluge vaše tvrtke.
- [Transakcijski bućkuriš](predict-transactional-churn.md): predviđa hoće li pojedinačni kupac više ne kupovati vaše proizvode ili usluge u određenom vremenski okvir.
- [Analiza](sentiment-analysis.md) naklonosti: Analizira naklonost povratnih informacija kupaca i identificira poslovne aspekte koji se često spominju.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

- [Transakcijski bućkuriš](predict-transactional-churn.md): predviđa hoće li korisnički račun više ne kupovati vaše proizvode ili usluge u određenom vremenski okvir.

---

> [!TIP]
> Preporučujemo da redovito osvježavate modele izvan okvira ažuriranim podacima kako biste bili sigurni da točno obavještavaju o slučaju vaše poslovne upotrebe. Podaci se osvježavaju ad hoc kada sustav proguta nove ili ažurirane izvore podataka. Međutim, modeli će se u ovom slučaju tek ponovno uključiti i nastaviti upotrebljavati postojeće podatke o osposobljavanju.
>
> **Konfigurirajte raspored** ažuriranja postavljanjem rasporeda prekvalifikacije modela tijekom konfiguracije. Model će se prekvalificirati i ponovno uključiti u ovaj raspored, koji možete promijeniti u bilo kojem trenutku.

## <a name="azure-machine-learning-integration"></a>Integracija Strojnog učenja Azure

Ako tvrtka ili ustanova već koristi scenarije strojnog učenja na temelju eksperimenata Strojnog učenja Azure, značajka prilagođenih modela u rješenju Customer Insights pomaže spojiti točkice. Stvorite tijekove rada koji vam pomažu u odabiru podataka od kojih želite stvoriti uvide i mapiranju rezultata u vaše objedinjene profile klijenata. Za dodatne informacije pogledajte [Prilagođeni modeli strojnog učenja](custom-models.md).

## <a name="manage-existing-predictions"></a>Upravljanje postojećim predviđanjima

Otvorite **stranicu Predviđanja obavještajnih podataka** > **·**. **Na kartici Moja predviđanja pogledajte predviđanja koja ste stvorili**, njihovu vrstu predviđanje, naziv izlaznog entiteta, status, posljednji put kada je predviđanje uređen i posljednji put kada su podaci osvježeni. Popis predviđanja možete sortirati po bilo kojem stupcu.

Odaberite predviđanje za prikaz dostupnih akcija.

:::image type="content" source="media/predictions.png" alt-text="Moja stranica predviđanja.":::

- **Uredite** predviđanje da biste promijenili njegova svojstva.
- [**Osvježite**](#refresh-a-prediction) predviđanje tako da uključuje najnovije podatke.
- **Pogledajte** detalje o predviđanje.
- [**Izvješće o**](#view-the-input-data-usability-report) upotrebljivosti ulaznih podataka za prikaz pogrešaka, upozorenja i preporuka.
- **Izbrišite** predviđanje.

### <a name="refresh-a-prediction"></a>Osvježavanje predviđanja

Predviđanja se mogu osvježiti prema automatskom rasporedu ili ručno osvježiti na zahtjev. Da biste ručno osvježili sva predviđanja, odaberite **Osvježi sve**. Da biste ručno osvježili predviđanje, odaberite ga i odaberite **Osvježi**. Da biste [zakazali automatsko osvježavanje](schedule-refresh.md), idite na **Raspored** > **administratorskih** > **sustava**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Prikaz izvješća o upotrebljivosti ulaznih podataka

Izvješće o upotrebljivosti ulaznih podataka pruža pročišćeni prikaz pogrešaka i upozorenja koja mogu proizvesti vaša gotova predviđanja. Također daje preporuke o tome kako poboljšati performanse modela.

Izvješće je dostupno nakon što model završi svoj proces obuke. Stvoren je za svaki model zasebno, bez obzira na to je li uspješno završio obuku ili ne.

Na kartici **Moja predviđanja** odaberite predviđanje, a zatim izvješće **o** upotrebljivosti ulaznih podataka. Ili iz prikaza s detaljima predviđanje odaberite **Izvješće o** upotrebljivosti ulaznih podataka.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Primjer izvješća o upotrebljivosti ulaznih podataka koji prikazuje tablicu s pogreškama, upozorenjima i preporukama.":::

Izvješće uključuje:

- **Naziv:** Opisni naziv pogreške, upozorenja ili preporuke.
- **Korak:** Model faza, vlak ili rezultat, informacije se odnose na.
- **Stanje:** Ozbiljnost informacija (pogreška, upozorenje, preporuka).
- **Naziv stupca:** Stupac u entitetu koji treba izmijeniti da bi se poboljšale performanse modela.
- **Naziv entiteta:** naziv entiteta koji treba izmijeniti da bi se poboljšale performanse modela.
- **Detalji:** Pojedinosti o pogrešci, upozorenju ili preporuci.

[!INCLUDE [footer-include](includes/footer-banner.md)]
