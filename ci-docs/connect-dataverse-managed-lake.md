---
title: Povezivanje s tablicama u usluzi Microsoft Dataverse
description: Uvoz podataka iz rješenja Data Lake kojim upravlja platforma Microsoft Dataverse.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: e8a294a4bad1581539b5905160cddcd625699d90
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642219"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Povezivanje s podacima iz rješenja Data Lake kojim upravlja platforma Microsoft Dataverse.

Ovaj članak pruža informacije o tome kako Dataverse se korisnici mogu brzo povezati s analitičkim entitetima u upravljanom jezeru Microsoft Dataverse. 

> [!NOTE]
> Da biste nastavili i pogledali popis entiteta dostupnih u upravljanom jezeru Dataverse, morate biti administrator tvrtke ili ustanove.

## <a name="important-considerations"></a>Važne stavke

1. Podaci pohranjeni u internetskom servisu kao što je Azure Data Lake Storage mogu biti pohranjeni na mjestu drugačijem od onoga na kojemu se podaci obrađuju ili pohranjuju u sustavu Dynamics 365 Customer Insights.Uvozom ili povezivanjem s podacima pohranjenim u mrežnim uslugama slažete se da se podaci mogu prenositi i pohranjivati pomoću programa Dynamics 365 Customer Insights. [Saznajte više u Microsoftovu centru za](https://www.microsoft.com/trust-center) pouzdanost.
2. Vidljivi su samo Dataverse entiteti s omogućenim [praćenjem](/power-platform/admin/enable-change-tracking-control-data-synchronization) promjena. Ti se entiteti mogu izvesti u Dataverse jezero podataka kojima upravlja i koristiti u customer insights. Gotove tablice Dataverse prema zadanim postavkama imaju omogućeno evidentiranje promjena. Morate uključiti evidentiranje promjena za prilagođene tablice. Da biste provjerili je li tablica omogućena Dataverse za praćenje promjena, idite na [Power Apps](https://make.powerapps.com) > **Podatkovne** > **tablice**. Pronađite tablicu koja vas zanima i odaberite je. Otvorite **Mogućnosti** > **SettingsAdvanced** i pregledajte postavku **Evidentiranje promjena**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Povezivanje s jezerom za upravljanje Dataverse

1. U značajci Customer Insights idite na **Podaci** > **Izvori podataka**.

2. Odaberite **Dodaj izvor podataka**.

3. Odaberite **Microsoft Dataverse** i odaberite **Dalje**.

4. Unesite **Naziv** za izvor podataka i odaberite **Dalje**. 

5. Omogućite **Adresa poslužitelja** za tvrtku ili ustanovu koja koristi Dataverse i odaberite **Prijavi se**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Zaslon u koraku obrade podataka gdje korisnik može unijeti URL okruženja usluge Dataverse.":::

6. Odaberite tablice koje želite unijeti kao entitete u Uvide kupaca s dostupnog popisa.    

   > [!NOTE]
   > Ako su neke tablice već odabrane, mogu ih koristiti ostale aplikacije sustava Dynamics 365 (kao što su Dynamics 365 Sales Insights ili Customer Service Insights). Taj odabir ne možete promijeniti. Ove tablice bit će dostupne kao entiteti nakon što se stvori izvor podataka.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dijaloški okvir koji prikazuje popis entiteta u okruženju Dataverse.":::

7. Spremite svoj odabir za početak sinkronizacije odabranih tablica iz usluge Dataverse. Novu dodanu vezu pronaći ćete na stranici **Izvori podataka**. Bit će stavljena u red čekanja za osvježavanje i pokazivati broj entiteta kao 0 dok se sve odabrane tablice ne sinkroniziraju.

Samo jedan izvor podataka okruženja može istovremeno koristiti isto upravljano jezero servisa Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Uređivanje izvora podataka jezera za upravljanje Dataverse

Odabir entiteta uređujete tek nakon što stvorite izvor podataka. Na primjer, ako su platformi Dataverse dodani dodatni entiteti, a i njih također želite uvesti.    
Za povezivanje s drugim data lake usluge Dataverse [stvorite novi izvor podataka](#connect-to-a-dataverse-managed-lake).

1. Idite na **Podaci** > **Izvor podataka**.

2. Pored izvora podataka koji želite ažurirati odaberite elipsu.

3. S popisa odaberite mogućnost **Uredi**.

4. Odaberite dodatne entitete s dostupnog popisa entiteta i odaberite **Spremi**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
