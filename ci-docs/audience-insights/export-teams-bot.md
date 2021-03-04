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
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot Timovi za Dynamics 365 Customer Insights (pretpregled)

Povežite se s Microsoft Teams kako bi bot mogao potražiti objedinjene profile klijenata na kanalima Timovi.

> [!div class="mx-imgBorder"]
> ![Botovi timova koji pokazuju zapis o klijentu](media/teams-bot.png "Botovi timova koji pokazuju zapis o klijentu")

## <a name="prerequisites"></a>Preduvjeti

Da biste postavili i konfigurirali bot, moraju se ispuniti sljedeći preduvjeti:

- Barem jedan [izvor podataka je dodan](data-sources.md).
- [Proces objedinjavanja](data-unification.md) je dovršen.
- Polja se dodaju u [index pretraživanja i filtera](search-filter-index.md).
- Customer Insights i Timovi su u istoj tvrtki ili ustanovi.

## <a name="configure-the-bot"></a>Konfiguriranje bota

1. U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta za izvoz**.
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]