---
title: Segmenti koji se temelje na izlazu predviđanja
description: Stvorite segmente na temelju izlaznog entiteta modela predviđanja.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741420"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="ec701-103">Stvaranje segmenta na temelju modela predviđanja (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="ec701-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="ec701-104">Rezultati predviđanja ponekad se odnose samo na podskup vaših klijenata.</span><span class="sxs-lookup"><span data-stu-id="ec701-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="ec701-105">Povećajte personalizaciju preporuka stvaranjem segmenata iz rezultata modela predviđanja.</span><span class="sxs-lookup"><span data-stu-id="ec701-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="ec701-106">Na primjer, možda ćete htjeti dati određene preporuke klijentima koji preferiraju određenu vrstu usluge.</span><span class="sxs-lookup"><span data-stu-id="ec701-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ec701-107">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="ec701-107">Prerequisites</span></span>

- <span data-ttu-id="ec701-108">Barem [dozvole suradnika](permissions.md) u aplikaciji Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ec701-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="ec701-109">Preporuka proizvoda, odbijanje transakcija, gubitak pretplate ili model trajne vrijednosti klijenta konfigurirani su u Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ec701-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="ec701-110">Pregled zahtjeva za postavljanje različitih modela:</span><span class="sxs-lookup"><span data-stu-id="ec701-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="ec701-111">Model preporuke proizvoda</span><span class="sxs-lookup"><span data-stu-id="ec701-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="ec701-112">Model gubitka pretplate</span><span class="sxs-lookup"><span data-stu-id="ec701-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="ec701-113">Model odbijanja transakcija</span><span class="sxs-lookup"><span data-stu-id="ec701-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="ec701-114">Model trajne vrijednosti klijenta</span><span class="sxs-lookup"><span data-stu-id="ec701-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="ec701-115">Stvaranje segmenta klijenta na temelju predviđanja</span><span class="sxs-lookup"><span data-stu-id="ec701-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="ec701-116">Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="ec701-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="ec701-117">Odaberite vertikalne elipse pored modela koji želite pregledati i odaberite **Prikaži**.</span><span class="sxs-lookup"><span data-stu-id="ec701-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="ec701-118">Na stranici s rezultatima odaberite **Stvori segment**.</span><span class="sxs-lookup"><span data-stu-id="ec701-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="ec701-119">Za više informacija o stranici s rezultatima pregledajte članak o modelu.</span><span class="sxs-lookup"><span data-stu-id="ec701-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Snimka zaslona stranice s rezultatima predviđanja s naglaskom na radnji Stvori segment.":::

1. <span data-ttu-id="ec701-121">Stvorite novi segment na temelju izlaznog entiteta odabranog modela.</span><span class="sxs-lookup"><span data-stu-id="ec701-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="ec701-122">Za dodatne informacije, pogledajte [Stvaranje segmenata i upravljanje njima](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ec701-122">For more information, see [Create and manage segments](segments.md).</span></span>