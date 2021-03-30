---
title: Povezivanje podataka oblika Common Data Model s računom servisa Azure Data Lake
description: Rad s podacima oblika Common Data Model pomoću servisa Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596536"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="aaef5-103">Povezivanje s mapom značajke Common Data Model s pomoću računa za Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="aaef5-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="aaef5-104">Ovaj članak pruža informacije o unosu podataka iz mape Common Data Model pomoću vašeg računa servisa Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="aaef5-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="aaef5-105">Važne stavke</span><span class="sxs-lookup"><span data-stu-id="aaef5-105">Important considerations</span></span>

- <span data-ttu-id="aaef5-106">Podaci u Azure Data Lake trebaju slijediti standard Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="aaef5-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="aaef5-107">Ostali formati trenutno nisu podržani.</span><span class="sxs-lookup"><span data-stu-id="aaef5-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="aaef5-108">Unos podataka podržava isključivo račune servis za pohranu Azure Data Lake *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="aaef5-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="aaef5-109">Ne možete koristiti račune za pohranu servisa Azure Data Lake Gen1 za unos podataka.</span><span class="sxs-lookup"><span data-stu-id="aaef5-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="aaef5-110">Da biste provjerili autentičnost s upraviteljem servisa Azure, provjerite je li konfiguriran na vašem klijentu.</span><span class="sxs-lookup"><span data-stu-id="aaef5-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="aaef5-111">Za više informacija pogledajte [Povezivanje uvida ciljne skupine s računom servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="aaef5-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="aaef5-112">Azure Data Lake s kojim se želite povezati i s kojeg želite unositi podatke mora biti u istoj regiji platforme Azure kao i okruženje Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="aaef5-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="aaef5-113">Veze s mapom Common Data Model iz podatkovnog jezera u drugoj Azure regiji nisu podržane.</span><span class="sxs-lookup"><span data-stu-id="aaef5-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="aaef5-114">Da biste znali koja je Azure regija okruženja, idite na **Administrator** > **Sustav** > **O sustavu** u uvidima ciljne skupine.</span><span class="sxs-lookup"><span data-stu-id="aaef5-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="aaef5-115">Podaci pohranjeni na mrežnim servisima mogu se pohraniti na lokaciji koje se razlikuje od lokacije na kojoj se obrađuju ili pohranjuju u značajci Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="aaef5-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="aaef5-116"> Uvozom ili povezivanjem s podacima pohranjenima u internetskim servisima slažete se da se podaci mogu prenijeti i pohraniti sa sustavom Dynamics 365 Customer Insights. [Saznajte više u programu Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="aaef5-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="aaef5-117">Spojite se na mapu Common Data Model</span><span class="sxs-lookup"><span data-stu-id="aaef5-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="aaef5-118">U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="aaef5-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="aaef5-119">Odaberite **Dodaj izvor podataka**.</span><span class="sxs-lookup"><span data-stu-id="aaef5-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="aaef5-120">Odaberie **Poveži se s mapom Common Data Model**, unesite **Naziv** za izvor podataka pa odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="aaef5-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="aaef5-121">Imenujte smjernice:</span><span class="sxs-lookup"><span data-stu-id="aaef5-121">Name guidelines:</span></span> 
   - <span data-ttu-id="aaef5-122">Započnite slovom.</span><span class="sxs-lookup"><span data-stu-id="aaef5-122">Start with a letter.</span></span>
   - <span data-ttu-id="aaef5-123">Koristite samo slova i brojeve.</span><span class="sxs-lookup"><span data-stu-id="aaef5-123">Use letters and numbers only.</span></span> <span data-ttu-id="aaef5-124">Nisu dopušteni posebni znakovi i razmaci.</span><span class="sxs-lookup"><span data-stu-id="aaef5-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="aaef5-125">Koristite između 3 i 64 znaka.</span><span class="sxs-lookup"><span data-stu-id="aaef5-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="aaef5-126">Možete birati između korištenja mogućnosti koja se temelji na resursima i mogućnosti koja se temelji na pretplati za provjeru autentičnosti.</span><span class="sxs-lookup"><span data-stu-id="aaef5-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="aaef5-127">Za više informacija pogledajte [Povezivanje uvida ciljne skupine s računom servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="aaef5-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="aaef5-128">Unesite podatke za **Spremnik** pa odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="aaef5-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aaef5-129">![Dijaloški okvir za unos novih pojedinosti o vezi za Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="aaef5-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="aaef5-130">Potrebna vam je jedna od sljedećih uloga u gore navedenom spremniku ili računu za pohranu da biste se mogli povezati i stvoriti izvor podataka:</span><span class="sxs-lookup"><span data-stu-id="aaef5-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="aaef5-131">Čitač podataka bloba pohrane</span><span class="sxs-lookup"><span data-stu-id="aaef5-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="aaef5-132">Vlasnik podataka bloba pohrane</span><span class="sxs-lookup"><span data-stu-id="aaef5-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="aaef5-133">Suradnik podataka bloba pohrane</span><span class="sxs-lookup"><span data-stu-id="aaef5-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="aaef5-134">U dijaloškom okviru **Odaberi mapu Common Data Model** odaberite datoteku model.json ili manifest.json iz koje želite uvesti podatke pa odaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="aaef5-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="aaef5-135">Nijedna datoteka model.json ili manifest.json povezana s drugim izvorom podataka u okruženju neće se prikazati na popisu.</span><span class="sxs-lookup"><span data-stu-id="aaef5-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="aaef5-136">Dobit ćete popis dostupnih entiteta u odabranoj datoteci model.json ili manifest.json.</span><span class="sxs-lookup"><span data-stu-id="aaef5-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="aaef5-137">Možete pregledati i odabrati neki s popisa dostupnih entiteta i odabrati **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="aaef5-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="aaef5-138">Svi odabrani entiteti unijet će se iz novog izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="aaef5-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aaef5-139">![Dijaloški okvir s popisom entiteta iz datoteke model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="aaef5-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="aaef5-140">Navedite za koje entitete podataka želite omogućiti profiliranje podataka pa odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="aaef5-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="aaef5-141">Profiliranje podataka omogućuje analitiku i druge mogućnosti.</span><span class="sxs-lookup"><span data-stu-id="aaef5-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="aaef5-142">Možete odabrati cijeli entitet koji odabire sve atribute iz entiteta ili odabrati određene atribute po svom izboru.</span><span class="sxs-lookup"><span data-stu-id="aaef5-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="aaef5-143">Prema zadanim postavkama nijedan entitet nije omogućen za profiliranje podataka.</span><span class="sxs-lookup"><span data-stu-id="aaef5-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aaef5-144">![Dijaloški okvir u kojem se prikazuje profiliranje podataka](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="aaef5-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="aaef5-145">Nakon spremanja odabira otvara se stranica **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="aaef5-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="aaef5-146">Sada biste trebali vidjeti vezu mape Common Data Model kao izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="aaef5-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="aaef5-147">Datoteke model.json ili manifest.json mogu se povezati samo s jednim izvorom podataka u istom okruženju.</span><span class="sxs-lookup"><span data-stu-id="aaef5-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="aaef5-148">Međutim, ista datoteka model.json ili manifest.json može se koristiti za izvore podataka u više okruženja.</span><span class="sxs-lookup"><span data-stu-id="aaef5-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="aaef5-149">Uređivanje izvora podataka mape Common Data Model</span><span class="sxs-lookup"><span data-stu-id="aaef5-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="aaef5-150">Možete ažurirati pristupni ključ za račun pohrane koji sadrži mapu Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="aaef5-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="aaef5-151">Možete i promijeniti datoteke model.json ili manifest.json.</span><span class="sxs-lookup"><span data-stu-id="aaef5-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="aaef5-152">Da biste se povezali sa spremnikom drugačijim od računa za pohranu ili promijenili naziv računa, [stvorite novu vezu izvora podataka](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="aaef5-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="aaef5-153">U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="aaef5-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="aaef5-154">Pored izvora podataka koji želite ažurirati odaberite elipsu.</span><span class="sxs-lookup"><span data-stu-id="aaef5-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="aaef5-155">S popisa odaberite mogućnost **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="aaef5-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="aaef5-156">Ako želite ažurirajte **Pristupni ključ** i odaberite **Sljedeće**.</span><span class="sxs-lookup"><span data-stu-id="aaef5-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dijaloški okvir za uređivanje i ažuriranje pristupnog ključa za postojeći izvor podataka](media/edit-access-key.png)

5. <span data-ttu-id="aaef5-158">Ako želite, možete ažurirati s veze ključa računa na vezu koja se temelji na resursima ili pretplati.</span><span class="sxs-lookup"><span data-stu-id="aaef5-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="aaef5-159">Za više informacija pogledajte [Povezivanje uvida ciljne skupine s računom servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="aaef5-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="aaef5-160">Ne možete promijeniti podatke za **Spremnik** prilikom ažuriranja veze.</span><span class="sxs-lookup"><span data-stu-id="aaef5-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Dijaloški okvir za unos pojedinosti o vezi za Azure Data Lake na postojeći račun za pohranu](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="aaef5-162">Potrebna vam je jedna od sljedećih uloga u gore navedenom spremniku ili računu za pohranu da biste se mogli povezati i stvoriti izvor podataka:</span><span class="sxs-lookup"><span data-stu-id="aaef5-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="aaef5-163">Čitač podataka bloba pohrane</span><span class="sxs-lookup"><span data-stu-id="aaef5-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="aaef5-164">Vlasnik podataka bloba pohrane</span><span class="sxs-lookup"><span data-stu-id="aaef5-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="aaef5-165">Suradnik podataka bloba pohrane</span><span class="sxs-lookup"><span data-stu-id="aaef5-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="aaef5-166">Neobavezno odaberite drugu datoteku model.json ili manifest.json s različitim skupom entiteta iz spremnika.</span><span class="sxs-lookup"><span data-stu-id="aaef5-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="aaef5-167">Po želji možete odabrati dodatne entitete za unos.</span><span class="sxs-lookup"><span data-stu-id="aaef5-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="aaef5-168">Također, možete ukloniti sve već odabrane entitete ako nema ovisnosti.</span><span class="sxs-lookup"><span data-stu-id="aaef5-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="aaef5-169">Ako postoje ovisnosti o postojećoj datoteci model.json ili manifest.json i skupu entiteta, vidjet ćete poruku o pogrešci i ne možete odabrati drugu datoteku model.json ili manifest.json.</span><span class="sxs-lookup"><span data-stu-id="aaef5-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="aaef5-170">Uklonite te ovisnosti prije promjene datoteke model.json ili manifest.json ili stvorite novi izvor podataka s datotekom model.json ili manifest.json koju želite koristiti da biste izbjegli uklanjanje ovisnosti.</span><span class="sxs-lookup"><span data-stu-id="aaef5-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="aaef5-171">Po želji možete odabrati dodatne atribute ili entitete kako biste omogućili profiliranje podataka ili onemogućili već odabrane.</span><span class="sxs-lookup"><span data-stu-id="aaef5-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]