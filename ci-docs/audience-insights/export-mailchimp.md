---
title: Izvoz podataka usluge Customer Insights u Mailchimp
description: Saznajte kako konfigurirati vezu s uslugom Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598192"
---
# <a name="connector-for-mailchimp-preview"></a>Poveznik za Mailchimp (pretpregled)

Izvezite segmente objedinjenih profila klijenata u Mailchimp da biste stvorili biltene i kampanje e-pošte.

## <a name="prerequisites"></a>Preduvjeti

-   Imate [račun za Mailchimp](https://mailchimp.com/) i odgovarajuće vjerodajnice administratora.
-   Mailchimp sadrži postojeće ciljne skupine i odgovarajuće ID-ove. Dodatne informacije potražite u [ciljnim skupinama usluge Mailchimp](https://mailchimp.com/help/create-audience/).
-   Imate [konfigurirane segmente](segments.md)
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="connect-to-mailchimp"></a>Povezivanje na Mailchimp

1. Otvorite **Administrator** > **Izvozna odredišta**.

1. U odjeljku **Mailchimp** odaberite **Postavljanje**.

1. Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Unesite svoj **[ID ciljne skupine za Mailchimp](https://mailchimp.com/help/find-audience-id/)** i odaberite **Povezivanje** za inicijalizaciju veze s uslugom Mailchimp.

1. Odaberite mogućnost **Provjera autentičnosti pomoću usluge Mailchimp** i unesite svoje vjerodajnice za Mailchimp.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Snimka zaslona s izvozom za vezu s uslugom Mailchimp":::

1. Odaberite **Dalje** da biste konfigurirali izvoz.

## <a name="configure-the-connector"></a>Konfiguracija poveznika

1. U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta. 

1. Ako želite, možete izvesti stavke **Ime** i **Prezime** kao dodatna polja za stvaranje osobnijih poruka e-pošte. Odaberite **Dodavanje atributa** za mapiranje ovih polja.

1. Odaberite segmente koje želite izvesti. U Mailchimp možete ukupno izvesti do 1 milijun profila klijenata.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Odabir polja i segmenata za izvoz u Mailchimp":::

1. Odaberite **Spremi**.

## <a name="export-the-data"></a>Izvoz podataka

Možete [izvesti podatke na zahtjev](export-destinations.md). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab). U usluzi Mailchimp svoje segmente sada možete pronaći u odjeljku [ciljne skupine usluge Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Poznata ograničenja

- Do 1 milijun profila po izvozu u Mailchimp.
- Izvoz u Mailchimp ograničen je na segmente.
- Izvoz segmenata s ukupno milijun profila može potrajati do tri sata zbog ograničenja na strani davatelja usluga. 
- Broj profila koje možete izvesti u Mailchimp ovisi i ograničen je vašim ugovorom s tvrtkom Mailchimp.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Mailchimp, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Mailchimp ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE[footer-include](../includes/footer-banner.md)]