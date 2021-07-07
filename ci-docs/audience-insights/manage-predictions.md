---
title: Zajednički zadaci za scenarije predviđanja
description: Saznajte kako upravljati predviđanjima, rješavati ih i pročišćavati.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315869"
---
# <a name="manage-predictions"></a><span data-ttu-id="78721-103">Upravljanje predviđanjima</span><span class="sxs-lookup"><span data-stu-id="78721-103">Manage predictions</span></span>

<span data-ttu-id="78721-104">U ovom članku se razmatraju neki zadaci koje dijeli većina scenarija predviđanja.</span><span class="sxs-lookup"><span data-stu-id="78721-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="78721-105">Otklanjanje poteškoća s neuspjelim predviđanjem</span><span class="sxs-lookup"><span data-stu-id="78721-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="78721-106">Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="78721-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="78721-107">Odaberite okomite elipse pored predviđanja za koje želite pregledati zapisnike pogrešaka.</span><span class="sxs-lookup"><span data-stu-id="78721-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="78721-108">Odaberite **Zapisnici**.</span><span class="sxs-lookup"><span data-stu-id="78721-108">Select **Logs**.</span></span>

1. <span data-ttu-id="78721-109">Pregledajte sve pogreške.</span><span class="sxs-lookup"><span data-stu-id="78721-109">Review all the errors.</span></span> <span data-ttu-id="78721-110">Može se dogoditi nekoliko vrsta pogrešaka i one opisuju kakvo je stanje prouzročilo pogrešku.</span><span class="sxs-lookup"><span data-stu-id="78721-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="78721-111">Na primjer, pogreška za koju nema dovoljno podataka da bi se točno predvidjela obično se razrješava učitavanjem dodatnih podataka u Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="78721-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="78721-112">Izvješće o upotrebljivosti ulaznih podataka</span><span class="sxs-lookup"><span data-stu-id="78721-112">Input data usability report</span></span>

<span data-ttu-id="78721-113">Izvješće o upotrebljivosti ulaznih podataka pruža pročišćeni prikaz pogrešaka i upozorenja koja mogu proizvesti vaša gotova predviđanja.</span><span class="sxs-lookup"><span data-stu-id="78721-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="78721-114">Također daje preporuke kako poboljšati izvedbu modela.</span><span class="sxs-lookup"><span data-stu-id="78721-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="78721-115">Izvješće je dostupno nakon što model završi svoj proces obuke.</span><span class="sxs-lookup"><span data-stu-id="78721-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="78721-116">Stvara se za svaki model zasebno, bez obzira je li uspješno dovršen ili ne.</span><span class="sxs-lookup"><span data-stu-id="78721-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="78721-117">Prikaz izvješća o upotrebljivosti ulaznih podataka</span><span class="sxs-lookup"><span data-stu-id="78721-117">View the input data usability report</span></span>

<span data-ttu-id="78721-118">Nakon što je gotovi model završio svoj korak obuke, pogledajte izvješće:</span><span class="sxs-lookup"><span data-stu-id="78721-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="78721-119">Odaberite elipse pored naziva modela i odaberite **Izvješće o upotrebljivosti ulaznih podataka**.</span><span class="sxs-lookup"><span data-stu-id="78721-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="78721-120">Odaberite status modela i **Prikaz Izvješća o upotrebljivosti ulaznih podataka** u bočnom oknu.</span><span class="sxs-lookup"><span data-stu-id="78721-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="78721-121">Odaberite jedan od modela s popisa i odaberite **Izvješće o upotrebljivosti ulaznih podataka** na naredbenoj traci.</span><span class="sxs-lookup"><span data-stu-id="78721-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="78721-122">Otvorite stranicu s rezultatima modela i odaberite **Izvješće o upotrebljivosti ulaznih podataka** na naredbenoj traci.</span><span class="sxs-lookup"><span data-stu-id="78721-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="78721-123">Informacije u izvješću o upotrebljivosti ulaznih podataka</span><span class="sxs-lookup"><span data-stu-id="78721-123">Information in the input data usability report</span></span>

<span data-ttu-id="78721-124">Sljedeći stupci u izvješću sadrže korisne informacije za poboljšanje podataka za model.</span><span class="sxs-lookup"><span data-stu-id="78721-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Primjer izvješća o upotrebljivosti ulaznih podataka koji prikazuje tablicu s pogreškama, upozorenjima i preporukama.":::

- <span data-ttu-id="78721-126">Naziv: opisni naziv pogreške, upozorenja ili preporuke.</span><span class="sxs-lookup"><span data-stu-id="78721-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="78721-127">Korak: faza modela, obuka ili rezultat na koji se informacije odnose.</span><span class="sxs-lookup"><span data-stu-id="78721-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="78721-128">Stanje: ozbiljnost informacija (pogreška, upozorenje, preporuka).</span><span class="sxs-lookup"><span data-stu-id="78721-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="78721-129">Naziv stupca: stupac u entitetu koji treba izmijeniti radi poboljšanja izvedbe modela.</span><span class="sxs-lookup"><span data-stu-id="78721-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="78721-130">Naziv entiteta: naziv entiteta koji treba izmijeniti radi poboljšanja izvedbe modela.</span><span class="sxs-lookup"><span data-stu-id="78721-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="78721-131">Pojedinosti: pojedinosti o pogrešci, upozorenju ili preporuci.</span><span class="sxs-lookup"><span data-stu-id="78721-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="78721-132">Osvježavanje predviđanja</span><span class="sxs-lookup"><span data-stu-id="78721-132">Refresh a prediction</span></span>

<span data-ttu-id="78721-133">Predviđanja će se automatski osvježiti na istom [rasporedu osvježavanja podataka](system.md#schedule-tab) kao što je konfigurirano u postavkama.</span><span class="sxs-lookup"><span data-stu-id="78721-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="78721-134">Možete ih osvježiti i ručno.</span><span class="sxs-lookup"><span data-stu-id="78721-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="78721-135">Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="78721-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="78721-136">Odaberite okomitu trotočku uz predviđanje koje želite osvježiti.</span><span class="sxs-lookup"><span data-stu-id="78721-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="78721-137">Odaberite **Osvježi**.</span><span class="sxs-lookup"><span data-stu-id="78721-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="78721-138">Brisanje predviđanja</span><span class="sxs-lookup"><span data-stu-id="78721-138">Delete a prediction</span></span>

<span data-ttu-id="78721-139">Brisanjem predviđanja uklanja se i njegov izlazni entitet.</span><span class="sxs-lookup"><span data-stu-id="78721-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="78721-140">Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="78721-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="78721-141">Odaberite okomitu trotočku uz predviđanje koje želite izbrisati.</span><span class="sxs-lookup"><span data-stu-id="78721-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="78721-142">Odaberite **Obriši**.</span><span class="sxs-lookup"><span data-stu-id="78721-142">Select **Delete**.</span></span>
