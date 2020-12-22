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
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="2386f-103">Poveznik za Microsoft Power Apps (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="2386f-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="2386f-104">Unesite objedinjene profile klijenta u svoje personalizirane aplikacije pomoću Power Apps.</span><span class="sxs-lookup"><span data-stu-id="2386f-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="2386f-105">Povežite Power Apps i Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="2386f-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="2386f-106">Customer Insights jedan je od mnogih [dostupnih izvora za podatke u Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="2386f-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="2386f-107">Pogledajte dokumentaciju Power Apps da biste saznali kako [dodati podatkovnu vezu u aplikaciju](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="2386f-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="2386f-108">Preporučujemo da pregledate i [kako Power Apps koristi delegiranje za obradu velikih skupova podataka u aplikacijama od gotovih gradivnih elemenata](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="2386f-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="2386f-109">Dostupni entiteti</span><span class="sxs-lookup"><span data-stu-id="2386f-109">Available entities</span></span>

<span data-ttu-id="2386f-110">Nakon dodavanja Customer Insights kao podatkovne veze možete odabrati sljedeće entitete u Power Apps:</span><span class="sxs-lookup"><span data-stu-id="2386f-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="2386f-111">Klijent: za korištenje podataka s [objedinjenog profila klijenta](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2386f-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="2386f-112">Objedinjena aktivnost klijenta: za prikaz [vremenske trake aktivnosti](activities.md) u aplikaciji.</span><span class="sxs-lookup"><span data-stu-id="2386f-112">Unified Customer Activity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="2386f-113">Ograničenja</span><span class="sxs-lookup"><span data-stu-id="2386f-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="2386f-114">Dohvatljivi entiteti</span><span class="sxs-lookup"><span data-stu-id="2386f-114">Retrievable entities</span></span>

<span data-ttu-id="2386f-115">Možete dohvatiti samo entitete **Klijent**, **UnifiedActivity** i **Segmenti** putem priključka za Power Apps.</span><span class="sxs-lookup"><span data-stu-id="2386f-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="2386f-116">Prikazani su drugi entiteti jer ih temeljni povezivač podržava putem okidača na usluzi Power Automate.</span><span class="sxs-lookup"><span data-stu-id="2386f-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="2386f-117">Delegacija</span><span class="sxs-lookup"><span data-stu-id="2386f-117">Delegation</span></span>

<span data-ttu-id="2386f-118">Delegiranje radi za entitet Klijent i entitet UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="2386f-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="2386f-119">Delegiranje za entitet **Klijent**: da biste koristili delegiranje za ovaj entitet, polja treba indeksirati u [indeksu pretraživanja i filtriranja](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="2386f-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="2386f-120">Delegiranje za entitet **UnifiedActivity**: Delegiranje za ovaj entitet radi samo za polja **ActivityId** i **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="2386f-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="2386f-121">Za više informacija o delegiranju pogledajte [Funkcije i operacije koje se mogu delegirati na usluzi Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="2386f-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="2386f-122">Primjer kontrole zbirke</span><span class="sxs-lookup"><span data-stu-id="2386f-122">Example gallery control</span></span>

<span data-ttu-id="2386f-123">Na primjer, profile klijenata dodajete [kontroli galerije](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="2386f-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="2386f-124">Dodajte kontrolu **Zbirka** aplikaciji koju gradite.</span><span class="sxs-lookup"><span data-stu-id="2386f-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2386f-125">![Dodavanje elementa galerije](media/connector-powerapps9.png "Dodavanje elementa galerije")</span><span class="sxs-lookup"><span data-stu-id="2386f-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="2386f-126">Odaberite **Klijent** kao izvor podataka za stavke.</span><span class="sxs-lookup"><span data-stu-id="2386f-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2386f-127">![Odabir izvora podataka](media/choose-datasource-powerapps.png "Odabir izvora podataka")</span><span class="sxs-lookup"><span data-stu-id="2386f-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="2386f-128">Možete promijeniti podatkovni panel s desne strane da biste odabrali polje za prikaz entiteta Klijent u galeriji.</span><span class="sxs-lookup"><span data-stu-id="2386f-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="2386f-129">Ako želite prikazati bilo koje polje odabranog klijenta u galeriji, ispunite svojstvo Tekst oznake:  **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="2386f-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="2386f-130">Primjer: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="2386f-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="2386f-131">Da biste prikazali objedinjenu vremensku traku za klijenta, dodajte element Galerija i dodajte svojstvo Stavke: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="2386f-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="2386f-132">Primjer: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="2386f-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>
