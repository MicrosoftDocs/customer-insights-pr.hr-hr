---
title: Izvoz podataka usluge Customer Insights u SendGrid
description: Saznajte kako konfigurirati vezu s uslugom SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597272"
---
# <a name="connector-for-sendgrid-preview"></a>Poveznik za SendGrid (pretpregled)

Izvezite segmente objedinjenih profila klijenata u popise kontakata usluge SendGrid i koristite ih za kampanje i marketing putem e-pošte u usluzi SendGrid. 

## <a name="prerequisites"></a>Preduvjeti

-   Imate [račun za SendGrid](https://sendgrid.com/) i odgovarajuće vjerodajnice administratora.
-   SendGrid sadrži postojeće popise kontakata i odgovarajuće ID-jeve. Za dodatne informacije pogledajte [SendGrid – Upravljanje kontaktima](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="connect-to-sendgrid"></a>Povezivanje s uslugom SendGrid

1. Otvorite **Administrator** > **Izvozna odredišta**.

1. Pod **SendGrid** odaberite **Postavi**.

1. Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Okno za konfiguraciju izvoza usluge SendGrid.":::

1. Unesite svoj **Ključ za API za SendGrid** [Ključ za API za SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Unesite svoj **[ID popisa usluge SendGridI](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** za inicijalizaciju veze s uslugom SendGrid.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Dalje** da biste konfigurirali izvoz.

## <a name="configure-the-connector"></a>Konfiguracija poveznika

1. U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta. Ponovite iste korake za ostala neobavezna polja kao što su **Ime**, **Prezime**, **Zemlja/Regija**, **Država**, **Grad** i **Poštanski broj**.

1. Odaberite segmente koje želite izvesti. Snažno **preporučujemo da ne izvozite više od ukupno 100 000 profila klijenata** u uslugu SendGrid. 

1. Odaberite **Spremi**.

## <a name="export-the-data"></a>Izvoz podataka

Možete [izvesti podatke na zahtjev](export-destinations.md). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).

## <a name="known-limitations"></a>Poznata ograničenja

- Ukupno do 100 000 profila u SendGrid.
- Izvoz u SendGrid ograničen je na segmente.
- Izvoz do 100 000 profila u SendGrid može potrajati do nekoliko sati. 
- Broj profila koje možete izvesti u SendGrid ovisi i ograničen je vašim ugovorom s tvrtkom SendGrid.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u SendGrid, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da SendGrid ispunjava sve obaveze zaštite privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE[footer-include](../includes/footer-banner.md)]