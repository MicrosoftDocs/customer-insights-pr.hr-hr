---
title: Veze s ostalim uslugama iz Customer Insights.
description: Podijelite podatke s drugim uslugama.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304963"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="e6b8c-103">Pregled (pretpregled) veza</span><span class="sxs-lookup"><span data-stu-id="e6b8c-103">Connections (preview) overview</span></span>

<span data-ttu-id="e6b8c-104">Veze su ključ za omogućavanje dijeljenja podataka s i iz Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="e6b8c-105">Svaka veza uspostavlja dijeljenje podataka s određenom uslugom.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="e6b8c-106">Veze su temelj za [konfiguriranje obogaćivanja treće strane](enrichment-hub.md) i [konfiguriranje izvoza](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e6b8c-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="e6b8c-107">Ista veza može se koristiti više puta.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="e6b8c-108">Na primjer, jedna veza s Dynamics 365 Marketing funkcionira za više izvoza, a jedna veza Leadspace može se koristiti za nekoliko obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="e6b8c-109">Idite na **Admin** > **Veze** za stvaranje i pregled veza.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="e6b8c-110">Kartica **Veze** prikazuje sve aktivne veze.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="e6b8c-111">Popis prikazuje redak za svaku vezu.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="e6b8c-112">Dobijte brzi pregled, opis i saznajte što možete učiniti sa svakom mogućnosti proširenja na kartici **Otkrij**.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="e6b8c-113">Izvozi</span><span class="sxs-lookup"><span data-stu-id="e6b8c-113">Exports</span></span>

<span data-ttu-id="e6b8c-114">Samo administratori mogu konfigurirati nove veze, ali suradnicima mogu odobriti pristup korištenju postojećih veza.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="e6b8c-115">Administratori kontroliraju kamo podaci mogu ići, suradnici definiraju korisne podatke i frekvenciju u skladu sa svojim potrebama.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="e6b8c-116">Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e6b8c-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="e6b8c-117">Obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="e6b8c-117">Enrichments</span></span>

<span data-ttu-id="e6b8c-118">Samo administratori mogu konfigurirati nove veze, ali stvorene veze uvijek su dostupne i administratorima i suradnicima.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="e6b8c-119">Administratori upravljaju vjerodajnicama i daju pristanak za prijenos podataka.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="e6b8c-120">Tada veze za obogaćivanja mogu koristiti i administratori i suradnici.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="e6b8c-121">Dodavanje nove veze</span><span class="sxs-lookup"><span data-stu-id="e6b8c-121">Add a new connection</span></span>

<span data-ttu-id="e6b8c-122">Da biste dodali veze, morate imati [administratorske dozvole](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e6b8c-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="e6b8c-123">Ako se povežete s ostalim Microsoftovim uslugama, pretpostavljamo da su obje usluge u istoj tvrtki ili ustanovi.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="e6b8c-124">Idite na **Admin** > **Veze (pretpregled)**.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="e6b8c-125">Idite na karticu **Veze**.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="e6b8c-126">Odaberite **Nova veza** da biste stvorili novu vezu.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="e6b8c-127">Na padajućem izborniku odaberite vrstu veze koju želite stvoriti.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="e6b8c-128">U oknu **Postavi vezu** okno navedite potrebne pojedinosti.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="e6b8c-129">**Zaslonski naziv** i vrsta veze opisuju vezu.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="e6b8c-130">Preporučujemo odabir naziva koji objašnjava svrhu i cilj te veze.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="e6b8c-131">Točna polja ovise o tome na koju se uslugu povezujete.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="e6b8c-132">O pojedinostima određene vrste veze možete saznati u članku o ciljnoj usluzi.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="e6b8c-133">Da biste stvorili vezu, odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="e6b8c-134">Možete odabrati i **Postavljanje** na pločici na kartici **Otkrivanje**.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="e6b8c-135">Omogućavanje korištenja veze za izvoze suradnicima</span><span class="sxs-lookup"><span data-stu-id="e6b8c-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="e6b8c-136">Kada postavljate ili uređujete vezu za izvoz, odabirete koji korisnici smiju koristiti tu određenu vezu za definiranje [izvoza](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e6b8c-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="e6b8c-137">Prema zadanim postavkama veza je dostupna korisnicima s ulogom administratora.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="e6b8c-138">Ovu postavku možete promijeniti pod **Odaberi tko može koristiti ovu vezu** i dopustite korisnicima s ulogom suradnika da koriste ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="e6b8c-139">Suradnici neće moći pregledati ili urediti vezu.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="e6b8c-140">Vidjet će samo zaslonski naziv i njegovu vrstu prilikom stvaranja izvoza.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="e6b8c-141">Dijeljenjem veze dopuštate suradnicima korištenje veze.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="e6b8c-142">Suradnici će vidjeti dijeljene veze kada postave izvoze.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="e6b8c-143">Oni mogu upravljati svakim izvozom koji koristi ovu specifičnu vezu.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="e6b8c-144">Ovu postavku možete promijeniti zadržavajući izvoze koje su suradnici već definirali.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="e6b8c-145">Uređivanje veze</span><span class="sxs-lookup"><span data-stu-id="e6b8c-145">Edit a connection</span></span>

1. <span data-ttu-id="e6b8c-146">Idite na **Admin** > **Veze (pretpregled)**.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="e6b8c-147">Idite na karticu **Veze**.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="e6b8c-148">Odaberite okomitu elipsu za vezu koju želite urediti.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="e6b8c-149">Odaberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-149">Select **Edit**.</span></span>

1. <span data-ttu-id="e6b8c-150">Promijenite vrijednosti koje želite ažurirati i odaberite **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="e6b8c-151">Uklanjanje veze</span><span class="sxs-lookup"><span data-stu-id="e6b8c-151">Remove a connection</span></span>

<span data-ttu-id="e6b8c-152">Ako se veza koju uklanjate koristi za obogaćivanje ili izvoze, najprije ih morate odvojiti ili ukloniti.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="e6b8c-153">Dijaloški okvir za uklanjanje vodit će vas do relevantnih obogaćivanja ili izvoza.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="e6b8c-154">Odvojena obogaćivanja i izvozi postaju neaktivni.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="e6b8c-155">Ponovno ih aktivirate tako da im dodate drugu vezu na stranici [Obogaćivanja](enrichment-hub.md) ili [Izvozi](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e6b8c-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="e6b8c-156">Idite na **Admin** > **Veze (pretpregled)**.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="e6b8c-157">Idite na karticu **Veze**.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="e6b8c-158">Odaberite okomitu elipsu za vezu koju želite ukloniti.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="e6b8c-159">Na padajućem popisu odaberite **Ukloni**.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="e6b8c-160">Pojavljuje se dijaloški okvir za potvrdu.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="e6b8c-161">Ako postoje obogaćivanja ili izvozi koji koriste ovu vezu, odaberite gumb da biste vidjeli što koristi vezu.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="e6b8c-162">**Izvozi:** Možete odabrati da uklonite ili prekinete izvoze kako biste mogli ukloniti vezu.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="e6b8c-163">Da bi prekinuli izvoz, administratori mogu koristiti radnju **Prekini vezu**.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="e6b8c-164">Ova je radnja dostupna za pojedinačne i višestruko odabrane izvoze.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="e6b8c-165">Prekidanjem veze zadržavate konfiguraciju izvoza, ali ona se neće pokrenuti dok joj se ne doda druga veza.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="e6b8c-166">**Obogaćivanja:** Možete odabrati da uklonite ili deaktivirate obogaćivanja kako biste mogli ukloniti vezu.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="e6b8c-167">Kada veza više nema ovisnosti, vratite se na **Admin** > **Veze** i ponovno pokušajte ukloniti vezu.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="e6b8c-168">Da biste potvrdili brisanje, odaberite **Ukloni**.</span><span class="sxs-lookup"><span data-stu-id="e6b8c-168">To confirm the deletion, select **Remove**.</span></span>

