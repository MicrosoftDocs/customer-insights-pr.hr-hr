---
title: Zahtjevi subjekta podataka (ZSP) za prava pod OUZP-om | Microsoft Docs
description: Odgovaranje na zahtjeve subjekta podataka za Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387102"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahtjevi subjekta podataka (ZSP) za prava pod OUZP-om

Opća uredba o zaštiti podataka Europske unije (OUZP) na snazi je od 25. svibnja 2018. Pruža značajna prava pojedincima u vezi s njihovim podacima. Cilj OUZP-a je zaštita i omogućavanje prava na privatnost pojedinaca. Saznajte više o Microsoftovoj predanosti sigurnosti i usklađenosti u Microsoftovu [centru za pouzdanost](https://www.microsoft.com/trust-center).

Posvećeni smo pomaganju našim klijentima u ispunjavanju njihovih zahtjeva u vezi s OUZP-om. Uključuje pravo brisanja ili izvoza podataka koji uključuju osobne podatke kao što su korisnički ID-ovi, telefonski brojevi i adrese e-pošte. Administratori mogu implementirati zahtjeve korisnika za brisanje ili izvoz osobnih podataka.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Odgovaranje na GDPR data subject brisanje zahtjeva za Customer Insights

"Pravo na zaborav" brisanjem osobnih podataka iz korisničkih podataka organizacije ključna je zaštita u Općoj uredbi o zaštiti podataka (OUZP). Uklanjanje osobnih podataka uključuje uklanjanje svih osobnih podataka i dnevnika koje generira sustav, osim informacija iz dnevnika revizije.

### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtjevima za brisanje subjekta podataka

Customer Insights nudi sljedeća iskustva u proizvodu za brisanje osobnih podataka za određenog kupca ili korisnika:

- **Upravljanje zahtjevima za brisanje za podatke o klijentu**: podaci o klijentu u stavci Customer Insights unose se iz izvornih izvora podataka koji su izvan stavke Customer Insights. Najprije izvršite gdpr zahtjeve za brisanjem u izvornom izvor podataka.
- **Upravljaj zahtjevima za brisanje korisničkih podataka u sustavu Customer Insights**: podatke za korisnike stvara Customer Insights. Izvršite sve zahtjeve za brisanje GDPR-a u customer insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Upravljanje zahtjevima za brisanje podataka o klijentima

Kao administrator korisničkog uvida uklonite korisničke uvide korisničke podatke koji su izbrisani u izvor podataka. Provjerite jesu li zahtjevi za brisanje GDPR-a izvršeni u izvornom izvor podataka.

1. Prijavite se u sustav Dynamics 365 Customer Insights.

1. Idite na **Podaci** > **Izvor podataka**.

1. Za svaki izvor podataka na popisu koji sadrži izbrisane podatke o klijentu:
   1. Odaberite izvor podataka, a zatim **Osvježi**.
   1. Provjerite status izvora podataka pod **Status**. Oznaka kvačice znači da je osvježavanja bilo uspješno. Trokut upozorenja znači da je došlo do pogreške. Ako se prikaže znak upozorenja, kontaktirajte D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Upravljanje zahtjevima za brisanje OUZP-a za podatke o klijentima.":::

1. Nakon uspješnog osvježavanja izvora podataka pokrenite i nizvodno osvježavanje. Pogotovo ako nemate zakazano ponavljajuće potpuno osvježenje uvida u kupce.

   > [!IMPORTANT]
   > Statični segmenti nisu uključeni u potpuno osvježavanje ili pokretanje nizvodno osvježavanja nakon zahtjeva za brisanjem. Da biste osigurali uklanjanje podataka o klijentima i iz statičkih segmenata, ponovno stvorite statičke segmente s osvježenim izvorišnim podacima.

#### <a name="manage-delete-requests-for-user-data"></a>Upravljanje zahtjevima za brisanje za podatke o korisniku

Kao administrator korisničkog uvida izbrišite korisničke podatke Customer Insights.

1. Prijavite se u sustav Dynamics 365 Customer Insights.

1. Otvorite **> Sigurnost** > **administratora** i odaberite karticu **Korisnici**.

1. Potvrdite okvir za korisnike koje želite izbrisati.

1. Odaberite mogućnost **Ukloni**.

1. Potvrdite brisanje.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Odgovaranje na OUZP zahtjeve ispitanika za izvoz

Pravo na prenosivost podataka omogućuje subjektima podataka da zatraže kopiju svojih osobnih podataka u elektroničkom obliku ("strukturirani, uobičajeno korišten, strojno čitljiv i interoperabilni format") koji se može prenijeti drugom kontroloru podataka.

### <a name="manage-export-and-view-requests"></a>Upravljanje izvozom i pregledavanjem zahtjeva

Upravljajte zahtjevima za izvoz korisničkih ili korisničkih podataka.

#### <a name="export-customer-data-tenant-admin"></a>Izvoz podataka klijenta (administrator klijenta)

Kao administrator klijenta izvezite podatke o kupcima.

1. Pošaljite e-poštu na D365CI@microsoft.com i u zahtjevu navedite adresu e-pošte klijenta. Tim Customer Insights poslat će poruku e-pošte na registriranu adresu e-pošte administratora klijenta i zatražiti potvrdu za izvoz podataka.
2. Potvrdite zahtjev za izvozom podataka za zatraženog klijenta.
3. Primite izvezene podatke putem adrese e-pošte administratora klijenta.

#### <a name="export-user-data-tenant-admin"></a>Izvoz podataka o korisniku (administrator klijenta)

Kao administrator klijenta izvezite korisničke podatke.

1. Pošaljite e-poštu na D365CI@microsoft.com i u zahtjevu navedite adresu e-pošte korisnika. Tim Customer Insights šalje e-poštu na adresu e-pošte registriranog administratora klijenta, tražeći potvrdu za izvoz podataka.
1. Potvrdite zahtjev za izvozom podataka za zatraženog korisnika.
1. Primite izvezene podatke putem adrese e-pošte administratora klijenta.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Rukovanje brisanjem podataka u sustavu Dynamics 365 Customer Insights

Podaci se brišu (particije podataka i snimke podataka) ako su particije podataka i snimke podataka neaktivne dulje od 30 dana, što znači da su zamijenjene novom particijom podataka i snimkom putem osvježavanja izvora podataka.

Ne brišu se svi podaci i snimke. Najnovija particija podataka i snimka podataka aktivni su jer se koriste u customer insights. Za najnovije podatke nije važno jesu li izvori podataka osvježeni u posljednjih 30 dana.

[!INCLUDE [footer-include](includes/footer-banner.md)]
