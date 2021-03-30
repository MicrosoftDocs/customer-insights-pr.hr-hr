---
title: Unos podataka i ograničenja u stvarnom vremenu
description: Opće informacije o mogućnostima u stvarnom vremenu u uvidima u ciljnu skupinu.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598560"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="03cc5-103">Unos podataka u stvarnom vremenu (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="03cc5-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="03cc5-104">Rad praktično u stvarnom vremenu omogućuje vam da za nekoliko sekundi vidite najnovije interakcije klijenata s vašim proizvodima ili uslugama.</span><span class="sxs-lookup"><span data-stu-id="03cc5-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="03cc5-105">[Zakazana osvježenja](system.md#schedule-tab) uključuju velik broj zapisa i nekoliko složenih operacija.</span><span class="sxs-lookup"><span data-stu-id="03cc5-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="03cc5-106">Prvo se podaci izvlače iz izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="03cc5-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="03cc5-107">Zatim se podaci objedinjuju, a onda obogaćuju dodatnim informacijama.</span><span class="sxs-lookup"><span data-stu-id="03cc5-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="03cc5-108">Svako pokretanje ovog procesa može trajati nekoliko minuta ili sati.</span><span class="sxs-lookup"><span data-stu-id="03cc5-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="03cc5-109">Funkcija u stvarnom vremenu odmah pruža podatke za potrošnju, sve dok ih naknadno zakazano osvježenje ne izvuče iz izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="03cc5-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="03cc5-110">Ažuriranja u stvarnom vremenu imaju vrijeme isteka nakon kojeg više ne zamjenjuju vrijednost iz izvora podataka:</span><span class="sxs-lookup"><span data-stu-id="03cc5-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="03cc5-111">Ažuriranja profila čuvat će se 4 sata</span><span class="sxs-lookup"><span data-stu-id="03cc5-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="03cc5-112">Aktivnosti će se čuvati 30 dana</span><span class="sxs-lookup"><span data-stu-id="03cc5-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="03cc5-113">Te su vrijednosti parametri pozivanja API-ja koje možete promijeniti.</span><span class="sxs-lookup"><span data-stu-id="03cc5-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="03cc5-114">Cilj im je osigurati da vaši izvorni podaci ostanu vaš izvor istine.</span><span class="sxs-lookup"><span data-stu-id="03cc5-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="03cc5-115">Ako želite da ažuriranja u stvarnom vremenu dulje budu uključena, morate ih dodati u izvor podataka tako da se povuku tijekom sljedećeg zakazanog osvježavanja.</span><span class="sxs-lookup"><span data-stu-id="03cc5-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="03cc5-116">Ažuriranje polja unificiranog profila klijenta u stvarnom vremenu</span><span class="sxs-lookup"><span data-stu-id="03cc5-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="03cc5-117">Ažurirani profili prikazat će se u prikazu kartice klijenta li bilo kojoj drugoj vizualizaciji u roku od nekoliko sekundi.</span><span class="sxs-lookup"><span data-stu-id="03cc5-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="03cc5-118">Budući da se operacije u stvarnom vremenu odvijaju nakon objedinjavanja podataka, one se primjenjuju samo na objedinjene profile korisnika.</span><span class="sxs-lookup"><span data-stu-id="03cc5-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="03cc5-119">Prema tome, promjene profila u stvarnom vremenu neće ažurirati mjere, članstvo segmenta ili obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="03cc5-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="03cc5-120">Ograničenja</span><span class="sxs-lookup"><span data-stu-id="03cc5-120">Limitations</span></span>

- <span data-ttu-id="03cc5-121">Korisnički profili mogu se ažurirati, ali ne i stvarati ili brisati.</span><span class="sxs-lookup"><span data-stu-id="03cc5-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="03cc5-122">Izvoz ažuriranja u stvarnom vremenu u vanjske sustave, poput Power BI, trenutno nije moguće.</span><span class="sxs-lookup"><span data-stu-id="03cc5-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="03cc5-123">Stvaranje aktivnosti u stvarnom vremenu</span><span class="sxs-lookup"><span data-stu-id="03cc5-123">Real-time creation of activities</span></span>

<span data-ttu-id="03cc5-124">API u stvarnom vremenu omogućuje vam objavljivanje nove aktivnosti iz vašeg izvornog sustava (pojedinačni izvorni zapis) na jedinstveni profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="03cc5-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="03cc5-125">Nova će aktivnost biti u roku od nekoliko sekundi dostupna kao objedinjena aktivnost na vremenskoj traci tog objedinjenog korisničkog profila.</span><span class="sxs-lookup"><span data-stu-id="03cc5-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="03cc5-126">Vremensku traku možete vidjeti u prikazu kartice klijenta ili bilo kojoj drugoj integraciji vremenske trake koju ste konfigurirali.</span><span class="sxs-lookup"><span data-stu-id="03cc5-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="03cc5-127">Aktivnosti su nepromjenjive.</span><span class="sxs-lookup"><span data-stu-id="03cc5-127">Activities are immutable.</span></span> <span data-ttu-id="03cc5-128">Nakon stvaranja se ne mijenjaju.</span><span class="sxs-lookup"><span data-stu-id="03cc5-128">They don't change once created.</span></span>
> - <span data-ttu-id="03cc5-129">Trenutno se segmenti i mjere neće ažurirati na temelju nove aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="03cc5-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="03cc5-130">Aktivnosti dodane samo putem API-ja u stvarnom vremenu nisu dio izvoza i neće se pojaviti na nadzornoj ploči PowerBI.</span><span class="sxs-lookup"><span data-stu-id="03cc5-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="03cc5-131">Dva su načina povezivanja s API-jem u stvarnom vremenu:</span><span class="sxs-lookup"><span data-stu-id="03cc5-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="03cc5-132">[posredno](#connect-via-the-dynamics-365-customer-insights-connector), korištenjem [Dynamics 365 Customer Insights poveznika](/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="03cc5-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)</span></span>
- <span data-ttu-id="03cc5-133">[izravno](#connect-directly-to-the-real-time-api), s kodom</span><span class="sxs-lookup"><span data-stu-id="03cc5-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="03cc5-134">Oba načina dijele iste sljedeće preduvjete:</span><span class="sxs-lookup"><span data-stu-id="03cc5-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="03cc5-135">A Okruženje Customer Insights</span><span class="sxs-lookup"><span data-stu-id="03cc5-135">A Customer Insights environment</span></span>
- <span data-ttu-id="03cc5-136">Objedinjeni profili klijenata</span><span class="sxs-lookup"><span data-stu-id="03cc5-136">Unified customer profiles</span></span>
- <span data-ttu-id="03cc5-137">Aktivnosti konfigurirane i pokrenute</span><span class="sxs-lookup"><span data-stu-id="03cc5-137">Activities configured and run</span></span>
- <span data-ttu-id="03cc5-138">Dozvole suradnika ili administratora za provjeru autentičnosti vašeg računa</span><span class="sxs-lookup"><span data-stu-id="03cc5-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="03cc5-139">Povezivanje putem Dynamics 365 Customer Insights poveznika</span><span class="sxs-lookup"><span data-stu-id="03cc5-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="03cc5-140">API u stvarnom vremenu može unositi podatke s namjenskog Power Platform poveznika, [Dynamics 365 Customer Insights poveznika](/connectors/customerinsights/), bez potrebe za pisanjem i implementiranjem bilo kojeg koda.</span><span class="sxs-lookup"><span data-stu-id="03cc5-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="03cc5-141">Poveznik može raditi iste radnje u stvarnom vremenu kao API.</span><span class="sxs-lookup"><span data-stu-id="03cc5-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="03cc5-142">Za vrhunske poveznike potrebna je valjana licenca.</span><span class="sxs-lookup"><span data-stu-id="03cc5-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="03cc5-143">Za dodatne informacije pogledajte [Najčešća pitanja o licenciranju za Power Apps i Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="03cc5-143">For more information, see [Power Apps and Power Automate licensing FAQs](/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="03cc5-144">Power Platform [Power Apps i/ili Power Automate](/connectors/)</span><span class="sxs-lookup"><span data-stu-id="03cc5-144">Power Platform [Power Apps and/or Power Automate](/connectors/)</span></span>
- <span data-ttu-id="03cc5-145">Azure [Logičke aplikacije](/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="03cc5-145">Azure [Logic Apps](/azure/connectors/apis-list)</span></span>

<span data-ttu-id="03cc5-146">Za pojedinosti o stvaranju tokova pogledajte [Dokumentaciju za Power Automate](/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="03cc5-146">For details about creating flows, see the [Power Automate documentation](/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="03cc5-147">Izravno povezivanje s API-jem u stvarnom vremenu</span><span class="sxs-lookup"><span data-stu-id="03cc5-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="03cc5-148">Mogućnosti u stvarnom vremenu možete se koristiti izgradnjom vlastitog kanala i izravnim povezivanjem s API-jem u stvarnom vremenu.</span><span class="sxs-lookup"><span data-stu-id="03cc5-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="03cc5-149">Aktivnost možete objaviti u formatu svog izvornog sustava ili u formatu UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="03cc5-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="03cc5-150">Nabavite format upućivanjem API poziva u /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="03cc5-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="03cc5-151">Pojedinosti ovog API-ja, uključujući parametre i odgovore, možete pronaći u odjeljku **EntityData** o [Referenci API-ja Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="03cc5-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="03cc5-152">Dodatne informacije potražite u odjeljku [Rad s API-jima Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="03cc5-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="03cc5-153">Objašnjenje uporabe u stvarnom vremenu uz telemetriju</span><span class="sxs-lookup"><span data-stu-id="03cc5-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="03cc5-154">Dohvatite pregled količine zahtjeva API-ju u stvarnom vremenu i informacije o problemima na koje sustav može naići.</span><span class="sxs-lookup"><span data-stu-id="03cc5-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="03cc5-155">Možete [pristupiti telemetriji u stvarnom vremenu](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="03cc5-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]