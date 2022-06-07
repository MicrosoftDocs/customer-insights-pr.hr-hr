---
title: Zahtjevi subjekta podataka (ZSP) za prava pod OUZP-om | Microsoft Docs
description: Odgovaranje na zahtjeve subjekta podataka za Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: af2583295627f98e980adbca4f216b9c34c3cad8
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808537"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahtjevi subjekta podataka (ZSP) za prava pod OUZP-om

Opća uredba o zaštiti podataka Europske unije (OUZP) na snazi je od 25. svibnja 2018. Pruža značajna prava pojedincima u vezi s njihovim podacima. Cilj OUZP-a je zaštita i omogućavanje prava na privatnost pojedinaca. Možete pročitati više o Microsoftovoj predanosti sigurnosti i usklađenosti u [Microsoftovom centru za pouzdanost](https://www.microsoft.com/trust-center).

Posvećeni smo pomaganju našim klijentima u ispunjavanju njihovih zahtjeva u vezi s OUZP-om. Sadrži pravo brisanja i izvoza podataka koji uključuju osobne podatke, poput korisničkih ID-ova, telefonskih brojeva i adresa e-pošte. Administratori mogu implementirati zahtjeve korisnika za brisanje ili izvoz osobnih podataka.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Odgovaranje na zahtjeve subjekta za brisanje podataka OUZP-a za Dynamics 365 Customer Insights

"Pravo na zaborav" brisanjem osobnih podataka iz korisničkih podataka organizacije ključna je zaštita u Općoj uredbi o zaštiti podataka (OUZP). Uklanjanje osobnih podataka uključuje uklanjanje svih osobnih podataka i dnevnika koje generira sustav, osim informacija iz dnevnika revizije.

#### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtjevima za brisanje subjekta podataka

Customer Insights nudi sljedeća iskustva u proizvodu za brisanje osobnih podataka za određenog kupca ili korisnika:

- **Upravljanje zahtjevima za brisanje za podatke o klijentu**: podaci o klijentu u stavci Customer Insights unose se iz izvornih izvora podataka koji su izvan stavke Customer Insights. Svi OUZP zahtjevi za brisanje moraju se provesti u originalnom izvoru podataka.
- **Upravljaj zahtjevima za brisanje korisničkih podataka u sustavu Customer Insights**: podatke za korisnike stvara Customer Insights. Svi OUZP zahtjevi za brisanje moraju se provesti unutar stavke Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Upravljanje zahtjevima za brisanje podataka o klijentima

Administrator za Customer Insights može slijediti ove korake kako bi uklonio korisničke podatke koji su izbrisani u izvoru podataka:

1. Prijavite se u sustav Dynamics 365 Customer Insights.
2. Idite na **izvore podataka podataka** > **·**
3. Za svaki izvor podataka na popisu koji sadrži izbrisane podatke o klijentu:
   1. Odaberite okomitu trotočje (&vellip;), a zatim **Osvježi**.
   2. Provjerite status izvora podataka pod **Status**. Oznaka kvačice znači da je osvježavanja bilo uspješno. Trokut upozorenja znači da je došlo do pogreške. Ako se prikaže znak upozorenja, kontaktirajte D365CI@microsoft.com.

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

## <a name="consent-management-preview"></a>Upravljanje pristankom (pretpregled)

Mogućnost upravljanja pristankom ne prikuplja izravno korisničke podatke. Uvozi i obrađuje samo podatke o pristanku koje korisnici pružaju u drugim aplikacijama.

Da biste uklonili podatke o pristanku o određenim korisnicima, uklonite ih u izvorima podataka unesenima u sposobnost upravljanja pristankom. Nakon osvježavanja izvor podataka, uklonjeni podaci bit će izbrisani i u Centru za pristanak. Aplikacije koje koriste entitet pristanka također će izbrisati podatke koji su uklonjeni na izvoru [nakon osvježavanja](system.md#refresh-processes). Preporučujemo brzo osvježavanje izvora podataka nakon odgovora na zahtjev ispitanika za uklanjanje korisničkih podataka iz svih ostalih procesa i aplikacija.

[!INCLUDE [footer-include](includes/footer-banner.md)]