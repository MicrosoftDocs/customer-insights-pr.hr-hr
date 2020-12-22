---
title: Zahtjevi subjekta podataka (ZSP) za prava pod OUZP-om | Microsoft Docs
description: Odgovorite na zahtjeve ispitanika za mogućnost uvida u ciljnu skupinu sustava Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405325"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="77b60-103">Zahtjevi subjekta podataka (ZSP) za prava pod OUZP-om</span><span class="sxs-lookup"><span data-stu-id="77b60-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="77b60-104">Odgovaranje na OUZP zahtjeve ispitanika za brisanje mogućnosti uvida u ciljnu skupinu sustava Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="77b60-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="77b60-105">"Pravo na zaborav" brisanjem osobnih podataka iz korisničkih podataka organizacije ključna je zaštita u Općoj uredbi o zaštiti podataka (OUZP).</span><span class="sxs-lookup"><span data-stu-id="77b60-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="77b60-106">Uklanjanje osobnih podataka uključuje uklanjanje svih osobnih podataka i dnevnika koje generira sustav, osim informacija iz dnevnika revizije.</span><span class="sxs-lookup"><span data-stu-id="77b60-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="77b60-107">Upravljanje zahtjevima za brisanje subjekta podataka</span><span class="sxs-lookup"><span data-stu-id="77b60-107">Manage data subject delete requests</span></span>

<span data-ttu-id="77b60-108">Uvidi u ciljnu skupinu nude sljedeća iskustva u proizvodu za brisanje osobnih podataka za specifičnog klijenta ili korisnika:</span><span class="sxs-lookup"><span data-stu-id="77b60-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="77b60-109">**Upravljanje zahtjevima za brisanje za podatke o klijentu**: podaci o klijentu u stavci Customer Insights unose se iz izvornih izvora podataka koji su izvan stavke Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="77b60-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="77b60-110">Svi OUZP zahtjevi za brisanje moraju se provesti u originalnom izvoru podataka.</span><span class="sxs-lookup"><span data-stu-id="77b60-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="77b60-111">**Upravljaj zahtjevima za brisanje korisničkih podataka u sustavu Customer Insights**: podatke za korisnike stvara Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="77b60-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="77b60-112">Svi OUZP zahtjevi za brisanje moraju se provesti unutar stavke Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="77b60-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="77b60-113">Upravljanje zahtjevima za brisanje za podatke o klijentima</span><span class="sxs-lookup"><span data-stu-id="77b60-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="77b60-114">Administrator za Customer Insights može slijediti ove korake kako bi uklonio korisničke podatke koji su izbrisani u izvoru podataka:</span><span class="sxs-lookup"><span data-stu-id="77b60-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="77b60-115">Prijavite se u sustav Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="77b60-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="77b60-116">U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**</span><span class="sxs-lookup"><span data-stu-id="77b60-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="77b60-117">Za svaki izvor podataka na popisu koji sadrži izbrisane podatke o klijentu:</span><span class="sxs-lookup"><span data-stu-id="77b60-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="77b60-118">Odaberite (...), a zatim odaberite **Osvježi**.</span><span class="sxs-lookup"><span data-stu-id="77b60-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="77b60-119">Provjerite status izvora podataka pod **Status**.</span><span class="sxs-lookup"><span data-stu-id="77b60-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="77b60-120">Oznaka kvačice znači da je osvježavanja bilo uspješno.</span><span class="sxs-lookup"><span data-stu-id="77b60-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="77b60-121">Trokut upozorenja znači da je došlo do pogreške.</span><span class="sxs-lookup"><span data-stu-id="77b60-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="77b60-122">Ako se prikaže znak upozorenja, kontaktirajte D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="77b60-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77b60-123">![Upravljanje zahtjevima za brisanje OUZP-a za podatke o klijentima](media/gdpr-data-sources.png "Upravljanje zahtjevima za brisanje OUZP-a za podatke o klijentima")</span><span class="sxs-lookup"><span data-stu-id="77b60-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="77b60-124">Upravljanje zahtjevima za brisanje za podatke o korisniku</span><span class="sxs-lookup"><span data-stu-id="77b60-124">Manage delete requests for user data</span></span>

<span data-ttu-id="77b60-125">Administrator za Customer Insights može poduzeti ove korake za brisanje podataka o klijentu za Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="77b60-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="77b60-126">Prijavite se u sustav Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="77b60-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="77b60-127">U uvidima u ciljnu skupinu idite na **Admin** > **Dozvole**.</span><span class="sxs-lookup"><span data-stu-id="77b60-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="77b60-128">Potvrdite okvir korisnika kojeg želite izbrisati.</span><span class="sxs-lookup"><span data-stu-id="77b60-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="77b60-129">Odaberite mogućnost **Ukloni**.</span><span class="sxs-lookup"><span data-stu-id="77b60-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77b60-130">![Upravljanje OUZP zahtjevima za brisanje za podatke o korisniku](media/gdpr-permissions.png "Upravljanje OUZP zahtjevima za brisanje za podatke o korisniku")</span><span class="sxs-lookup"><span data-stu-id="77b60-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="77b60-131">Odgovaranje na OUZP zahtjeve ispitanika za izvoz</span><span class="sxs-lookup"><span data-stu-id="77b60-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="77b60-132">Kao dio naše obveze za sklapanje partnerstva s vama na vašem putu prema Općoj uredbi o zaštiti podataka (OUZP-u), razvili smo dokumentaciju kako bismo vam pomogli da se pripremite.</span><span class="sxs-lookup"><span data-stu-id="77b60-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="77b60-133">Ova dokumentacija opisuje korake koje danas možete poduzeti da biste podržali usklađenost s GDPR-om kada koristite uvide u ciljnu skupinu.</span><span class="sxs-lookup"><span data-stu-id="77b60-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="77b60-134">Upravljanje izvozom i pregledavanjem zahtjeva</span><span class="sxs-lookup"><span data-stu-id="77b60-134">Manage export and view requests</span></span>

<span data-ttu-id="77b60-135">Pravo na prenosivost podataka omogućuje subjektima podataka da zatraže kopiju svojih osobnih podataka u elektroničkom obliku ("strukturirani, uobičajeno korišten, strojno čitljiv i interoperabilni format") koji se može prenijeti drugom kontroloru podataka.</span><span class="sxs-lookup"><span data-stu-id="77b60-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="77b60-136">Izvoz podataka klijenta (administrator klijenta)</span><span class="sxs-lookup"><span data-stu-id="77b60-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="77b60-137">Administrator klijenta može pratiti ove korake za izvoz podataka:</span><span class="sxs-lookup"><span data-stu-id="77b60-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="77b60-138">Pošaljite e-poštu na D365CI@microsoft.com i u zahtjevu navedite adresu e-pošte klijenta.</span><span class="sxs-lookup"><span data-stu-id="77b60-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="77b60-139">Tim Customer Insights poslat će poruku e-pošte na registriranu adresu e-pošte administratora klijenta i zatražiti potvrdu za izvoz podataka.</span><span class="sxs-lookup"><span data-stu-id="77b60-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="77b60-140">Potvrdite zahtjev za izvozom podataka za zatraženog klijenta.</span><span class="sxs-lookup"><span data-stu-id="77b60-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="77b60-141">Primite izvezene podatke putem adrese e-pošte administratora klijenta.</span><span class="sxs-lookup"><span data-stu-id="77b60-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="77b60-142">Izvoz podataka o korisniku (administrator klijenta)</span><span class="sxs-lookup"><span data-stu-id="77b60-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="77b60-143">Pošaljite e-poštu na D365CI@microsoft.com i u zahtjevu navedite adresu e-pošte korisnika.</span><span class="sxs-lookup"><span data-stu-id="77b60-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="77b60-144">Tim Customer Insights poslat će poruku e-pošte na registriranu adresu e-pošte administratora klijenta i zatražiti potvrdu za izvoz podataka.</span><span class="sxs-lookup"><span data-stu-id="77b60-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="77b60-145">Potvrdite zahtjev za izvozom podataka za zatraženog korisnika.</span><span class="sxs-lookup"><span data-stu-id="77b60-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="77b60-146">Primite izvezene podatke putem adrese e-pošte administratora klijenta.</span><span class="sxs-lookup"><span data-stu-id="77b60-146">Receive the exported data through the tenant admin email address.</span></span>
