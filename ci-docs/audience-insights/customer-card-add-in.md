---
title: Instalacija i konfiguracija Dodatka za karticu klijenta
description: Instalirajte i konfigurirajte dodatak za korisničku karticu za Dynamics 365 Customer Insights.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644034"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="e03f2-103">Dodatak kartice klijenta (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="e03f2-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e03f2-104">Dobijte prikaz svojih klijenata od 360 stupnjeva izravno u Dynamics 365 aplikacijama.</span><span class="sxs-lookup"><span data-stu-id="e03f2-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="e03f2-105">Pregledajte demografske podatke, uvide i vremenske trake aktivnosti pomoću dodatka kartice klijenta.</span><span class="sxs-lookup"><span data-stu-id="e03f2-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e03f2-106">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="e03f2-106">Prerequisites</span></span>

- <span data-ttu-id="e03f2-107">Aplikacija Dynamics 365 (poput središta za prodaju ili središta službe za korisnike), verzije 9.0 i novije s omogućenim objedinjenim sučeljem.</span><span class="sxs-lookup"><span data-stu-id="e03f2-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="e03f2-108">Profili klijenata [uneseno iz Dynamics 365 aplikacije pomoću servisa Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e03f2-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="e03f2-109">Korisnici Dodatka za karticu klijenta moraju se [dodati kao korisnici](permissions.md) u uvidima ciljne skupine.</span><span class="sxs-lookup"><span data-stu-id="e03f2-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="e03f2-110">[Konfigurirane mogućnosti pretraživanja i filtriranja](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="e03f2-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="e03f2-111">Kontrola demografije: Demografska polja, poput dobi ili spola, dostupna su u objedinjenom profilu klijenta.</span><span class="sxs-lookup"><span data-stu-id="e03f2-111">Demographic control: Demographic fields, such as age or gender are available in the unified customer profile.</span></span>
- <span data-ttu-id="e03f2-112">Kontrola obogaćivanja: Zahtijeva aktivna [obogaćivanja](enrichment-hub.md) primijenjena na profile klijenata.</span><span class="sxs-lookup"><span data-stu-id="e03f2-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="e03f2-113">Kontrola inteligencije: Potrebni su podaci stvoreni pomoću alata za strojno učenje na platformi Azure ([Predviđanja](predictions.md) ili [Prilagođeni modeli](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="e03f2-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="e03f2-114">Kontrola mjerenja: Zahtijeva [konfigurirana mjerenja](measures.md).</span><span class="sxs-lookup"><span data-stu-id="e03f2-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="e03f2-115">Kontrola vremenske trake: Zahtijeva [konfigurirane aktivnosti](activities.md).</span><span class="sxs-lookup"><span data-stu-id="e03f2-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="e03f2-116">Instaliranje dodatka za korisničku karticu</span><span class="sxs-lookup"><span data-stu-id="e03f2-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="e03f2-117">Dodatak za korisničku karticu rješenje je za aplikacije Customer Engagement u programu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e03f2-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="e03f2-118">Da biste instalirali rješenje, idite na AppSource i potražite **Kartica klijenta Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="e03f2-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="e03f2-119">Odaberite [Dodatak kartice klijenta na AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i odaberite **Nabavi odmah**.</span><span class="sxs-lookup"><span data-stu-id="e03f2-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="e03f2-120">Možda ćete se trebati prijaviti s vjerodajnicama svog administratora za aplikaciju Dynamics 365 da biste postavili rješenje.</span><span class="sxs-lookup"><span data-stu-id="e03f2-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="e03f2-121">Možda će biti potrebno neko vrijeme da se rješenje instalira u vaše okruženje.</span><span class="sxs-lookup"><span data-stu-id="e03f2-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="e03f2-122">Konfiguriranje dodatka kartice klijenta</span><span class="sxs-lookup"><span data-stu-id="e03f2-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="e03f2-123">Kao administrator, idite na dio **Postavke** u aplikaciji Dynamics 365 i odaberite **Rješenja**.</span><span class="sxs-lookup"><span data-stu-id="e03f2-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="e03f2-124">Odaberite vezu **Naziv zaslona** za rješenje **Dynamics 365 Customer Insights dodatak kartice klijenta (pretpregled)**.</span><span class="sxs-lookup"><span data-stu-id="e03f2-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e03f2-125">![Odabir zaslonskog naziva](media/select-display-name.png "Odabir zaslonskog naziva")</span><span class="sxs-lookup"><span data-stu-id="e03f2-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="e03f2-126">Odaberite **Prijavi se** i unesite vjerodajnice za administratorski račun koji koristite za konfiguriranje aplikacije Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e03f2-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e03f2-127">Provjerite blokira li blokator skočnih prozora preglednika prozor za provjeru autentičnosti kada odaberete gumb **Prijavi se**.</span><span class="sxs-lookup"><span data-stu-id="e03f2-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="e03f2-128">Odaberite okruženenje iz kojeg želite dohvatiti podatke.</span><span class="sxs-lookup"><span data-stu-id="e03f2-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="e03f2-129">Definirajte koje mapiranje polja na zapise u aplikaciji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e03f2-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="e03f2-130">Za mapiranje s kontaktom odaberite polje u entitetu Kupac koje se podudara s ID-om entiteta vašeg kontakta.</span><span class="sxs-lookup"><span data-stu-id="e03f2-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="e03f2-131">Za mapiranje računom odaberite polje u entitetu Kupac koje se podudara s ID-om entiteta vašeg računa.</span><span class="sxs-lookup"><span data-stu-id="e03f2-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e03f2-132">![Polje za ID kontakta](media/contact-id-field.png "Polje za ID kontakta")</span><span class="sxs-lookup"><span data-stu-id="e03f2-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="e03f2-133">Odaberite **Spremi konfiguraciju** da biste spremili postavke.</span><span class="sxs-lookup"><span data-stu-id="e03f2-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="e03f2-134">Zatim trebate dodijeliti sigurnosne uloge u sustavu Dynamics 365 da bi korisnici mogli prilagoditi i vidjeti karticu klijenta.</span><span class="sxs-lookup"><span data-stu-id="e03f2-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="e03f2-135">U sustavu Dynamics 365 idite na **Postavke** > **Sigurnost** > **Korisnici**.</span><span class="sxs-lookup"><span data-stu-id="e03f2-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="e03f2-136">Odaberite korisnike da biste uredili uloge korisnika i odaberite **Upravljaj ulogama**.</span><span class="sxs-lookup"><span data-stu-id="e03f2-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="e03f2-137">Dodijelite ulogu **osobe za prilagodbu kartice Customer Insights** korisnicima koji će cijeloj organizaciji prilagoditi sadržaj prikazan na kartici.</span><span class="sxs-lookup"><span data-stu-id="e03f2-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="e03f2-138">Dodavanje kontrola kartice klijenta u obrasce</span><span class="sxs-lookup"><span data-stu-id="e03f2-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="e03f2-139">Da biste dodali kontrole kartice klijenta u obrazac za kontakt, idite na **Postavke** > **Prilagodbe** u sustavu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e03f2-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="e03f2-140">Odaberite **Prilagođavanje sustava**.</span><span class="sxs-lookup"><span data-stu-id="e03f2-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="e03f2-141">Idite na entitet **Kontakt**, proširite ga i odaberite **Obrasci**.</span><span class="sxs-lookup"><span data-stu-id="e03f2-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="e03f2-142">Odaberite obrazac za kontakt kojemu želite dodati kontrole kartice klijenta.</span><span class="sxs-lookup"><span data-stu-id="e03f2-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e03f2-143">![Odabir obrasca za kontakt](media/contact-active-forms.png "Odabir obrasca za kontakt")</span><span class="sxs-lookup"><span data-stu-id="e03f2-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="e03f2-144">Da biste dodali kontrolu, u uređivaču obrazaca povucite bilo koje polje iz **Preglednika polja** tamo gdje želite da se kontrola pojavi.</span><span class="sxs-lookup"><span data-stu-id="e03f2-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="e03f2-145">Odaberite polje na obrascu koje ste upravo dodali i odaberite **Promjena svojstava**.</span><span class="sxs-lookup"><span data-stu-id="e03f2-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="e03f2-146">Otvorite karticu **Kontrole** i odaberite **Dodaj kontrolu**.</span><span class="sxs-lookup"><span data-stu-id="e03f2-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="e03f2-147">Odaberite jednu od dostupnih prilagođenih kontrola i odaberite **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="e03f2-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="e03f2-148">U dijalogu **Svojstva polja** poništite potvrdni okvir **Prikazani natpis na obrascu**.</span><span class="sxs-lookup"><span data-stu-id="e03f2-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="e03f2-149">Odaberite mogućnost **Web** za kontrolu.</span><span class="sxs-lookup"><span data-stu-id="e03f2-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="e03f2-150">Za kontrolu obogaćivanja, konfiguriranjem polja **enrichmentType** odaberite vrstu obogaćivanja koju želite prikazati.</span><span class="sxs-lookup"><span data-stu-id="e03f2-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="e03f2-151">Za svaku vrstu obogaćivanja morate dodati zasebnu kontrolu obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="e03f2-151">You need to add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="e03f2-152">Odaberite **Spremi** i **Objavi** da biste objavili ažurirani obrazac za kontakt.</span><span class="sxs-lookup"><span data-stu-id="e03f2-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="e03f2-153">Idite na objavljeni obrazac za kontakt.</span><span class="sxs-lookup"><span data-stu-id="e03f2-153">Go to the published contact form.</span></span> <span data-ttu-id="e03f2-154">Vidjet ćete novododanu kontrolu.</span><span class="sxs-lookup"><span data-stu-id="e03f2-154">You'll see the newly added control.</span></span> <span data-ttu-id="e03f2-155">Možda ćete se morati prijaviti prilikom prvog korištenja.</span><span class="sxs-lookup"><span data-stu-id="e03f2-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="e03f2-156">Da biste prilagodili ono što želite prikazati na prilagođenoj kontroli, odaberite gumb za uređivanje u gornjem desnom kutu.</span><span class="sxs-lookup"><span data-stu-id="e03f2-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>
