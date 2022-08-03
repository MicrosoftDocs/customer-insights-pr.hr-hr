---
title: Bot Timovi za Dynamics 365 Customer Insights (pretpregled)
description: Potražite objedinjene profile klijenata u Microsoft Teams pomoću bota.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195833"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot Timovi za Dynamics 365 Customer Insights (pretpregled)

Povežite se s Microsoft Teams kako bi bot mogao potražiti objedinjene profile klijenata na kanalima Timovi.

:::image type="content" source="media/teams-bot.png" alt-text="Botovi timova koji pokazuju zapis o klijentu":::

## <a name="prerequisites"></a>Preduvjeti

- Dodana je barem jedna [izvor podataka](data-sources.md).
- [Proces objedinjavanja](data-unification.md) je dovršen.
- Polja se dodaju indeksu [pretraživanja i filtriranja](search-filter-index.md).
- Customer Insights i Timovi su u istoj tvrtki ili ustanovi.
- Okruženje ima primarnu ciljnu skupinu postavljen na pojedinačne klijente. Poslovni računi nisu podržani.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Konfiguriranje bota

1. Idite na **Admin** > **Veze**.
1. Na pločici Microsoft Teams odaberite **Postavljanje**.
1. Preusmjereni ste napodručje **Aplikacije** u Timovima. Možete otvoriti i Timove i odabrati **Aplikacije** u donjem lijevom kutu ili [joj izravno pristupiti u AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Potražite **Customer Insights** i odaberite aplikaciju.
1. Odaberite **Dodaj**.
1. Prijavite se u Customer Insights u aplikaciji Teams. Prikazuje se poruka dobrodošlice.

## <a name="things-you-can-do-with-the-bot"></a>Što bot omogućuje

Bot pruža mogućnosti pretraživanja za objedinjene profile klijenata.

- Unesite **pretraživanje** nakon kojeg slijedi ime, adresa e-pošte ili bilo koje drugo polje na jedinstvenom profilu kupca koje se dodaje indeksu pretraživanja i filtra.

  Iz rezultirajućeg profila klijenta dobit ćete karticu s najviše 15 polja. Višestruka podudaranja vraćaju popis rezultata gdje možete odabrati profil. Da biste potražili točno podudaranje, dodajte termin za pretraživanje dvostrukim navodnicima.

- Ako vaša tvrtka ili ustanova održava više okruženja customer insights u istoj tvrtki ili ustanovi, unesite **switchinstance** da biste odabrali s kojim okruženjem želite povezati bota.

- Unesite **pomoć** da bi se prikazao popis dostupnih naredbi za bot.  

[!INCLUDE [footer-include](includes/footer-banner.md)]