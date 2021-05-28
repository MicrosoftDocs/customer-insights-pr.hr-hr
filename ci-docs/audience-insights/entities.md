---
title: Entiteti i skupovi podataka
description: Pogledajte podatke na stranici Entiteti.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049385"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="52338-103">Entiteti u uvidima u ciljnu skupinu</span><span class="sxs-lookup"><span data-stu-id="52338-103">Entities in audience insights</span></span>

<span data-ttu-id="52338-104">Nakon [konfiguriranja izvora podataka](data-sources.md) otvorite stranicu **Entiteti** za evaluaciju kvalitete unesenih podataka.</span><span class="sxs-lookup"><span data-stu-id="52338-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="52338-105">Entiteti se smatraju skupovima podataka.</span><span class="sxs-lookup"><span data-stu-id="52338-105">Entities are considered datasets.</span></span> <span data-ttu-id="52338-106">Više mogućnosti servisa Dynamics 365 Customer Insights izgrađeno je oko ovih entiteta.</span><span class="sxs-lookup"><span data-stu-id="52338-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="52338-107">Ako ih pažljivo pregledate, mogli biste provjeriti rezultate tih mogućnosti.</span><span class="sxs-lookup"><span data-stu-id="52338-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="52338-108">Stranica **Entiteti** navodi entitete i uključuje nekoliko stupaca:</span><span class="sxs-lookup"><span data-stu-id="52338-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="52338-109">**Naziv**: naziv entiteta podatka.</span><span class="sxs-lookup"><span data-stu-id="52338-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="52338-110">Ako vidite znak upozorenja pored naziva entiteta to znači da se podaci za taj entitet nisu uspješno učitali.</span><span class="sxs-lookup"><span data-stu-id="52338-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="52338-111">**Izvor**: vrsta izvora podataka koji su uneseni za entitet</span><span class="sxs-lookup"><span data-stu-id="52338-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="52338-112">**Autor**: ime osobe koja je izradila entitet</span><span class="sxs-lookup"><span data-stu-id="52338-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="52338-113">**Izrađeno**: datum i vrijeme izrade entiteta</span><span class="sxs-lookup"><span data-stu-id="52338-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="52338-114">**Ažurirao**: ime osobe koja je ažurirala entitet</span><span class="sxs-lookup"><span data-stu-id="52338-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="52338-115">**Posljednji put ažurirano**: datum i vrijeme posljednjeg ažuriranja entiteta</span><span class="sxs-lookup"><span data-stu-id="52338-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="52338-116">**Posljednji put osvježeno**: datum i vrijeme posljednjeg osvježavanja podataka</span><span class="sxs-lookup"><span data-stu-id="52338-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="52338-117">Istraživanje podataka određenog entiteta</span><span class="sxs-lookup"><span data-stu-id="52338-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="52338-118">Odaberite entitet za istraživanje različitih polja i zapisa koji su uključeni u taj entitet.</span><span class="sxs-lookup"><span data-stu-id="52338-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="52338-119">![Odabir entiteta](media/data-manager-entities-data.png "Odaberite entitet")</span><span class="sxs-lookup"><span data-stu-id="52338-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="52338-120">Kartica **Podaci** prikazuje tablicu s popisom pojedinosti o pojedinačnim zapisima entiteta.</span><span class="sxs-lookup"><span data-stu-id="52338-120">The **Data** tab shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="52338-121">![Tablica polja](media/data-manager-entities-fields.PNG "Tablica polja")</span><span class="sxs-lookup"><span data-stu-id="52338-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="52338-122">Kartica **Atributi** je odabrana prema zadanim postavkama i prikazuje tablicu za pregled pojedinosti za odabrani entitet, kao što su nazivi polja, vrste podataka i vrste.</span><span class="sxs-lookup"><span data-stu-id="52338-122">The **Attributes** tab is selected by default and shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="52338-123">Stupac **Vrsta** prikazuje povezane vrste modela uobičajenih podataka, koji automatski identificira sustav ili [ručno mapiraju](map-entities.md) korisnici.</span><span class="sxs-lookup"><span data-stu-id="52338-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="52338-124">To su semantičke vrste koje se mogu razlikovati ovisno o vrstama podataka atributa – primjerice polje *E-pošta* u nastavku ima vrstu podataka *Tekst*, ali njegova (semantička) vrsta modela uobičajenih podataka može biti *E-pošta* ili *Adresa e-pošte*.</span><span class="sxs-lookup"><span data-stu-id="52338-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="52338-125">Obje tablice prikazuju samo uzorak podataka entiteta.</span><span class="sxs-lookup"><span data-stu-id="52338-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="52338-126">Za prikaz cijelog skupa podataka idite na stranicu **Izvori podataka**, odaberite entitet, nakon toga **Uredi** i zatim pregledajte podatke tog entiteta uz pomoć alata za uređivanje Power Query, kao što je objašnjeno u poglavlju [Izvori podataka](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="52338-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="52338-127">Da biste saznali više o podacima koji su uneseni u entitet, stupac **Sažetak** pruža vam neke važne karakteristike podataka, kao što su nule, vrijednosti koje nedostaju, brojevi i distribucije, kako je primjenjivo za vaše podatke.</span><span class="sxs-lookup"><span data-stu-id="52338-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="52338-128">Odaberite ikonu grafikona za prikaz sažetka podataka.</span><span class="sxs-lookup"><span data-stu-id="52338-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="52338-129">![Simbol sažetka](media/data-manager-entities-summary.png "Tablica sažetka podataka")</span><span class="sxs-lookup"><span data-stu-id="52338-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="52338-130">Sljedeći korak</span><span class="sxs-lookup"><span data-stu-id="52338-130">Next step</span></span>

<span data-ttu-id="52338-131">Pogledajte temu [Ujedinjavanje](data-unification.md) da biste saznali kako *mapirati*, *upariti* i *spojiti* unesene podatke.</span><span class="sxs-lookup"><span data-stu-id="52338-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
