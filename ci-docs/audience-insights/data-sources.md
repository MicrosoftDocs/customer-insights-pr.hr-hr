---
title: Upotreba izvora podataka za unos podataka
description: Saznajte način uvoza podataka iz različitih izvora.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 78379c827e132b3b172aa7381f4c5ef2c70b9771
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977820"
---
# <a name="data-sources-overview"></a>Pregled izvora podataka

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Mogućnost uvida u ciljnu skupinu na platformi Dynamics 365 Customer Insights povezuje se s podacima iz širokog skupa izvora. Povezivanje s izvorom podataka često se naziva postupkom *gutanja podataka*. Nakon unosa podataka, možete ih [ujediniti](data-unification.md) i na njima raditi.

## <a name="add-a-data-source"></a>Dodaj izvor podataka

Pogledajte detaljne članke o dodavanju izvor podataka, ovisno o mogućnosti koju odaberete.

Možete dodati sljedeće izvore podataka:

- [Power Query Priključci](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataverse jezero](connect-dataverse-managed-lake.md)

> [!NOTE]
> Ako koristite probnu verziju, odjeljak Načini uvoza sadrži **mogućnost biblioteke podataka Customer Insights.** Odaberite ovu mogućnost da biste odabrali ogledni skup podataka dostupan za različite industrije. Dodatne informacije potražite u [Dynamics 365 Customer Insights odjeljku Suđenje](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Dodavanje podataka iz lokalnih izvora podataka

Unošenje podataka iz lokalnih izvora podataka u uvidima publike podržano je na temelju tijekova podataka platforme Microsoft Power Platform. Protok podataka u uvidima u korisnike možete omogućiti [pružanjem Microsoft Dataverse URL-a](create-environment.md) okruženja prilikom postavljanja okruženja.

Izvori podataka stvoreni nakon povezivanja Dataverse okruženja s uvidima korisnika [Power Platform prema zadanim postavkama koriste tijekove](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) podataka. Tijekovi podataka podržavaju lokalnu povezivost pomoću pristupnika za podatke. Možete ukloniti i ponovno stvoriti izvore podataka koji su postojali prije Dataverse povezivanja okruženja [pomoću lokalno pristupnika podataka](/data-integration/gateway/service-gateway-app).

Pristupnici za podatke iz postojećeg okruženja Power BI ili Power Apps bit će vidljivi i možete ih ponovno koristiti u Customer Insights. Stranica izvora podataka prikazuje veze do okruženja platforme Microsoft Power Platform u kojem možete pregledavati i konfigurirati lokalne pristupnike za podatke.

## <a name="review-ingested-data"></a>Pregled unijetih podataka

Vidjet ćete naziv svakog unijetog izvor podataka, njegov status i zadnji put kada su podaci iz tog izvora osvježavani. Popis izvora podataka možete sortirati prema svakom stupcu.

> [!div class="mx-imgBorder"]
> ![Dodan je izvor podataka.](media/configure-data-datasource-added.png "Dodan je izvor podataka")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Učitavanje podataka može potrajati. Nakon uspješnog osvježavanja umetnuti podaci mogu se pregledati na stranici **Entiteti**. Dodatne informacije potražite u odjeljku [Entiteti](entities.md).

## <a name="refresh-a-data-source"></a>Osvježavanje izvora podataka

Izvori podataka mogu se osvježiti prema automatskom rasporedu ili ručno na zahtjev. 

Idite u odjeljak **Administrator** > **Sustav** > [**Raspored**](system.md#schedule-tab) za konfiguriranje zakazanih osvježavanja svih unesenih izvora podataka.

Da biste osvježili izvor podataka na zahtjev, slijedite korake u nastavku:

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Odaberite okomito trotočje pored izvora podataka koji želite osvježiti i odaberite **Osvježi** s padajućeg popisa.

3. Izvor podataka sada se pokreće za ručno osvježavanje. Osvježavanje izvora podataka ažurirat će i shemu entiteta i podatke za sve entitete navedene u izvoru podataka.

4. Odaberite **Zaustavljanje osvježavanja** ako želite otkazati postojeće osvježavanje i izvor podataka će se vratiti na posljednji status osvježavanja.

## <a name="delete-a-data-source"></a>Brisanje izvora podataka

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Odaberite okomito trotočje pored izvora podataka koji želite ukloniti i odaberite **Izbriši** s padajućeg izbornika.

3. Potvrdite brisanje.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
