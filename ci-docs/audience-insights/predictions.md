---
title: Dopunite djelomične podatke pomoću predviđanja
description: Koristite predviđanja za popunjavanje nepotpunih podataka o kupcima.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268263"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="8442a-103">Dopunite djelomične podatke predviđanjima</span><span class="sxs-lookup"><span data-stu-id="8442a-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8442a-104">Predviđanja omogućuju lako stvaranje predviđenih vrijednosti koje mogu poboljšati razumijevanje klijenta.</span><span class="sxs-lookup"><span data-stu-id="8442a-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="8442a-105">Na stranici **Inteligencija** > **Predviđanja** možete odabrati **Moja predviđanja** da biste vidjeli predviđanja koja ste konfigurirali u drugim dijelovima uvida u ciljne skupine i omogućili vam da ih dodatno prilagodite.</span><span class="sxs-lookup"><span data-stu-id="8442a-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="8442a-106">Ne možete upotrebljavati tu značajku ako vaše okruženje koristi pohranu Azure Data Lake Gen 2 Storage.</span><span class="sxs-lookup"><span data-stu-id="8442a-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="8442a-107">Značajka predviđanja upotrebljava automatizirana sredstva za procjenu podataka i predviđanja na temelju tih podataka, pa se stoga može upotrijebiti kao metoda profiliranja jer je taj pojam definiran Općom uredbom o zaštiti podataka (GDPR odn. OUZP).</span><span class="sxs-lookup"><span data-stu-id="8442a-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="8442a-108">Klijentova upotreba ove značajke za obradu podataka može biti podložna OUZP-u ili drugim zakonima ili propisima.</span><span class="sxs-lookup"><span data-stu-id="8442a-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="8442a-109">Odgovorni ste osigurati da je da vaše korištenje Dynamics 365 Customer Insights, uključujući predviđanja, u skladu sa svim primjenjivim zakonima i uredbama, uključujući zakone koji se odnose na privatnost, osobne podatke, biometrijske podatke, zaštitu podataka i povjerljivost komunikacija.</span><span class="sxs-lookup"><span data-stu-id="8442a-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8442a-110">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="8442a-110">Prerequisites</span></span>

<span data-ttu-id="8442a-111">Da bi vaša tvrtka ili ustanova mogla upotrebljavati značajku predviđanja, mora ispuniti sljedeće preduvjete:</span><span class="sxs-lookup"><span data-stu-id="8442a-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="8442a-112">Vaša organizacija ima instancu [postavljenu u Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) i u istoj je organizaciji kao i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8442a-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="8442a-113">Vaše okruženje je vezano za vašu instancu Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8442a-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="8442a-114">Ako [stvarate novo okruženje](manage-environments.md), konfigurirajte ga u dijaloškom okviru **Stvaranje okruženja** i odaberite **Napredno**.</span><span class="sxs-lookup"><span data-stu-id="8442a-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="8442a-115">Ako ste već stvorili okruženje, idite na njegove postavke i odaberite **Napredno**.</span><span class="sxs-lookup"><span data-stu-id="8442a-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="8442a-116">U svakom slučaju, u odjeljak **Koristite predviđanja** unesite instancu URL-a Common Data Service kojem želite priložiti svoje okruženje.</span><span class="sxs-lookup"><span data-stu-id="8442a-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="8442a-117">Stvaranje predviđanja u entitetu klijenta</span><span class="sxs-lookup"><span data-stu-id="8442a-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="8442a-118">U uvidima u ciljnu skupinu idite na **Podaci** > **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="8442a-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="8442a-119">Odaberite entitet **Klijent**.</span><span class="sxs-lookup"><span data-stu-id="8442a-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="8442a-120">U entitetu **Klijent: CustomerInsights** odaberite karticu **Polja**.</span><span class="sxs-lookup"><span data-stu-id="8442a-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="8442a-121">Pronađite naziv atributa za koje želite predvidjeti vrijednosti, a zatim odaberite ikonu **Pregled** u stupcu **Sažetak**.</span><span class="sxs-lookup"><span data-stu-id="8442a-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8442a-122">![Ikona pregleda](media/intelligence-overviewicon.png "Ikona pregleda")</span><span class="sxs-lookup"><span data-stu-id="8442a-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="8442a-123">Ako za atribut postoji visoka stopa vrijednosti koje nedostaju, odaberite **Predviđanje vrijednosti koje nedostaju** da biste nastavili s predviđanjima.</span><span class="sxs-lookup"><span data-stu-id="8442a-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8442a-124">![Status pregleda s prikazanim gumbom za predviđanje vrijednosti koje nedostaju](media/intelligence-overviewpredictmissingvalues.png "Status pregleda s prikazanim gumbom za predviđanje vrijednosti koje nedostaju")</span><span class="sxs-lookup"><span data-stu-id="8442a-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="8442a-125">Unesite **Zaslonski naziv** i **Naziv izlaznog entiteta** za rezultate predviđanja.</span><span class="sxs-lookup"><span data-stu-id="8442a-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="8442a-126">Unaprijed popunjen popis opcija prikazat će mjesto gdje možete preslikati vrijednosti u predviđenu kategoriju.</span><span class="sxs-lookup"><span data-stu-id="8442a-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="8442a-127">U tom slučaju, jedine mogućnosti kategorije bit će 0 ili 1 jer se preslikavaju na točnu/netočnu ili binarnu prirodu predviđanja.</span><span class="sxs-lookup"><span data-stu-id="8442a-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="8442a-128">U stupcu Kategorija preslikajte vrijednosti polja koje želite klasificirati kao „0” u konačnom predviđanju na „0”, a stavke koje želite klasificirati kao „1” u konačnom predviđanju na „1”.</span><span class="sxs-lookup"><span data-stu-id="8442a-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8442a-129">![Primjer koji prikazuje preslikane vrijednosti polja u kategorije](media/intelligence-categorymapping.png "Primjer koji prikazuje preslikane vrijednosti polja u kategorije")</span><span class="sxs-lookup"><span data-stu-id="8442a-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="8442a-130">Odaberite **Gotovo** i predviđanje će se obraditi.</span><span class="sxs-lookup"><span data-stu-id="8442a-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="8442a-131">Obrada traje neko vrijeme, ovisno o veličini i složenosti podataka.</span><span class="sxs-lookup"><span data-stu-id="8442a-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="8442a-132">Rezultati će biti dostupni u novom entitetu temeljenom na **Nazivu izlaznog entiteta** predviđanja koje ste stvorili.</span><span class="sxs-lookup"><span data-stu-id="8442a-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="8442a-133">Stvaranje predviđanja tijekom stvaranja segmenta</span><span class="sxs-lookup"><span data-stu-id="8442a-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="8442a-134">Predviđanje vrijednosti koje nedostaju za određeni atribut moguće je i prilikom stvaranja segmenta.</span><span class="sxs-lookup"><span data-stu-id="8442a-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="8442a-135">Preciznije, kada brzo stvorite segment na temelju objedinjenog entiteta klijenta ili entiteta Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="8442a-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="8442a-136">Kao dio tog tijeka, odabirete određeni atribut na kojem ćete temeljiti svoj segment, kao što su zadovoljstvo klijenta ili iznos kupnje.</span><span class="sxs-lookup"><span data-stu-id="8442a-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="8442a-137">Nakon stvaranja segmenta sustav će predložiti metodu za predviđanje vrijednosti koje nedostaju za ovaj atribut.</span><span class="sxs-lookup"><span data-stu-id="8442a-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="8442a-138">U uvidima u ciljnu skupinu idite na **Segmenti** i odaberite pločicu **Profili**.</span><span class="sxs-lookup"><span data-stu-id="8442a-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="8442a-139">Odaberite **Polje** da biste stvorili segment i odaberite **Operator**, a zatim odaberite **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="8442a-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="8442a-140">Unesite **Naziv** i **Zaslonski naziv** za segment.</span><span class="sxs-lookup"><span data-stu-id="8442a-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="8442a-141">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="8442a-141">Select **Save**.</span></span>

5. <span data-ttu-id="8442a-142">Ako segment koji ste upravo stvorili ima nepotpune podatke u polju izvora, možete odlučiti predvidjeti vrijednosti koje nedostaju.</span><span class="sxs-lookup"><span data-stu-id="8442a-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8442a-143">![Gumb predviđanja](media/segments-predictoption.png "Gumb predviđanja")</span><span class="sxs-lookup"><span data-stu-id="8442a-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="8442a-144">Unesite **Zaslonski naziv** i **Naziv izlaznog entiteta** za rezultate predviđanja.</span><span class="sxs-lookup"><span data-stu-id="8442a-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="8442a-145">Odaberite **Gotovo**.</span><span class="sxs-lookup"><span data-stu-id="8442a-145">Select **Done**.</span></span> <span data-ttu-id="8442a-146">Predviđanja će se uskoro generirati u novom entitetu s nazivom koji ste naveli za **Naziv izlaznog entiteta**.</span><span class="sxs-lookup"><span data-stu-id="8442a-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="8442a-147">Prikaz predviđanja</span><span class="sxs-lookup"><span data-stu-id="8442a-147">View a prediction</span></span>

1. <span data-ttu-id="8442a-148">U uvidima u ciljnu skupinu idite na **Inteligencija** > **Predviđanja** > **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="8442a-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="8442a-149">Odaberite predviđanje koje želite pregledati.</span><span class="sxs-lookup"><span data-stu-id="8442a-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="8442a-150">Odaberite elipsu u stupcu **Radnje** i odaberite **Prikaz**.</span><span class="sxs-lookup"><span data-stu-id="8442a-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="8442a-151">U prikazu predviđanja vidjet ćete brojne podatkovne točke.</span><span class="sxs-lookup"><span data-stu-id="8442a-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8442a-152">![Stranica predviđanja](media/intelligence-predictionsviewpage.png "Stranica predviđanja")</span><span class="sxs-lookup"><span data-stu-id="8442a-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="8442a-153">**Predviđene vrijednosti** prikazuje preslikavanje koje ste stvorili tijekom faze vrijednosti polja u fazi preslikavanja kategorije.</span><span class="sxs-lookup"><span data-stu-id="8442a-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="8442a-154">To su vrijednosti u vašem skupu podataka koje su preslikane u određenu kategoriju.</span><span class="sxs-lookup"><span data-stu-id="8442a-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="8442a-155">-**Glavni utjecaji** su faktori unutar skupa podataka koji bi najvjerojatnije mogli utjecati na povjerenje predviđanja vrijednosti polja koje se preslikava u određenu kategoriju.</span><span class="sxs-lookup"><span data-stu-id="8442a-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="8442a-156">**Performanse** označava kako rade predviđanja.</span><span class="sxs-lookup"><span data-stu-id="8442a-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="8442a-157">Odaberite vezu da biste saznali više.</span><span class="sxs-lookup"><span data-stu-id="8442a-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="8442a-158">**Pregled** prikazuje uzorke izlaznog skupa podataka iz vašeg predviđanja i vjerojatnost ili naše pouzdanje za predviđene vrijednosti, gdje je 0 neizvjestan, a 1 je sigurno.</span><span class="sxs-lookup"><span data-stu-id="8442a-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="8442a-159">Ažuriranje predviđanja</span><span class="sxs-lookup"><span data-stu-id="8442a-159">Update a prediction</span></span>

1. <span data-ttu-id="8442a-160">U uvidima u ciljnu skupinu idite na **Inteligencija** > **Predviđanja** > **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="8442a-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="8442a-161">Odaberite predviđanje koje želite ažurirati i odaberite ikonu **Ažuriraj**.</span><span class="sxs-lookup"><span data-stu-id="8442a-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="8442a-162">Predviđanje će biti zakazano za obradu.</span><span class="sxs-lookup"><span data-stu-id="8442a-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="8442a-163">Vrijeme posljednjeg ažuriranja možete vidjeti u stupcu **Ažurirano** na stranici **Predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="8442a-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="8442a-164">Uređivanje predviđanja</span><span class="sxs-lookup"><span data-stu-id="8442a-164">Edit a prediction</span></span>

<span data-ttu-id="8442a-165">Nakon što ste stvorili predviđanje, možete prilagoditi model u alatu AI Builder kako biste povećali učinkovitost modela.</span><span class="sxs-lookup"><span data-stu-id="8442a-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="8442a-166">U uvidima u ciljnu skupinu idite na **Inteligencija** > **Predviđanja** > **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="8442a-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="8442a-167">Odaberite predviđanje koje želite urediti.</span><span class="sxs-lookup"><span data-stu-id="8442a-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="8442a-168">Odaberite elipsu u stupcu **Radnje** i odaberite **Prikaz**.</span><span class="sxs-lookup"><span data-stu-id="8442a-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="8442a-169">Odaberite **Prilagodi u alatu AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="8442a-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="8442a-170">Ažurirajte model u alatu AI Builder.</span><span class="sxs-lookup"><span data-stu-id="8442a-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="8442a-171">[Saznajte više o upravljanju modelima u alatu AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models),</span><span class="sxs-lookup"><span data-stu-id="8442a-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="8442a-172">Sljedeće pokretanje predviđanja upotrebljavat će ažurirani model koji ste stvorili.</span><span class="sxs-lookup"><span data-stu-id="8442a-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="8442a-173">Novi modeli stvoreni u značajci AI Builder neće se prikazivati u uvidima u ciljnu skupinu, osim ako model nije stvoren iz gore navedenih iskustava.</span><span class="sxs-lookup"><span data-stu-id="8442a-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="8442a-174">Uklanjanje predviđanja</span><span class="sxs-lookup"><span data-stu-id="8442a-174">Remove a prediction</span></span>

1. <span data-ttu-id="8442a-175">U uvidima u ciljnu skupinu idite na **Inteligencija** > **Predviđanja** > **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="8442a-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="8442a-176">Odaberite predviđanje koje želite izbrisati.</span><span class="sxs-lookup"><span data-stu-id="8442a-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="8442a-177">Odaberite elipsu u stupcu **Radnje** i odaberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="8442a-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="8442a-178">Potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="8442a-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="8442a-179">Rješavanje problema</span><span class="sxs-lookup"><span data-stu-id="8442a-179">Troubleshooting</span></span>

<span data-ttu-id="8442a-180">Ako ne možete dovršiti proces prilaganja usluge Common Data Service zbog pogreške, možete pokušati ručno dovršiti proces.</span><span class="sxs-lookup"><span data-stu-id="8442a-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="8442a-181">Postoje dva poznata problema koji se mogu pojaviti u procesu prilaganja:</span><span class="sxs-lookup"><span data-stu-id="8442a-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="8442a-182">Rješenje dodatka za korisničku karticu nije instalirano.</span><span class="sxs-lookup"><span data-stu-id="8442a-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="8442a-183">Dopunite upute za [instaliranje i konfiguriranje rješenja](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="8442a-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="8442a-184">Dopuštenja za aplikacije nisu dodijeljena.</span><span class="sxs-lookup"><span data-stu-id="8442a-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="8442a-185">Idite na [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8442a-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="8442a-186">Odaberite **Okruženja**.</span><span class="sxs-lookup"><span data-stu-id="8442a-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="8442a-187">Odaberite tri točke pored okruženja kojem želite dodati dozvolu i odaberite **Postavke**.</span><span class="sxs-lookup"><span data-stu-id="8442a-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="8442a-188">Proširite **Korisnici + dozvole** i odaberite **Korisnici**.</span><span class="sxs-lookup"><span data-stu-id="8442a-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="8442a-189">Odaberite **+ Novo** i odaberite **Korisnik**.</span><span class="sxs-lookup"><span data-stu-id="8442a-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="8442a-190">Odaberite **Korisnik aplikacije** ako već nije odabran i unesite sljedeće informacije:</span><span class="sxs-lookup"><span data-stu-id="8442a-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="8442a-191">**Korisničko ime:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8442a-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="8442a-192">**ID aplikacije:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="8442a-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="8442a-193">**Ime:** Customer</span><span class="sxs-lookup"><span data-stu-id="8442a-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="8442a-194">**Prezime:** Insights</span><span class="sxs-lookup"><span data-stu-id="8442a-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="8442a-195">**Primarna e-pošta:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8442a-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="8442a-196">Odaberite **Spremi i zatvori**.</span><span class="sxs-lookup"><span data-stu-id="8442a-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="8442a-197">Odaberite korisnika kojeg ste stvorili.</span><span class="sxs-lookup"><span data-stu-id="8442a-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="8442a-198">Odaberite **Upravljanje ulogama** na traci izbornika na vrhu.</span><span class="sxs-lookup"><span data-stu-id="8442a-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="8442a-199">Odaberite **Administrator sustava**, zatim odaberite **U redu**.</span><span class="sxs-lookup"><span data-stu-id="8442a-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]