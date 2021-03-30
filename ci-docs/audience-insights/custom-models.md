---
title: Prilagođeni modeli za strojno učenje | Microsoft Docs
description: Radite s prilagođenim modelima iz Strojnog učenja Azure u aplikaciji Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 87fb517e9f0b380f9721f77470dceb3bcb7e5616
ms.sourcegitcommit: 55c00ea61c78db7b3b54894c01afb3246dff31c8
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/22/2021
ms.locfileid: "5700659"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="41e91-103">Prilagođeni modeli za strojno učenje</span><span class="sxs-lookup"><span data-stu-id="41e91-103">Custom machine learning models</span></span>

<span data-ttu-id="41e91-104">**Inteligencija** > **Prilagođeni modeli** omogućava upravljanje tijekovima rada na temelju modela strojnog učenja Azure.</span><span class="sxs-lookup"><span data-stu-id="41e91-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="41e91-105">Tijekovi rada pomažu vam u odabiru podataka iz kojih želite generirati uvide i mapiranju rezultata u vaše objedinjene podatke o klijentima.</span><span class="sxs-lookup"><span data-stu-id="41e91-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="41e91-106">Dodatne informacije o izradi prilagođenih modela strojnog učenja potražite u odjeljku [Upotreba modela na temelju Strojnog učenja Azure](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="41e91-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="41e91-107">Odgovorna umjetna inteligencija</span><span class="sxs-lookup"><span data-stu-id="41e91-107">Responsible AI</span></span>

<span data-ttu-id="41e91-108">Predviđanja nude mogućnosti stvaranja boljih korisničkih iskustava, poboljšanja poslovnih mogućnosti i izvora prihoda.</span><span class="sxs-lookup"><span data-stu-id="41e91-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="41e91-109">Preporučujemo vam da uravnotežite vrijednost svog predviđanja u odnosu na učinak koji ima i pristranosti koje bi se mogle uvesti na etičan način.</span><span class="sxs-lookup"><span data-stu-id="41e91-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="41e91-110">Saznajte više o tome kako Microsoft [obrađuje odgovornu umjetnu inteligenciju](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="41e91-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="41e91-111">Također možete saznati o [tehnikama i postupcima za odgovorno strojno učenje](/azure/machine-learning/concept-responsible-ml) specifičnim za Strojno učenje Azure.</span><span class="sxs-lookup"><span data-stu-id="41e91-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="41e91-112">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="41e91-112">Prerequisites</span></span>

- <span data-ttu-id="41e91-113">Trenutno ova značajka podržava web-servise objavljene putem [Studija strojnog učenja (klasično)](https://studio.azureml.net) i [skupnih kanala Strojnog učenja Azure](/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="41e91-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="41e91-114">Za upotrebu ove značajke potreban vam je račun za pohranu Azure Data Lake Gen2 povezan s instancom Azure Studio.</span><span class="sxs-lookup"><span data-stu-id="41e91-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="41e91-115">Dodatne informacije potražite u odjeljku [Stvaranje računa za pohranu Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span><span class="sxs-lookup"><span data-stu-id="41e91-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="41e91-116">Za radne prostore Strojnog učenja Azure s kanalima trebaju vam dozvole administratora pristupa vlasnika ili korisnika za Radni prostor Strojnog učenja Azure.</span><span class="sxs-lookup"><span data-stu-id="41e91-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="41e91-117">Podaci se prenose između instanci servisa Customer Insights i odabranih web-servisa Azure ili kanala u tijeku rada.</span><span class="sxs-lookup"><span data-stu-id="41e91-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="41e91-118">Kada prenosite podatke na uslugu Azure, provjerite je li usluga konfigurirana za obradu podataka na način i na lokaciji koja je potrebna da ti podaci ispune sve pravne ili regulatorne zahtjeve vaše tvrtke ili ustanove.</span><span class="sxs-lookup"><span data-stu-id="41e91-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="41e91-119">Dodavanje novog tijeka rada</span><span class="sxs-lookup"><span data-stu-id="41e91-119">Add a new workflow</span></span>

1. <span data-ttu-id="41e91-120">Idite u odjeljak **Inteligencija** > **Prilagođeni modeli** i odaberite **Novi tijek rada**.</span><span class="sxs-lookup"><span data-stu-id="41e91-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="41e91-121">Dodijelite prilagođenom modelu neki prepoznatljiv naziv u polju **Naziv**.</span><span class="sxs-lookup"><span data-stu-id="41e91-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41e91-122">![Snimak zaslona okna Novi tijek rada](media/new-workflowv2.png "Snimak zaslona okna Novi tijek rada")</span><span class="sxs-lookup"><span data-stu-id="41e91-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="41e91-123">Odaberite tvrtku ili ustanovu koja sadrži web-servis u **Klijent koji sadrži vaš web-servis**.</span><span class="sxs-lookup"><span data-stu-id="41e91-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="41e91-124">Ako je pretplata na Strojno učenje Azure u nekom drugom klijentu, a ne u sustavu Customer Insights, odaberite **Prijava** s vjerodajnicama za odabranu tvrtku ili ustanovu.</span><span class="sxs-lookup"><span data-stu-id="41e91-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="41e91-125">Odaberite **Radne prostore** povezane s vašim web-servisom.</span><span class="sxs-lookup"><span data-stu-id="41e91-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="41e91-126">Navedena su dva odjeljka, jedan za Strojno učenje Azure v1 (Studio strojnog učenja (klasični)) i Strojno učenje Azure v2 (Strojno učenje Azure).</span><span class="sxs-lookup"><span data-stu-id="41e91-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="41e91-127">Ako niste sigurni koji radni prostor odgovara vašem web-servisu Studio strojnog učenja (klasični), odaberite **Bilo koji**.</span><span class="sxs-lookup"><span data-stu-id="41e91-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="41e91-128">Odaberite web-servis Studio strojnog učenja (klasični) ili kanal Strojno učenje Azure na padajućem popisu **Web-servis koji sadrži vaš model**.</span><span class="sxs-lookup"><span data-stu-id="41e91-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="41e91-129">Zatim odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="41e91-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="41e91-130">Saznajte više o [objavljivanju web-servisa u Studiju strojnog učenja (klasični)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="41e91-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="41e91-131">Saznajte više o [objavljivanju kanala u Strojnom učenju Azure pomoću dizajnera](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ili [SDK-a](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="41e91-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="41e91-132">Vaš kanal mora biti objavljen pod [krajnjom točkom kanala](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="41e91-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="41e91-133">Za svaki **Ulazni podatak web-servisa** odaberite odgovarajući **Entitet** iz uvida u ciljnu skupinu pa odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="41e91-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="41e91-134">Tijek rada prilagođenog modela primijenit će heuristiku za mapiranje polja za unos web-usluga u atribute entiteta na temelju naziva i vrste podataka polja.</span><span class="sxs-lookup"><span data-stu-id="41e91-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="41e91-135">Vidjet ćete pogrešku ako se polje web-usluge ne može mapirati na entitet.</span><span class="sxs-lookup"><span data-stu-id="41e91-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41e91-136">![Konfiguracija tijeka rada](media/intelligence-screen2-updated.png "Konfiguracija tijeka rada")</span><span class="sxs-lookup"><span data-stu-id="41e91-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="41e91-137">U koraku **Izlazni parametri modela**, postavite sljedeća svojstva:</span><span class="sxs-lookup"><span data-stu-id="41e91-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="41e91-138">Studio strojnog učenja (klasični)</span><span class="sxs-lookup"><span data-stu-id="41e91-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="41e91-139">Unesite izlazni **Naziv entiteta** u koji želite da idu izlazni rezultati web-servisa.</span><span class="sxs-lookup"><span data-stu-id="41e91-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="41e91-140">Strojno učenje Azure</span><span class="sxs-lookup"><span data-stu-id="41e91-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="41e91-141">Unesite izlazni **Naziv entiteta** u koji želite da idu izlazni rezultati kanala.</span><span class="sxs-lookup"><span data-stu-id="41e91-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="41e91-142">S padajućeg popisa odaberite **Izlazni naziv parametra pohrane podataka** skupnog kanala.</span><span class="sxs-lookup"><span data-stu-id="41e91-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="41e91-143">S padajućeg popisa odaberite **Izlazni naziv parametra puta** skupnog kanala.</span><span class="sxs-lookup"><span data-stu-id="41e91-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="41e91-144">![Okno izlaznog parametra modela](media/intelligence-screen3-outputparameters.png "Okno izlaznog parametra modela")</span><span class="sxs-lookup"><span data-stu-id="41e91-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="41e91-145">Odaberite odgovarajući atribut s padajućeg popisa **ID klijenta u rezultatima** koji identificira klijente pa odaberite **Spremanje**.</span><span class="sxs-lookup"><span data-stu-id="41e91-145">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41e91-146">![Okno usklađivanja rezultata s podacima klijenta](media/intelligence-screen4-relatetocustomer.png "Okno usklađivanja rezultata s podacima klijenta")</span><span class="sxs-lookup"><span data-stu-id="41e91-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="41e91-147">Vidjet ćete zaslon **Tijek rada spremljen** s pojedinostima o tijeku rada.</span><span class="sxs-lookup"><span data-stu-id="41e91-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="41e91-148">Ako ste konfigurirali tijek rada za kanal Strojno učenje Azure, uvidi u ciljnu skupinu će se pridružiti radnom prostoru koji sadrži kanal.</span><span class="sxs-lookup"><span data-stu-id="41e91-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="41e91-149">Uvidi u ciljnu skupinu dobit će ulogu **Suradnik** u radnom prostoru usluge Azure.</span><span class="sxs-lookup"><span data-stu-id="41e91-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="41e91-150">Odaberite **Gotovo**.</span><span class="sxs-lookup"><span data-stu-id="41e91-150">Select **Done**.</span></span>

1. <span data-ttu-id="41e91-151">Sada možete pokrenuti tijek rada na stranici **Prilagođeni modeli**.</span><span class="sxs-lookup"><span data-stu-id="41e91-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="41e91-152">Uređivanje tijeka rada</span><span class="sxs-lookup"><span data-stu-id="41e91-152">Edit a workflow</span></span>

1. <span data-ttu-id="41e91-153">Na stranici **Prilagođeni modeli** odaberite okomite tri točke u stupcu **Radnje** pokraj toka rada koji ste prethodno stvorili te odaberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="41e91-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="41e91-154">Prepoznatljivo ime vašeg tijeka rada možete ažurirati u polju **Zaslonski naziv**, ali ne možete promijeniti konfigurirani web-servis ili kanal.</span><span class="sxs-lookup"><span data-stu-id="41e91-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="41e91-155">Odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="41e91-155">Select **Next**.</span></span>

1. <span data-ttu-id="41e91-156">Za svaki **Ulazni podatak web-servisa** možete ažurirati odgovarajući **Entitet** iz uvida u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="41e91-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="41e91-157">Zatim odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="41e91-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="41e91-158">U koraku **Izlazni parametri modela**, postavite sljedeća svojstva:</span><span class="sxs-lookup"><span data-stu-id="41e91-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="41e91-159">Studio strojnog učenja (klasični)</span><span class="sxs-lookup"><span data-stu-id="41e91-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="41e91-160">Unesite izlazni **Naziv entiteta** u koji želite da idu izlazni rezultati web-servisa.</span><span class="sxs-lookup"><span data-stu-id="41e91-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="41e91-161">Strojno učenje Azure</span><span class="sxs-lookup"><span data-stu-id="41e91-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="41e91-162">Unesite izlazni **Naziv entiteta** u koji želite da idu izlazni rezultati kanala.</span><span class="sxs-lookup"><span data-stu-id="41e91-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="41e91-163">Odaberite **Izlazni naziv parametra pohrane podataka** za testni kanal.</span><span class="sxs-lookup"><span data-stu-id="41e91-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="41e91-164">Odaberite **Izlazni naziv parametra puta** za testni kanal.</span><span class="sxs-lookup"><span data-stu-id="41e91-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="41e91-165">Odaberite odgovarajući atribut s padajućeg popisa **ID klijenta u rezultatima** koji identificira klijente pa odaberite **Spremanje**.</span><span class="sxs-lookup"><span data-stu-id="41e91-165">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="41e91-166">Odaberite atribut iz zaključnih rezultata s vrijednostima sličnim stupcu ID klijenta entiteta Klijent.</span><span class="sxs-lookup"><span data-stu-id="41e91-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="41e91-167">Ako nemate takav stupac u svom skupu podataka, odaberite atribut koji jedinstveno identificira redak.</span><span class="sxs-lookup"><span data-stu-id="41e91-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="41e91-168">Pokretanje tijeka rada</span><span class="sxs-lookup"><span data-stu-id="41e91-168">Run a workflow</span></span>

1. <span data-ttu-id="41e91-169">Na stranici **Prilagođeni modeli** odaberite okomite tri točke u stupcu **Radnje** pokraj toka rada koji ste prethodno stvorili.</span><span class="sxs-lookup"><span data-stu-id="41e91-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="41e91-170">Odaberite **Pokretanje**.</span><span class="sxs-lookup"><span data-stu-id="41e91-170">Select **Run**.</span></span>

<span data-ttu-id="41e91-171">Vaš tijek rada se također pokreće automatski sa svakim zakazanim osvježavanjem.</span><span class="sxs-lookup"><span data-stu-id="41e91-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="41e91-172">Saznajte više o [postavljanju zakazanog osvježavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="41e91-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="41e91-173">Brisanje tijeka rada</span><span class="sxs-lookup"><span data-stu-id="41e91-173">Delete a workflow</span></span>

1. <span data-ttu-id="41e91-174">Na stranici **Prilagođeni modeli** odaberite okomite tri točke u stupcu **Radnje** pokraj toka rada koji ste prethodno stvorili.</span><span class="sxs-lookup"><span data-stu-id="41e91-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="41e91-175">Odaberite **Izbriši** i potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="41e91-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="41e91-176">Vaš će se tijek rada izbrisati.</span><span class="sxs-lookup"><span data-stu-id="41e91-176">Your workflow will be deleted.</span></span> <span data-ttu-id="41e91-177">[Entitet](entities.md) koji je stvoren kada ste stvorili tijek rada ostaje i može se pregledati na stranici **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="41e91-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="41e91-178">Rezultati</span><span class="sxs-lookup"><span data-stu-id="41e91-178">Results</span></span>

<span data-ttu-id="41e91-179">Rezultati tijeka rada pohranjuju se u entitetu konfiguriranom tijekom faze Izlazni parametar modela.</span><span class="sxs-lookup"><span data-stu-id="41e91-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="41e91-180">Ovim podacima možete pristupiti sa [stranice entiteta](entities.md) ili pomoću [API pristupa](apis.md).</span><span class="sxs-lookup"><span data-stu-id="41e91-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="41e91-181">API pristup</span><span class="sxs-lookup"><span data-stu-id="41e91-181">API Access</span></span>

<span data-ttu-id="41e91-182">Za određeni upit OData za dobivanje podataka iz entiteta prilagođenog modela koristite sljedeći format:</span><span class="sxs-lookup"><span data-stu-id="41e91-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="41e91-183">Zamijenite `<your instance id>` s ID-om vašeg okruženja Customer Insights, koji ćete pronaći u adresnoj traci svog preglednika prilikom pristupa servisu Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="41e91-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="41e91-184">Zamijenite `<custom model output entity>` s nazivom entiteta koji ste naveli tijekom koraka Izlazni parametri modela konfiguracije prilagođenog modela.</span><span class="sxs-lookup"><span data-stu-id="41e91-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="41e91-185">Zamijenite `<guid value>` s ID-om klijenta čijem zapisu želite pristupiti.</span><span class="sxs-lookup"><span data-stu-id="41e91-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="41e91-186">Ovaj ID obično možete pronaći na [stranici s profilima klijenata](customer-profiles.md) u polju ID klijenta.</span><span class="sxs-lookup"><span data-stu-id="41e91-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="41e91-187">Najčešća pitanja</span><span class="sxs-lookup"><span data-stu-id="41e91-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="41e91-188">Zašto ne mogu vidjeti svoj kanal prilikom postavljanja tijeka rada prilagođenog modela?</span><span class="sxs-lookup"><span data-stu-id="41e91-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="41e91-189">Uzrok ovog problema je često u konfiguraciji u kanalu.</span><span class="sxs-lookup"><span data-stu-id="41e91-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="41e91-190">Osigurajte da je [konfiguriran ulazni parametar](azure-machine-learning-experiments.md#dataset-configuration) i da su konfigurirani [izlazni parametri spremišta podataka i putanje](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).</span><span class="sxs-lookup"><span data-stu-id="41e91-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="41e91-191">Što znači pogreška "Nije bilo moguće spremiti tijek rada inteligencije"?</span><span class="sxs-lookup"><span data-stu-id="41e91-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="41e91-192">Korisnici obično vide ovu poruku o pogrešci ako u radnom prostoru nemaju privilegije administratora pristupa vlasnika ili korisnika.</span><span class="sxs-lookup"><span data-stu-id="41e91-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="41e91-193">Korisnik treba višu razinu dozvola kako bi omogućio servisu Customer Insights da obradi tijek rada kao uslugu umjesto korištenja korisničkih vjerodajnica za sljedeća izvođenja tijeka rada.</span><span class="sxs-lookup"><span data-stu-id="41e91-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
