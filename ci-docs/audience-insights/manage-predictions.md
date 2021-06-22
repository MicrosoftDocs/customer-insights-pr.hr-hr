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
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095694"
---
# <a name="manage-predictions"></a><span data-ttu-id="4fe74-103">Upravljanje predviđanjima</span><span class="sxs-lookup"><span data-stu-id="4fe74-103">Manage predictions</span></span>

<span data-ttu-id="4fe74-104">U ovom članku se razmatraju neki zadaci koje dijeli većina scenarija predviđanja.</span><span class="sxs-lookup"><span data-stu-id="4fe74-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="4fe74-105">Otklanjanje poteškoća s neuspjelim predviđanjem</span><span class="sxs-lookup"><span data-stu-id="4fe74-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="4fe74-106">Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="4fe74-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="4fe74-107">Odaberite okomite elipse pored predviđanja za koje želite pregledati zapisnike pogrešaka.</span><span class="sxs-lookup"><span data-stu-id="4fe74-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="4fe74-108">Odaberite **Zapisnici**.</span><span class="sxs-lookup"><span data-stu-id="4fe74-108">Select **Logs**.</span></span>

1. <span data-ttu-id="4fe74-109">Pregledajte sve pogreške.</span><span class="sxs-lookup"><span data-stu-id="4fe74-109">Review all the errors.</span></span> <span data-ttu-id="4fe74-110">Može se dogoditi nekoliko vrsta pogrešaka i one opisuju kakvo je stanje prouzročilo pogrešku.</span><span class="sxs-lookup"><span data-stu-id="4fe74-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="4fe74-111">Na primjer, pogreška za koju nema dovoljno podataka da bi se točno predvidjela obično se razrješava učitavanjem dodatnih podataka u Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4fe74-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="4fe74-112">Izvješće o upotrebljivosti ulaznih podataka</span><span class="sxs-lookup"><span data-stu-id="4fe74-112">Input data usability report</span></span>

<span data-ttu-id="4fe74-113">Izvješće o upotrebljivosti ulaznih podataka pruža pročišćeni prikaz pogrešaka i upozorenja koja mogu proizvesti vaša gotova predviđanja.</span><span class="sxs-lookup"><span data-stu-id="4fe74-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="4fe74-114">Također daje preporuke kako poboljšati izvedbu modela.</span><span class="sxs-lookup"><span data-stu-id="4fe74-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="4fe74-115">Izvješće je dostupno nakon što model završi svoj proces obuke.</span><span class="sxs-lookup"><span data-stu-id="4fe74-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="4fe74-116">Stvara se za svaki model zasebno, bez obzira je li uspješno dovršen ili ne.</span><span class="sxs-lookup"><span data-stu-id="4fe74-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="4fe74-117">Trenutno ova značajka radi samo za model Transakcijski gubitak klijenata.</span><span class="sxs-lookup"><span data-stu-id="4fe74-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="4fe74-118">Prikaz izvješća o upotrebljivosti ulaznih podataka</span><span class="sxs-lookup"><span data-stu-id="4fe74-118">View the input data usability report</span></span>

<span data-ttu-id="4fe74-119">Nakon što je gotovi model završio svoj korak obuke, pogledajte izvješće:</span><span class="sxs-lookup"><span data-stu-id="4fe74-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="4fe74-120">Odaberite elipse pored naziva modela i odaberite **Izvješće o upotrebljivosti ulaznih podataka**.</span><span class="sxs-lookup"><span data-stu-id="4fe74-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="4fe74-121">Odaberite status modela i **Prikaz Izvješća o upotrebljivosti ulaznih podataka** u bočnom oknu.</span><span class="sxs-lookup"><span data-stu-id="4fe74-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="4fe74-122">Odaberite jedan od modela s popisa i odaberite **Izvješće o upotrebljivosti ulaznih podataka** na naredbenoj traci.</span><span class="sxs-lookup"><span data-stu-id="4fe74-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="4fe74-123">Otvorite stranicu s rezultatima modela i odaberite **Izvješće o upotrebljivosti ulaznih podataka** na naredbenoj traci.</span><span class="sxs-lookup"><span data-stu-id="4fe74-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="4fe74-124">Informacije u izvješću o upotrebljivosti ulaznih podataka</span><span class="sxs-lookup"><span data-stu-id="4fe74-124">Information in the input data usability report</span></span>

<span data-ttu-id="4fe74-125">Sljedeći stupci u izvješću sadrže korisne informacije za poboljšanje podataka za model.</span><span class="sxs-lookup"><span data-stu-id="4fe74-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Primjer izvješća o upotrebljivosti ulaznih podataka koji prikazuje tablicu s pogreškama, upozorenjima i preporukama.":::

- <span data-ttu-id="4fe74-127">Naziv: opisni naziv pogreške, upozorenja ili preporuke.</span><span class="sxs-lookup"><span data-stu-id="4fe74-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="4fe74-128">Korak: faza modela, obuka ili rezultat na koji se informacije odnose.</span><span class="sxs-lookup"><span data-stu-id="4fe74-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="4fe74-129">Stanje: ozbiljnost informacija (pogreška, upozorenje, preporuka).</span><span class="sxs-lookup"><span data-stu-id="4fe74-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="4fe74-130">Naziv stupca: stupac u entitetu koji treba izmijeniti radi poboljšanja izvedbe modela.</span><span class="sxs-lookup"><span data-stu-id="4fe74-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="4fe74-131">Naziv entiteta: naziv entiteta koji treba izmijeniti radi poboljšanja izvedbe modela.</span><span class="sxs-lookup"><span data-stu-id="4fe74-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="4fe74-132">Pojedinosti: pojedinosti o pogrešci, upozorenju ili preporuci.</span><span class="sxs-lookup"><span data-stu-id="4fe74-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="4fe74-133">Osvježavanje predviđanja</span><span class="sxs-lookup"><span data-stu-id="4fe74-133">Refresh a prediction</span></span>

<span data-ttu-id="4fe74-134">Predviđanja će se automatski osvježiti na istom [rasporedu osvježavanja podataka](system.md#schedule-tab) kao što je konfigurirano u postavkama.</span><span class="sxs-lookup"><span data-stu-id="4fe74-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="4fe74-135">Možete ih osvježiti i ručno.</span><span class="sxs-lookup"><span data-stu-id="4fe74-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="4fe74-136">Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="4fe74-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="4fe74-137">Odaberite okomitu trotočku uz predviđanje koje želite osvježiti.</span><span class="sxs-lookup"><span data-stu-id="4fe74-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="4fe74-138">Odaberite **Osvježi**.</span><span class="sxs-lookup"><span data-stu-id="4fe74-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="4fe74-139">Brisanje predviđanja</span><span class="sxs-lookup"><span data-stu-id="4fe74-139">Delete a prediction</span></span>

<span data-ttu-id="4fe74-140">Brisanjem predviđanja uklanja se i njegov izlazni entitet.</span><span class="sxs-lookup"><span data-stu-id="4fe74-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="4fe74-141">Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="4fe74-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="4fe74-142">Odaberite okomitu trotočku uz predviđanje koje želite izbrisati.</span><span class="sxs-lookup"><span data-stu-id="4fe74-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="4fe74-143">Odaberite **Obriši**.</span><span class="sxs-lookup"><span data-stu-id="4fe74-143">Select **Delete**.</span></span>
