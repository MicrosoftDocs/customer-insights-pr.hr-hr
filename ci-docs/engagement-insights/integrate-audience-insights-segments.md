---
title: Upotreba segmenata uvida u ciljnu skupinu za filtriranje izvješća uvida o angažmanu
description: Koristite segmente uvida u ciljnu skupinu u interaktivnoj analizi podataka o ponašanju prikupljenih uvidima u angažman na web-stranici klijenta.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230477"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Upotreba segmenata uvida u ciljnu skupinu za filtriranje izvješća uvida o angažmanu

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Zahvaljujući uvidima u angažman možete se koristiti segmentima uvida u ciljnu skupinu u interaktivnoj analizi podataka o ponašanju prikupljenih uvidima u angažman svojim web-stranicama.

## <a name="prerequisite"></a>Preduvjet

- Okruženje uvida u angažman u kojem imate podatke segmenta uvida u ciljnu skupinu povezane s okruženjem uvida u ciljnu skupinu u kojem se izrađuju segmenti i profili klijenata. Više informacija: [Izrada veze između uvida u ciljnu skupinu i uvida u angažman](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Izrada segmenata uvida u ciljnu skupinu 

> [!IMPORTANT]
> Da bi se segmenti uvida u ciljnu skupinu prikazivali u uvidima u angažman, prvo morate [pokrenuti spajanje i nizvodne procese](../audience-insights/merge-entities.md). Nizvodni procesi važni su jer generiraju jedinstvenu tablicu koja priprema segmente uvida u ciljnu skupinu za dijeljenje s uvidima u angažman. (Ako je zakazano osvježavanje sustava, ono će automatski uključiti nizvodne procese.)

Segmente uvida u ciljnu skupinu možete upotrebljavati u gotovim ili prilagođenim izvješćima uvida u angažman koja ste izradili. Više informacije potražite u članku [Gotova izvješća o profilu](profile-reports.md) i [Izrada i uređivanje prilagođenih izvješća](custom-reports.md).

**Upotreba segmenata uvida u ciljnu skupinu u izvješćima uvida o angažmanu**

1. Na stranici **Radni prostor** odaberite **Podaci**, a zatim karticu **Segmenti**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Odaberite karticu Segmenti.":::

   >[!NOTE]
   > Odabirom segmenta uvida u ciljnu skupinu doći ćete na uvide u ciljnu skupinu gdje možete saznati kako je taj segment izrađen u pogledu pravila i logike. Više informacija o segmentima uvida u ciljnu skupinu potražite u članku [Prikaz i izrada segmenata](../audience-insights/segments.md).

2. Odaberite gotovo izvješće ili [izradite prilagođeno izvješće](custom-reports.md), a zatim odaberite **Dodaj uvjet**. (Za ovaj smo primjer odabrali izvješće **Pregledi stranice**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Dodajte uvjet.":::

3. Odaberite **Filtriranje po segmentima**, proširite popis **Vrsta segmenta**, a zatim odaberite **Demografski**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Odaberite vrstu segmenta Demografski.":::

4. Proširite popis **Naziv segmenta**, a zatim odaberite segment uvida u ciljnu skupinu.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Odaberite segment.":::

5. Možete primijeniti jedan ili više segmenata, uključujući segmente ponašanja (uvidi u angažman) i demografske segmente (uvidi u ciljnu skupinu). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Izvješće o prikazima stranice ograničeno je na korisnike iz SAD-a i segmente početne stranice.":::

Na prethodnoj slici odabrani su segmenti **Klijenti iz SAD-a** i **Početna stranica** čime se izvješće **Prikazi stranice** ograničava na prikaz samo ta dva segmenta. 


>[!NOTE]
> Segmente uvida u ciljnu skupinu možete upotrebljavati za filtriranje gotovih izvješća, prilagođenih izvješća i kanala uvida u angažman. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]