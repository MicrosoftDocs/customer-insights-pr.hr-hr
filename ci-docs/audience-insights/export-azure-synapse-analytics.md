---
title: Izvoz podataka iz Customer Insights u Analitiku servisa Azure Synapse
description: Saznajte kako konfigurirati vezu s Analitikom servisa Azure Synapse.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977368"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="85040-103">Izvoz podataka u Analitiku servisa Azure Synapse (Pretpregled)</span><span class="sxs-lookup"><span data-stu-id="85040-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="85040-104">Azure Synapse je analitička usluga koja ubrzava vrijeme za uvid u skladišta podataka i sustave velikih podataka.</span><span class="sxs-lookup"><span data-stu-id="85040-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="85040-105">Svoje Customer Insights podatke možete unijeti i upotrijebiti u servisu [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="85040-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85040-106">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="85040-106">Prerequisites</span></span>

<span data-ttu-id="85040-107">Za konfiguriranje veze od usluge Customer Insights do Azure Synapse moraju biti ispunjeni sljedeći preduvjeti.</span><span class="sxs-lookup"><span data-stu-id="85040-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="85040-108">Obavezno postavite sve **dodjele uloga** kako je opisano.</span><span class="sxs-lookup"><span data-stu-id="85040-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="85040-109">Preduvjeti u usluzi Customer Insights</span><span class="sxs-lookup"><span data-stu-id="85040-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="85040-110">Imate ulogu **Administrator** u uvidima u ciljne skupine.</span><span class="sxs-lookup"><span data-stu-id="85040-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="85040-111">Dodatne informacije o [postavljanju korisničkih dozvola u uvidima u ciljne skupine](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="85040-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="85040-112">U servisu Azure:</span><span class="sxs-lookup"><span data-stu-id="85040-112">In Azure:</span></span> 

- <span data-ttu-id="85040-113">Aktivna pretplata na Azure.</span><span class="sxs-lookup"><span data-stu-id="85040-113">An active Azure subscription.</span></span>

- <span data-ttu-id="85040-114">Ako koristite račun za novi Azure Data Lake Storage druge generacije, *upravitelj servisa za uvide u ciljne skupine* treba dozvole **Suradnik za podatke blobova pohrane**.</span><span class="sxs-lookup"><span data-stu-id="85040-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="85040-115">Saznajte više o [povezivanju na račun Azure Data Lake Storage druge generacije s upraviteljem usluge Azure za uvide u ciljne skupine](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="85040-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="85040-116">Data Lake Storage druge generacije **mora imati** omogućeno [hijerarhijsko polje imena](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="85040-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="85040-117">U grupi resursa u kojoj se nalazi radni prostor servisa Azure Synapse, *upravitelju usluge* i *korisniku za uvide u ciljne skupine* treba dodijeliti barem dozvole **Čitatelj**.</span><span class="sxs-lookup"><span data-stu-id="85040-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="85040-118">Dodatne informacije potražite u odjeljku [Dodjela uloga servisa Azure pomoću portala Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="85040-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="85040-119">*Korisnik* treba dozvole **Suradnik za podatke blobova pohrane** na računu Azure Data Lake Storage druge generacije na kojem su podaci smješteni i povezani s radnim prostorom servisa Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="85040-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="85040-120">Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="85040-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="85040-121">*[Identitet kojim upravlja radni prostor servisa Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* treba dozvole **Suradnik za podatke blobova pohrane** na računu Azure Data Lake Storage druge generacije na kojem su podaci smješteni i povezani s radnim prostorom servisa Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="85040-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="85040-122">Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="85040-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="85040-123">U radnom prostoru servisa Azure Synapse, *upravitelj usluge za uvide u ciljne skupine* treba dodijeljenu ulogu **Administrator za Synapse**.</span><span class="sxs-lookup"><span data-stu-id="85040-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="85040-124">Dodatne informacije potražite u odjeljku [Kako postaviti kontrolu pristupa za vaš radni prostor servisa Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="85040-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="85040-125">Postavljanje veze i izvoz u Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="85040-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="85040-126">Konfiguracija veze</span><span class="sxs-lookup"><span data-stu-id="85040-126">Configure a connection</span></span>

1. <span data-ttu-id="85040-127">Idite na **Admin** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="85040-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="85040-128">Odaberite **Dodaj vezu** i odaberite **Analitika servisa Azure Synapse** ili odaberite **Postavi** na pločici **Analitika servisa Azure Synapse** za konfiguriranje veze.</span><span class="sxs-lookup"><span data-stu-id="85040-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="85040-129">Dodijelite vezi prepoznatljivi naziv u polju Zaslonski naziv.</span><span class="sxs-lookup"><span data-stu-id="85040-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="85040-130">Naziv i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="85040-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="85040-131">Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="85040-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="85040-132">Odaberite tko može se može koristiti vezom.</span><span class="sxs-lookup"><span data-stu-id="85040-132">Choose who can use this connection.</span></span> <span data-ttu-id="85040-133">Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="85040-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="85040-134">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="85040-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="85040-135">Odaberite ili potražite pretplatu u kojoj želite koristiti podatke Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="85040-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="85040-136">Čim se odabere pretplata, možete odabrati i **Radni prostor**, **Račun za pohranu** i **Spremnik**.</span><span class="sxs-lookup"><span data-stu-id="85040-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="85040-137">Odaberite **Spremi** da biste spremili vezu.</span><span class="sxs-lookup"><span data-stu-id="85040-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="85040-138">Konfiguracija izvoza</span><span class="sxs-lookup"><span data-stu-id="85040-138">Configure an export</span></span>

<span data-ttu-id="85040-139">Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="85040-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="85040-140">Dodatne informacije potražite u odjeljku [dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="85040-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="85040-141">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="85040-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="85040-142">Da biste stvorili novi izvoz, ddaberite **Dodaj izvoz**.</span><span class="sxs-lookup"><span data-stu-id="85040-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="85040-143">U polju **Veza za izvoz** odaberite vezu iz odjeljka **Analitika servisa Azure Synapse**.</span><span class="sxs-lookup"><span data-stu-id="85040-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="85040-144">Ako ne vidite naziv ovog odjeljka, nema dostupnih [veza](connections.md) ove vrste.</span><span class="sxs-lookup"><span data-stu-id="85040-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="85040-145">Navedite prepoznatljiv **zaslonski naziv** za vaš izvoz i **naziv baze podataka**.</span><span class="sxs-lookup"><span data-stu-id="85040-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="85040-146">Odaberite koje entitete želite izvesti u Analitiku servisa Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="85040-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="85040-147">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="85040-147">Select **Save**.</span></span>

<span data-ttu-id="85040-148">Spremanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="85040-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="85040-149">Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="85040-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="85040-150">Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="85040-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="85040-151">Ažuriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="85040-151">Update an export</span></span>

1. <span data-ttu-id="85040-152">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="85040-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="85040-153">Odaberite **Uredi** na izvozu koji želite ažurirati.</span><span class="sxs-lookup"><span data-stu-id="85040-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="85040-154">**Dodajte** ili **uklonite** entitete iz odabira.</span><span class="sxs-lookup"><span data-stu-id="85040-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="85040-155">Ako se entiteti uklone iz odabira, neće se izbrisati iz baze podataka analitike servisa Synapse.</span><span class="sxs-lookup"><span data-stu-id="85040-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="85040-156">Međutim, buduća osvježavanja podataka neće ažurirati uklonjene entitete u toj bazi podataka.</span><span class="sxs-lookup"><span data-stu-id="85040-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="85040-157">**Promjena naziva baze podataka** stvara novu bazu podataka analitike servisa Synapse.</span><span class="sxs-lookup"><span data-stu-id="85040-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="85040-158">Baza podataka s nazivom koji je ranije konfiguriran neće primati ažuriranja u budućim osvježavanjima.</span><span class="sxs-lookup"><span data-stu-id="85040-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
