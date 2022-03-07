---
title: Segmenti u uvidima u ciljne skupine
description: Pregled segmenata i upute za stvaranje segmenata i upravljanje segmentima.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: c58f79c2beda1083d19bd36d94549ff1a46b096e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355974"
---
# <a name="segments-overview"></a>Pregled segmenata

Segmenti vam omogućuju grupiranje klijenata na temelju demografskih, transakcijskih ili bihevioralnih atributa. Možete koristiti segmente za ciljanje promotivnih kampanja, prodajnih aktivnosti i radnji za korisničku podršku kako biste postigli svoje poslovne ciljeve.

Profili klijenata koji odgovaraju filtrima definicije segmenta nazivaju se *članovima* segmenta. Primjenjuju se neka [ograničenja usluge](/dynamics365/customer-insights/service-limits).

## <a name="create-a-new-segment"></a>Izrada novog segmenta

Postoji više načina za stvaranje novog segmenta: 

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- Složeni segment sa sastavljačem segmenata: [Sastavimo vlastiti](segment-builder.md#create-a-new-segment) 
- Jednostavni segmenti s jednim operatorom: [Brzi segment](segment-builder.md#quick-segments) 
- Način za pronalaženje sličnih klijenata pogonjen umjetnom inteligencijom: [Slični klijenti](find-similar-customer-segments.md) 
- Prijedlozi na temelju mjera ili atributa pogonjeni umjetnom inteligencijom: [Predloženi segmenti za poboljšanje mjera](suggested-segments.md) 
- Prijedlozi na temelju aktivnosti: [Predloženi segmenti na temelju aktivnosti klijenata](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

- Složeni segment sa sastavljačem segmenata: [Sastavimo vlastiti](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Upravljanje postojećim segmentima

Idite na stranicu **Segmenti** da biste pregledali sve svoje spremljene segmente i upravljali njima.

Svaki segment predstavljen je retkom koji sadrži dodatne informacije o segmentu.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Odabrani segment s padajućim popisom opcija i dostupnim opcijama.":::

Sljedeća je radnja dostupna kada odaberete segment:

- **Prikaz** pojedinosti o segmentu, uključujući trend broja članova, pretpregled članova segmenta.
- **Uredi** segment da promijeni svoja svojstva.
- **Stvorite duplikat** segmenta. Možete odmah urediti njegova svojstva ili jednostavno spremiti duplikat.
- **Osvježi** segment tako da uključuje najnovije podatke.
- **Aktiviraj** ili **Deaktiviraj** segment. Segmenti imaju dva moguća stanja – aktivno ili neaktivno. Ta su stanja praktična tijekom uređivanja segmenta. Za neaktivne segmente definicija segmenta postoji, ali još ne sadrži korisnike. Kada aktivirate segment, njegovo se stanje mijenja iz „neaktivan” u „aktivan” i on počinje tražiti klijente koji pristaju definiciji segmenta. Ako je konfigurirano [planirano osvježavanje](system.md#schedule-tab), neaktivni segmenti imaju **Status** naveden kao **Preskočen**, što ukazuje da osvježenje nije ni pokušano. Kad se aktivira neaktivni segment, osvježit će se i uključiti u planirana osvježavanja.
  Umjesto toga, možete koristiti funkcionalnost **Zakaži kasnije** u padajućem izborniku **Aktiviraj/deaktiviraj** kako biste odredili budući datum i vrijeme aktivacije i deaktivacije određenog segmenta.
- **Preimenuj** segment.
- **Preuzmi** popis članova kao .CSV datoteku.
- **Upravljajte izvozima** da biste vidjeli segment povezan s izvozom i upravljali njime. [Saznajte više o izvozima.](export-destinations.md)
- **Izbriši** segment.

## <a name="refresh-segments"></a>Osvježavanje segmenata

Možete osvježiti sve segmente odjednom odabirom mogućenosti **Osvježi sve** na stranici **Segmenti** ili možete osvježiti jedan ili više segmenata kada ih odaberete i zatim među opcijama odaberete **Osvježi**. Možete i konfigurirati ponavljajuće osvježavanje na **Admin** > **Sustav** > **Raspored**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="export-segments"></a>Izvoz segmenata

Segment možete izvesti sa stranice segmenata ili [stranice izvoza](export-destinations.md). 

1. Idite na stranicu **Segmenti**.

1. Odaberite **Prikaži više [...]** za segment koji želite izvesti.

1. Odaberite **Upravljanje izvozom** s padajućeg popisa radnji.

1. Otvorit će se stranica **Izvozi (pretpregled) za segment**. Možete vidjeti sve konfigurirane izvoze grupirane prema tome sadrže li trenutačni segment ili ne.

   1. Da biste odabrani segment dodali izvozu, s pomoću opcije **Uredi** uredite odgovarajući izvoz da biste odabrali odgovarajući segment, a zatim spremite. U okruženjima za pojedinačne klijente umjesto toga možete odabrati izvoz na popisu i odabrati **Dodaj segment** kako bi se postigao isti ishod.

   1. Da biste stvorili novi izvoz s odabranim segmentom, odaberite **Dodaj izvoz**. Dodatne informacije o stvaranju izvoza potražite u odjeljku [Postavljanje novog izvoza](export-destinations.md#set-up-a-new-export).

1. Odaberite **Natrag** za povratak na glavnu stranicu za segmente.

## <a name="view-processing-history-and-segment-members"></a>Prikaz povijesti obrade i članova segmenta

Konsolidirane podatke o segmentu možete vidjeti prikazom njegovih pojedinosti.

Na stranici **Segmenti** odaberite segment koji želite pregledati.

Gornji dio stranice sadrži grafikon trenda koji prikazuje promjene u broju članova. Zadržite pokazivač iznad podataka da biste vidjeli broj članova na određeni datum.

Možete ažurirati vremenski okvir vizualizacije.

> [!div class="mx-imgBorder"]
> ![Vremenski raspon segmenta.](media/segment-time-range.png "Vremenski raspon segmenta")

U donjem dijelu nalazi se popis članova segmenta.

> [!NOTE]
> Polja koja se pojavljuju na tom popisu temelje se na atributima entiteta segmenta.
>
>Popis je pregled odgovarajućih članova segmenta i pokazuje prvih 100 zapisa vašeg segmenta tako da ga po potrebi možete brzo procijeniti i pregledati njegove definicije. Da biste prikazali sve odgovarajuće zapise, morate [izvesti segment](export-destinations.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]