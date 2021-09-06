---
title: Zajednički zadaci za scenarije predviđanja
description: Saznajte kako upravljati predviđanjima, rješavati ih i pročišćavati.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: eaccf23a81ca4de19763b761cc5a27c14515fe522ee36dc78f294208b681966e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036456"
---
# <a name="manage-predictions"></a>Upravljanje predviđanjima

U ovom članku se razmatraju neki zadaci koje dijeli većina scenarija predviđanja.

## <a name="troubleshoot-a-failed-prediction"></a>Otklanjanje poteškoća s neuspjelim predviđanjem

1. Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.

1. Odaberite okomite elipse pored predviđanja za koje želite pregledati zapisnike pogrešaka.

1. Odaberite **Zapisnici**.

1. Pregledajte sve pogreške. Može se dogoditi nekoliko vrsta pogrešaka i one opisuju kakvo je stanje prouzročilo pogrešku. Na primjer, pogreška za koju nema dovoljno podataka da bi se točno predvidjela obično se razrješava učitavanjem dodatnih podataka u Customer Insights.

## <a name="input-data-usability-report"></a>Izvješće o upotrebljivosti ulaznih podataka

Izvješće o upotrebljivosti ulaznih podataka pruža pročišćeni prikaz pogrešaka i upozorenja koja mogu proizvesti vaša gotova predviđanja. Također daje preporuke kako poboljšati izvedbu modela.

Izvješće je dostupno nakon što model završi svoj proces obuke. Stvara se za svaki model zasebno, bez obzira je li uspješno dovršen ili ne.

### <a name="view-the-input-data-usability-report"></a>Prikaz izvješća o upotrebljivosti ulaznih podataka

Nakon što je gotovi model završio svoj korak obuke, pogledajte izvješće:
- Odaberite elipse pored naziva modela i odaberite **Izvješće o upotrebljivosti ulaznih podataka**.
- Odaberite status modela i **Prikaz Izvješća o upotrebljivosti ulaznih podataka** u bočnom oknu.
- Odaberite jedan od modela s popisa i odaberite **Izvješće o upotrebljivosti ulaznih podataka** na naredbenoj traci.
- Otvorite stranicu s rezultatima modela i odaberite **Izvješće o upotrebljivosti ulaznih podataka** na naredbenoj traci.

### <a name="information-in-the-input-data-usability-report"></a>Informacije u izvješću o upotrebljivosti ulaznih podataka

Sljedeći stupci u izvješću sadrže korisne informacije za poboljšanje podataka za model.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Primjer izvješća o upotrebljivosti ulaznih podataka koji prikazuje tablicu s pogreškama, upozorenjima i preporukama.":::

- Naziv: opisni naziv pogreške, upozorenja ili preporuke.
- Korak: faza modela, obuka ili rezultat na koji se informacije odnose.
- Stanje: ozbiljnost informacija (pogreška, upozorenje, preporuka).
- Naziv stupca: stupac u entitetu koji treba izmijeniti radi poboljšanja izvedbe modela.
- Naziv entiteta: naziv entiteta koji treba izmijeniti radi poboljšanja izvedbe modela.
- Pojedinosti: pojedinosti o pogrešci, upozorenju ili preporuci.

## <a name="refresh-a-prediction"></a>Osvježavanje predviđanja

Predviđanja će se automatski osvježiti na istom [rasporedu osvježavanja podataka](system.md#schedule-tab) kao što je konfigurirano u postavkama. Možete ih osvježiti i ručno.

1. Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.

1. Odaberite okomitu trotočku uz predviđanje koje želite osvježiti.

1. Odaberite **Osvježi**.

## <a name="delete-a-prediction"></a>Brisanje predviđanja

Brisanjem predviđanja uklanja se i njegov izlazni entitet.

1. Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.

1. Odaberite okomitu trotočku uz predviđanje koje želite izbrisati.

1. Odaberite **Obriši**.
