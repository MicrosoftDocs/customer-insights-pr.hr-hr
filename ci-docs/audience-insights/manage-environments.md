---
title: Izrada okruženja i upravljanje njima
description: Saznajte kako se prijaviti za uslugu i kako upravljati okruženjima.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270103"
---
# <a name="manage-environments"></a><span data-ttu-id="3a30d-103">Upravljanje okruženjima</span><span class="sxs-lookup"><span data-stu-id="3a30d-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3a30d-104">Ovaj članak objašnjava kako stvoriti novu tvrtku ili ustanovu i kako pripremiti okruženje.</span><span class="sxs-lookup"><span data-stu-id="3a30d-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="3a30d-105">Prijavite se i stvorite tvrtku ili ustanovu</span><span class="sxs-lookup"><span data-stu-id="3a30d-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="3a30d-106">Idi na web-mjesto aplikacije [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="3a30d-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="3a30d-107">Odaberite **Početak rada**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="3a30d-108">Odaberite željeni scenarij prijave i odgovarajuću vezu.</span><span class="sxs-lookup"><span data-stu-id="3a30d-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="3a30d-109">Prihvatite uvjete i odredbe te odaberite **Nastavi** kako biste započeli stvaranje tvrtke ili ustanove.</span><span class="sxs-lookup"><span data-stu-id="3a30d-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="3a30d-110">Nakon stvaranja okruženja bit ćete preusmjereni na aplikaciju [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="3a30d-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="3a30d-111">Koristite demo okruženje da biste istražili aplikaciju ili stvorite novo okruženje slijedeći korake iz sljedećeg odjeljka.</span><span class="sxs-lookup"><span data-stu-id="3a30d-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="3a30d-112">Nakon što odredite postavke okruženja, odaberite **Stvaranje**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="3a30d-113">Bit ćete prijavljeni nakon što je okruženje uspješno stvoreno.</span><span class="sxs-lookup"><span data-stu-id="3a30d-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="3a30d-114">Stvaranje okruženja u postojećoj tvrtki ili ustanovi</span><span class="sxs-lookup"><span data-stu-id="3a30d-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="3a30d-115">Novo okruženje moguće je stvoriti na dva načina.</span><span class="sxs-lookup"><span data-stu-id="3a30d-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="3a30d-116">Možete odrediti potpuno novu konfiguraciju ili kopirati neke postavke konfiguracije iz postojećeg okruženja.</span><span class="sxs-lookup"><span data-stu-id="3a30d-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="3a30d-117">Da biste stvorili okruženje:</span><span class="sxs-lookup"><span data-stu-id="3a30d-117">To create an environment:</span></span>

1. <span data-ttu-id="3a30d-118">Odaberite birač **Okruženja** u zaglavlju aplikacije.</span><span class="sxs-lookup"><span data-stu-id="3a30d-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="3a30d-119">Odaberite **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a30d-120">![Postavke okruženja](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="3a30d-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="3a30d-121">U dijaloškom okviru **Stvori novo okruženje** odaberite **Novo okruženje**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="3a30d-122">Ako želite [kopirati podatke iz trenutačnog okruženja](#additional-considerations-for-copy-configuration-preview), odaberite mogućnnost **Kopiraj iz postojećeg okruženja**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="3a30d-123">Vidjet ćete popis svih dostupnih okruženja u svojoj tvrtki ili ustanovi iz kojih možete kopirati podatke.</span><span class="sxs-lookup"><span data-stu-id="3a30d-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="3a30d-124">Navedite sljedeće pojedinosti:</span><span class="sxs-lookup"><span data-stu-id="3a30d-124">Provide the following details:</span></span>
   - <span data-ttu-id="3a30d-125">**Naziv**: Naziv za ovo okruženje.</span><span class="sxs-lookup"><span data-stu-id="3a30d-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="3a30d-126">Ovo je polje već popunjeno ako ste kopirali iz postojećeg okruženja, ali to možete promijeniti.</span><span class="sxs-lookup"><span data-stu-id="3a30d-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="3a30d-127">**Regija**: Regija u kojoj je usluga uvedena i udomaćena.</span><span class="sxs-lookup"><span data-stu-id="3a30d-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="3a30d-128">**Tip**: Odaberite želite li stvoriti proizvodno okruženje ili okruženje sigurnosne ograde.</span><span class="sxs-lookup"><span data-stu-id="3a30d-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="3a30d-129">Po želji, možete odabrati **Napredne postavke**:</span><span class="sxs-lookup"><span data-stu-id="3a30d-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="3a30d-130">**Spremi sve podatke u**: Određuje gdje želite pohraniti izlazne podatke generirane iz aplikacije Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3a30d-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="3a30d-131">Imat ćete dvije mogućnosti: **Pohrana aplikacije Customer Insights** (pohrana Azure Data Lake kojom upravlja tim za Customer Insights) i **Azure Data Lake Storage Gen2** (vaša vlastita pohrana Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="3a30d-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="3a30d-132">Prema zadanome je odabrana mogućnost pohrane aplikacije Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3a30d-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3a30d-133">Pohranjivanjem podataka u Azure Data Lake Storage slažete se s prijenosom podataka na odgovarajuću geografsku lokaciju za taj račun za pohranu za Azure te s njihovom pohranom na toj lokaciji. Ta lokacija može se razlikovati od lokacije za pohranu podataka u aplikaciji Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3a30d-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="3a30d-134">Saznajte više u Microsoftom centru za pouzdanost.</span><span class="sxs-lookup"><span data-stu-id="3a30d-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="3a30d-135">Trenutno se korišteni entiteti uvijek pohranjuju u rješenju Data Lake kojim upravlja Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3a30d-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="3a30d-136">Podržavamo samo račune za pohranu Azure Data Lake Gen2 iz iste Azure regije koju ste odabrali prilikom stvaranja okruženja.</span><span class="sxs-lookup"><span data-stu-id="3a30d-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="3a30d-137">Podržavamo samo račune za pohranu Azure Data Lake Gen2 s omogućenom značajkom hijerarhijskog prostora za naziv (HNS).</span><span class="sxs-lookup"><span data-stu-id="3a30d-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="3a30d-138">Za mogućnost Azure Data Lake Storage Gen2 možete birati između mogućnosti koja se temelji na resursima i mogućnosti koja se temelji na pretplati za provjeru autentičnosti.</span><span class="sxs-lookup"><span data-stu-id="3a30d-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="3a30d-139">Za više informacija pogledajte [Povezivanje uvida ciljne skupine s računom servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="3a30d-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="3a30d-140">Naziv **spremnika** ne može se promijeniti i bit će „customerinsights”.</span><span class="sxs-lookup"><span data-stu-id="3a30d-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="3a30d-141">Ako želite koristiti [predviđanja](predictions.md) ili konfigurirati dijeljenje podataka s aplikacijama i rješenjima na temelju Microsoft Dataverse, navedite URL okruženja Microsoft Dataverse pod **Konfiguriraj dijeljenje podataka pomoću Microsoft Dataverse i omogući dodatne mogućnosti**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="3a30d-142">Odaberite **Omogući dijeljenje podataka** za dijeljenje izlaznih podataka usluge Customer Insights pomoću Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="3a30d-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="3a30d-143">Dijeljenje podataka pomoću Microsoft Dataverse Managed Data Lake trenutno nije podržano kada sve podatke spremite u vlastiti Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="3a30d-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="3a30d-144">[Predviđanje vrijednosti koje nedostaju u entitetu](predictions.md) trenutno nije podržano kada omogućite dijeljenje podataka pomoću Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="3a30d-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="3a30d-145">![Mogućnosti konfiguracije za omogućavanje dijeljenja podataka pomoću Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="3a30d-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="3a30d-146">Kada pokrenete procese, kao što su obrada podataka ili stvaranje segmenta, na računu za pohranu koji ste gore odredili stvorit će se odgovarajuće mape.</span><span class="sxs-lookup"><span data-stu-id="3a30d-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="3a30d-147">Stvorit će se podatkovne datoteke i datoteke model.json i dodati u odgovarajuće podmape na temelju procesa koji pokrećete.</span><span class="sxs-lookup"><span data-stu-id="3a30d-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="3a30d-148">Ako stvorite više okruženja značajke Customer Insights i odaberete spremiti izlazne entitete iz tih okruženja na svoj račun za pohranu, za svako će se okruženje stvoriti zasebne mape s ci_<environmentid> u spremniku.</span><span class="sxs-lookup"><span data-stu-id="3a30d-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="3a30d-149">Dodatna razmatranja o konfiguraciji kopije (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="3a30d-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="3a30d-150">Kopirane su sljedeće postavke konfiguracije:</span><span class="sxs-lookup"><span data-stu-id="3a30d-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="3a30d-151">Najvažnije konfiguracije</span><span class="sxs-lookup"><span data-stu-id="3a30d-151">Feature configurations</span></span>
- <span data-ttu-id="3a30d-152">Uneseni/uvezeni izvori podataka</span><span class="sxs-lookup"><span data-stu-id="3a30d-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="3a30d-153">Konfiguracija objedinjavanja podataka (mapiranje, podudaranje, spajanje)</span><span class="sxs-lookup"><span data-stu-id="3a30d-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="3a30d-154">Segmenti</span><span class="sxs-lookup"><span data-stu-id="3a30d-154">Segments</span></span>
- <span data-ttu-id="3a30d-155">Mjerila</span><span class="sxs-lookup"><span data-stu-id="3a30d-155">Measures</span></span>
- <span data-ttu-id="3a30d-156">Odnosi</span><span class="sxs-lookup"><span data-stu-id="3a30d-156">Relationships</span></span>
- <span data-ttu-id="3a30d-157">Aktivnosti</span><span class="sxs-lookup"><span data-stu-id="3a30d-157">Activities</span></span>
- <span data-ttu-id="3a30d-158">Pretraži i filtriraj indeks</span><span class="sxs-lookup"><span data-stu-id="3a30d-158">Search & filter Index</span></span>
- <span data-ttu-id="3a30d-159">Odredišta izvoza</span><span class="sxs-lookup"><span data-stu-id="3a30d-159">Export destinations</span></span>
- <span data-ttu-id="3a30d-160">Zakazano osvježavanje</span><span class="sxs-lookup"><span data-stu-id="3a30d-160">Scheduled refresh</span></span>
- <span data-ttu-id="3a30d-161">Obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="3a30d-161">Enrichments</span></span>
- <span data-ttu-id="3a30d-162">Upravljanje modelom</span><span class="sxs-lookup"><span data-stu-id="3a30d-162">Model management</span></span>
- <span data-ttu-id="3a30d-163">Dodjele uloga</span><span class="sxs-lookup"><span data-stu-id="3a30d-163">Role assignments</span></span>

<span data-ttu-id="3a30d-164">Sljedeće postavke *nisu* kopirane:</span><span class="sxs-lookup"><span data-stu-id="3a30d-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="3a30d-165">Profili klijenata.</span><span class="sxs-lookup"><span data-stu-id="3a30d-165">Customer profiles.</span></span>
- <span data-ttu-id="3a30d-166">Vjerodajnice izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="3a30d-166">Data source credentials.</span></span> <span data-ttu-id="3a30d-167">Morat ćete navesti vjerodajnice za svaki izvor podataka i ručno osvježiti izvore podataka.</span><span class="sxs-lookup"><span data-stu-id="3a30d-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="3a30d-168">Izvori podataka iz mape Common Data Model i jezera za upravljanje Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3a30d-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="3a30d-169">Te izvore podataka morat ćete stvoriti ručno s istim nazivom kao u izvornom okruženju.</span><span class="sxs-lookup"><span data-stu-id="3a30d-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="3a30d-170">Kad kopirate okruženje, vidjet ćete potvrdnu poruku da je stvoreno novo okruženje.</span><span class="sxs-lookup"><span data-stu-id="3a30d-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="3a30d-171">Odaberite **Idi na izvore podataka** da biste vidjeli popis izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="3a30d-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="3a30d-172">Svi će izvori podataka prikazati status **Potrebne su vjerodajnice**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="3a30d-173">Uredite izvore podataka i unesite vjerodajnice kako biste ih osvježili.</span><span class="sxs-lookup"><span data-stu-id="3a30d-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3a30d-174">![Kopirani izvori podataka](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="3a30d-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="3a30d-175">Nakon osvježenja izvora podataka, idite na **Podaci** > **Objedini**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="3a30d-176">Ovdje ćete pronaći postavke iz izvornog okruženja.</span><span class="sxs-lookup"><span data-stu-id="3a30d-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="3a30d-177">Uredite ih po potrebi ili odaberite **Pokreni** za pokretanje postupka objedinjavanja podataka i stvaranje jedinstvenog entiteta klijenta.</span><span class="sxs-lookup"><span data-stu-id="3a30d-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="3a30d-178">Nakon završetka objedinjavanja podataka idite na **Mjere** i **Segmenti** da ih osvježite.</span><span class="sxs-lookup"><span data-stu-id="3a30d-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="3a30d-179">Uređivanje postojećeg okruženja</span><span class="sxs-lookup"><span data-stu-id="3a30d-179">Edit an existing environment</span></span>

<span data-ttu-id="3a30d-180">Možete urediti neke pojedinosti postojećih okruženja.</span><span class="sxs-lookup"><span data-stu-id="3a30d-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="3a30d-181">Odaberite birač **Okruženja** u zaglavlju aplikacije.</span><span class="sxs-lookup"><span data-stu-id="3a30d-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="3a30d-182">Odaberite ikonu **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="3a30d-183">U okviru **Uredi okruženje** možete ažurirati **Zaslonski naziv** okruženja, ali ne možete promijeniti svojstva **Regija** ili **Vrsta**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="3a30d-184">Ako je okruženje konfigurirano za pohranu podataka u pohrani Azure Data Lake Storage Gen2, možete ažurirati **Ključ računa**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="3a30d-185">Međutim, ne možete promijeniti **Naziv računa** ili naziv **Spremnik**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="3a30d-186">Ako želite, možete ažurirati vezu koja se temelji na ključu računa na vezu koja se temelji na resursima ili pretplati.</span><span class="sxs-lookup"><span data-stu-id="3a30d-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="3a30d-187">Nakon nadogradnje i nakon ažuriranja ne možete se vratiti na prethodni ključ računa.</span><span class="sxs-lookup"><span data-stu-id="3a30d-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="3a30d-188">Za više informacija pogledajte [Povezivanje uvida ciljne skupine s računom servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="3a30d-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="3a30d-189">Ne možete promijeniti podatke za **Spremnik** prilikom ažuriranja veze.</span><span class="sxs-lookup"><span data-stu-id="3a30d-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="3a30d-190">Ponovno postavljanje postojećeg okruženja</span><span class="sxs-lookup"><span data-stu-id="3a30d-190">Reset an existing environment</span></span>

<span data-ttu-id="3a30d-191">Kao administrator možete ponovno postaviti okruženje u prazno stanje ako želite izbrisati sve konfiguracije i ukloniti unesene podatke.</span><span class="sxs-lookup"><span data-stu-id="3a30d-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="3a30d-192">Odaberite birač **Okruženja** u zaglavlju aplikacije.</span><span class="sxs-lookup"><span data-stu-id="3a30d-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="3a30d-193">Odaberite okruženje koje želite ponovno postaviti i odaberite trotočje **...**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="3a30d-194">Odaberite mogućnost **Ponovno postavi**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="3a30d-195">Da biste potvrdili brisanje, unesite naziv okruženja i odaberite **Ponovno postavi**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="3a30d-196">Brisanje postojećeg okruženja (dostupno samo za administratore)</span><span class="sxs-lookup"><span data-stu-id="3a30d-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="3a30d-197">Kao administrator možete izbrisati okruženje koje administrirate.</span><span class="sxs-lookup"><span data-stu-id="3a30d-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="3a30d-198">Odaberite birač **Okruženja** u zaglavlju aplikacije.</span><span class="sxs-lookup"><span data-stu-id="3a30d-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="3a30d-199">Odaberite okruženje koje želite ponovno postaviti i odaberite trotočje **...**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="3a30d-200">Odaberite mogućnost **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="3a30d-201">Da biste potvrdili brisanje, unesite naziv okruženja i odaberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="3a30d-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]