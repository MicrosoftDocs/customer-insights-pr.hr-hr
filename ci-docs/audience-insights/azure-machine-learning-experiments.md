---
title: Eksperimenti Strojnog učenja Azure
description: Koristite modele utemeljene na Strojnom učenju Azure sustavu Dynamics 365 Customer Insights.
ms.date: 12/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e37eec503c9df83ef72497e22afa1266296e642c
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881729"
---
# <a name="use-azure-machine-learning-based-models"></a>Korištenje modela utemeljenih na Strojnom učenju Azure

Objedinjeni podaci u sustavu Dynamics 365 Customer Insights izvor su za izgradnju modela strojnog učenja koji mogu stvoriti dodatne poslovne uvide. Customer Insights integrira se sa Strojnim učenjem Azure da biste mogli koristiti vlastite prilagođene modele.

## <a name="prerequisites"></a>Preduvjeti

- Pristup značajci Customer Insights
- Aktivna pretplata za Azure Enterprise
- [Objedinjeni profili klijenata](data-unification.md)
- [Izvoz entiteta u Pohranu blobova platforme Azure](export-azure-blob-storage.md) konfiguriran

## <a name="set-up-azure-machine-learning-workspace"></a>Postavljanje radnog prostora Strojnog učenja Azure

1. Pogledajte članak [Stvaranje radnog prostora Strojnog učenja Azure](/azure/machine-learning/concept-workspace#-create-a-workspace) za različite opcije za stvaranje radnog prostora. Za najbolje performanse stvorite radni prostor u Azure regiji koja je geografski najbliža vašem okruženju Customer Insights.

1. Pristupite svom radnom prostoru putem programa [Azure Machine Learning Studio](https://ml.azure.com/). Ima nekoliko [načina interakcije](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) sa svojim radnim prostorom.

## <a name="work-with-azure-machine-learning-designer"></a>Rad s dizajnerom za Strojno učenje Azure

Azure Strojno učenje designer pruža vizualno platno na kojem možete povlačiti i ispuštati skupove podataka i module. Skupni cjevovod stvoren u dizajneru može se integrirati u Customer Insights ako je odgovarajuće konfiguriran. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Rad s SDK-om za Strojno učenje Azure

Podatkovni znanstvenici i programeri za umjetnu inteligenciju koriste [SDK za Strojno učenje Azure](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) za izgradnju Strojno učenje tijekova rada. Trenutačno se modeli obučeni pomoću SDK-a ne mogu izravno integrirati u Customer Insights. Skupni cjevovod za procjenjivanje koji troši taj model potreban je za integraciju sa servisom Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Zahtjevi za integraciju skupnog cjevovoda sa servisom Customer Insights

### <a name="dataset-configuration"></a>Konfiguracija skupa podataka

Morate stvoriti skupove podataka da biste koristili podatke entiteta iz servisa Customer Insights za svoj skupni cjevovod za procjenjivanje. Te skupove podataka treba registrirati u radnom prostoru. Trenutačno podržavamo samo [tablične skupove podataka](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) u formatu .csv. Skupovi podataka koji odgovaraju podacima entiteta moraju se parametrizirati kao parametar cjevovoda.
   
* Parametri skupa podataka u Dizajneru
   
     U dizajneru, otvorite **Odabir stupaca u skupu podataka** pa odaberite **Postavi kao parametar cjevovoda** gdje ćete navesti naziv parametra.

     > [!div class="mx-imgBorder"]
     > ![Parametarizacija skupa podataka u dizajneru.](media/intelligence-designer-dataset-parameters.png "Parametrizacija skupa podataka u dizajneru")
   
* Parametar skupa podataka u SDK-u (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Skupni cjevovod za procjenjivanje
  
* U dizajneru se cjevovod za obuku može koristiti za stvaranje ili ažuriranje cjevovoda za procjenjivanje. Trenutačno su podržani samo skupni cjevovodi za procjenjivanje.

* Pomoću SDK-a cjevovod možete objaviti na krajnjoj točki. Trenutačno se Customer Insights integrira sa zadanim cjevovodom na krajnjoj točki skupnog cjevovoda u radnom prostoru Strojnog učenja.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Uvoz podataka cjevovoda u Customer Insights

* Dizajner pruža [Modul za izvoz podataka](/azure/machine-learning/algorithm-module-reference/export-data) koji omogućuje izvoz izlaznih podataka cjevovoda u pohranu platforme Azure. Modul trenutačno mora koristiti vrstu spremišta podataka **Pohrana blobova platforme Azure** i parameterizirati **Spremište podataka** i relativnu **Putanju**. Customer Insights nadjačava oba ova parametra tijekom izvođenja cjevovoda sa spremištem podataka i putanjom koja je dostupna proizvodu.
   > [!div class="mx-imgBorder"]
   > ![Konfiguracija modula za izvoz podataka.](media/intelligence-designer-importdata.png "Konfiguracija modula za izvoz podataka")
   
* Prilikom pisanja izlazne vrijednosti procjenjivanja u kodu možete prenijeti izlazun vrijednost na putanju unutar *registriranog spremišta podataka* u radnom prostoru. Ako su putanja i spremište podataka parametrizirani u cjevovodu, uvidi o klijenatima moći će čitati i uvesti izlaznu vrijednost zaključka. Trenutačno je podržana jedna tablična izlazna vrijednost u formatu csv. Putanja mora sadržavati direktorij i naziv datoteke.

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