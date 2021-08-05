---
title: Povezivanje s tablicama u usluzi Microsoft Dataverse
description: Uvoz podataka iz rješenja Data Lake kojim upravlja platforma Microsoft Dataverse.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: f92d64723e6a4d2fcebdbb3758519d4bfd4aeaf4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692565"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Povezivanje s podacima iz rješenja Data Lake kojim upravlja platforma Microsoft Dataverse.

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Ovaj članak pruža informacije o tome kako se korisnici usluge Dataverse mogu brzo povezati sa svojim analitičkim entitetima u upravljanom jezeru usluge Dataverse. Morate biti administrator u tvrtki ili ustanovi platforme Dataverse kako biste nastavili i vidjeli popis entiteta dostupnih u upravljanom jezeru.

## <a name="important-considerations"></a>Važne stavke

Podaci pohranjeni u internetskom servisu kao što je Azure Data Lake Storage mogu biti pohranjeni na mjestu drugačijem od onoga na kojemu se podaci obrađuju ili pohranjuju u sustavu Dynamics 365 Customer Insights. Uvozom ili povezivanjem s podacima pohranjenima u internetskim servisima slažete se da se podaci mogu prenijeti i pohraniti sa sustavom Dynamics 365 Customer Insights. [Saznajte više u programu Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Povezivanje s jezerom za upravljanje Dataverse

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Odaberite **Dodaj izvor podataka**.

3. Odaberite **Poveži se s upravljanim jezerom Microsoft Dataverse** i odaberite **Dalje**.

4. Unesite **Naziv** za izvor podataka i odaberite **Dalje**. Imenujte smjernice: 
   - Započnite slovom.
   - Koristite samo slova i brojeve. Nisu dopušteni posebni znakovi i razmaci.
   - Koristite između 3 i 64 znaka.

5. Omogućite **Adresa poslužitelja** za tvrtku ili ustanovu koja koristi Dataverse i odaberite **Prijavi se**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Zaslon u koraku obrade podataka gdje korisnik može unijeti URL okruženja usluge Dataverse.":::

6. Odaberite tablice koje želite obraditi kao entitete u uvidima u ciljnu skupinu s dostupnog popisa.    

   > [!NOTE]
   > Ako su neke tablice već odabrane, mogu ih koristiti ostale aplikacije sustava Dynamics 365 (kao što su Dynamics 365 Sales Insights ili Customer Service Insights). Taj odabir ne možete promijeniti. Ove tablice bit će dostupne kao entiteti nakon što se stvori izvor podataka.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dijaloški okvir koji prikazuje popis entiteta u okruženju Dataverse.":::

7. Spremite svoj odabir za početak sinkronizacije odabranih tablica iz usluge Dataverse. Novu dodanu vezu pronaći ćete na stranici **Izvori podataka**. Bit će stavljena u red čekanja za osvježavanje i pokazivati broj entiteta kao 0 dok se sve odabrane tablice ne sinkroniziraju.

Samo jedan izvor podataka okruženja može istovremeno koristiti isto upravljano jezero servisa Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Uređivanje izvora podataka jezera za upravljanje Dataverse

Odabir entiteta uređujete tek nakon što stvorite izvor podataka. Na primjer, ako su platformi Dataverse dodani dodatni entiteti, a i njih također želite uvesti.    
Za povezivanje s drugim data lake usluge Dataverse [stvorite novi izvor podataka](#connect-to-a-dataverse-managed-lake).

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Pored izvora podataka koji želite ažurirati odaberite elipsu.

3. S popisa odaberite mogućnost **Uredi**.

4. Odaberite dodatne entitete s dostupnog popisa entiteta i odaberite **Spremi**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]