---
title: Prilagođeni modeli za strojno učenje | Microsoft Docs
description: Radite s prilagođenim modelima iz Strojnog učenja Azure u aplikaciji Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668894"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="abb5f-103">Prilagođeni modeli za strojno učenje</span><span class="sxs-lookup"><span data-stu-id="abb5f-103">Custom machine learning models</span></span>

<span data-ttu-id="abb5f-104">**Inteligencija** > **Prilagođeni modeli** omogućava upravljanje tijekovima rada na temelju modela strojnog učenja Azure.</span><span class="sxs-lookup"><span data-stu-id="abb5f-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="abb5f-105">Tijekovi rada pomažu vam u odabiru podataka iz kojih želite generirati uvide i mapiranju rezultata u vaše objedinjene podatke o klijentima.</span><span class="sxs-lookup"><span data-stu-id="abb5f-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="abb5f-106">Dodatne informacije o izradi prilagođenih modela strojnog učenja potražite u odjeljku [Upotreba modela na temelju Strojnog učenja Azure](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="abb5f-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="abb5f-107">Odgovorna umjetna inteligencija</span><span class="sxs-lookup"><span data-stu-id="abb5f-107">Responsible AI</span></span>

<span data-ttu-id="abb5f-108">Predviđanja nude mogućnosti stvaranja boljih korisničkih iskustava, poboljšanja poslovnih mogućnosti i izvora prihoda.</span><span class="sxs-lookup"><span data-stu-id="abb5f-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="abb5f-109">Preporučujemo vam da uravnotežite vrijednost svog predviđanja u odnosu na učinak koji ima i pristranosti koje bi se mogle uvesti na etičan način.</span><span class="sxs-lookup"><span data-stu-id="abb5f-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="abb5f-110">Saznajte više o tome kako Microsoft [obrađuje odgovornu umjetnu inteligenciju](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="abb5f-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="abb5f-111">Također možete saznati o [tehnikama i postupcima za odgovorno strojno učenje](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specifičnim za Strojno učenje Azure.</span><span class="sxs-lookup"><span data-stu-id="abb5f-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="abb5f-112">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="abb5f-112">Prerequisites</span></span>

- <span data-ttu-id="abb5f-113">Trenutno ova značajka podržava web-servise objavljene putem [Studija strojnog učenja (klasično)](https://studio.azureml.net) i [skupnih kanala Strojnog učenja Azure](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="abb5f-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="abb5f-114">Za upotrebu ove značajke potreban vam je račun za pohranu Azure Data Lake Gen2 povezan s instancom Azure Studio.</span><span class="sxs-lookup"><span data-stu-id="abb5f-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="abb5f-115">Dodatne informacije potražite u odjeljku [Stvaranje računa za pohranu Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="abb5f-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="abb5f-116">Dodavanje novog tijeka rada</span><span class="sxs-lookup"><span data-stu-id="abb5f-116">Add a new workflow</span></span>

1. <span data-ttu-id="abb5f-117">Idite u odjeljak **Inteligencija** > **Prilagođeni modeli** i odaberite **Novi tijek rada**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="abb5f-118">Dodijelite prilagođenom modelu neki prepoznatljiv naziv u polju **Naziv**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="abb5f-119">![Snimak zaslona okna Novi tijek rada](media/new-workflowv2.png "Snimak zaslona okna Novi tijek rada")</span><span class="sxs-lookup"><span data-stu-id="abb5f-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="abb5f-120">Odaberite tvrtku ili ustanovu koja sadrži web-servis u **Klijent koji sadrži vaš web-servis**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="abb5f-121">Ako je pretplata na Strojno učenje Azure u nekom drugom klijentu, a ne u sustavu Customer Insights, odaberite **Prijava** s vjerodajnicama za odabranu tvrtku ili ustanovu.</span><span class="sxs-lookup"><span data-stu-id="abb5f-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="abb5f-122">Odaberite **Radne prostore** povezane s vašim web-servisom.</span><span class="sxs-lookup"><span data-stu-id="abb5f-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="abb5f-123">Navedena su dva odjeljka, jedan za Strojno učenje Azure v1 (Studio strojnog učenja (klasični)) i Strojno učenje Azure v2 (Strojno učenje Azure).</span><span class="sxs-lookup"><span data-stu-id="abb5f-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="abb5f-124">Ako niste sigurni koji radni prostor odgovara vašem web-servisu Studio strojnog učenja (klasični), odaberite **Bilo koji**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="abb5f-125">Odaberite web-servis Studio strojnog učenja (klasični) ili kanal Strojno učenje Azure na padajućem popisu **Web-servis koji sadrži vaš model**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="abb5f-126">Zatim odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="abb5f-127">Saznajte više o [objavljivanju web-servisa u Studiju strojnog učenja (klasični)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="abb5f-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="abb5f-128">Saznajte više o [objavljivanju kanala u Strojnom učenju Azure pomoću dizajnera](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ili [SDK-a](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="abb5f-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="abb5f-129">Vaš kanal mora biti objavljen pod [krajnjom točkom kanala](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="abb5f-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="abb5f-130">Za svaki **Ulazni podatak web-servisa** odaberite odgovarajući **Entitet** iz uvida u ciljnu skupinu pa odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="abb5f-131">![Konfiguracija tijeka rada](media/intelligence-screen2-updated.png "Konfiguracija tijeka rada")</span><span class="sxs-lookup"><span data-stu-id="abb5f-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="abb5f-132">U koraku **Izlazni parametri modela**, postavite sljedeća svojstva:</span><span class="sxs-lookup"><span data-stu-id="abb5f-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="abb5f-133">Studio strojnog učenja (klasični)</span><span class="sxs-lookup"><span data-stu-id="abb5f-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="abb5f-134">Unesite izlazni **Naziv entiteta** u koji želite da idu izlazni rezultati web-servisa.</span><span class="sxs-lookup"><span data-stu-id="abb5f-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="abb5f-135">Strojno učenje Azure</span><span class="sxs-lookup"><span data-stu-id="abb5f-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="abb5f-136">Unesite izlazni **Naziv entiteta** u koji želite da idu izlazni rezultati kanala.</span><span class="sxs-lookup"><span data-stu-id="abb5f-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="abb5f-137">S padajućeg popisa odaberite **Izlazni naziv parametra pohrane podataka** skupnog kanala.</span><span class="sxs-lookup"><span data-stu-id="abb5f-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="abb5f-138">S padajućeg popisa odaberite **Izlazni naziv parametra puta** skupnog kanala.</span><span class="sxs-lookup"><span data-stu-id="abb5f-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="abb5f-139">![Okno izlaznog parametra modela](media/intelligence-screen3-outputparameters.png "Okno izlaznog parametra modela")</span><span class="sxs-lookup"><span data-stu-id="abb5f-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="abb5f-140">Odaberite odgovarajući atribut s padajućeg popisa **ID klijenta u rezultatima** koji identificira klijente pa odaberite **Spremanje**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="abb5f-141">![Okno usklađivanja rezultata s podacima klijenta](media/intelligence-screen4-relatetocustomer.png "Okno usklađivanja rezultata s podacima klijenta")</span><span class="sxs-lookup"><span data-stu-id="abb5f-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="abb5f-142">Vidjet ćete zaslon **Tijek rada spremljen** s pojedinostima o tijeku rada.</span><span class="sxs-lookup"><span data-stu-id="abb5f-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="abb5f-143">Ako ste konfigurirali tijek rada za kanal Strojno učenje Azure, uvidi u ciljnu skupinu će se pridružiti radnom prostoru koji sadrži kanal.</span><span class="sxs-lookup"><span data-stu-id="abb5f-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="abb5f-144">Uvidi u ciljnu skupinu dobit će ulogu **Suradnik** u radnom prostoru usluge Azure.</span><span class="sxs-lookup"><span data-stu-id="abb5f-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="abb5f-145">Odaberite **Gotovo**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-145">Select **Done**.</span></span>

1. <span data-ttu-id="abb5f-146">Sada možete pokrenuti tijek rada na stranici **Prilagođeni modeli**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="abb5f-147">Uređivanje tijeka rada</span><span class="sxs-lookup"><span data-stu-id="abb5f-147">Edit a workflow</span></span>

1. <span data-ttu-id="abb5f-148">Na stranici **Prilagođeni modeli** odaberite okomite tri točke u stupcu **Radnje** pokraj toka rada koji ste prethodno stvorili te odaberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="abb5f-149">Prepoznatljivo ime vašeg tijeka rada možete ažurirati u polju **Zaslonski naziv**, ali ne možete promijeniti konfigurirani web-servis ili kanal.</span><span class="sxs-lookup"><span data-stu-id="abb5f-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="abb5f-150">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-150">Select **Next**.</span></span>

1. <span data-ttu-id="abb5f-151">Za svaki **Ulazni podatak web-servisa** možete ažurirati odgovarajući **Entitet** iz uvida u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="abb5f-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="abb5f-152">Zatim odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="abb5f-153">U koraku **Izlazni parametri modela**, postavite sljedeća svojstva:</span><span class="sxs-lookup"><span data-stu-id="abb5f-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="abb5f-154">Studio strojnog učenja (klasični)</span><span class="sxs-lookup"><span data-stu-id="abb5f-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="abb5f-155">Unesite izlazni **Naziv entiteta** u koji želite da idu izlazni rezultati web-servisa.</span><span class="sxs-lookup"><span data-stu-id="abb5f-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="abb5f-156">Strojno učenje Azure</span><span class="sxs-lookup"><span data-stu-id="abb5f-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="abb5f-157">Unesite izlazni **Naziv entiteta** u koji želite da idu izlazni rezultati kanala.</span><span class="sxs-lookup"><span data-stu-id="abb5f-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="abb5f-158">Odaberite **Izlazni naziv parametra pohrane podataka** za testni kanal.</span><span class="sxs-lookup"><span data-stu-id="abb5f-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="abb5f-159">Odaberite **Izlazni naziv parametra puta** za testni kanal.</span><span class="sxs-lookup"><span data-stu-id="abb5f-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="abb5f-160">Odaberite odgovarajući atribut s padajućeg popisa **ID klijenta u rezultatima** koji identificira klijente pa odaberite **Spremanje**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="abb5f-161">Morate odabrati atribut iz zaključnih rezultata s vrijednostima sličnim stupcu ID klijenta entiteta Klijent.</span><span class="sxs-lookup"><span data-stu-id="abb5f-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="abb5f-162">Ako nemate takav stupac u svom skupu podataka, odaberite atribut koji jedinstveno identificira redak.</span><span class="sxs-lookup"><span data-stu-id="abb5f-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="abb5f-163">Pokretanje tijeka rada</span><span class="sxs-lookup"><span data-stu-id="abb5f-163">Run a workflow</span></span>

1. <span data-ttu-id="abb5f-164">Na stranici **Prilagođeni modeli** odaberite okomite tri točke u stupcu **Radnje** pokraj toka rada koji ste prethodno stvorili.</span><span class="sxs-lookup"><span data-stu-id="abb5f-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="abb5f-165">Odaberite **Pokretanje**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-165">Select **Run**.</span></span>

<span data-ttu-id="abb5f-166">Vaš tijek rada se također pokreće automatski sa svakim zakazanim osvježavanjem.</span><span class="sxs-lookup"><span data-stu-id="abb5f-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="abb5f-167">Saznajte više o [postavljanju zakazanog osvježavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="abb5f-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="abb5f-168">Brisanje tijeka rada</span><span class="sxs-lookup"><span data-stu-id="abb5f-168">Delete a workflow</span></span>

1. <span data-ttu-id="abb5f-169">Na stranici **Prilagođeni modeli** odaberite okomite tri točke u stupcu **Radnje** pokraj toka rada koji ste prethodno stvorili.</span><span class="sxs-lookup"><span data-stu-id="abb5f-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="abb5f-170">Odaberite **Izbriši** i potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="abb5f-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="abb5f-171">Vaš će se tijek rada izbrisati.</span><span class="sxs-lookup"><span data-stu-id="abb5f-171">Your workflow will be deleted.</span></span> <span data-ttu-id="abb5f-172">[Entitet](entities.md) koji je stvoren kada ste stvorili tijek rada ostaje i može se pregledati na stranici **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="abb5f-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
