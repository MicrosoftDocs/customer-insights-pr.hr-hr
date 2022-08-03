---
title: Povezivanje s podacima iz rješenja Data Lake kojim upravlja platforma Microsoft Dataverse.
description: Uvoz podataka iz rješenja Data Lake kojim upravlja platforma Microsoft Dataverse.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206944"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Povezivanje s podacima iz rješenja Data Lake kojim upravlja platforma Microsoft Dataverse.

Microsoft Dataverse korisnici se mogu brzo povezati s analitičkim entitetima u upravljanom jezeru Microsoft Dataverse. Samo jedan izvor podataka okruženja može istovremeno koristiti isto upravljano jezero servisa Dataverse.

> [!NOTE]
> Da biste nastavili i pogledali popis entiteta dostupnih u upravljanom jezeru Dataverse, morate biti administrator tvrtke ili ustanove.

## <a name="prerequisites"></a>Preduvjeti

- Podaci pohranjeni u internetskom servisu kao što je Azure Data Lake Storage mogu biti pohranjeni na mjestu drugačijem od onoga na kojemu se podaci obrađuju ili pohranjuju u sustavu Dynamics 365 Customer Insights.Uvozom ili povezivanjem s podacima pohranjenim u mrežnim uslugama slažete se da se podaci mogu prenositi i pohranjivati pomoću programa Dynamics 365 Customer Insights. [Saznajte više u Microsoftovu centru za](https://www.microsoft.com/trust-center) pouzdanost.

- Vidljivi su samo Dataverse entiteti s omogućenim [praćenjem](/power-platform/admin/enable-change-tracking-control-data-synchronization) promjena. Ti se entiteti mogu izvesti u Dataverse jezero podataka kojima upravlja i koristiti u customer insights. Gotove tablice Dataverse prema zadanim postavkama imaju omogućeno evidentiranje promjena. Morate uključiti evidentiranje promjena za prilagođene tablice. Da biste provjerili je li tablica omogućena Dataverse za praćenje promjena, idite na [Power Apps](https://make.powerapps.com) > **Tablice** > **podataka**. Pronađite tablicu koja vas zanima i odaberite je. Otvorite **Dodatne mogućnosti postavki** > **i** pregledajte postavku **Evidentiranje promjena**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Povezivanje s jezerom za upravljanje Dataverse

1. Idite na **Podaci** > **Izvor podataka**.

1. Odaberite **Dodaj izvor podataka**.

1. Odaberite **Microsoft Dataverse**.

1. **Unesite naziv** izvor podataka i neobavezni **Opis**.

1. Omogućite **Adresa poslužitelja** za tvrtku ili ustanovu koja koristi Dataverse i odaberite **Prijavi se**.

1. Odaberite tablice koje želite unijeti kao entitete u Uvide u kupce s dostupnog popisa.

   > [!NOTE]
   > Ako su neke tablice već odabrane, mogu ih koristiti ostale aplikacije sustava Dynamics 365 (kao što su Dynamics 365 Sales Insights ili Customer Service Insights). Taj odabir ne možete promijeniti. Ove tablice bit će dostupne kao entiteti nakon što se stvori izvor podataka.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dijaloški okvir koji prikazuje popis entiteta u okruženju Dataverse.":::

1. Spremite svoj odabir za početak sinkronizacije odabranih tablica iz usluge Dataverse. Novu dodanu vezu pronaći ćete na stranici **Izvori podataka**. Bit će stavljena u red čekanja za osvježavanje i pokazivati broj entiteta kao 0 dok se sve odabrane tablice ne sinkroniziraju.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Učitavanje podataka može potrajati. Nakon uspješnog osvježavanja uneseni podaci mogu se pregledati sa [**stranice Entiteti**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Uređivanje izvora podataka jezera za upravljanje Dataverse

Odabir entiteta uređujete tek nakon što stvorite izvor podataka. Na primjer, ako su platformi Dataverse dodani dodatni entiteti, a i njih također želite uvesti.
Za povezivanje s drugim data lake usluge Dataverse [stvorite novi izvor podataka](#connect-to-a-dataverse-managed-lake).

1. Idite na **Podaci** > **Izvor podataka**.

1. Uz izvor podataka koje želite ažurirati odaberite **Uredi**.

1. Odaberite dodatne entitete s dostupnog popisa entiteta.

1. Kliknite **Spremi** da biste primijenili promjene i vratili se na **stranicu Izvori** podataka.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
