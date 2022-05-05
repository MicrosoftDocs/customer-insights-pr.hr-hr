---
title: Bot za Microsoft Teams
description: Potražite objedinjene profile klijenata u Microsoft Teams pomoću bota.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 89a293d5b6f9f5452b2ccba495d2475002806019
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642917"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot Timovi za Dynamics 365 Customer Insights (pretpregled)

Povežite se s Microsoft Teams kako bi bot mogao potražiti objedinjene profile klijenata na kanalima Timovi.

> [!div class="mx-imgBorder"]
> ![Bot za Teams koji pokazuje zapis o klijentu.](media/teams-bot.png "Botovi timova koji pokazuju zapis o klijentu")

## <a name="prerequisites"></a>Preduvjeti

Da biste postavili i konfigurirali bot, moraju se ispuniti sljedeći preduvjeti:

- Barem jedan [izvor podataka je dodan](data-sources.md).
- [Proces objedinjavanja](data-unification.md) je dovršen.
- Polja se dodaju u [index pretraživanja i filtera](search-filter-index.md).
- Customer Insights i Timovi su u istoj tvrtki ili ustanovi.
- Okruženje ima primarnu ciljnu skupinu postavljen na pojedinačne klijente. Poslovni računi nisu podržani.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Konfiguriranje bota

1. Otvorite **Odredišta adminexporta** > **·**.
1. Na pločici Microsoft Teams odaberite **Postavljanje**.
1. Preusmjereni ste napodručje **Aplikacije** u Timovima. Možete otvoriti i Timove i odabrati **Aplikacije** u donjem lijevom kutu ili [joj izravno pristupiti u AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Potražite **Customer Insights** i odaberite aplikaciju.
1. Odaberite **Dodaj**.
1. Nakon što se prijavite na Customer Insights u Timovima, prikazat će se poruka dobrodošlice i možete započeti.

## <a name="things-you-can-do-with-the-bot"></a>Što bot omogućuje

Bot pruža mogućnosti pretraživanja za objedinjene profile klijenata.

- Unesite **traži**, a zatim ime, adresu e-pošte ili bilo koje drugo polje na objedinjenom profilu klijenta koje se dodaje indeksu pretraživanja i filtra.

  Iz rezultirajućeg profila klijenta dobit ćete karticu s najviše 15 polja. Višestruka podudaranja vraćaju popis rezultata gdje možete odabrati profil. Pojam za pretraživanje možete staviti pod dvostruke navodnike da biste potražili točno podudaranje.

- Ako vaša tvrtka ili ustanova održava više okruženja Customer Insights u istoj tvrtki ili ustanovi, možete pristupiti **zamjeni instance** da biste odabrali u koje okruženje želite povezati bot.

- Unesite **pomoć** da bi se prikazao popis dostupnih naredbi za bot.  


[!INCLUDE [footer-include](includes/footer-banner.md)]