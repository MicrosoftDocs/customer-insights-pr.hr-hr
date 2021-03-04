---
title: Izvoz podataka usluge Customer Insights u DotDigital
description: Saznajte kako konfigurirati vezu s uslugom DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269091"
---
# <a name="connector-for-dotdigital-preview"></a>Poveznik za DotDigital (pretpregled)

Izvezite segmente objedinjenih profila klijenata u adresare usluge DotDigital i koristite ih za kampanje, marketing putem e-pošte i za izgradnju segmenata klijenata pomoću usluge DotDigital. 

## <a name="prerequisites"></a>Preduvjeti

-   Imate [račun za DotDigital](https://dotdigital.com/) i odgovarajuće vjerodajnice administratora.
-   DotDigital sadrži postojeće adresare i odgovarajuće ID-ove. ID se može pronaći u URL-u kada odaberete i otvorite adresar. Dodatne informacije potražite u [adresarima usluge DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="connect-to-dotdigital"></a>Povezivanje s uslugom DotDigital

1. Otvorite **Administrator** > **Izvozna odredišta**.

1. U odjeljku **DotDigital** odaberite **Postavljanje**.

1. Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Okno za konfiguraciju za izvoz u DotDigital.":::

1. Unesite **korisničko ime i lozinku za DotDigital**.

1. Unesite svoj **[ID adresara usluge DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Povezivanje** za inicijalizaciju veze s uslugom DotDigital.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Dalje** da biste konfigurirali izvoz.

## <a name="configure-the-connector"></a>Konfiguracija poveznika

1. U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta. Ponovite iste korake za druga neobavezna polja kao što su **Ime**, **Prezime**, **Puno ime**, **Spol** i **Poštanski broj**.

1. Odaberite segmente koje želite izvesti. U DotDigital možete ukupno izvesti do 1 milijun profila klijenata.

1. Odaberite **Spremi**.

## <a name="export-the-data"></a>Izvoz podataka

Možete [izvesti podatke na zahtjev](export-destinations.md). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab). U usluzi DotDigital sada možete pronaći svoje segmente u [adresaru usluge DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Poznata ograničenja

- Do 1 milijun profila po izvozu u DotDigital.
- Izvoz u DotDigital ograničen je na segmente.
- Izvoz segmenata s ukupno milijun profila može potrajati do 3 sata zbog ograničenja na strani davatelja usluga. 
- Broj profila koje možete izvesti u DotDigital ovisi i ograničen je vašim ugovorom s tvrtkom DotDigital.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u DotDigital, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da DotDigital ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE[footer-include](../includes/footer-banner.md)]