---
title: Izvoz podataka usluge Customer Insights u AdRoll
description: Saznajte kako konfigurirati vezu s uslugom AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697065"
---
# <a name="connector-for-adroll-preview"></a>Poveznik za AdRoll (pretpregled)

Izvezite segmente objedinjenih profila klijenata u AdRoll i upotrijebite ih za oglašavanje. 

## <a name="prerequisites"></a>Preduvjeti

-   Imate [račun za AdRoll](https://www.adroll.com/) i odgovarajuće vjerodajnice administratora.
-   Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="connect-to-adroll"></a>Poveži s platformom AdRoll

1. Otvorite **Administrator** > **Izvozna odredišta**.

1. U odjeljku **AdRoll** odaberite **Postavljanje**.

1. Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfiguracijsko okno za vezu za AdRoll.":::

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Poveži** za inicijalizaciju veze s uslugom AdRoll.

1. Odaberite mogućnost **Provjera autentičnosti pomoću usluge AdRoll** i unesite svoje vjerodajnice administratora za AdRoll. 

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Unesite svoj **ID oglašivača za AdRoll** [Pogodno za oglašavanje za AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Odaberite **Dalje** da biste konfigurirali izvoz.

## <a name="configure-the-connector"></a>Konfiguracija poveznika

1. U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta. Potrebno je izvesti segmente u AdRoll.

1. Odaberite segmente koje želite izvesti. Odaberite segment s najmanje 100 članova. Ne možete izvesti manje segmente. Uz to, maksimalna veličina segmenta za izvoz je 250 000 članova po izvozu. 

1. Odaberite **Spremi**.

## <a name="export-the-data"></a>Izvoz podataka

Možete [izvesti podatke na zahtjev](export-destinations.md). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).

## <a name="known-limitations"></a>Poznata ograničenja

- U AdRoll možete izvesti do 250 000 profila po izvozu.
- Ne možete izvesti segmente s manje od 100 profila u AdRoll. 
- Izvoz u AdRoll ograničen je na segmente.
- Izvoz do 250 000 profila u AdRoll može potrajati do 10 minuta. 
- Broj profila koje možete izvesti u AdRoll ovisi i ograničen je vašim ugovorom s tvrtkom AdRoll.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u AdRoll, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da AdRoll ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
