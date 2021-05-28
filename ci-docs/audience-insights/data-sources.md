---
title: Upotreba izvora podataka za unos podataka
description: Saznajte način uvoza podataka iz različitih izvora.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085521"
---
# <a name="data-sources-overview"></a>Pregled izvora podataka

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Mogućnost uvida u ciljnu skupinu na platformi Dynamics 365 Customer Insights povezuje se s podacima iz širokog skupa izvora. Povezivanje s izvorom podataka često se naziva postupkom *gutanja podataka*. Nakon unosa podataka, možete ih [ujediniti](data-unification.md) i na njima raditi.

## <a name="add-a-data-source"></a>Dodaj izvor podataka

Pogledajte iscrpne članke o načinu dodavanja izvora podataka, ovisno o odabranoj mogućnosti.

Izvor podataka možete dodati na tri osnovna načina:

- [Putem desetaka poveznika aplikacije Power Query](connect-power-query.md)
- [Iz mape Common Data Model](connect-common-data-model.md)
- [Iz svog vlastitog jezera aplikacije Common Data Service](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Dodavanje podataka iz lokalnih izvora podataka

Unošenje podataka iz lokalnih izvora podataka u Audience Insights podržano je na temelju tijekova podataka platforme Power Platform. Tijekovi podataka mogu se omogućiti u Customer Insights pomoću [pružanja URL-a okruženja Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) prilikom postavljanja okruženja.

Izvori podataka koji se stvaraju nakon pridruživanja okruženja Dataverse uz Customer Insights koristit će [Power Platform tijekove podataka](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) prema zadanim postavkama. Tijekovi podataka podržavaju lokalnu povezivost pomoću pristupnika za podatke. Uklonite i ponovno stvorite izvore podataka koji su postojali prije nego je okruženje Dataverse bilo povezano za [korištenje lokalnih pristupnika za podatke](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).

Pristupnici za podatke iz postojećeg okruženja Power BI ili Power Apps bit će vidljivi i možete ih ponovno koristiti u Customer Insights. Stranica izvora podataka prikazuje veze do okruženja Power Platform u kojem možete pregledavati i konfigurirati lokalne pristupnike za podatke.

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

Odaberite vrijednost u stupcu **Status** bilo kojeg izvora podataka za pregled više pojedinosti. U oknu **Pojedinosti o napretku** proširite **Izvori podataka**. Odaberite **Vidi pojedinosti** za više podataka o statusu osvježavanja, uključujući pojedinosti o pogreškama i ažuriranjima završnih procesa.

Učitavanje podataka može potrajati. Nakon uspješnog osvježavanja umetnuti podaci mogu se pregledati na stranici **Entiteti**. Dodatne informacije potražite u odjeljku [Entiteti](entities.md).

## <a name="refresh-a-data-source"></a>Osvježavanje izvora podataka

Izvori podataka mogu se osvježiti prema automatskom rasporedu ili ručno na zahtjev. 

Idite u odjeljak **Administrator** > **Sustav** > [**Raspored**](system.md#schedule-tab) za konfiguriranje zakazanih osvježavanja svih unesenih izvora podataka.

Da biste osvježili izvor podataka na zahtjev, slijedite korake u nastavku:

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**

2. Odaberite vertikalnu elipsu pored izvora podataka koji želite osvježiti i s padajućeg popisa odaberite **Osvježavanje**.

3. Izvor podataka sada se pokreće za ručno osvježavanje. Osvježavanje izvora podataka ažurirat će i shemu entiteta i podatke za sve entitete navedene u izvoru podataka.

4. Odaberite **Zaustavljanje osvježavanja** ako želite otkazati postojeće osvježavanje i izvor podataka će se vratiti na posljednji status osvježavanja.

## <a name="delete-a-data-source"></a>Brisanje izvora podataka

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Odaberite okomitu trotočku pored izvora podataka koju želite ukloniti i odaberite **Izbriši** iz padajućeg izbornika.

3. Potvrdite brisanje.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
