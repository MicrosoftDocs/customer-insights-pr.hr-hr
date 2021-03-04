---
title: Bot za Microsoft Teams
description: Potražite objedinjene profile klijenata u Microsoft Teams pomoću bota.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267943"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="6ffe3-103">Bot Timovi za Dynamics 365 Customer Insights (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="6ffe3-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="6ffe3-104">Povežite se s Microsoft Teams kako bi bot mogao potražiti objedinjene profile klijenata na kanalima Timovi.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6ffe3-105">![Botovi timova koji pokazuju zapis o klijentu](media/teams-bot.png "Botovi timova koji pokazuju zapis o klijentu")</span><span class="sxs-lookup"><span data-stu-id="6ffe3-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6ffe3-106">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="6ffe3-106">Prerequisites</span></span>

<span data-ttu-id="6ffe3-107">Da biste postavili i konfigurirali bot, moraju se ispuniti sljedeći preduvjeti:</span><span class="sxs-lookup"><span data-stu-id="6ffe3-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="6ffe3-108">Barem jedan [izvor podataka je dodan](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="6ffe3-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="6ffe3-109">[Proces objedinjavanja](data-unification.md) je dovršen.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="6ffe3-110">Polja se dodaju u [index pretraživanja i filtera](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="6ffe3-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="6ffe3-111">Customer Insights i Timovi su u istoj tvrtki ili ustanovi.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="6ffe3-112">Konfiguriranje bota</span><span class="sxs-lookup"><span data-stu-id="6ffe3-112">Configure the bot</span></span>

1. <span data-ttu-id="6ffe3-113">U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="6ffe3-114">Na pločici Microsoft Teams odaberite **Postavljanje**.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="6ffe3-115">Preusmjereni ste napodručje **Aplikacije** u Timovima.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="6ffe3-116">Možete otvoriti i Timove i odabrati **Aplikacije** u donjem lijevom kutu ili [joj izravno pristupiti u AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="6ffe3-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="6ffe3-117">Potražite **Customer Insights** i odaberite aplikaciju.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="6ffe3-118">Odaberite **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-118">Select **Add**.</span></span>
1. <span data-ttu-id="6ffe3-119">Nakon što se prijavite na Customer Insights u Timovima, prikazat će se poruka dobrodošlice i možete započeti.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="6ffe3-120">Što bot omogućuje</span><span class="sxs-lookup"><span data-stu-id="6ffe3-120">Things you can do with the bot</span></span>

<span data-ttu-id="6ffe3-121">Bot pruža mogućnosti pretraživanja za objedinjene profile klijenata.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="6ffe3-122">Unesite **traži**, a zatim ime, adresu e-pošte ili bilo koje drugo polje na objedinjenom profilu klijenta koje se dodaje indeksu pretraživanja i filtra.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="6ffe3-123">Iz rezultirajućeg profila klijenta dobit ćete karticu s najviše 15 polja.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="6ffe3-124">Višestruka podudaranja vraćaju popis rezultata gdje možete odabrati profil.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="6ffe3-125">Pojam za pretraživanje možete staviti pod dvostruke navodnike da biste potražili točno podudaranje.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="6ffe3-126">Ako vaša tvrtka ili ustanova održava više okruženja Customer Insights u istoj tvrtki ili ustanovi, možete pristupiti **zamjeni instance** da biste odabrali u koje okruženje želite povezati bot.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="6ffe3-127">Unesite **pomoć** da bi se prikazao popis dostupnih naredbi za bot.</span><span class="sxs-lookup"><span data-stu-id="6ffe3-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]