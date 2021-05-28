---
title: Dodatak kartice klijenta za aplikacije Dynamics 365
description: Pomoću ovog dodatka prikažite podatke iz uvida u ciljne skupine u aplikacijama Dynamics 365.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059579"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="e7413-103">Dodatak kartice klijenta (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="e7413-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e7413-104">Dobijte prikaz svojih klijenata od 360 stupnjeva izravno u Dynamics 365 aplikacijama.</span><span class="sxs-lookup"><span data-stu-id="e7413-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="e7413-105">Pomoću dodatka kartice klijenta instaliranog u podržanoj aplikaciji Dynamics 365 možete odabrati prikaz demografskih podataka, uvida i vremenskih traka aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="e7413-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="e7413-106">Dodatak će dohvatiti podatke iz usluge Customer Insights bez utjecaja na podatke u povezanoj aplikaciji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e7413-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e7413-107">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="e7413-107">Prerequisites</span></span>

- <span data-ttu-id="e7413-108">Dodatak funkcionira samo s aplikacijama Dynamics 365 stvorenim prema modelu, kao što su Sales ili Customer Service verzije 9.0 i novije.</span><span class="sxs-lookup"><span data-stu-id="e7413-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="e7413-109">Da bi se vaši podaci sustava Dynamics 365 preslikali u profile klijenata uvida u ciljne skupine, moraju se [unijeti iz aplikacije Dynamics 365 pomoću poveznika Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e7413-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="e7413-110">Svi korisnici sustava Dynamics 365 za dodatak kartice klijenta moraju se [dodati kao korisnici](permissions.md) u uvidima u ciljne skupine da bi vidjeli podatke.</span><span class="sxs-lookup"><span data-stu-id="e7413-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="e7413-111">[Konfigurirane mogućnosti pretraživanja i filtriranja](search-filter-index.md) u uvidima u ciljne skupine su potrebne za funkcioniranje pretraživanja podataka.</span><span class="sxs-lookup"><span data-stu-id="e7413-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="e7413-112">Svaka kontrola dodatka oslanja se na određene podatke u uvidima u ciljne skupine:</span><span class="sxs-lookup"><span data-stu-id="e7413-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="e7413-113">Kontrola mjerenja: Zahtijeva [konfigurirana mjerenja](measures.md).</span><span class="sxs-lookup"><span data-stu-id="e7413-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="e7413-114">Kontrola inteligencije: zahtijeva podatke stvorene pomoću [predviđanja](predictions.md) ili [prilagođenih modela](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="e7413-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="e7413-115">Kontrola demografije: demografska polja (kao što su dob ili spola) dostupna su u objedinjenom profilu klijenta.</span><span class="sxs-lookup"><span data-stu-id="e7413-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="e7413-116">Kontrola obogaćivanja: Zahtijeva aktivna [obogaćivanja](enrichment-hub.md) primijenjena na profile klijenata.</span><span class="sxs-lookup"><span data-stu-id="e7413-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="e7413-117">Kontrola vremenske trake: Zahtijeva [konfigurirane aktivnosti](activities.md).</span><span class="sxs-lookup"><span data-stu-id="e7413-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="e7413-118">Instaliranje dodatka za korisničku karticu</span><span class="sxs-lookup"><span data-stu-id="e7413-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="e7413-119">Dodatak za korisničku karticu rješenje je za aplikacije Customer Engagement u programu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e7413-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="e7413-120">Da biste instalirali rješenje, idite na AppSource i potražite **Kartica klijenta Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="e7413-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="e7413-121">Odaberite [Dodatak kartice klijenta na AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i odaberite **Nabavi odmah**.</span><span class="sxs-lookup"><span data-stu-id="e7413-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="e7413-122">Možda ćete se trebati prijaviti s vjerodajnicama svog administratora za aplikaciju Dynamics 365 da biste postavili rješenje.</span><span class="sxs-lookup"><span data-stu-id="e7413-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="e7413-123">Možda će biti potrebno neko vrijeme da se rješenje instalira u vaše okruženje.</span><span class="sxs-lookup"><span data-stu-id="e7413-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="e7413-124">Konfiguriranje dodatka kartice klijenta</span><span class="sxs-lookup"><span data-stu-id="e7413-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="e7413-125">Kao administrator, idite na dio **Postavke** u aplikaciji Dynamics 365 i odaberite **Rješenja**.</span><span class="sxs-lookup"><span data-stu-id="e7413-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="e7413-126">Odaberite vezu **Naziv zaslona** za rješenje **Dynamics 365 Customer Insights dodatak kartice klijenta (pretpregled)**.</span><span class="sxs-lookup"><span data-stu-id="e7413-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7413-127">![Odabir zaslonskog naziva](media/select-display-name.png "Odabir zaslonskog naziva")</span><span class="sxs-lookup"><span data-stu-id="e7413-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="e7413-128">Odaberite **Prijavi se** i unesite vjerodajnice za administratorski račun koji koristite za konfiguriranje aplikacije Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e7413-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e7413-129">Provjerite blokira li blokator skočnih prozora preglednika prozor za provjeru autentičnosti kada odaberete gumb **Prijavi se**.</span><span class="sxs-lookup"><span data-stu-id="e7413-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="e7413-130">Odaberite okruženje usluge Customer Insights iz kojeg želite dohvatiti podatke.</span><span class="sxs-lookup"><span data-stu-id="e7413-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="e7413-131">Definirajte preslikavanje polja u zapise u aplikaciji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e7413-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="e7413-132">Ovisno o vašim podacima u usluzi Customer Insights, možete odabrati preslikavanje sljedećih mogućnosti:</span><span class="sxs-lookup"><span data-stu-id="e7413-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="e7413-133">Za mapiranje s kontaktom odaberite polje u entitetu Kupac koje se podudara s ID-om entiteta vašeg kontakta.</span><span class="sxs-lookup"><span data-stu-id="e7413-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="e7413-134">Za mapiranje računom odaberite polje u entitetu Kupac koje se podudara s ID-om entiteta vašeg računa.</span><span class="sxs-lookup"><span data-stu-id="e7413-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7413-135">![Polje za ID kontakta](media/contact-id-field.png "Polje za ID kontakta")</span><span class="sxs-lookup"><span data-stu-id="e7413-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="e7413-136">Odaberite **Spremi konfiguraciju** da biste spremili postavke.</span><span class="sxs-lookup"><span data-stu-id="e7413-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="e7413-137">Zatim trebate dodijeliti sigurnosne uloge u sustavu Dynamics 365 da bi korisnici mogli prilagoditi i vidjeti karticu klijenta.</span><span class="sxs-lookup"><span data-stu-id="e7413-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="e7413-138">U sustavu Dynamics 365 idite na **Postavke** > **Sigurnost** > **Korisnici**.</span><span class="sxs-lookup"><span data-stu-id="e7413-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="e7413-139">Odaberite korisnike da biste uredili uloge korisnika i odaberite **Upravljaj ulogama**.</span><span class="sxs-lookup"><span data-stu-id="e7413-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="e7413-140">Dodijelite ulogu **osobe za prilagodbu kartice Customer Insights** korisnicima koji će cijeloj organizaciji prilagoditi sadržaj prikazan na kartici.</span><span class="sxs-lookup"><span data-stu-id="e7413-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="e7413-141">Dodavanje kontrola kartice klijenta u obrasce</span><span class="sxs-lookup"><span data-stu-id="e7413-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="e7413-142">Da biste dodali kontrole kartice klijenta u obrazac za kontakt, idite na **Postavke** > **Prilagodbe** u sustavu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e7413-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="e7413-143">Odaberite **Prilagođavanje sustava**.</span><span class="sxs-lookup"><span data-stu-id="e7413-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="e7413-144">Idite na entitet **Kontakt**, proširite ga i odaberite **Obrasci**.</span><span class="sxs-lookup"><span data-stu-id="e7413-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="e7413-145">Odaberite obrazac za kontakt kojemu želite dodati kontrole kartice klijenta.</span><span class="sxs-lookup"><span data-stu-id="e7413-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e7413-146">![Odabir obrasca za kontakt](media/contact-active-forms.png "Odabir obrasca za kontakt")</span><span class="sxs-lookup"><span data-stu-id="e7413-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="e7413-147">Da biste dodali kontrolu, u uređivaču obrazaca povucite bilo koje polje iz **Preglednika polja** tamo gdje želite da se kontrola pojavi.</span><span class="sxs-lookup"><span data-stu-id="e7413-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="e7413-148">Odaberite polje na obrascu koje ste upravo dodali i odaberite **Promjena svojstava**.</span><span class="sxs-lookup"><span data-stu-id="e7413-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="e7413-149">Otvorite karticu **Kontrole** i odaberite **Dodaj kontrolu**.</span><span class="sxs-lookup"><span data-stu-id="e7413-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="e7413-150">Odaberite jednu od dostupnih prilagođenih kontrola i odaberite **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="e7413-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="e7413-151">U dijalogu **Svojstva polja** poništite potvrdni okvir **Prikazani natpis na obrascu**.</span><span class="sxs-lookup"><span data-stu-id="e7413-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="e7413-152">Odaberite mogućnost **Web** za kontrolu.</span><span class="sxs-lookup"><span data-stu-id="e7413-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="e7413-153">Za kontrolu obogaćivanja, konfiguriranjem polja **enrichmentType** odaberite vrstu obogaćivanja koju želite prikazati.</span><span class="sxs-lookup"><span data-stu-id="e7413-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="e7413-154">Dodajte zasebnu kontrolu obogaćivanja za svaku vrstu obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="e7413-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="e7413-155">Odaberite **Spremi** i **Objavi** da biste objavili ažurirani obrazac za kontakt.</span><span class="sxs-lookup"><span data-stu-id="e7413-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="e7413-156">Idite na objavljeni obrazac za kontakt.</span><span class="sxs-lookup"><span data-stu-id="e7413-156">Go to the published contact form.</span></span> <span data-ttu-id="e7413-157">Vidjet ćete novododanu kontrolu.</span><span class="sxs-lookup"><span data-stu-id="e7413-157">You'll see the newly added control.</span></span> <span data-ttu-id="e7413-158">Možda ćete se morati prijaviti prilikom prvog korištenja.</span><span class="sxs-lookup"><span data-stu-id="e7413-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="e7413-159">Da biste prilagodili ono što želite prikazati na prilagođenoj kontroli, odaberite gumb za uređivanje u gornjem desnom kutu.</span><span class="sxs-lookup"><span data-stu-id="e7413-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="e7413-160">Nadogradnja dodatka za karticu kupca</span><span class="sxs-lookup"><span data-stu-id="e7413-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="e7413-161">Dodatak za karticu kupca ne nadograđuje se automatski.</span><span class="sxs-lookup"><span data-stu-id="e7413-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="e7413-162">Da biste nadogradili na najnoviju verziju, slijedite ovaj postupak u aplikaciji Dynamics 365 u kojoj je instaliran dodatak.</span><span class="sxs-lookup"><span data-stu-id="e7413-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="e7413-163">U aplikaciji Dynamics 365 idite na **Postavke** > **Prilagođavanje** i odaberite **Rješenja**.</span><span class="sxs-lookup"><span data-stu-id="e7413-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="e7413-164">U tablici dodataka potražite **CustomerInsightsCustomerCard** i odaberite redak.</span><span class="sxs-lookup"><span data-stu-id="e7413-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="e7413-165">Odaberite **Primijeni nadogradnju rješenja** na akcijskoj traci.</span><span class="sxs-lookup"><span data-stu-id="e7413-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Nadogradite rješenje u području prilagođavanja aplikacija Dynamics 365":::

1. <span data-ttu-id="e7413-167">Nakon pokretanja postupka nadogradnje vidjet ćete indikator učitavanja sve dok nadogradnja ne završi.</span><span class="sxs-lookup"><span data-stu-id="e7413-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="e7413-168">Ako nema novije verzije, nadogradnja će prikazati poruku o pogrešci.</span><span class="sxs-lookup"><span data-stu-id="e7413-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
