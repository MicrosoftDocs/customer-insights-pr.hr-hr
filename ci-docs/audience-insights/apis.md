---
title: Rad s API-jima
description: Koristite API-je i shvatite ograničenja.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304733"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="d19e2-103">Rad s API-jima Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d19e2-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="d19e2-104">Dynamics 365 Customer Insights pruža API-je za izradu vlastitih aplikacija na temelju vaših podataka u značajci Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d19e2-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d19e2-105">Pojedinosti o tim API-jima navedeni su u [Referenci za API-je za Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="d19e2-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="d19e2-106">Oni uključuju dodatne informacije o operacijama, parametrima i odgovorima.</span><span class="sxs-lookup"><span data-stu-id="d19e2-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="d19e2-107">Ovaj članak opisuje kako pristupiti API-jima značajke Customer Insights, stvoriti registraciju za Azure aplikaciju i započeti s dostupnim bibliotekama klijenta.</span><span class="sxs-lookup"><span data-stu-id="d19e2-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="d19e2-108">Početak s isprobavanjem API-ja za Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d19e2-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="d19e2-109">[Prijavite se](https://home.ci.ai.dynamics.com) u Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d19e2-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="d19e2-110">Ako još nemate pretplatu, [prijavite se za probnu verziju Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="d19e2-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="d19e2-111">Da biste omogućili API-je u svom okruženju Customer Insights, idite na **Administrator** > **Dozvole**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="d19e2-112">Za to će vam trebati administratorske dozvole.</span><span class="sxs-lookup"><span data-stu-id="d19e2-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="d19e2-113">Idite na karticu **API-ji** pa odaberite gumb **Omogući**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="d19e2-114">Omogućavanjem API-ja stvara se primarni i sekundarni ključ pretplate za vašu instancu koji se koristi u zahtjevima API-ja.</span><span class="sxs-lookup"><span data-stu-id="d19e2-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="d19e2-115">Ključeve možete ponovno generirati odabirom **Ponovno generiraj primarni** ili **Ponovno generiraj sekundarni** na **Administrator** > **Dozvole** > **API-ji**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Omogućavanje API-jeva za Customer Insights":::

1. <span data-ttu-id="d19e2-117">Odaberite **Istražite naše API-je** da [isprobate API-je](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="d19e2-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="d19e2-118">Odaberite operaciju API-ja pa odaberite **Isprobaj**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="d19e2-119">U bočnom oknu vrijednost na padajućem izborniku **Autorizacija** postavite na **implicitna**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="d19e2-120">Zaglavlje `Authorization` dodaje se tokenom nositelja.</span><span class="sxs-lookup"><span data-stu-id="d19e2-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="d19e2-121">Vaš ključ pretplate automatski će se popuniti.</span><span class="sxs-lookup"><span data-stu-id="d19e2-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="d19e2-122">Po želji dodajte sve potrebne parametre upita.</span><span class="sxs-lookup"><span data-stu-id="d19e2-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="d19e2-123">Pomaknite se do dna bočnog okna pa odaberite **Pošalji**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="d19e2-124">HTTP odgovor uskoro će se pojaviti u nastavku.</span><span class="sxs-lookup"><span data-stu-id="d19e2-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="Kako testirati API-je.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="d19e2-126">Stvaranje nove registracije aplikacije na Azure portalu</span><span class="sxs-lookup"><span data-stu-id="d19e2-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="d19e2-127">Ovi vam koraci pomažu u početku korištenja API-ja značajke Customer Insights u Azure aplikaciji pomoću delegiranih dozvola.</span><span class="sxs-lookup"><span data-stu-id="d19e2-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="d19e2-128">Obavezno prvo popunite [odjeljak Početak](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="d19e2-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="d19e2-129">Prijavite se na [Azure portal](https://portal.azure.com) s računom koji može pristupiti podacima Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d19e2-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="d19e2-130">S lijeve strane odaberite **Registracije aplikacija**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="d19e2-131">Odaberite **Nova registracija**, navedite naziv aplikacije pa odaberite vrstu računa.</span><span class="sxs-lookup"><span data-stu-id="d19e2-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="d19e2-132">Ako želite, dodajte URL preusmjeravanja.</span><span class="sxs-lookup"><span data-stu-id="d19e2-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="d19e2-133">http://localhost dovoljan je za razvoj aplikacije na vašem lokalnom računalu.</span><span class="sxs-lookup"><span data-stu-id="d19e2-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="d19e2-134">Na novoj registraciji aplikacije idite na **Dozvole API-ja**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Kako postaviti dopuštenja API-ja u Registraciji aplikacija.":::

1. <span data-ttu-id="d19e2-136">Odaberite **Dodaj dozvolu** pa odaberite **Customer Insights** u bočnom oknu.</span><span class="sxs-lookup"><span data-stu-id="d19e2-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="d19e2-137">Za opciju **Vrsta dozvole** odaberite **Delegirane dozvole**, a zatim odaberite dozvolu **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="d19e2-138">Odaberite **Dodaj dozvole**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-138">Select **Add permissions**.</span></span> <span data-ttu-id="d19e2-139">Ako trebate pristupiti API-ju bez prijave korisnika, pregledajte odjeljak [Dozvole aplikacija s poslužitelja na poslužitelj](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="d19e2-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="d19e2-140">Odaberite **Daj pristanak administratora za...** da biste dovršili registraciju aplikacije.</span><span class="sxs-lookup"><span data-stu-id="d19e2-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="d19e2-141">Možete koristiti ID aplikacije/klijenta za registraciju ove aplikacije u Microsoftovoj biblioteci za provjeru autentičnosti (MSAL) da biste dobili token nositelja koji će se s vašim zahtjevom poslati API-ju.</span><span class="sxs-lookup"><span data-stu-id="d19e2-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Kako odobriti pristanak administratora.":::

<span data-ttu-id="d19e2-143">Za više informacija o MSAL-u pogledajte [Pregled Microsoftove biblioteke za provjeru autentičnosti (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="d19e2-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="d19e2-144">Za više informacija o registraciji aplikacija na platformi Azure pogledajte [Registracija aplikacije](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span><span class="sxs-lookup"><span data-stu-id="d19e2-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="d19e2-145">Za informacije o korištenju API-ja u našim klijentskim bibliotekama pogledajte [Klijentske bliblioteke značajke Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="d19e2-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="d19e2-146">Dozvole aplikacije s poslužitelja na poslužitelj</span><span class="sxs-lookup"><span data-stu-id="d19e2-146">Server-to-server application permissions</span></span>

<span data-ttu-id="d19e2-147">U [odjeljku za registraciju aplikacije](#create-a-new-app-registration-in-the-azure-portal) opisuje se kako registrirati aplikaciju koja zahtijeva da se korisnik prijavi radi provjere autentičnosti.</span><span class="sxs-lookup"><span data-stu-id="d19e2-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="d19e2-148">Saznajte kako stvoriti registraciju aplikacije koja ne treba interakciju korisnika i može se pokrenuti na poslužitelju.</span><span class="sxs-lookup"><span data-stu-id="d19e2-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="d19e2-149">Na registraciji svoje aplikacije na Azure portalu idite na **Dozvole API-ja**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="d19e2-150">Odaberite **Dodaj dozvolu**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="d19e2-151">Odaberite karticu **API-ji koje koristi moja tvrtka ili ustanova** pa s popisa odaberite **Dynamics 365 AI za Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="d19e2-152">Za opciju **Vrsta dozvole** odaberite **Dozvole aplikacije**, a zatim odaberite dozvolu **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="d19e2-153">Odaberite **Dodaj dozvole**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="d19e2-154">Vratite se na **Dozvole API-ja** za registraciju svoje aplikacije.</span><span class="sxs-lookup"><span data-stu-id="d19e2-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="d19e2-155">Odaberite **Daj pristanak administratora za...** da biste dovršili registraciju aplikacije.</span><span class="sxs-lookup"><span data-stu-id="d19e2-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Kako odobriti pristanak administratora.":::

1. <span data-ttu-id="d19e2-157">Da zaključimo, moramo dodati naziv registracije aplikacije kao korisnika u Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d19e2-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="d19e2-158">Otvorite Customer Insights, idite na **Administrator** > **Dozvole** pa odaberite **Dodaj korisnika**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="d19e2-159">Potražite naziv registracije svoje aplikacije, odaberite ga iz rezultata pretraživanja pa odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="d19e2-160">Klijentske biblioteke Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d19e2-160">Customer Insights client libraries</span></span>

<span data-ttu-id="d19e2-161">Ovaj vam odjeljak pomaže u početku korištenja klijentskih knjižnica dostupnih za API-je Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d19e2-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="d19e2-162">Svi izvorni kodovi biblioteke i ogledne aplikacije mogu se naći na [stranici servisa GitHub za Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="d19e2-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="d19e2-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="d19e2-163">C# NuGet</span></span>

<span data-ttu-id="d19e2-164">Naučite kako započeti s korištenjem klijentskih biblioteka za C# s NuGet.org. Za više informacija o paketu NuGet pogledajte [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="d19e2-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="d19e2-165">Trenutačno ovaj paket cilja okvire netstandard2.0 i netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="d19e2-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="d19e2-166">Dodavanje klijentske biblioteke za C# projektu u C#</span><span class="sxs-lookup"><span data-stu-id="d19e2-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="d19e2-167">U Visual Studio otvorite **Upravitelj paketa NuGet** za svoj projekt.</span><span class="sxs-lookup"><span data-stu-id="d19e2-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="d19e2-168">Potražite **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="d19e2-169">Odaberite **Instaliraj** za dodavanje paketa u projekt.</span><span class="sxs-lookup"><span data-stu-id="d19e2-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="d19e2-170">Alternativno, pokrenite ovu naredbu u **Konzoli upravitelja paketa NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="d19e2-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Dodavanje NuGet paketa Visual Studio projektu":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="d19e2-172">Korištenje klijentske biblioteke za C#</span><span class="sxs-lookup"><span data-stu-id="d19e2-172">Use the C# client library</span></span>

1. <span data-ttu-id="d19e2-173">Koristite [Microsoftovu biblioteku za provjeru autentičnosti (MSAL)](/azure/active-directory/develop/msal-overview) da biste dobili `AccessToken` koristeći svoju postojeću [Registraciju Azure aplikacije](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="d19e2-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="d19e2-174">Nakon uspješne autentifikacije i stjecanja tokena, izgradite novi ili upotrijebite postojeći `HttpClient` s dodatnim **DefaultRequestHeaders "Authorization"** postavljenim na **Nositelj <access token>** i **Ocp-Apim-Subscription-Key** postavljenim na [**ključ pretplate** iz svog okruženja Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="d19e2-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="d19e2-175">Po potrebi resetirajte zaglavlje **Authorization**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="d19e2-176">Primjerice, kada token istekne.</span><span class="sxs-lookup"><span data-stu-id="d19e2-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="d19e2-177">Proslijedite ovaj `HttpClient` u izgradnju klijenta `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="d19e2-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Ogledni httpclient":::

1. <span data-ttu-id="d19e2-179">Uputite pozive s klijentom na „metode produženja“, primjerice `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="d19e2-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="d19e2-180">Ako se preferira pristup temeljnom `Microsoft.Rest.HttpOperationResponse`, upotrijebite "metode poruka http", primjerice `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="d19e2-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="d19e2-181">Odgovor će vjerojatno biti vrste `object` jer metoda može vratiti više vrsta (primjerice `IList<InstanceInfo>` i `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="d19e2-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="d19e2-182">Da biste provjerili vrstu povrata, možete sigurno pretvoriti objekte u vrste odgovora navedene na [stranica s pojedinostima API-ja](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) za tu operaciju.</span><span class="sxs-lookup"><span data-stu-id="d19e2-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="d19e2-183">Ako su potrebne dodatne informacije o zahtjevu, upotrijebite **http metode poruka** za pristup neobrađenom objektu odgovora.</span><span class="sxs-lookup"><span data-stu-id="d19e2-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="d19e2-184">Paket NodeJS</span><span class="sxs-lookup"><span data-stu-id="d19e2-184">NodeJS package</span></span>

<span data-ttu-id="d19e2-185">Upotrijebite klijentske biblioteke NodeJS dostupne putem NPM-a: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="d19e2-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="d19e2-186">Paket Python</span><span class="sxs-lookup"><span data-stu-id="d19e2-186">Python package</span></span>

<span data-ttu-id="d19e2-187">Upotrijebite klijentske biblioteke Python dostupne putem PyPi-ja: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="d19e2-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
