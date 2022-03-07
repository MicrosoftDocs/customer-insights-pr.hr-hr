---
title: Prikaz i stvaranje metrike
description: Kako stvarati, uređivati i brisati metriku.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7e8c96f38af74f25080a40fd92e73f05c71320a8
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229807"
---
# <a name="view-and-create-metrics"></a>Prikaz i stvaranje metrike

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Metrika pomaže razumjeti ponašanje vaših posjetitelja. Ona sakuplja svojstva događaja i mjeri statistiku i izvedbu vaših web-svojstava.  

Pretpostavimo da na svom web-mjestu provodite marketinšku promociju. Pomoću metrike možete pratiti broj jedinstvenih posjetitelja ili korisnika koji su posjetili vaše web-mjesto tijekom promocije. Analiza metrike pomaže vam da bolje razumijete ciljnu skupinu svog web-mjesta. Kombiniranje metrike s [dimenzijama](dimensions.md) na [prilagođenom izvješću](custom-reports.md) omogućuje vam mjerenje ponašanja kako biste razumjeli svoje korisnike. Na primjer, posjetitelje možete razdvojiti u nove i povratne kategorije kako biste utvrdili razlike u interesima i namjerama između grupa.

## <a name="view-metrics"></a>Prikaz metrike

Uvidi u angažman uključuju uobičajene agregacije svojstava događaja kao metriku sustava: 

- Posjetitelji
- Posjeti
- Prikazi stranica
- Klikovi

Te se metrike sustava temelje na postojećim svojstvima događaja u osnovnim događajima.

1. Idite u odjeljak **Podaci** u lijevom navigacijskom oknu. 
1. Odaberite karticu **Metrika** da biste vidjeli popis svih metrika u radnom prostoru. 
   > [!NOTE]
   > Metrika koju generira sustav je samo za čitanje. Ne možete je uređivati ili brisati. Stvarati i uređivati možete samo prilagođenu metriku.

## <a name="create-a-metric"></a>Stvaranje metrike

Metriku mogu stvarati administratori okruženja i radnog prostora. Svojstva događaja moraju se poslati u radni prostor prije nego što stvorite metriku. Možete stvoriti metriku na temelju svojstava događaja koja šalju osnovni događaji ili koristiti web SDK za [slanje prilagođenih svojstava događaja](advanced-SDK-implementation.md).

1. Idite u odjeljak **Podaci** > **Metrika**.
1. Odaberite **Nova metrika** da biste otvorili **Biblioteku resursa** i dijaloški okvir **Nova metrika bez naziva**.

   :::image type="content" source="media/new-metric.png" alt-text="Dodajte događaju metriku.":::

1. U dijaloškom okviru **Nova metrika bez naziva** odaberite padajući popis **Format** te odaberite vrstu podataka **Cijeli broj** ili **Dvostruko**. Integer je cijeli broj. Za Dvostruko možete odabrati jedno i tri decimalna mjesta.

   :::image type="content" source="media/create-new-metric.png" alt-text="Stvorite novu metriku.":::
   
5. U oknu **Biblioteka resursa** pronađite svojstvo događaja na kojem će se temeljiti metrika.
6. Odaberite **znak plus (+)** pored svojstva da biste ga koristili u formuli. Formulu možete stvoriti samo na temelju jednog svojstva. 
7. Odaberite jednu od sljedećih agregatnih funkcija. 

   - Zbroj: aritmetički zbroj svih vrijednosti 
   - Prosjek: srednji prosjek svih vrijednosti
   - Broj: ukupan broj vrijednosti
   - Broj različitih vrijednosti: ukupan broj različitih vrijednosti

   Nakon definiranja metrike, vidjet ćete pregled aktivnosti metrike za posljednjih sat vremena.

1. Odaberite **Spremi**. 
1. Unesite naziv za metriku, a zatim odaberite **Spremi**.

Metrika može potrajati do minute prije nego što je možete upotrijebiti za [stvaranje prilagođenih izvješća](custom-reports.md).

## <a name="edit-a-metric"></a>Uređivanje metrike

Možete uređivati samo prilagođenu metriku.

1. Idite u odjeljak **Podaci** > **Metrika**.
1. Odaberite metriku s popisa.
1. Promjena definicije metrike
1. Odaberite **Spremi**.

## <a name="change-the-name-of-a-metric"></a>Promjena naziva metrike

Možete promijeniti samo naziv prilagođene metrike.

1. Idite u odjeljak **Podaci** > **Metrika**.
1. Odaberite **Više [...]** za metriku i odaberite **Uredi naziv**.
1. Promijenite naziv. 
1. Odaberite **Preimenuj**.

## <a name="delete-a-metric"></a>Brisanje metrike

Možete brisati samo prilagođenu metriku.

1. Idite u odjeljak **Podaci** > **Metrika**.
1. Odaberite **Više [...]** za metriku i odaberite **Izbriši**.

   :::image type="content" source="media/delete-metric.png" alt-text="Izbrišite metriku za događaj.":::

1. Odaberite **Izbriši** da biste potvrdili brisanje.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
