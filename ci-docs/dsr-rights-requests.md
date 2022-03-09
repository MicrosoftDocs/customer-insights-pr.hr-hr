---
title: Zahtjevi subjekta podataka (ZSP) za prava pod OUZP-om | Microsoft Docs
description: Odgovorite na zahtjeve ispitanika za mogućnost uvida u ciljnu skupinu sustava Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350260"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahtjevi subjekta podataka (ZSP) za prava pod OUZP-om

Opća uredba o zaštiti podataka Europske unije (OUZP) na snazi je od 25. svibnja 2018. Pruža značajna prava pojedincima u vezi s njihovim podacima. Cilj OUZP-a je zaštita i omogućavanje prava na privatnost pojedinaca. Možete pročitati više o Microsoftovoj predanosti sigurnosti i usklađenosti u [Microsoftovom centru za pouzdanost](https://www.microsoft.com/trust-center).

Posvećeni smo pomaganju našim klijentima u ispunjavanju njihovih zahtjeva u vezi s OUZP-om. Sadrži pravo brisanja i izvoza podataka koji uključuju osobne podatke, poput korisničkih ID-ova, telefonskih brojeva i adresa e-pošte. Administratori mogu implementirati zahtjeve korisnika za brisanje ili izvoz osobnih podataka.

## <a name="audience-insights"></a>Uvidi u ciljne skupine

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odgovaranje na OUZP zahtjeve ispitanika za brisanje mogućnosti uvida u ciljnu skupinu sustava Dynamics 365 Customer Insights

"Pravo na zaborav" brisanjem osobnih podataka iz korisničkih podataka organizacije ključna je zaštita u Općoj uredbi o zaštiti podataka (OUZP). Uklanjanje osobnih podataka uključuje uklanjanje svih osobnih podataka i dnevnika koje generira sustav, osim informacija iz dnevnika revizije.

#### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtjevima za brisanje subjekta podataka

Uvidi u ciljnu skupinu nude sljedeća iskustva u proizvodu za brisanje osobnih podataka za specifičnog klijenta ili korisnika:

- **Upravljanje zahtjevima za brisanje za podatke o klijentu**: podaci o klijentu u stavci Customer Insights unose se iz izvornih izvora podataka koji su izvan stavke Customer Insights. Svi OUZP zahtjevi za brisanje moraju se provesti u originalnom izvoru podataka.
- **Upravljaj zahtjevima za brisanje korisničkih podataka u sustavu Customer Insights**: podatke za korisnike stvara Customer Insights. Svi OUZP zahtjevi za brisanje moraju se provesti unutar stavke Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Upravljanje zahtjevima za brisanje podataka o klijentima

Administrator za Customer Insights može slijediti ove korake kako bi uklonio korisničke podatke koji su izbrisani u izvoru podataka:

1. Prijavite se u sustav Dynamics 365 Customer Insights.
2. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**
3. Za svaki izvor podataka na popisu koji sadrži izbrisane podatke o klijentu:
   1. Odaberite (...), a zatim odaberite **Osvježi**.
   2. Provjerite status izvora podataka pod **Status**. Oznaka kvačice znači da je osvježavanja bilo uspješno. Trokut upozorenja znači da je došlo do pogreške. Ako se prikaže znak upozorenja, kontaktirajte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Upravljanje zahtjevima za brisanje OUZP-a za podatke o klijentima.](audience-insights/media/gdpr-data-sources.png "Upravljanje zahtjevima za brisanje OUZP-a za podatke o klijentima")

##### <a name="manage-delete-requests-for-user-data"></a>Upravljanje zahtjevima za brisanje za podatke o korisniku

Administrator za Customer Insights može poduzeti ove korake za brisanje podataka o klijentu za Customer Insights:

1. Prijavite se u sustav Dynamics 365 Customer Insights.
2. U uvidima u ciljnu skupinu idite na **Admin** > **Dozvole**.
3. Potvrdite okvir korisnika kojeg želite izbrisati.
4. Odaberite mogućnost **Ukloni**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odgovaranje na OUZP zahtjeve ispitanika za izvoz

Kao dio naše obveze za sklapanje partnerstva s vama na vašem putu prema Općoj uredbi o zaštiti podataka (OUZP-u), razvili smo dokumentaciju kako bismo vam pomogli da se pripremite. Ova dokumentacija opisuje korake koje danas možete poduzeti da biste podržali usklađenost s GDPR-om kada koristite uvide u ciljnu skupinu.

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

Mogućnost upravljanja pristankom ne prikuplja izravno korisničke podatke. Uvozi i obrađuje samo podatke o pristanku koje pružaju korisnici u drugim aplikacijama.

Da biste uklonili podatke o pristanku o određenim korisnicima, uklonite ih u izvorima podataka koji se unose u sposobnost upravljanja pristankom. Nakon osvježavanja izvor podataka, uklonjeni podaci bit će izbrisani i u Centru za pristanak. Aplikacije koje koriste entitet privole također će izbrisati podatke koji su uklonjeni na izvoru nakon [osvježavanja](audience-insights/system.md#refresh-processes). Preporučujemo brzo osvježavanje izvora podataka nakon odgovora na zahtjev ispitanika za uklanjanje korisničkih podataka iz svih drugih procesa i aplikacija.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]