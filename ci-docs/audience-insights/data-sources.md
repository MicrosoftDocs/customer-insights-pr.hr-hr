---
title: Upotreba izvora podataka za unos podataka
description: Saznajte način uvoza podataka iz različitih izvora.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643944"
---
# <a name="overview-about-data-sources"></a>Pregled izvora podataka

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Mogućnost uvida u ciljnu skupinu na platformi Dynamics 365 Customer Insights povezuje se s podacima iz širokog skupa izvora. Povezivanje s izvorom podataka često se naziva postupkom *gutanja podataka*. Nakon unosa podataka, možete ih [ujediniti](data-unification.md) i na njima raditi.

## <a name="add-a-data-source"></a>Dodaj izvor podataka

Pogledajte iscrpne članke o načinu dodavanja izvora podataka, ovisno o odabranoj mogućnosti.

Izvor podataka možete dodati na tri osnovna načina:

- [Putem desetaka poveznika aplikacije Power Query](connect-power-query.md)
- [Iz mape Common Data Model](connect-common-data-model.md)
- [Iz svog vlastitog jezera aplikacije Common Data Service](connect-common-data-service-lake.md)

> [!NOTE]
> Još uvijek ne možete dodati podatke iz lokalnih izvora podataka.

## <a name="review-ingested-data"></a>Pregled unijetih podataka

Vidjet ćete naziv svakog unijetog izvor podataka, njegov status i zadnji put kada su podaci iz tog izvora osvježavani. Popis izvora podataka možete sortirati prema svakom stupcu.

> [!div class="mx-imgBorder"]
> ![Dodan je izvor podataka](media/configure-data-datasource-added.png "Dodan je izvor podataka")

|Stanje  |Opis  |
|---------|---------|
|Uspješno   |Izvor podataka je uspješno unesen ako je u stupcu **Osvježeno** navedeno vrijeme.
|Nije pokrenuto   |Izvor podataka još nema unesenih podataka ili je još uvijek u načinu skice.         |
|Osvježavanje    |U tijeku je unos podataka. Ovu operaciju možete otkazati tako da odaberete **Prekini osvježavanje** u stupcu **Radnje**. Ako prekinete osvježavanje, izvor podataka vratit će se na posljednje stanje osvježavanja.       |
|Neuspjelo     |Došlo je do pogreške pri unosu podataka.         |

Odaberite **Osvježavanje statusa** za pregled više pojedinosti o statusu osvježavanja, uključujući pojedinosti o pogreškama i ažuriranjima završnih procesa.

Učitavanje podataka može potrajati. Nakon uspješnog osvježavanja umetnuti podaci mogu se pregledati na stranici **Entiteti**. Dodatne informacije potražite u odjeljku [Entiteti](entities.md).

## <a name="refresh-a-data-source"></a>Osvježavanje izvora podataka

Izvori podataka mogu se osvježiti prema automatskom rasporedu ili ručno na zahtjev. 

Idite u odjeljak **Administrator** > **Sustav** > [**Raspored**](system.md#schedule-tab) za konfiguriranje zakazanih osvježavanja svih unesenih izvora podataka.

Da biste osvježili izvor podataka na zahtjev, slijedite korake u nastavku:

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**

2. Odaberite vertikalnu elipsu pored izvora podataka koji želite osvježiti i s padajućeg popisa odaberite **Osvježavanje**.

3. Izvor podataka sada se pokreće za ručno osvježavanje. Osvježavanjem izvora podataka ažurirat će se i shema entiteta, kao i podaci za sve entitete navedene u izvoru podataka.

4. Odaberite **Zaustavljanje osvježavanja** ako želite otkazati postojeće osvježavanje i izvor podataka će se vratiti na posljednji status osvježavanja.

## <a name="delete-a-data-source"></a>Brisanje izvora podataka

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Odaberite okomitu trotočku pored izvora podataka koju želite ukloniti i odaberite **Izbriši** iz padajućeg izbornika.

3. Potvrdite brisanje.
