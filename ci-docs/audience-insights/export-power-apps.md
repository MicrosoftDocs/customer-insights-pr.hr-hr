---
title: Poveznik za Power Apps
description: Povežite se s uslugama Power Apps i Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405296"
---
# <a name="microsoft-power-apps-connector-preview"></a>Poveznik za Microsoft Power Apps (pretpregled)

Unesite objedinjene profile klijenta u svoje personalizirane aplikacije pomoću Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Povežite Power Apps i Dynamics 365 Customer Insights

Customer Insights jedan je od mnogih [dostupnih izvora za podatke u Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).

Pogledajte dokumentaciju Power Apps da biste saznali kako [dodati podatkovnu vezu u aplikaciju](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection). Preporučujemo da pregledate i [kako Power Apps koristi delegiranje za obradu velikih skupova podataka u aplikacijama od gotovih gradivnih elemenata](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Dostupni entiteti

Nakon dodavanja Customer Insights kao podatkovne veze možete odabrati sljedeće entitete u Power Apps:

- Klijent: za korištenje podataka s [objedinjenog profila klijenta](customer-profiles.md).
- Objedinjena aktivnost klijenta: za prikaz [vremenske trake aktivnosti](activities.md) u aplikaciji.

## <a name="limitations"></a>Ograničenja

### <a name="retrievable-entities"></a>Dohvatljivi entiteti

Možete dohvatiti samo entitete **Klijent**, **UnifiedActivity** i **Segmenti** putem priključka za Power Apps. Prikazani su drugi entiteti jer ih temeljni povezivač podržava putem okidača na usluzi Power Automate.  

### <a name="delegation"></a>Delegacija

Delegiranje radi za entitet Klijent i entitet UnifiedActivity. 

- Delegiranje za entitet **Klijent**: da biste koristili delegiranje za ovaj entitet, polja treba indeksirati u [indeksu pretraživanja i filtriranja](search-filter-index.md).  

- Delegiranje za entitet **UnifiedActivity**: Delegiranje za ovaj entitet radi samo za polja **ActivityId** i **CustomerId**.  

- Za više informacija o delegiranju pogledajte [Funkcije i operacije koje se mogu delegirati na usluzi Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Primjer kontrole zbirke

Na primjer, profile klijenata dodajete [kontroli galerije](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).

1. Dodajte kontrolu **Zbirka** aplikaciji koju gradite.

> [!div class="mx-imgBorder"]
> ![Dodavanje elementa galerije](media/connector-powerapps9.png "Dodavanje elementa galerije")

1. Odaberite **Klijent** kao izvor podataka za stavke.

    > [!div class="mx-imgBorder"]
    > ![Odabir izvora podataka](media/choose-datasource-powerapps.png "Odabir izvora podataka")

1. Možete promijeniti podatkovni panel s desne strane da biste odabrali polje za prikaz entiteta Klijent u galeriji.

1. Ako želite prikazati bilo koje polje odabranog klijenta u galeriji, ispunite svojstvo Tekst oznake:  **{Name_of_the_gallery}.Selected.{property_name}**

    Primjer: Gallery1.Selected.address1_city

1. Da biste prikazali objedinjenu vremensku traku za klijenta, dodajte element Galerija i dodajte svojstvo Stavke: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Primjer: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)
