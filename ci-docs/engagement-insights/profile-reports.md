---
title: Omogućavanje gotovih izvješća o profilima
description: Kako stvoriti gotova izvješća o profilima grupirana prema spolu, dobi i županiji ili regiji podrijetla.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486111"
---
# <a name="out-of-box-profile-reports"></a>Gotova izvješća o profilima

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Izvješće je zbirka vizualizacije podataka koja vam pomaže razumjeti kako se korisnici ponašaju. Povezivanjem s uvidima u ciljnu skupinu Customer Insights uvidi u angažmane mogu prikazati izvješće s informacijama o objedinjenim profilima klijenata. Ovo izvješće uključuje broj vaših profila, grupiranih prema spolu, dobi i zemljopisnom položaju.

## <a name="prerequisites"></a>Preduvjeti

Okruženje uvida u ciljnu skupinu mora pohranjivati podatke na račun Azure Data Lake Storage kojim upravljaju klijenti.

Ako koristite probnu verziju mogućnosti uvida u ciljnu skupinu ili okruženje u data lake kojim upravlja Customer Insights, [obratite nam se](https://go.microsoft.com/fwlink/?linkid=2145734) za pomoć.  


## <a name="enable-the-customer-profile-report"></a>Omogućavanje izvješće o profilu klijenta

Administrator okruženja mora [povezati uvide u angažman i uvide u ciljnu skupinu](integrate-audience-insights-engagement-insights.md).

Nakon navođenja pojedinosti o vezi administrator može odobriti pristup ostalim ljudima u tvrtki ili ustanovi kako bi vidjeli izvješće. Administrator okruženja koji postavlja vezu ima automatski pristup izvješću. 

Nakon dovršetka veze značajka **Profili** bit će dostupna u lijevom navigacijskom oknu. 

- Da biste vidjeli izvješće, idite na **Otkrij** > **Profili**.

Izvješće **Profili** sadrži vizualizacije o spolu, dobi i zemljopisnom položaju povezanih profila klijenata.

:::image type="content" source="media/customer-profiles.png" alt-text="Izvješće o profilu klijenta.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]