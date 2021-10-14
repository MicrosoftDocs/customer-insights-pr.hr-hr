---
title: Prikaz i stvaranje segmenata
description: Kako stvarati, uređivati i brisati segmente i gdje ih koristiti.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036139"
---
# <a name="view-and-create-segments"></a>Prikaz i stvaranje segmenata

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Segmenti vam omogućuju prepoznavanje podskupova posjetitelja na temelju karakteristika ili interakcija na web-mjestu. Segmenti vam omogućuju primjenu filtara i analizu tih podskupova. Analiza može pomoći u ispitivanju i odgovaranju na trendove u vašem poslovanju. 

:::image type="content" source="media/segments-page.png" alt-text="Snimka zaslona aplikacije za uvide o angažmanu koja prikazuje popis postojećih segmenata u radnom prostoru.":::

## <a name="view-segments"></a>Prikaz segmenata

1. Idite u odjeljak **Podaci** u lijevom navigacijskom oknu. 

1. Odaberite karticu **Segmenti** da biste vidjeli popis svih segmenata u radnom prostoru. 

## <a name="create-a-segment"></a>Izrada segmenta

Segmenti se sastoje od pravila i uvjeta koji su povezani s logičkim operatorima. Uvjeti primjenjuju filtre na odabranu dimenziju. Svaki segment može koristiti do pet dimenzija.

Sljedeći primjer prikazuje segment s dva uvjeta u jednom pravilu. Filtrira sve događaje na web-mjestu gdje je preglednik Chrome, a operativni sustav iOS ili Android.

:::image type="content" source="media/segment-sample.png" alt-text="Primjeri segmenata s dva uvjeta u pravilu za filtriranje događaja na web-mjestu.":::

U ovom odjeljku je opisano kako stvoriti *prazan segment* od početka.

1. Idite u odjeljak **Podaci** > **Segmenti**.

1. Odaberite **Novi segment**.

1. U odjeljku **Biblioteka resursa** odaberite atribut prema kojem želite filtrirati. Trenutno segmente možete stvarati samo na temelju dimenzija.

1. Odaberite operatora i vrijednost za odabrani atribut. Podržane su sljedeće operacije.
   - **je**: zahtijeva točno podudaranje za uključivanje vrijednosti. Koristi **jednako** za jednu vrijednost ili **bilo koje** za uključivanje više vrijednosti.
   - **nije**: zahtijeva točno podudaranje za isključivanje vrijednosti. Koristi **jednako** za jednu vrijednost ili **bilo koje** za uključivanje više vrijednosti.
   - **počinje sa**: niz kojim započinju odgovarajuće vrijednosti.
   - **završava sa**: niz kojim završavaju odgovarajuće vrijednosti.
   - **sadrži**: niz sadržan u odgovarajućim vrijednostima.

1. Da biste grupi dodali više uvjeta, možete upotrijebiti dva logička operatora. Projicirani atributi uzimaju se u obzir pri korištenju postavljenih operatora.
   - Operator **I**: oba uvjeta moraju biti ispunjena kao dio postupka segmentacije. Ova je mogućnost najkorisnija kada definirate uvjete u različitim entitetima.
   - Operator **ILI**: jedan od uvjeta mora biti ispunjen kao dio postupka segmentacije. Ova je mogućnost najkorisnija kada definirate više uvjeta za isti entitet.

1. Odaberite **Spremi** i naziv segmenta. 

Segment će biti naveden na stranici Segmenti i možete ga primijeniti na sva izvješća i kanale u radnom prostoru.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Upotreba segmenta u izvješću ili kanalu

Segmente možete primijeniti na izvješće ili kanal kako biste ih filtrirali na temelju uvjeta u segmentu. Međutim, segmente ne možete primijeniti na izvješće o upotrebi u stvarnom vremenu.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Izvješće o prikazima stranice s proširenim padajućim popisom za odabir segmenata koji će se primijeniti.":::

Da biste primijenili segment, otvorite izvješće ili kanal. Odaberite **Dodaj uvjet** i odaberite **Filtriraj po segmentima**. Odaberite segment s popisa koji želite primijeniti. Segment se primjenjuje na izvješće. Ako grafikon ne podržava segment, prikazuje pogrešku.
 
Možete primijeniti *do tri segmenta* na izvješće ili kanal.

## <a name="edit-a-segment"></a>Uređivanje segmenta

1. Idite u odjeljak **Podaci** > **Segmenti**.
1. Odaberite segment na popisu da biste ga otvorili. 
1. Promijenite ili dodajte vrijednosti po potrebi.
1. Odaberite **Spremi** za primjenu izmjena.

## <a name="change-the-name-of-a-segment"></a>Promjena naziva segmenta

1. Idite u odjeljak **Podaci** > **Segmenti**.
1. Na popisu segmenata odaberite **Više [...]**. 
1. Na padajućem popisu odaberite **Uredi ime**.
1. Unesite novi naziv i odaberite **Preimenuj**.

## <a name="delete-a-segment"></a>Brisanje segmenta

1. Idite u odjeljak **Podaci** > **Segmenti**.
1. Na popisu segmenata odaberite **Više [...]**. 
1. Na padajućem popisu odaberite **Izbriši**.
1. Odaberite **Izbriši** da biste potvrdili.

[!INCLUDE[footer-include](../includes/footer-banner.md)]