---
title: Upotreba demografskih dimenzija za razdjeljivanje podataka o ponašanju (priređene dimenzije)
description: Koristite se priređenim dimenzijama objedinjenih profila da biste omogućili svojstva profila klijenata uvida u ciljnu skupinu.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232958"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Upotreba demografskih dimenzija za razdjeljivanje podataka o ponašanju

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Upotrebom demografskih dimenzija objedinjenih profila korisnici uvida u angažman mogu pristupiti svojstvima profila uvida u ciljnu skupinu. Ta svojstva tada možete upotrebljavati u interaktivnim analizama podataka o ponašanju, uključujući podatke prikupljene uvidima u angažman na vašoj web-stranici ili u mobilnoj aplikaciji.

>[!NOTE]
> Uvidi o angažmanu uključuju gotove dimenzije za svojstva događaja. Više informacije: [Pregled i izrada dimenzija](dimensions.md)

## <a name="prerequisite"></a>Preduvjet

- Okruženje uvida u angažman u kojem imate podatke profila korisnika povezane s okruženjem uvida u ciljnu skupinu u kojem se izrađuju profili klijenata. Više informacija: [Izrada veze između uvida u ciljnu skupinu i uvida u angažman](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Nakon što izradite vezu između okruženja uvida u ciljnu skupinu i okruženja uvida u angažman, možda ćete htjeti samo podatke specifične za svojstva profila klijenta koji mogu biti korisni kao dimenzije u uvidima u angažman. Više informacija potražite u članku [Omogućavanje atributa i segmenata objedinjenih profila uvida u ciljnu skupinu](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Izrada novog prilagođenog izvješća

1. U lijevom oknu odaberite **Prilagođeno** > **Novo izvješće**, a zatim odaberite metriku koju želite. (Za ovaj smo primjer odabrali **Pregledi stranice po satu**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Odaberite metriku.":::

2. U uređivaču vizualnog prikaza odaberite **Dimenzije**, a zatim odaberite **Demografski** u padajućem izborniku **Vrsta dimenzije**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Odaberite Demografski.":::

3. Odaberite dimenziju **Signal.Customer.*xxx***. (Ovaj primjer prikazuje Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Odaberite dimenziju.":::
  
## <a name="limitations"></a>Ograničenja

Demografske dimenzije trenutačno možete upotrebljavati samo za razdjeljivanje podataka o ponašanju.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
