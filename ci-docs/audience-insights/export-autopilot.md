---
title: Izvoz podataka usluge Customer Insights u Autopilot
description: Saznajte kako konfigurirati vezu s uslugom Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269229"
---
# <a name="connector-for-autopilot-preview"></a>Poveznik za Autopilot (pretpregled)

Izvezite segmente objedinjenih profila klijenata u Autopilot i koristite ih za marketing putem e-pošte u usluzi Autopilot. 

## <a name="prerequisites"></a>Preduvjeti

-   Imate [račun za Autopilot](https://www.autopilothq.com/) i odgovarajuće vjerodajnice administratora.
-   Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="connect-to-autopilot"></a>Povezivanje s uslugom Autopilot

1. Otvorite **Administrator** > **Izvozna odredišta**.

1. Pod **Autopilot** odaberite **Postavi**.

1. Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfiguracijsko okno za vezu za Autopilot.":::

1. Unesite svoj **Ključ za API za Autopilot** [Ključ za API za Autopilot](https://autopilot.docs.apiary.io/#).

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** za inicijalizaciju veze s uslugom Autopilot.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Dalje** da biste konfigurirali izvoz.

## <a name="configure-the-connector"></a>Konfiguracija poveznika

1. U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta. Ponovite iste korake za ostala neobavezna polja kao što su **Ime**, **Prezime**.

1. Odaberite segmente koje želite izvesti. Snažno **preporučujemo da ne izvozite više od ukupno 100 000 profila klijenata** u uslugu Autopilot. 

1. Odaberite **Spremi**.

## <a name="export-the-data"></a>Izvoz podataka

Možete [izvesti podatke na zahtjev](export-destinations.md). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).

## <a name="known-limitations"></a>Poznata ograničenja

- U Autopilot možete ukupno izvesti do 100 000 profila.
- Izvoz u Autopilot ograničen je na segmente.
- Izvoz do 100 000 profila u Autopilot može potrajati do nekoliko sati. 
- Broj profila koje možete izvesti u Autopilot ovisi i ograničen je vašim ugovorom s tvrtkom Autopilot.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Autopilot, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Autopilot ispunjava sve obaveze zaštite privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE[footer-include](../includes/footer-banner.md)]