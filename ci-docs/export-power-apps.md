---
title: Poveznik za Power Apps (pretpregled)
description: Povežite se s uslugama Power Apps i Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 0b71f723d1e491d422d24b1be6616d2f33c95d40
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055251"
---
# <a name="power-apps-connector-preview"></a>Poveznik za Power Apps (pretpregled)

Unesite objedinjene profile klijenta u svoje personalizirane aplikacije pomoću Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Povežite Power Apps i Dynamics 365 Customer Insights

Customer Insights jedan je od mnogih [dostupnih izvora za podatke u Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Pogledajte dokumentaciju Power Apps da biste saznali kako [dodati podatkovnu vezu u aplikaciju](/powerapps/maker/canvas-apps/add-data-connection). Preporučujemo da pregledate i [kako Power Apps koristi delegiranje za obradu velikih skupova podataka u aplikacijama od gotovih gradivnih elemenata](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Dostupni entiteti

Nakon dodavanja Customer Insights kao podatkovne veze možete odabrati sljedeće entitete u Power Apps:

- **Klijent**: za korištenje podataka s [objedinjenog profila klijenta](customer-profiles.md).
- **UnifiedActivity**: za prikaz [vremenske trake aktivnosti](activities.md) u aplikaciji.
- **ContactProfile**: za prikaz kontakata klijenta. Taj je entitet dostupan samo u okruženjima Customer Insights za poslovne račune.

## <a name="limitations"></a>Ograničenja

### <a name="retrievable-entities"></a>Dohvatljivi entiteti

Entitete **Klijent**, **UnifiedActivity**, **Segmenti** i **ContactProfile** možete dohvatiti samo putem poveznika Power Apps. ContactProfile dostupan je samo u instanci Customer Insights za poslovne račune. Prikazani su drugi entiteti jer ih temeljni povezivač podržava putem okidača na usluzi Power Automate.

Možete obaviti najviše 100 poziva u 60 sekundi. API možete nazvati krajnja točka više puta pomoću parametra $skip. [Saznajte više o parametru $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegacija

Delegiranje radi samo za entitet **Klijent** i **UnifiedActivity**. 

- Delegiranje za entitet **Klijent**: da biste koristili delegiranje za ovaj entitet, polja treba indeksirati u [indeksu pretraživanja i filtriranja](search-filter-index.md).  
- Delegiranje za entitet **UnifiedActivity**: Delegiranje za ovaj entitet radi samo za polja **ActivityId** i **CustomerId**.  
- Delegiranje za **ContactProfile**: Delegiranje za ovaj entitet radi samo za polja **ContactId** i **CustomerId**. ContactProfile dostupan je samo u okruženjima Customer Insights za poslovne račune.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
