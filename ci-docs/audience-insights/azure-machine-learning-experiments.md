---
title: Eksperimenti Strojnog učenja Azure
description: Koristite modele utemeljene na Strojnom učenju Azure sustavu Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597410"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="874f7-103">Korištenje modela utemeljenih na Strojnom učenju Azure</span><span class="sxs-lookup"><span data-stu-id="874f7-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="874f7-104">Objedinjeni podaci u sustavu Dynamics 365 Customer Insights izvor su za izgradnju modela strojnog učenja koji mogu stvoriti dodatne poslovne uvide.</span><span class="sxs-lookup"><span data-stu-id="874f7-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="874f7-105">Customer Insights integrira se s r programom Machine Learning Studio (klasični) i Strojnim učenjem Azure kako bi koristio vlastite prilagođene modele.</span><span class="sxs-lookup"><span data-stu-id="874f7-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="874f7-106">Pogledajte članak [Eksperimenti programa Machine Learning Studio (klasični)](machine-learning-studio-experiments.md) za primjere eksperimenata izrađenih u programu Machine Learning Studio (klasični).</span><span class="sxs-lookup"><span data-stu-id="874f7-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="874f7-107">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="874f7-107">Prerequisites</span></span>

- <span data-ttu-id="874f7-108">Pristup značajci Customer Insights</span><span class="sxs-lookup"><span data-stu-id="874f7-108">Access to Customer Insights</span></span>
- <span data-ttu-id="874f7-109">Aktivna pretplata za Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="874f7-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="874f7-110">Objedinjeni profili klijenata</span><span class="sxs-lookup"><span data-stu-id="874f7-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="874f7-111">[Izvoz entiteta u Pohranu blobova platforme Azure](export-azure-blob-storage.md) konfiguriran</span><span class="sxs-lookup"><span data-stu-id="874f7-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="874f7-112">Postavljanje radnog prostora Strojnog učenja Azure</span><span class="sxs-lookup"><span data-stu-id="874f7-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="874f7-113">Pogledajte članak [Stvaranje radnog prostora Strojnog učenja Azure](/azure/machine-learning/concept-workspace#-create-a-workspace) za različite opcije za stvaranje radnog prostora.</span><span class="sxs-lookup"><span data-stu-id="874f7-113">See [create a Azure Machine Learning workspace](/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="874f7-114">Za najbolje performanse stvorite radni prostor u Azure regiji koja je geografski najbliža vašem okruženju Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="874f7-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="874f7-115">Pristupite svom radnom prostoru putem programa [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="874f7-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="874f7-116">Ima nekoliko [načina interakcije](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) sa svojim radnim prostorom.</span><span class="sxs-lookup"><span data-stu-id="874f7-116">There are several [ways to interact](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="874f7-117">Rad s dizajnerom za Strojno učenje Azure</span><span class="sxs-lookup"><span data-stu-id="874f7-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="874f7-118">Dizajner za Strojno učenje Azure pruža vizualno radno područje na kojem možete povlačiti i ispuštati skupove podataka i module, slično kao u programu Machine Learning Studio (klasični).</span><span class="sxs-lookup"><span data-stu-id="874f7-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="874f7-119">Skupni cjevovod stvoren u dizajneru može se integrirati u Customer Insights ako je odgovarajuće konfiguriran.</span><span class="sxs-lookup"><span data-stu-id="874f7-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="874f7-120">Rad s SDK-om za Strojno učenje Azure</span><span class="sxs-lookup"><span data-stu-id="874f7-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="874f7-121">Podatkovni znanstvenici i programeri za umjetnu inteligenciju koriste [SDK za Strojno učenje Azure](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) za izgradnju Strojno učenje tijekova rada.</span><span class="sxs-lookup"><span data-stu-id="874f7-121">Data scientists and AI developers use the [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) to build machine learning workflows.</span></span> <span data-ttu-id="874f7-122">Trenutačno se modeli obučeni pomoću SDK-a ne mogu izravno integrirati u Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="874f7-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="874f7-123">Skupni cjevovod za procjenjivanje koji troši taj model potreban je za integraciju sa servisom Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="874f7-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="874f7-124">Zahtjevi za integraciju skupnog cjevovoda sa servisom Customer Insights</span><span class="sxs-lookup"><span data-stu-id="874f7-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="874f7-125">Konfiguracija skupa podataka</span><span class="sxs-lookup"><span data-stu-id="874f7-125">Dataset Configuration</span></span>

<span data-ttu-id="874f7-126">Morate stvoriti skupove podataka da biste koristili podatke entiteta iz servisa Customer Insights za svoj skupni cjevovod za procjenjivanje.</span><span class="sxs-lookup"><span data-stu-id="874f7-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="874f7-127">Te skupove podataka treba registrirati u radnom prostoru.</span><span class="sxs-lookup"><span data-stu-id="874f7-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="874f7-128">Trenutačno podržavamo samo [tablične skupove podataka](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) u formatu .csv.</span><span class="sxs-lookup"><span data-stu-id="874f7-128">Currently, we only support [tabular datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="874f7-129">Skupovi podataka koji odgovaraju podacima entiteta moraju se parametrizirati kao parametar cjevovoda.</span><span class="sxs-lookup"><span data-stu-id="874f7-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="874f7-130">Parametri skupa podataka u Dizajneru</span><span class="sxs-lookup"><span data-stu-id="874f7-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="874f7-131">U dizajneru, otvorite **Odabir stupaca u skupu podataka** pa odaberite **Postavi kao parametar cjevovoda** gdje ćete navesti naziv parametra.</span><span class="sxs-lookup"><span data-stu-id="874f7-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="874f7-132">![Parametrizacija skupa podataka u dizajneru](media/intelligence-designer-dataset-parameters.png "Parametrizacija skupa podataka u dizajneru")</span><span class="sxs-lookup"><span data-stu-id="874f7-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="874f7-133">Parametar skupa podataka u SDK-u (Python)</span><span class="sxs-lookup"><span data-stu-id="874f7-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="874f7-134">Skupni cjevovod za procjenjivanje</span><span class="sxs-lookup"><span data-stu-id="874f7-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="874f7-135">U dizajneru se cjevovod za obuku može koristiti za stvaranje ili ažuriranje cjevovoda za procjenjivanje.</span><span class="sxs-lookup"><span data-stu-id="874f7-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="874f7-136">Trenutačno su podržani samo skupni cjevovodi za procjenjivanje.</span><span class="sxs-lookup"><span data-stu-id="874f7-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="874f7-137">Pomoću SDK-a cjevovod možete objaviti na krajnjoj točki.</span><span class="sxs-lookup"><span data-stu-id="874f7-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="874f7-138">Trenutačno se Customer Insights integrira sa zadanim cjevovodom na krajnjoj točki skupnog cjevovoda u radnom prostoru Strojnog učenja.</span><span class="sxs-lookup"><span data-stu-id="874f7-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="874f7-139">Uvoz podataka cjevovoda u Customer Insights</span><span class="sxs-lookup"><span data-stu-id="874f7-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="874f7-140">Dizajner pruža [Modul za izvoz podataka](/azure/machine-learning/algorithm-module-reference/export-data) koji omogućuje izvoz izlaznih podataka cjevovoda u pohranu platforme Azure.</span><span class="sxs-lookup"><span data-stu-id="874f7-140">The designer provides the [Export Data module](/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="874f7-141">Modul trenutačno mora koristiti vrstu spremišta podataka **Pohrana blobova platforme Azure** i parameterizirati **Spremište podataka** i relativnu **Putanju**.</span><span class="sxs-lookup"><span data-stu-id="874f7-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="874f7-142">Customer Insights nadjačava oba ova parametra tijekom izvođenja cjevovoda sa spremištem podataka i putanjom koja je dostupna proizvodu.</span><span class="sxs-lookup"><span data-stu-id="874f7-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="874f7-143">![Konfiguracija modula za izvoz podataka](media/intelligence-designer-importdata.png "Konfiguracija modula za izvoz podataka")</span><span class="sxs-lookup"><span data-stu-id="874f7-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="874f7-144">Prilikom pisanja izlazne vrijednosti procjenjivanja u kodu možete prenijeti izlazun vrijednost na putanju unutar *registriranog spremišta podataka* u radnom prostoru.</span><span class="sxs-lookup"><span data-stu-id="874f7-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="874f7-145">Ako su putanja i spremište podataka parametrizirani u cjevovodu, uvidi o klijenatima moći će čitati i uvesti izlaznu vrijednost zaključka.</span><span class="sxs-lookup"><span data-stu-id="874f7-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="874f7-146">Trenutačno je podržana jedna tablična izlazna vrijednost u formatu csv.</span><span class="sxs-lookup"><span data-stu-id="874f7-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="874f7-147">Putanja mora sadržavati direktorij i naziv datoteke.</span><span class="sxs-lookup"><span data-stu-id="874f7-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]