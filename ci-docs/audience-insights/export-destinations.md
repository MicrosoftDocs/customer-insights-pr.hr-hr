---
title: Odredišta izvoza
description: Izvezite podatke i upravljajte odredištima izvoza.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596076"
---
# <a name="export-destinations-preview-overview"></a>Odredišta izvoza (pretpregled) pregled

Stranica **Odredišta izvoza** prikazuje sva mjesta koja ste postavili za izvoz podataka. Možete dodati i nova odredišta za izvoz. Uz to, prikazuje trenutno dostupne mogućnosti izvoza.. Dobijte brzi pregled, opis i saznajte što možete učiniti sa svakom mogućnošću proširenja. Izvezite objedinjene profile, mjere i segmente u podržane aplikacije relevantne za vašu tvrtku.

Otvorite **Administrator** > **Odredišta izvoza** kako biste pronašli sljedeće mogućnosti proširenja:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Adobe Experience Platform](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Spremište Azure bloba](export-azure-blob-storage.md)
- [Azure Data Lake Storage druge generacije](export-azure-data-lake-storage-gen2.md)
- [Bot za Microsoft Teams](export-teams-bot.md)
- [API za Customer Insights](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (Dodatak za korisničku karticu)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Središte za prodaju sustava Dynamics 365 (Dodatak za korisničku karticu)](customer-card-add-in.md)
- [Upravitelj oglasa za Facebook](export-facebook.md)
- [Google Ads](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [Mailchimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

## <a name="add-a-new-export-destination"></a>Dodavanje novog odredišta izvoza

Da biste dodali odredišta izvoza, imate [dozvole aministratora](permissions.md). Ako izvozite u Microsoftove usluge, pretpostavljamo da su obje usluge u istoj tvrtki ili ustanovi.

1. Otvorite **Administrator** > **Izvozna odredišta**.

1. Prebacite se na karticu **Moja odredišta izvoza**.

1. Odaberite **Dodavanje odredišta** za stvaranje novog odredišta izvoza.

1. U okno **Dodavanje odredišta** odaberite **Vrsta** odredišta izvoza na padajućem izborniku.

1. Unesite potrebne detalje i odaberite **Dalje** za stvaranje odredišta izvoza.

Možete odabrati i **Postavljanje** na pločici na kartici **Otkrivanje**.

## <a name="view-export-destinations"></a>Prikaz odredišta izvoza

Nakon stvaranja odredišta izvoza pronaći ćete ih u tablici na kartici **Moja odredišta izvoza**. Ova tablica ima tri stupca:

- **Zaslonski naziv**: Naziv koje ste unijeli prilikom izrade odredišta.
- **Vrsta**: Vrsta odredišta izvoza koju ste postavili prilikom stvaranja odredišta.
- **Stvoreno**: Datum izrade odredišta.

## <a name="edit-an-export-destination"></a>Uređivanje odredišta izvoza

1. Odaberite okomite tri točke za odredište izvoza koje želite urediti.

   > [!div class="mx-imgBorder"]
   > ![Okomita elipsa](media/export-destinations-page-ellipsis.png "Okomita elipsa")

1. Na padajućem izborniku odaberite **Uredi**.

1. Promijenite vrijednosti koje zahtijevaju ažuriranje i odaberite **Spremi**.

## <a name="export-data-on-demand"></a>Izvoz podataka na zahtjev

Nakon konfiguriranja poveznika za odredište izvoza podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).

Da biste izvezli podatke bez čekanja zakazanog osvježavanja, otvorite karticu **Moja odredišta izvoza** u odjeljku **Administrator** > **Odredišta izvoza**.

> [!div class="mx-imgBorder"]
> ![Okomita elipsa](media/export-destinations-page-ellipsis.png "Okomita elipsa")

- Odaberite **Izvoz** iznad popisa kako biste istovremeno izvezli podatke izvoz na sva odredišta izvoza.
- Izaberite tri točke (...) nakon stavke popisa, a zatim odaberite mogućnost **Izvoz** za pokretanje izvoza za jedno odredište izvoza.

## <a name="remove-an-export-destination"></a>Uklanjanje izvoznog odredišta

Da biste uklonili odredište izvoza, otvorite glavnu stranicu **Odredišta izvoza**.

1. Odaberite okomitu elipsu za odredište izvoza koje želite ukloniti.

   > [!div class="mx-imgBorder"]
   > ![Okomita elipsa](media/export-destinations-page-ellipsis.png "Okomita elipsa")

2. Na padajućem popisu odaberite **Ukloni**.

3. Potvrdite uklanjanje odabirom opcije **Ukloni** na zaslonu za potvrdu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]