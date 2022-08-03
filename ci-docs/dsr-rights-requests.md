---
title: Zahtjevi subjekta podataka (ZSP) za prava pod OUZP-om | Microsoft Docs
description: Odgovaranje na zahtjeve subjekta podataka za Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146686"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahtjevi subjekta podataka (ZSP) za prava pod OUZP-om

Opća uredba o zaštiti podataka Europske unije (OUZP) na snazi je od 25. svibnja 2018. Pruža značajna prava pojedincima u vezi s njihovim podacima. Cilj OUZP-a je zaštita i omogućavanje prava na privatnost pojedinaca. Možete pročitati više o Microsoftovoj predanosti sigurnosti i usklađenosti u [Microsoftovom centru za pouzdanost](https://www.microsoft.com/trust-center).

Posvećeni smo pomaganju našim klijentima u ispunjavanju njihovih zahtjeva u vezi s OUZP-om. Sadrži pravo brisanja i izvoza podataka koji uključuju osobne podatke, poput korisničkih ID-ova, telefonskih brojeva i adresa e-pošte. Administratori mogu implementirati zahtjeve korisnika za brisanje ili izvoz osobnih podataka.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Odgovaranje na zahtjeve subjekta za brisanje podataka OUZP-a za Dynamics 365 Customer Insights

"Pravo na zaborav" brisanjem osobnih podataka iz korisničkih podataka organizacije ključna je zaštita u Općoj uredbi o zaštiti podataka (OUZP). Uklanjanje osobnih podataka uključuje uklanjanje svih osobnih podataka i dnevnika koje generira sustav, osim informacija iz dnevnika revizije.

#### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtjevima za brisanje subjekta podataka

Customer Insights nudi sljedeća iskustva u proizvodu za brisanje osobnih podataka za određenog kupca ili korisnika:

- **Upravljanje zahtjevima za brisanje za podatke o klijentu**: podaci o klijentu u stavci Customer Insights unose se iz izvornih izvora podataka koji su izvan stavke Customer Insights. Najprije izvršite gdpr zahtjeve za brisanjem u izvornom izvor podataka.
- **Upravljaj zahtjevima za brisanje korisničkih podataka u sustavu Customer Insights**: podatke za korisnike stvara Customer Insights. Svi OUZP zahtjevi za brisanje moraju se provesti unutar stavke Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Upravljanje zahtjevima za brisanje podataka o klijentima

Administrator customer insightsa može slijediti ove korake da bi uklonio podatke o klijentima koji su izbrisani u izvor podataka. Prije nego što nastavite s dolje navedenim koracima, provjerite je li zahtjev za brisanjem izvršen u vašoj izvor podataka. 

1. Prijavite se u sustav Dynamics 365 Customer Insights.
1. Idite na **izvore podataka podataka** > **·**
1. Za svaki izvor podataka na popisu koji sadrži izbrisane podatke o klijentu:
   1. Odaberite okomitu trotočje (&vellip;), a zatim **Osvježi**.
   1. Provjerite status izvora podataka pod **Status**. Oznaka kvačice znači da je osvježavanja bilo uspješno. Trokut upozorenja znači da je došlo do pogreške. Ako se prikaže znak upozorenja, kontaktirajte D365CI@microsoft.com.
1. Nakon uspješnog osvježavanja izvora podataka pokrenite i nizvodno osvježavanje. Pogotovo ako nemate zakazano ponavljajuće potpuno osvježenje uvida u kupce. 

> [!IMPORTANT]
> Statični segmenti nisu uključeni u potpuno osvježavanje ili pokretanje nizvodno osvježavanja nakon zahtjeva za brisanjem. Da biste osigurali uklanjanje podataka o klijentima i iz statičkih segmenata, ponovno stvorite statičke segmente s osvježenim izvorišnim podacima.

> [!div class="mx-imgBorder"]
> ![Upravljanje zahtjevima za brisanje OUZP-a za podatke o klijentima.](media/gdpr-data-sources.png "Upravljanje zahtjevima za brisanje OUZP-a za podatke o klijentima")

##### <a name="manage-delete-requests-for-user-data"></a>Upravljanje zahtjevima za brisanje za podatke o korisniku

Administrator za Customer Insights može poduzeti ove korake za brisanje podataka o klijentu za Customer Insights:

1. Prijavite se u sustav Dynamics 365 Customer Insights.
2. Otvorite Sigurnosne **dozvole administratora** > **·** > **.**
3. Potvrdite okvir korisnika kojeg želite izbrisati.
4. Odaberite mogućnost **Ukloni**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odgovaranje na OUZP zahtjeve ispitanika za izvoz

Kao dio naše predanosti partnerstvu s vama na vašem putovanju do Opće uredbe o zaštiti podataka (GDPR), razvili smo dokumentaciju koja će vam pomoći da odgovorite na zahtjeve ispitanika.

#### <a name="manage-export-and-view-requests"></a>Upravljanje izvozom i pregledavanjem zahtjeva

Pravo na prenosivost podataka omogućuje subjektima podataka da zatraže kopiju svojih osobnih podataka u elektroničkom obliku ("strukturirani, uobičajeno korišten, strojno čitljiv i interoperabilni format") koji se može prenijeti drugom kontroloru podataka.

##### <a name="export-customer-data-tenant-admin"></a>Izvoz podataka klijenta (administrator klijenta)

Administrator klijenta može pratiti ove korake za izvoz podataka:

1. Pošaljite e-poštu na D365CI@microsoft.com i u zahtjevu navedite adresu e-pošte klijenta. Tim Customer Insights poslat će poruku e-pošte na registriranu adresu e-pošte administratora klijenta i zatražiti potvrdu za izvoz podataka.
2. Potvrdite zahtjev za izvozom podataka za zatraženog klijenta.
3. Primite izvezene podatke putem adrese e-pošte administratora klijenta.

##### <a name="export-user-data-tenant-admin"></a>Izvoz podataka o korisniku (administrator klijenta)

1. Pošaljite e-poštu na D365CI@microsoft.com i u zahtjevu navedite adresu e-pošte korisnika. Tim Customer Insights poslat će poruku e-pošte na registriranu adresu e-pošte administratora klijenta i zatražiti potvrdu za izvoz podataka.
2. Potvrdite zahtjev za izvozom podataka za zatraženog korisnika.
3. Primite izvezene podatke putem adrese e-pošte administratora klijenta.

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Rukovanje brisanjem podataka u sustavu Dynamics 365 Customer Insights

1. Podaci će se izbrisati (particije podataka i snimke podataka) ako su particije podataka i snimke podataka neaktivne više od 30 dana, što znači da su zamijenjeni novom particijom podataka i snimkama kroz osvježavanje izvora podataka.
2. Ne brišu se svi podaci i snimke. Najnovija particija podataka i snimka podataka po definiciji su aktivni jer se koriste u customer insights. Za najnovije podatke nije važno jesu li izvori podataka osvježeni u posljednjih 30 dana.

[!INCLUDE [footer-include](includes/footer-banner.md)]
