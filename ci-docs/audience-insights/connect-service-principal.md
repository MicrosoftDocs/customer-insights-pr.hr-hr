---
title: Povezivanje se s računom za Azure Data Lake Storage Gen2 s upraviteljem servisa
description: koristite upravitelja servisa Azure za uvide ciljne skupine da biste se povezali s vlastitim podatkovnim jezerom kada ga priključite uvidima ciljne skupine.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644079"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="e627a-103">Povezivanje na račun servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure za uvide ciljne skupine</span><span class="sxs-lookup"><span data-stu-id="e627a-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="e627a-104">Automatizirani alati koji koriste servise Azure uvijek bi trebali imati ograničene dozvole.</span><span class="sxs-lookup"><span data-stu-id="e627a-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="e627a-105">Umjesto da se aplikacije prijavljuju kao potpuno privilegirani korisnik, Azure nudi upravitelje servisa.</span><span class="sxs-lookup"><span data-stu-id="e627a-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="e627a-106">Pročitajte kako biste saznali kako povezati uvide ciljne skupine s računom za Azure Data Lake Storage Gen2 koji koristi upravitelja servisa Azure umjesto ključeva računa za pohranu.</span><span class="sxs-lookup"><span data-stu-id="e627a-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="e627a-107">Upravitelja servisa možete koristiti za sigurno [dodavanje ili uređivanje mape Common Data Model kao izvor podataka](connect-common-data-model.md) ili [stvaranje novog ili ažuriranje postojećeg okruženja](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="e627a-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="e627a-108">Za izradu upravitelja servisa trebaju vam administratorske dozvole za vašu pretplatu na Azure.</span><span class="sxs-lookup"><span data-stu-id="e627a-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="e627a-109">Stvaranje upravitelja servisa Azure za uvide ciljne skupine</span><span class="sxs-lookup"><span data-stu-id="e627a-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="e627a-110">Prije stvaranja novog upravitelja usluge za uvide ciljne skupine provjerite postoji li već u vašoj organizaciji.</span><span class="sxs-lookup"><span data-stu-id="e627a-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="e627a-111">Traženje postojećeg upravitelja servisa</span><span class="sxs-lookup"><span data-stu-id="e627a-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="e627a-112">Idite na [administracijski portal za Azure](https://portal.azure.com) i prijavite se u svoju organizaciju.</span><span class="sxs-lookup"><span data-stu-id="e627a-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="e627a-113">Među servisima Azure odaberite **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="e627a-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="e627a-114">Pod stavkom **Upravljanje** odaberite **Enterprise Applications**.</span><span class="sxs-lookup"><span data-stu-id="e627a-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="e627a-115">Potražite ID aplikacije prve strane `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` za uvide ciljne skupine ili naziv `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="e627a-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="e627a-116">Ako pronađete odgovarajući zapis, to znači da postoji upravitelj servisa za uvide ciljne skupine.</span><span class="sxs-lookup"><span data-stu-id="e627a-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="e627a-117">Ne morate ga ponovno stvoriti.</span><span class="sxs-lookup"><span data-stu-id="e627a-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snimka zaslona na kojoj se prikazuje postojeći upravitelj servisa.":::
   
6. <span data-ttu-id="e627a-119">Ako se ne dobiju rezultati, stvorite novog upravitelja servisa.</span><span class="sxs-lookup"><span data-stu-id="e627a-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="e627a-120">Stvaranje novog upravitelja servisa</span><span class="sxs-lookup"><span data-stu-id="e627a-120">Create a new service principal</span></span>

1. <span data-ttu-id="e627a-121">Instalirajte najnoviju verziju **Azure Active Directory PowerShell za graf**.</span><span class="sxs-lookup"><span data-stu-id="e627a-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="e627a-122">Za više informacija pogledajte [Instalacija Azure Active Directory PowerShell za graf](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="e627a-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="e627a-123">Na računalu na tipkovnici odaberite tipku Windows pa potražite **Windows PowerShell** i **Pokreni kao administrator**.</span><span class="sxs-lookup"><span data-stu-id="e627a-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="e627a-124">U prozoru PowerShell koji se otvori unesite `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="e627a-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="e627a-125">Stvorite upravitelja servisa za uvide ciljne skupine s Azure AD PowerShell modulom.</span><span class="sxs-lookup"><span data-stu-id="e627a-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="e627a-126">U prozoru PowerShell unesite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="e627a-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="e627a-127">Zamijenite "your tenant ID" stvarnim ID-om svog klijenta na kojem želite stvoriti upravitelja servisa.</span><span class="sxs-lookup"><span data-stu-id="e627a-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="e627a-128">Parametar naziva okruženja `AzureEnvironmentName` nije obvezan.</span><span class="sxs-lookup"><span data-stu-id="e627a-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="e627a-129">Unesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="e627a-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="e627a-130">Ova naredba stvara upravitelja usluge za uvide ciljne skupne na odabranom klijentu.</span><span class="sxs-lookup"><span data-stu-id="e627a-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="e627a-131">Dodjela dozvola za pristup računu za pohranu upravitelju usluge</span><span class="sxs-lookup"><span data-stu-id="e627a-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="e627a-132">Idite na Azure portal kako biste dodijelili dozvole upravitelju serviss za račun pohrane koji želite koristiti u uvidima ciljne skupine.</span><span class="sxs-lookup"><span data-stu-id="e627a-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="e627a-133">Idite na [administracijski portal za Azure](https://portal.azure.com) i prijavite se u svoju organizaciju.</span><span class="sxs-lookup"><span data-stu-id="e627a-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="e627a-134">Otvorite račun za pohranu kojem želite da ima pristup upravitelj servisa za uvide ciljne skupine.</span><span class="sxs-lookup"><span data-stu-id="e627a-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="e627a-135">Odaberite **Kontrola pristupa (IAM)** u navigacijskom oknu pa odaberite **Dodaj** > **Dodaj dodjelu uloge**.</span><span class="sxs-lookup"><span data-stu-id="e627a-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snimka zaslona na kojoj se prikazuje Azure portal tijekom dodavanja dodjele uloge.":::
   
1. <span data-ttu-id="e627a-137">U oknu **Dodavanje dodjele uloge** postavite sljedeća svojstva:</span><span class="sxs-lookup"><span data-stu-id="e627a-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="e627a-138">Uloga: *Suradnik spremišta podataka za blob*</span><span class="sxs-lookup"><span data-stu-id="e627a-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="e627a-139">Dodijelite pristup: *Korisnik, grupa ili upravitelj servisa*</span><span class="sxs-lookup"><span data-stu-id="e627a-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="e627a-140">Odaberite: *Dynamics 365 AI za Customer Insights* ([upravitelja servisa kojeg ste stvorili](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="e627a-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="e627a-141">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="e627a-141">Select **Save**.</span></span>

<span data-ttu-id="e627a-142">Provedba izmjena može potrajati i do 15 minuta.</span><span class="sxs-lookup"><span data-stu-id="e627a-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="e627a-143">Unesite ID Azure resursa ili pojedinosti o pretplati na Azure u prilogu računa za pohranu servisa Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="e627a-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="e627a-144">Priložite račun za Azure Data Lake Storage u uvide ciljne skupine radi [pohrane izlaznih podataka](manage-environments.md) ili [za upotrebu kao izvora podataka](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="e627a-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="e627a-145">Odabirom opcije Azure Data Lake omogućuje vam se odabir između pristupa temeljenog na resursima ili na pretplati.</span><span class="sxs-lookup"><span data-stu-id="e627a-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="e627a-146">Slijedite korake u nastavku kako biste pružili potrebne informacije o odabranom pristupu.</span><span class="sxs-lookup"><span data-stu-id="e627a-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="e627a-147">Veza računa utemeljena na resursima</span><span class="sxs-lookup"><span data-stu-id="e627a-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="e627a-148">Idite na [Azure administrativni portal](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite račun za pohranu.</span><span class="sxs-lookup"><span data-stu-id="e627a-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="e627a-149">Idite na **Postavke** > **Svojstva** na navigacijskom oknu.</span><span class="sxs-lookup"><span data-stu-id="e627a-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="e627a-150">Kopirajte vrijednost ID-a resursa računa za pohranu.</span><span class="sxs-lookup"><span data-stu-id="e627a-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopirajte ID resursa računa za pohranu.":::

1. <span data-ttu-id="e627a-152">U uvidima ciljne skupine umetnite ID resursa u polje resursa prikazano na zaslonu veze računa za pohranu.</span><span class="sxs-lookup"><span data-stu-id="e627a-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Unesite podatke ID-a resursa računa za pohranu.":::   
   
1. <span data-ttu-id="e627a-154">Nastavite s preostalim koracima u uvidima ciljne skupine da biste priložili račun za pohranu.</span><span class="sxs-lookup"><span data-stu-id="e627a-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="e627a-155">Veza računa utemeljena na pretplati</span><span class="sxs-lookup"><span data-stu-id="e627a-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="e627a-156">Idite na [Azure administrativni portal](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite račun za pohranu.</span><span class="sxs-lookup"><span data-stu-id="e627a-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="e627a-157">Idite na **Postavke** > **Svojstva** na navigacijskom oknu.</span><span class="sxs-lookup"><span data-stu-id="e627a-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="e627a-158">Pregledajte **Pretplatu**, **Grupu resursa** i **Naziv** računa za pohranu kako biste bili sigurni da ste odabrali prave vrijednosti u uvidima ciljne skupine.</span><span class="sxs-lookup"><span data-stu-id="e627a-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="e627a-159">U uvidima ciljne skupine odaberite vrijednosti ili za odgovarajuća polja prilikom prilaganja računa za pohranu.</span><span class="sxs-lookup"><span data-stu-id="e627a-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Unesite podatke ID-a resursa računa za pohranu.":::
   
1. <span data-ttu-id="e627a-161">Nastavite s preostalim koracima u uvidima ciljne skupine da biste priložili račun za pohranu.</span><span class="sxs-lookup"><span data-stu-id="e627a-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
