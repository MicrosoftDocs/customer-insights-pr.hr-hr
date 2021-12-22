---
title: Povezivanje s tablicama u usluzi Microsoft Dataverse
description: Uvoz podataka iz rješenja Data Lake kojim upravlja platforma Microsoft Dataverse.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: fecf3e33b5bc1eec17006fc196004be902c03b40
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900142"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Povezivanje s podacima iz rješenja Data Lake kojim upravlja platforma Microsoft Dataverse.

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Ovaj članak pruža informacije o tome kako Dataverse se korisnici mogu brzo povezati s analitičkim entitetima u Microsoft Dataverse upravljanom jezeru. 

> [!NOTE]
> Da biste Dataverse nastavili i pogledali popis entiteta dostupnih u upravljanom jezeru, morate biti administrator u tvrtki ili ustanovi.

## <a name="important-considerations"></a>Važne stavke

Podaci pohranjeni u internetskom servisu kao što je Azure Data Lake Storage mogu biti pohranjeni na mjestu drugačijem od onoga na kojemu se podaci obrađuju ili pohranjuju u sustavu Dynamics 365 Customer Insights.Uvozom ili povezivanjem s podacima pohranjenima u mrežnim servisima suglasni ste da se podaci mogu prenositi i pohranjivati sa sustavom Dynamics 365 Customer Insights .  [Saznajte više u Microsoftovu centru za pouzdanost](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-dataverse-managed-lake"></a>Povezivanje s jezerom za upravljanje Dataverse

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Odaberite **Dodaj izvor podataka**.

3. Odaberite **Microsoft Dataverse** i odaberite **Dalje**.

4. Unesite **Naziv** za izvor podataka i odaberite **Dalje**. 

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
