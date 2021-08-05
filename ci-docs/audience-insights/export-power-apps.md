---
title: Poveznik za Power Apps
description: Povežite se s uslugama Power Apps i Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 2ab5a9059991611a2959a19cc688d232ec782e1e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554104"
---
# <a name="microsoft-power-apps-connector-preview"></a>Poveznik za Microsoft Power Apps (pretpregled)

Unesite objedinjene profile klijenta u svoje personalizirane aplikacije pomoću Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Povežite Power Apps i Dynamics 365 Customer Insights

Customer Insights jedan je od mnogih [dostupnih izvora za podatke u Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Pogledajte dokumentaciju Power Apps da biste saznali kako [dodati podatkovnu vezu u aplikaciju](/powerapps/maker/canvas-apps/add-data-connection). Preporučujemo da pregledate i [kako Power Apps koristi delegiranje za obradu velikih skupova podataka u aplikacijama od gotovih gradivnih elemenata](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Dostupni entiteti

Nakon dodavanja Customer Insights kao podatkovne veze možete odabrati sljedeće entitete u Power Apps:

- Klijent: za korištenje podataka s [objedinjenog profila klijenta](customer-profiles.md).
- UnifiedActivity: za prikaz [vremenske trake aktivnosti](activities.md) u aplikaciji.

## <a name="limitations"></a>Ograničenja

### <a name="retrievable-entities"></a>Dohvatljivi entiteti

Možete dohvatiti samo entitete **Klijent**, **UnifiedActivity** i **Segmenti** putem priključka za Power Apps. Prikazani su drugi entiteti jer ih temeljni povezivač podržava putem okidača na usluzi Power Automate.  

### <a name="delegation"></a>Delegacija

Delegiranje radi za entitet Klijent i entitet UnifiedActivity. 

- Delegiranje za entitet **Klijent**: da biste koristili delegiranje za ovaj entitet, polja treba indeksirati u [indeksu pretraživanja i filtriranja](search-filter-index.md).  

- Delegiranje za entitet **UnifiedActivity**: Delegiranje za ovaj entitet radi samo za polja **ActivityId** i **CustomerId**.  

- Za više informacija o delegiranju pogledajte [Funkcije i operacije koje se mogu delegirati na usluzi Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Primjer kontrole zbirke

Na primjer, profile klijenata dodajete [kontroli galerije](/powerapps/maker/canvas-apps/add-gallery).

1. Dodajte kontrolu **Zbirka** aplikaciji koju gradite.

> [!div class="mx-imgBorder"]
> ![Dodajte element galerije.](media/connector-powerapps9.png "Dodavanje elementa galerije")

1. Odaberite **Klijent** kao izvor podataka za stavke.

    > [!div class="mx-imgBorder"]
    > ![Odaberite izvor podataka.](media/choose-datasource-powerapps.png "Odabir izvora podataka")

1. Možete promijeniti podatkovni panel s desne strane da biste odabrali polje za prikaz entiteta Klijent u galeriji.

1. Ako želite prikazati bilo koje polje odabranog klijenta u galeriji, ispunite svojstvo Tekst oznake:  **{Name_of_the_gallery}.Selected.{property_name}**

    Primjer: Gallery1.Selected.address1_city

1. Da biste prikazali objedinjenu vremensku traku za klijenta, dodajte element Galerija i dodajte svojstvo Stavke: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Primjer: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]