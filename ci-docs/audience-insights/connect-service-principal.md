---
title: Povezivanje se s računom za Azure Data Lake Storage Gen2 s upraviteljem servisa
description: Koristite upravitelja servisa Azure za uvide u ciljnu skupinu da biste se povezali s vlastitim data lake kada ga priključite uvidima u ciljnu skupinu.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267713"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="4006f-103">Povezivanje na račun servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure za uvide ciljne skupine</span><span class="sxs-lookup"><span data-stu-id="4006f-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="4006f-104">Automatizirani alati koji koriste servise Azure uvijek bi trebali imati ograničene dozvole.</span><span class="sxs-lookup"><span data-stu-id="4006f-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="4006f-105">Umjesto da se aplikacije prijavljuju kao potpuno privilegirani korisnik, Azure nudi upravitelje servisa.</span><span class="sxs-lookup"><span data-stu-id="4006f-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="4006f-106">Pročitajte kako biste saznali kako povezati uvide ciljne skupine s računom za Azure Data Lake Storage Gen2 koji koristi upravitelja servisa Azure umjesto ključeva računa za pohranu.</span><span class="sxs-lookup"><span data-stu-id="4006f-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="4006f-107">Upravitelja servisa možete koristiti za sigurno [dodavanje ili uređivanje mape Common Data Model kao izvor podataka](connect-common-data-model.md) ili [stvaranje novog ili ažuriranje postojećeg okruženja](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="4006f-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="4006f-108">Račun za pohranu Azure Data Lake druge generacije koji namjerava koristiti upravitelja servisa mora imati [Hijerarhijski prostor naziva (HNS) omogućen](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="4006f-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="4006f-109">Za izradu upravitelja servisa trebaju vam administratorske dozvole za vašu pretplatu na Azure.</span><span class="sxs-lookup"><span data-stu-id="4006f-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="4006f-110">Stvaranje upravitelja servisa Azure za uvide ciljne skupine</span><span class="sxs-lookup"><span data-stu-id="4006f-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="4006f-111">Prije stvaranja novog upravitelja usluge za uvide ciljne skupine provjerite postoji li već u vašoj organizaciji.</span><span class="sxs-lookup"><span data-stu-id="4006f-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="4006f-112">Traženje postojećeg upravitelja servisa</span><span class="sxs-lookup"><span data-stu-id="4006f-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="4006f-113">Idite na [administracijski portal za Azure](https://portal.azure.com) i prijavite se u svoju organizaciju.</span><span class="sxs-lookup"><span data-stu-id="4006f-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="4006f-114">Među servisima Azure odaberite **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="4006f-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="4006f-115">Pod stavkom **Upravljanje** odaberite **Enterprise Applications**.</span><span class="sxs-lookup"><span data-stu-id="4006f-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="4006f-116">Potražite ID aplikacije prve strane `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` za uvide ciljne skupine ili naziv `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="4006f-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="4006f-117">Ako pronađete odgovarajući zapis, to znači da postoji upravitelj servisa za uvide ciljne skupine.</span><span class="sxs-lookup"><span data-stu-id="4006f-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="4006f-118">Ne morate ga ponovno stvoriti.</span><span class="sxs-lookup"><span data-stu-id="4006f-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snimka zaslona na kojoj se prikazuje postojeći upravitelj servisa.":::
   
6. <span data-ttu-id="4006f-120">Ako se ne dobiju rezultati, stvorite novog upravitelja servisa.</span><span class="sxs-lookup"><span data-stu-id="4006f-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="4006f-121">Stvaranje novog upravitelja servisa</span><span class="sxs-lookup"><span data-stu-id="4006f-121">Create a new service principal</span></span>

1. <span data-ttu-id="4006f-122">Instalirajte najnoviju verziju **Azure Active Directory PowerShell za graf**.</span><span class="sxs-lookup"><span data-stu-id="4006f-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="4006f-123">Za više informacija pogledajte [Instalacija Azure Active Directory PowerShell za graf](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="4006f-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="4006f-124">Na računalu na tipkovnici odaberite tipku Windows pa potražite **Windows PowerShell** i **Pokreni kao administrator**.</span><span class="sxs-lookup"><span data-stu-id="4006f-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="4006f-125">U prozoru PowerShell koji se otvori unesite `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="4006f-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="4006f-126">Stvorite upravitelja servisa za uvide ciljne skupine s Azure AD PowerShell modulom.</span><span class="sxs-lookup"><span data-stu-id="4006f-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="4006f-127">U prozoru PowerShell unesite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="4006f-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="4006f-128">Zamijenite "your tenant ID" stvarnim ID-om svog klijenta na kojem želite stvoriti upravitelja servisa.</span><span class="sxs-lookup"><span data-stu-id="4006f-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="4006f-129">Parametar naziva okruženja `AzureEnvironmentName` nije obvezan.</span><span class="sxs-lookup"><span data-stu-id="4006f-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="4006f-130">Unesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="4006f-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="4006f-131">Ova naredba stvara upravitelja usluge za uvide ciljne skupne na odabranom klijentu.</span><span class="sxs-lookup"><span data-stu-id="4006f-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="4006f-132">Dodjela dozvola za pristup računu za pohranu upravitelju usluge</span><span class="sxs-lookup"><span data-stu-id="4006f-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="4006f-133">Idite na Azure portal kako biste dodijelili dozvole upravitelju serviss za račun pohrane koji želite koristiti u uvidima ciljne skupine.</span><span class="sxs-lookup"><span data-stu-id="4006f-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="4006f-134">Idite na [administracijski portal za Azure](https://portal.azure.com) i prijavite se u svoju organizaciju.</span><span class="sxs-lookup"><span data-stu-id="4006f-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="4006f-135">Otvorite račun za pohranu kojem želite da ima pristup upravitelj servisa za uvide ciljne skupine.</span><span class="sxs-lookup"><span data-stu-id="4006f-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="4006f-136">Odaberite **Kontrola pristupa (IAM)** u navigacijskom oknu pa odaberite **Dodaj** > **Dodaj dodjelu uloge**.</span><span class="sxs-lookup"><span data-stu-id="4006f-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snimka zaslona na kojoj se prikazuje Azure portal tijekom dodavanja dodjele uloge.":::
   
1. <span data-ttu-id="4006f-138">U oknu **Dodavanje dodjele uloge** postavite sljedeća svojstva:</span><span class="sxs-lookup"><span data-stu-id="4006f-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="4006f-139">Uloga: *Suradnik spremišta podataka za blob*</span><span class="sxs-lookup"><span data-stu-id="4006f-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="4006f-140">Dodijelite pristup: *Korisnik, grupa ili upravitelj servisa*</span><span class="sxs-lookup"><span data-stu-id="4006f-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="4006f-141">Odaberite: *Dynamics 365 AI za Customer Insights* ([upravitelja servisa kojeg ste stvorili](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="4006f-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="4006f-142">Odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="4006f-142">Select **Save**.</span></span>

<span data-ttu-id="4006f-143">Provedba izmjena može potrajati i do 15 minuta.</span><span class="sxs-lookup"><span data-stu-id="4006f-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="4006f-144">Unesite ID Azure resursa ili pojedinosti o pretplati na Azure u prilogu računa za pohranu servisa Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="4006f-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="4006f-145">Priložite račun za Azure Data Lake Storage u uvide ciljne skupine radi [pohrane izlaznih podataka](manage-environments.md) ili [za upotrebu kao izvora podataka](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="4006f-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="4006f-146">Odabirom opcije Azure Data Lake omogućuje vam se odabir između pristupa temeljenog na resursima ili na pretplati.</span><span class="sxs-lookup"><span data-stu-id="4006f-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="4006f-147">Slijedite korake u nastavku kako biste pružili potrebne informacije o odabranom pristupu.</span><span class="sxs-lookup"><span data-stu-id="4006f-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="4006f-148">Veza računa pohrane temeljena na resursima</span><span class="sxs-lookup"><span data-stu-id="4006f-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="4006f-149">Idite na [Azure administrativni portal](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite račun za pohranu.</span><span class="sxs-lookup"><span data-stu-id="4006f-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="4006f-150">Idite na **Postavke** > **Svojstva** na navigacijskom oknu.</span><span class="sxs-lookup"><span data-stu-id="4006f-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="4006f-151">Kopirajte vrijednost ID-a resursa računa za pohranu.</span><span class="sxs-lookup"><span data-stu-id="4006f-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopirajte ID resursa računa za pohranu.":::

1. <span data-ttu-id="4006f-153">U uvidima ciljne skupine umetnite ID resursa u polje resursa prikazano na zaslonu veze računa za pohranu.</span><span class="sxs-lookup"><span data-stu-id="4006f-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Unesite podatke ID-a resursa računa za pohranu.":::   
   
1. <span data-ttu-id="4006f-155">Nastavite s preostalim koracima u uvidima ciljne skupine da biste priložili račun za pohranu.</span><span class="sxs-lookup"><span data-stu-id="4006f-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="4006f-156">Veza računa utemeljena na pretplati</span><span class="sxs-lookup"><span data-stu-id="4006f-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="4006f-157">Idite na [Azure administrativni portal](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite račun za pohranu.</span><span class="sxs-lookup"><span data-stu-id="4006f-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="4006f-158">Idite na **Postavke** > **Svojstva** na navigacijskom oknu.</span><span class="sxs-lookup"><span data-stu-id="4006f-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="4006f-159">Pregledajte **Pretplatu**, **Grupu resursa** i **Naziv** računa za pohranu kako biste bili sigurni da ste odabrali prave vrijednosti u uvidima ciljne skupine.</span><span class="sxs-lookup"><span data-stu-id="4006f-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="4006f-160">U uvidima ciljne skupine odaberite vrijednosti ili za odgovarajuća polja prilikom prilaganja računa za pohranu.</span><span class="sxs-lookup"><span data-stu-id="4006f-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="4006f-161">Nastavite s preostalim koracima u uvidima ciljne skupine da biste priložili račun za pohranu.</span><span class="sxs-lookup"><span data-stu-id="4006f-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]