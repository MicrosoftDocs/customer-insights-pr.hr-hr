---
title: Odredišta izvoza
description: Izvezite podatke i upravljajte odredištima izvoza.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643854"
---
# <a name="export-destinations-preview"></a>Odredišta izvoza (pretpregled)

Stranica **Odredišta izvoza** prikazuje sva mjesta koja ste postavili za izvoz podataka. Možete dodati i nova odredišta za izvoz. Uz to, prikazuje trenutno dostupne mogućnosti izvoza.. Dobijte brzi pregled, opis i saznajte što možete učiniti sa svakom mogućnošću proširenja. Izvezite objedinjene profile, mjere i segmente u podržane aplikacije relevantne za vašu tvrtku.

Otvorite **Administrator** > **Odredišta izvoza** kako biste pronašli sljedeće mogućnosti proširenja:

- [Dodatak za korisničku karticu za Dynamics 365 Customer](customer-card-add-in.md)
- [Facebook Poveznik upravitelja oglasa](export-facebook.md)
- [Poveznik za Power Automate](export-power-automate.md)
- [Poveznik za Power Apps](export-power-apps.md)
- [Poveznik za Power BI](export-power-bi.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Spremište Azure bloba](export-azure-blob-storage.md)
- [LiveRamp&reg; poveznik](export-liveramp.md)
- [Bot za Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [API za Customer Insights](apis.md)

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
