---
title: Upotreba izvora podataka za unos podataka
description: Saznajte način uvoza podataka iz različitih izvora.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 27cbd0346b1219c7812f4b90327dd27b645c2b8e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732118"
---
# <a name="data-sources-overview"></a>Pregled izvora podataka

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Mogućnost uvida u publika u Dynamics 365 Customer Insights povezuje se s podacima iz širokog skupa izvora. Povezivanje s izvorom podataka često se naziva postupkom *gutanja podataka*. Nakon unosa podataka, možete ih [ujediniti](data-unification.md) i na njima raditi.

## <a name="add-a-data-source"></a>Dodaj izvor podataka

Pogledajte iscrpne članke o načinu dodavanja izvora podataka, ovisno o odabranoj mogućnosti.

Izvor podataka možete dodati na tri osnovna načina:

- [Putem desetaka poveznika aplikacije Power Query](connect-power-query.md)
- [Iz mape Common Data Model](connect-common-data-model.md)
- [Iz vlastitog Microsoft Dataverse jezera](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Dodavanje podataka iz lokalnih izvora podataka

Unos podataka iz lokalno izvora podataka u publika uvidima podržan je na temelju Microsoft Power Platform protoka podataka. Tijekovi podataka mogu se omogućiti u uvidima u korisnike [pružanjem URL-a okruženja Microsoft Dataverse](create-environment.md) prilikom postavljanja okruženja.

Izvori podataka stvoreni nakon povezivanja Dataverse okruženja s uvidima u klijente prema zadanim će postavkama koristiti [Power Platform tijekove](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) podataka. Tijekovi podataka podržavaju lokalnu povezivost pomoću pristupnika za podatke. Uklonite i ponovno stvorite izvore podataka koji su postojali prije povezivanja Dataverse okruženja za [korištenje lokalno pristupnika podataka](/data-integration/gateway/service-gateway-app).

Pristupnici podataka iz postojećeg okruženja Power BI ili Power Apps bit će vidljivi i možete ih ponovno koristiti u korisničkim uvidima. Stranica izvori podataka prikazuje veze za odlazak u Microsoft Power Platform okruženje u kojem možete pregledavati i konfigurirati lokalno pristupnike podataka.

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
