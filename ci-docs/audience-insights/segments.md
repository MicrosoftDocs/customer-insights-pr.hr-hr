---
title: Segmenti u uvidima u ciljne skupine
description: Pregled segmenata i upute za stvaranje segmenata i upravljanje segmentima.
ms.date: 03/30/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 68e71df3853470af47228c7365f25db3a71d15b0
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529530"
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

Idite na **stranicu Segmenti da biste pogledali** sve spremljene segmente i upravljali njima.

Svaki segment predstavljen je retkom koji sadrži dodatne informacije o segmentu.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Odabrani segment s padajućim popisom opcija i dostupnim opcijama." lightbox="media/segments-selected-segment.png":::

Prilikom odabira segmenta dostupne su sljedeće akcije:

- **Prikaz** pojedinosti o segmentu, uključujući trend broja članova, pretpregled članova segmenta.
- **Preuzmi** popis članova kao .CSV datoteku.
- **Uredi** segment da promijeni svoja svojstva.
- **Stvorite duplikat** segmenta. Možete odmah urediti njegova svojstva ili jednostavno spremiti duplikat.
- **Osvježi** segment tako da uključuje najnovije podatke.
- **Aktiviraj** ili **Deaktiviraj** segment. Za neaktivne segmente definicija segmenta postoji, ali još ne sadrži korisnike. Aktivni segment traži kupce koji odgovaraju definiciji segmenta. Ako je konfigurirano [planirano osvježavanje](system.md#schedule-tab), neaktivni segmenti imaju **Status** naveden kao **Preskočen**, što ukazuje da osvježenje nije ni pokušano. Kad se aktivira neaktivni segment, osvježit će se i uključiti u planirana osvježavanja.
  Umjesto toga, možete koristiti funkcionalnost **Zakaži kasnije** u padajućem izborniku **Aktiviraj/deaktiviraj** kako biste odredili budući datum i vrijeme aktivacije i deaktivacije određenog segmenta.
- **[Pronađite slične kupce](find-similar-customer-segments.md)** iz segmenta.
- **Preimenuj** segment.
- **Oznaka** za [upravljanje strukturnim oznakama](work-with-tags-columns.md#manage-tags) za segment.
- **Preuzmi** popis članova kao .CSV datoteku.
- **Upravljajte izvozima** da biste vidjeli segment povezan s izvozom i upravljali njime. [Saznajte više o izvozima.](export-destinations.md)
- **Izbriši** segment.
- **Stupci** za [prilagodbu stupaca](work-with-tags-columns.md#customize-columns) koji se prikazuju.
- **Filtrirajte** za filtriranje [na strukturnim oznakama](work-with-tags-columns.md#filter-on-tags).
- **Naziv** za pretraživanje radi pretraživanja prema nazivu segmenta.

## <a name="refresh-segments"></a>Osvježavanje segmenata

Možete osvježiti sve segmente odjednom odabirom mogućenosti **Osvježi sve** na stranici **Segmenti** ili možete osvježiti jedan ili više segmenata kada ih odaberete i zatim među opcijama odaberete **Osvježi**. Možete i konfigurirati ponavljajuće osvježavanje na **Admin** > **Sustav** > **Raspored**. Kada je konfigurirano ponavljajuće osvježavanje, primjenjuju se sljedeća pravila:
- Svi segmenti s vrstom **Dinamička** ili **Ekspanzija** automatski će se osvježiti na postavljenoj kadenci. Kada je osvježavanje dovršeno **, status** pokazuje je li bilo problema s osvježavanjem segmenta. Posljednji **osvježeni** prikazuje vremensku oznaku posljednjeg uspješnog osvježavanja. Ako dođe do pogreške, odaberite pogrešku da biste vidjeli detalje o tome što se dogodilo.
- Segmenti vrste **Statik** *neće* se automatski osvježavati. Posljednji **osvježeni** prikazuje vremensku oznaku posljednjeg pokretanja ili osvježavanja statičkih segmenata ručno.

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
