---
title: Izvoz podataka usluge Customer Insights u Upravitelj Facebook oglasa
description: Saznajte kako konfigurirati vezu s Upraviteljem Facebook oglasa.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269965"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Poveznik za Upravitelj Facebook oglasa (pretpregled)

Izvezite segmente objedinjenih korisničkih profila u Upravitelj Facebook oglasa radi izrade kampanja na Facebooku i Instagramu.

## <a name="prerequisites"></a>Preduvjeti

- Trebate imati [račun **Facebook oglasa**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) koji obuhvaća [poslovni **Facebook račun**](https://business.facebook.com/).
- Morate biti administrator za [račun **Facebook oglasa**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Povezivanje s Upraviteljem Facebook oglasa

1. Otvorite **Administrator** > **Izvozna odredišta**.

1. Pod **Upravitelj Facebook oglasa**, odaberite **Postavljanje**.

1. Dodijelite odredištu izvoza prepoznatljiv naziv u polju **Zaslonski naziv**.

1. Odaberite **Nastavi s Facebookom** da se prijavite na svoj račun Facebook oglasa.

1. Omogućite dozvolu za **upravljanje oglasima** nakon provjere autentičnosti pomoću usluge Facebook.

1. Odaberite **Upravitelj Facebook oglasa** s kojim želite raditi.

1. Odaberite **Postojeću prilagođenu publiku** s padajućeg popisa ili stvorite **Novu prilagođenu publiku**. Za više informacija pogledajte [**Publike u Upravitelju Facebook oglasa**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Dalje** da biste konfigurirali izvoz.

## <a name="configure-the-connector"></a>Konfiguracija poveznika

1. U polju **Odaberite ključni identifikator**, odaberite **E-pošta**, **Ime i adresa** ili **Telefon** koji će se poslati u Upravitelj Facebook oglasa.

1. Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za odabrani identifikator ključa.
   > [SAVJET] Najveće šanse za podudaranje pojavljuju se ako kao ključni identifikator odaberete **E-pošta**. Dodavanje dodatnih identifikatora može poboljšati podudaranje.

1. Odaberite **Dodaj atribut** da biste mapirali dodatnih atributa koji se šalju Upravitelju Facebook oglasa. Atributi iz Upravitelja Facebook oglasa preslikavaju se na sljedeća korisnička imena: **FN** = **Ime**, **LN** = **Prezime**, **FI** = **Prvi inicijal**, **PHONE** = **Telefon**, **GEN** = **Pol**, **DOB** = **Datum rođenja**, **ST** = **Savezna država**, **CT** = **Grad**, **ZIP** = **Poštanski broj**, **COUNTRY** = **Država / regija**

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

## <a name="export-the-data"></a>Izvoz podataka

Možete [izvesti podatke na zahtjev](export-destinations.md). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).

## <a name="known-limitations"></a>Poznata ograničenja

- Do 10 milijuna profila klijenata po izvozu u Facebook Upravitelj oglasa 
- Izvoz u Facebook Upravitelj oglasa ograničen je na segmente
- Izvoz segmenata s ukupno 10 milijuna profila može trajati do 90 minuta

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Upravitelj Facebook oglasa, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da usluga Facebook oglasi ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE[footer-include](../includes/footer-banner.md)]