---
title: Poveznik za Power Apps
description: Povežite se s uslugama Power Apps i Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 985e6c85795fba8ca3063cdffc7f9012e798856a
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623214"
---
# <a name="microsoft-power-apps-connector-preview"></a>Poveznik za Microsoft Power Apps (pretpregled)

Unesite objedinjene profile klijenta u svoje personalizirane aplikacije pomoću Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Povežite Power Apps i Dynamics 365 Customer Insights

Customer Insights jedan je od mnogih [dostupnih izvora za podatke u Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Pogledajte dokumentaciju Power Apps da biste saznali kako [dodati podatkovnu vezu u aplikaciju](/powerapps/maker/canvas-apps/add-data-connection). Preporučujemo da pregledate i [kako Power Apps koristi delegiranje za obradu velikih skupova podataka u aplikacijama od gotovih gradivnih elemenata](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Dostupni entiteti

Nakon dodavanja Customer Insights kao podatkovne veze možete odabrati sljedeće entitete u Power Apps:

- **Klijent**: za korištenje podataka s [objedinjenog profila klijenta](customer-profiles.md).
- **UnifiedActivity**: za prikaz [vremenske trake aktivnosti](activities.md) u aplikaciji.
- **ContactProfile**: za prikaz kontakata klijenta. Taj entitet dostupan je samo u okruženjima uvida u ciljnu skupinu za poslovne račune.

## <a name="limitations"></a>Ograničenja

### <a name="retrievable-entities"></a>Dohvatljivi entiteti

Entitete **Klijent**, **UnifiedActivity**, **Segmenti** i **ContactProfile** možete dohvatiti samo putem poveznika Power Apps. ContactProfile dostupan je samo u instanci uvida u ciljnu skupinu za poslovne račune. Prikazani su drugi entiteti jer ih temeljni povezivač podržava putem okidača na usluzi Power Automate.

### <a name="delegation"></a>Delegacija

Delegiranje radi samo za entitet **Klijent** i **UnifiedActivity**. 

- Delegiranje za entitet **Klijent**: da biste koristili delegiranje za ovaj entitet, polja treba indeksirati u [indeksu pretraživanja i filtriranja](search-filter-index.md).  
- Delegiranje za entitet **UnifiedActivity**: Delegiranje za ovaj entitet radi samo za polja **ActivityId** i **CustomerId**.  
- Delegiranje za **ContactProfile**: Delegiranje za ovaj entitet radi samo za polja **ContactId** i **CustomerId**. ContactProfile dostupan je samo u okruženjima uvida u ciljnu skupinu za poslovne račune.

Dodatne informacije o delegiranju potražite u odjeljku [Funkcije i radnje usluge Power Apps koje se mogu delegirati](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Primjer kontrole zbirke

Možete dodati profile klijenata u [kontrolu galerije](/powerapps/maker/canvas-apps/add-gallery).

1. Dodajte kontrolu **galerija** aplikaciji koju gradite.

    > [!div class="mx-imgBorder"]
    > ![Dodajte element galerije.](media/connector-powerapps9.png "Dodajte element galerije.")

2. Odaberite **Klijent** kao izvor podataka za stavke.

    > [!div class="mx-imgBorder"]
    > ![Odaberite izvor podataka.](media/choose-datasource-powerapps.png "Odaberite izvor podataka.")

3. Možete promijeniti podatkovni panel s desne strane da biste odabrali polje za prikaz entiteta Klijent u galeriji.

4. Ako želite prikazati bilo koje polje odabranog klijenta u galeriji, ispunite svojstvo **Tekst** oznake s pomoću **{Name_of_the_gallery}.Selected.{property_name}**  
    - Na primjer: _Gallery1.Selected.address1_city_

5. Da biste prikazali objedinjenu vremensku traku za klijenta, dodajte element galerije i dodajte svojstvo **Stavke** s pomoću **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Na primjer: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE[footer-include](../includes/footer-banner.md)]
