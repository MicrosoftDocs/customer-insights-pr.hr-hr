---
title: Pregled segmenata
description: Pregled segmenata i upute za stvaranje segmenata i upravljanje segmentima.
ms.date: 05/20/2022
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
ms.openlocfilehash: 4bcfbb50b893ca7e6ec4607d3c156a3c6979f775
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170672"
---
# <a name="segments-overview"></a>Pregled segmenata

Segmenti vam omogućuju grupiranje klijenata na temelju demografskih, transakcijskih ili bihevioralnih atributa. Možete koristiti segmente za ciljanje promotivnih kampanja, prodajnih aktivnosti i radnji za korisničku podršku kako biste postigli svoje poslovne ciljeve.

Profili kupaca koji odgovaraju filtrima definicije segmenta nazivaju se *članovima* segmenta. Primjenjuju se neka [ograničenja usluge](/dynamics365/customer-insights/service-limits).

## <a name="create-a-segment"></a>Izrada segmenta

Odaberite način stvaranja segmenta na temelju ciljnog publika.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- Složeni segmenti s sastavljačem segmenata: [Izgradite vlastiti](segment-builder.md)
- Jednostavni segmenti s jednim operatorom: [Brzi segment](segment-quick.md)
- Način pronalaženja sličnih kupaca koji pokreću umjetnu inteligenciju: [Slični kupci](find-similar-customer-segments.md)
- Prijedlozi utemeljeni na umjetnoj inteligenciji koji se temelje na mjerama ili atributima: [Predloženi segmenti koji se temelje na mjerama](suggested-segments.md)
- Prijedlozi na temelju aktivnosti: [Predloženi segmenti na temelju aktivnosti klijenata](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

- Jednostavni ili složeni segmenti s sastavljačem segmenata: [Izgradite vlastite](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Upravljanje postojećim segmentima

Idite na **stranicu Segmenti** da biste vidjeli segmente koje ste stvorili, njihov status i stanje, broj članova i posljednji put kada su podaci osvježeni. Popis segmenata možete sortirati po bilo kojem stupcu ili pomoću okvira za pretraživanje pronaći segment kojim želite upravljati.

Odaberite segment za prikaz dostupnih akcija.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Odabrani segment s padajućim popisom opcija i dostupnim opcijama." lightbox="media/segments-selected-segment.png":::

- [**Pogledajte**](#view-segment-details) detalje segmenta, uključujući trend broja članova i pregled članova segmenta.
- **Preuzmi** popis članova kao .CSV datoteku.
- **Uredi** segment da promijeni svoja svojstva.
- **Stvorite duplikat** segmenta. Možete odmah urediti njegova svojstva ili spremiti duplikat.
- [**Osvježite**](#refresh-segments) segment tako da uključuje najnovije podatke.
- **Aktiviraj** ili **Deaktiviraj** segment. Neaktivni segmenti neće se osvježiti tijekom zakazanog [osvježavanja](system.md#schedule-tab) i status je **naveden** kao **Preskočen**, što znači da osvježavanje nije ni pokušano. Aktivni segmenti osvježavaju se na temelju njihove vrste: statični ili dinamički.
- **Postavite statiku** ili **učinite dinamičkom** vrstu segmenta. Statični segmenti moraju se ručno osvježiti. Dinamički segmenti automatski se osvježavaju tijekom osvježavanja sustava.
- [**Pronađite slične kupce**](find-similar-customer-segments.md) iz segmenta.
- **Preimenuj** segment.
- **Oznaka** za [upravljanje strukturnim oznakama](work-with-tags-columns.md#manage-tags) za segment.
- [**Upravljajte izvozom**](#export-segments) da biste vidjeli segmente povezane s izvozom i upravljali njima. [Saznajte više o izvozima.](export-destinations.md)
- **Izbriši** segment.
- **Stupci** za [prilagodbu stupaca](work-with-tags-columns.md#customize-columns) koji se prikazuju.
- **Filtrirajte** za filtriranje [na strukturnim oznakama](work-with-tags-columns.md#filter-on-tags).
- **Naziv** za pretraživanje radi pretraživanja prema nazivu segmenta.

## <a name="view-segment-details"></a>Prikaz detalja o segmentu

**Na stranici Segmenti** odaberite segment za prikaz povijesti obrade i članova segmenta.

Gornji dio stranice sadrži grafikon trenda koji prikazuje promjene u broju članova. Zadržite pokazivač iznad podataka da biste vidjeli broj članova na određeni datum. Promijenite vremenski okvir vizualizacije.

:::image type="content" source="media/segment-time-range.png" alt-text="Vremenski raspon segmenta.":::

U donjem dijelu nalazi se popis članova segmenta.

> [!NOTE]
> Polja koja se pojavljuju na tom popisu temelje se na atributima entiteta segmenta.
>
>Popis je pregled odgovarajućih članova segmenta i pokazuje prvih 100 zapisa vašeg segmenta tako da ga po potrebi možete brzo procijeniti i pregledati njegove definicije. Da biste vidjeli sve podudarne zapise, [izvezite segment](export-destinations.md).

## <a name="refresh-segments"></a>Osvježavanje segmenata

Segmenti se mogu osvježiti prema automatskom rasporedu ili ručno osvježiti na zahtjev. Da biste ručno osvježili jedan ili više segmenata, odaberite ih i odaberite **Osvježi**.

Da biste [zakazali automatsko osvježavanje](system.md#schedule-tab), idite na **Raspored** > **administratorskih** > **sustava**. Primjenjuju se sljedeća pravila:

- Svi segmenti s vrstom **Dinamička** ili **Ekspanzija** automatski će se osvježiti na postavljenoj kadenci. Nakon dovršetka osvježavanja status **pokazuje** je li bilo problema s osvježavanjem segmenta. Posljednji **osvježeni** prikazuje vremensku oznaku posljednjeg uspješnog osvježavanja. Ako dođe do pogreške, odaberite pogrešku da biste vidjeli detalje o tome što se dogodilo.
- Segmenti vrste **Statik** *neće* se automatski osvježavati. Posljednji **osvježeni** prikazuje vremensku oznaku posljednjeg pokretanja ili osvježavanja statički segment ručno.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Izvoz segmenata

Izvezite segmente u druge aplikacije da biste dalje koristili podatke. Izvezite segment sa stranice segmenata ili sa stranice [izvoza](export-destinations.md).

1. Idite na **stranicu Segmenti** i odaberite segment koji želite izvesti.

1. Odaberite **Upravljanje izvozom**. Otvorit će se stranica **Izvozi (pretpregled) za segment**. Prikažite sve konfigurirane izvoze grupirane prema tome sadrže li trenutni segment ili ne.

   1. Da biste odabrani segment dodali izvozu, s pomoću opcije **Uredi** uredite odgovarajući izvoz da biste odabrali odgovarajući segment, a zatim spremite. U okruženjima za pojedinačne kupce odaberite izvoz na popisu i odaberite **Dodaj segment** da biste postigli isti ishod.

   1. Da biste stvorili novi izvoz s odabranim segmentom, odaberite **Dodaj izvoz**. Dodatne informacije o stvaranju izvoza potražite u odjeljku [Postavljanje novog izvoza](export-destinations.md#set-up-a-new-export).

1. Odaberite **Natrag** za povratak na glavnu stranicu za segmente.

## <a name="track-usage-of-a-segment"></a>Praćenje korištenja segmenta

Ako koristite segmente u aplikacijama koje se temelje na istoj Microsoft Dataverse organizaciji koja je povezana s Customer Insights, možete pratiti upotrebu segmenta. Za [segmente Customer Insights koji se koriste u korisničkim putovanjima sustava Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), sustav vas informira o korištenju tog segmenta.

Prilikom uređivanja segmenta koji se koristi u okruženju Customer Insights ili u put klijenta u marketingu, natpis u [sastavljaču](segment-builder.md) segmenata obavještava vas o ovisnostima. Provjerite detalje o zavisnosti izravno s natpisa ili odabirom **Mogućnosti** korištenja u sastavljaču segmenata.

Okno **korištenja** segmenta prikazuje detalje o korištenju ovog segmenta u Dataverse aplikacijama koje se temelje na njima. Za segmente koji se koriste na putovanjima kupaca pronaći ćete vezu za pregled putovanja u marketingu gdje se taj segment koristi. Ako imate dozvole za pristup aplikaciji Marketing, tamo pogledajte više detalja.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Bočno okno s pojedinostima o korištenju segmenta u sastavljaču segmenata.":::

Sustav vas obavještava o korištenju praćenog segmenta kada ga pokušate izbrisati. Ako se segment koji ćete izbrisati koristi u put klijenta u marketingu, to će se putovanje zaustaviti za sve korisnike u segmentu. Ako je putovanje dio marketinške kampanje, brisanje će utjecati na samu tu kampanju. Međutim, i dalje možete izbrisati segment unatoč upozorenjima.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dijaloški okvir za potvrdu brisanja segmenta kada se segment koristi u aplikaciji Dataverse .":::

### <a name="supported-apps"></a>Podržane aplikacije

Korištenje se trenutno prati u sljedećim Dataverse aplikacijama koje se temelje na programu:

- [Putovanja korisnika u sustavu Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
