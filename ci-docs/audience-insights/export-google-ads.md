---
title: Izvoz podataka usluge Customer Insights u Google Ads
description: Saznajte kako konfigurirati vezu s uslugom Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568415"
---
# <a name="connector-for-google-ads-preview"></a>Poveznik za Google Ads (pretpregled)

Izvezite segmente objedinjenih profila klijenata u popis ciljnih skupina usluge Google Ads i upotrijebite ih za oglašavanje na uslugama Google pretraživanje, Gmail, YouTube i Google prikazivačkoj mreži. 

## <a name="prerequisites"></a>Preduvjeti

-   Imate [račun za Google Ads](https://ads.google.com/) i odgovarajuće vjerodajnice administratora.
-   Google Ads sadrži postojeće ciljne skupine i odgovarajuće ID-ove. Dodatne informacije potražite u [ciljnim skupinama usluge Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Imate [konfigurirane segmente](segments.md)
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polja koja predstavljaju adresu e-pošte, ime i prezime

## <a name="connect-to-google-ads"></a>Povezivanje s uslugom Google Ads

1. Otvorite **Administrator** > **Izvozna odredišta**.

1. U odjeljku **Google Ads** odaberite **Postavljanje**.

1. Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.

1. Unesite svoj **[ID klijenta za Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Unesite svoj **[token razvojnog inženjera koji je odobren za Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Unesite svoj **[ID ciljne skupine za Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i odaberite **Povezivanje** za inicijalizaciju veze s uslugom Google Ads.

1. Odaberite mogućnost **Provjera autentičnosti pomoću usluge Google Ads** i unesite svoje vjerodajnice za Google Ads.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Snimka zaslona s izvozom za vezu s uslugom Google Ads":::

1. Odaberite **Dalje** da biste konfigurirali izvoz.

## <a name="configure-the-connector"></a>Konfiguracija poveznika

1. U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta. Ponovite iste korake za polja **Ime** i **Prezime**.

1. Odaberite segmente koje želite izvesti. U Google Ads možete ukupno izvesti do 1 milijun profila klijenata.

1. Odaberite **Spremi**.

## <a name="export-the-data"></a>Izvoz podataka

Možete [izvesti podatke na zahtjev](export-destinations.md). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab). U usluzi Google Ads sada možete pronaći svoje segmente u odjeljku [ciljne skupine usluge Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Poznata ograničenja

- Do 1 milijun profila po izvozu u Google Ads.
- Izvoz u Google Ads ograničen je na segmente.
- Izvoz segmenata s ukupno milijun profila može potrajati do 5 minuta zbog ograničenja na strani davatelja usluga. 
- Podudaranje u usluzi Google Ads može potrajati do 48 sati.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Google Ads, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Google Ads ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
