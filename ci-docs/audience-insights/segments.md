---
title: Stvaranje i upravljanje segmentima
description: Izradite segmente klijenata da biste ih grupirali na temelju različitih atributa.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405346"
---
# <a name="create-and-manage-segments"></a>Stvaranje i upravljanje segmentima

Segmenti vam omogućuju grupiranje klijenata na temelju demografskih, transakcijskih ili bihevioralnih atributa. Možete koristiti segmente za ciljanje promotivnih kampanja, prodajnih aktivnosti i radnji za korisničku podršku kako biste postigli svoje poslovne ciljeve.

Složene filtre možete definirati oko entiteta Profil klijenta i povezanih entiteta. Nakon obrade, svaki segment stvara skup zapisa o klijentima koji možete izvesti i koristiti za rad. Primjenjuju se neka [ograničenja usluge](service-limits.md).

Ako nije drugačije navedeno, svi segmenti jesu **Dinamički segmenti** koji se redovito osvježavaju.

Sljedeći primjer prikazuje način upotrebe segmentacije. Definirali smo segment za klijente koji su naručili najmanje $500 robe u posljednjih 90 dana *i* koji su bili uključeni u poziv službe za korisnike koji je eskalirao.

> [!div class="mx-imgBorder"]
> ![Više grupa](media/segmentation-group1-2.png "Više grupa")

## <a name="create-a-new-segment"></a>Izrada novog segmenta

Segmentima se upravlja na stranici **Segmenti**.

1. U uvidima u ciljnu skupinu idite na stranicu **Segmenti**.

2. Odaberite **Novo** > **Prazni segment**.

3. U oknu **Novi segment** odaberite vrstu segmenta i navedite **Naziv**.

   Po želji navedite zaslonski naziv i opis koji pomaže u prepoznavanju segmenta.

4. Odaberite **Dalje** da biste pristupili stranici **Alat za sastavljanje segmenata** na kojoj definirate grupu. Grupa je skup klijenata.

5. Odaberite entitet koji uključuje atribut za koji želite segmentiranje.

6. Odaberite atribut za segmentaciju. Ovaj atribut može imati jednu od četiri vrste vrijednosti: numeričku, niz, datum ili Booleov izraz.

7. Odaberite operatora i vrijednost za odabrani atribut.

   > [!div class="mx-imgBorder"]
   > ![Prilagođeni filtar grupe](media/customer-group-numbers.png "Filtar grupe klijenata")

   |Broj |Definicija  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribut          |
   |3    |Operater         |
   |4    |Value         |

8. Ako je entitet povezan s objedinjenim entitetom klijenta putem [odnosa](relationships.md), morate definirati putanju odnosa za stvaranje valjanog segmenta. Dodajte entitete s putanje odnosa sve dok ne možete odabrati entitet **Klijent: CustomerInsights** s padajućeg izbornika. Zatim odaberite **Svi zapisi** za svaki uvjet.

   > [!div class="mx-imgBorder"]
   > ![Putanja odnosa tijekom stvaranja segmenta](media/segments-multiple-relationships.png "Putanja odnosa tijekom stvaranja segmenta")

9. Odaberite **Spremi** da biste spremili segment. Segment će se spremiti i obraditi ako su potvrđeni svi zahtjevi. U protivnom će se spremiti kao skica.

10. Odaberite **Natrag na segmente** za povratak na stranicu **Segmenti**.

## <a name="manage-existing-segments"></a>Upravljanje postojećim segmentima

Na stranici **Segmenti** možete pregledati sve spremljene segmente i upravljati njima.

Svaki segment predstavljen je retkom koji sadrži dodatne informacije o segmentu.

Segmente možete sortirati u stupcu odabirom zaglavlja stupca.

Za filtriranje segmenata koristite okvir **Traži** u gornjem desnom kutu.

> [!div class="mx-imgBorder"]
> ![Mogućnosti za upravljanje postojećim segmentom](media/segments-selected-segment.png "Mogućnosti za upravljanje postojećim segmentom")

Sljedeća je radnja dostupna kada odaberete segment:

- **Prikaz** pojedinosti o segmentu, uključujući trend broja članova, pretpregled članova segmenta.
- **Uredi** segment da promijeni svoja svojstva.
- **Osvježi** segment tako da uključuje najnovije podatke.
- **Aktiviraj** ili **Deaktiviraj** segment. Segmenti imaju dva moguća stanja – aktivno ili neaktivno. Ta su stanja praktična tijekom uređivanja segmenta. Za neaktivne segmente definicija segmenta postoji, ali još ne sadrži korisnike. Kada aktivirate segment, njegovo se stanje mijenja iz „neaktivan” u „aktivan” i on počinje tražiti klijente koji pristaju definiciji segmenta. Ako je konfigurirano [planirano osvježavanje](system.md#schedule-tab), neaktivni segmenti imaju **Status** naveden kao **Preskočen**, što ukazuje da osvježenje nije ni pokušano. Kad se aktivira neaktivni segment, osvježit će se i uključiti u planirana osvježavanja.
  Umjesto toga, možete koristiti funkcionalnost **Zakaži kasnije** u padajućem izborniku **Aktiviraj/deaktiviraj** kako biste odredili budući datum i vrijeme aktivacije i deaktivacije određenog segmenta.
- **Preimenuj** segment.
- **Preuzmi** popis članova kao .CSV datoteku.
- Mogućnost **Dodaj u** šalje popis korisničkih ID-a u segmentu na obradu u drugu aplikaciju.
- **Izbriši** segment.

## <a name="refresh-segments"></a>Osvježavanje segmenata

Možete osvježiti sve segmente odjednom odabirom mogućenosti **Osvježi sve** na stranici **Segmenti** ili možete osvježiti jedan ili više segmenata kada ih odaberete i zatim među opcijama odaberete **Osvježi**. Možete i konfigurirati ponavljajuće osvježavanje na **Admin** > **Sustav** > **Raspored**.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies). Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla. Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.

## <a name="download-and-export-segments"></a>Preuzimanje i izvoz segmenata

Možete preuzeti segmente u CSV datoteku ili ih izvesti u sustav Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Preuzimanje segmenata u CSV datoteku

1. U uvidima u ciljnu skupinu idite na stranicu **Segmenti**.

2. Odaberite trotočku na pločici određenog segmenta.

3. Odaberite **Preuzmi kao CSV** s padajućeg popisa akcija.

### <a name="export-segments-to-dynamics-365-sales"></a>Izvoz segmenata u sustav Dynamics 365 Sales

Prije izvoza segmenata u sustav Dynamics 365 Sales administrator treba [stvoriti odredište za izvoz](export-destinations.md) za Dynamics 365 Sales.

1. U uvidima u ciljnu skupinu idite na stranicu **Segmenti**.

2. Odaberite trotočku na pločici određenog segmenta.

3. Odaberite **Dodaj u** s padajućeg popisa radnji i odaberite odredište za izvoz na koje želite poslati podatke.

## <a name="draft-mode-for-segments"></a>Način skice za segmente

Ako nisu ispunjeni svi zahtjevi za obradu segmenta, segment možete spremiti kao skicu i pristupiti mu sa stranice **Segmenti**.

Spremit će se kao neaktivni segment i neće ga biti moguće aktivirati dok nije valjan.

## <a name="add-more-conditions-to-a-group"></a>Dodavanje dodatnih uvjeta grupi

Da biste grupi dodali više uvjeta, možete upotrijebiti dva logička operatora:

- Operator **I**: oba uvjeta moraju biti ispunjena kao dio postupka segmentacije. Ova je mogućnost najkorisnija kada definirate uvjete u različitim entitetima.

- Operator **ILI**: jedan od uvjeta mora biti ispunjen kao dio postupka segmentacije. Ova je mogućnost najkorisnija kada definirate više uvjeta za isti entitet.

   > [!div class="mx-imgBorder"]
   > ![Operator ILI ako je potrebno ispuniti bilo koji uvjet](media/segmentation-either-condition.png "Operator ILI ako je potrebno ispuniti bilo koji uvjet")

Trenutačno je moguće ugnijezditi operator **ILI** pod operatorom **I**, ali ne i obratno.

## <a name="combine-multiple-groups"></a>Kombiniranje više grupa

Svaka grupa proizvodi određeni skup klijenata. Te grupe možete kombinirati da biste uključili klijente koji su potrebni za vaš poslovni slučaj.

1. U uvidima u ciljnu skupinu idite na stranicu **Segmenti** i odaberite segment.

2. Odaberite **Dodaj grupu**.

   > [!div class="mx-imgBorder"]
   > ![Grupa za dodavanje grupe klijenata](media/customer-group-add-group.png "Grupa za dodavanje grupe klijenata")

3. Odaberite jedan od sljedećih operatora skupa: **Unija**, **Sjecište** ili **Osim**.

   > [!div class="mx-imgBorder"]
   > ![Unija za dodavanje grupe klijenata](media/customer-group-union.png "Unija za dodavanje grupe klijenata")

   Odaberite skup operatora za definiranje nove grupe. Spremite različite grupe da bi se odredilo koji će se podaci zadržati:

   - **Unija** objedinjuje dvije grupe.

   - **Unakrsno** preklapa dvije grupe. Samo podaci koji su *zajednički* u obje grupe zadržavaju se u objedinjenoj grupi.

   - **Izuzmi** kombinira dvije grupe. Zadržavaju se samo podaci u grupi A koji *nisu zajednički* s podacima grupe B.

## <a name="view-processing-history-and-segment-members"></a>Prikaz povijesti obrade i članova segmenta

Konsolidirane podatke o segmentu možete vidjeti prikazom njegovih pojedinosti.

Na stranici **Segmenti** odaberite segment koji želite pregledati.

Gornji dio stranice sadrži grafikon trenda koji prikazuje promjene u broju članova. Zadržite pokazivač iznad podataka da biste vidjeli broj članova na određeni datum.

Možete ažurirati vremenski okvir vizualizacije.

> [!div class="mx-imgBorder"]
> ![Vremenski raspon segmenta](media/segment-time-range.png "Vremenski raspon segmenta")

U donjem dijelu nalazi se popis članova segmenta.

> [!NOTE]
> Polja koja se pojavljuju na tom popisu temelje se na atributima entiteta segmenta.
>
>Popis je pregled odgovarajućih članova segmenta i pokazuje prvih 100 zapisa vašeg segmenta tako da ga po potrebi možete brzo procijeniti i pregledati njegove definicije. Da biste prikazali sve odgovarajuće zapise, morate [izvesti segment](export-destinations.md).

## <a name="quick-segments"></a>Brzi segmenti

Pored alata za stvaranje segmenata, postoji još jedan put za stvaranje segmenata. Brzi segmenti omogućavaju vam brzu izradu jednostavnih segmenata s jednim operatorom uz trenutačne uvide.

1. Na stranici **Segmenti** odaberite **Novo** > **Brzo stvorite od**.

   - Odaberite opciju **Profili** za stvaranje segmenta koji se temelji na jedinstvenom entitetu klijenta.
   - Odaberite opciju **Mjere** da biste stvorili segment oko svake vrste mjera atributa klijenta koje ste prethodno stvorili na stranici **Mjere**.
   - Odaberite mogućnost **Inteligencija** za izgradnju segmenta oko jednog od izlaznih entiteta koje ste generirali pomoću mogućnosti **Predviđanja** ili **Prilagođeni modeli**.

2. U dijaloškom okviru **Novi brzi segment** odaberite atribut iz padajućeg izbornika **Polje**.

3. Sustav će pružiti neke dodatne uvide koji će vam pomoći stvoriti bolje segmente svojih klijenata.
   - Za kategorijska polja prikazat ćemo 10 brojeva najboljih kupaca. Odaberite **Vrijednost** te **Pregled**.

   - Za numerički atribut sustav će pokazati koja vrijednost atributa spada pod svaki postotak klijenta. Odaberite **Operator** i **Vrijednost**, a zatim odaberite **Pregled**.

4. Sustav će vam pružiti **Procijenjenu veličinu segmenta**. Možete odabrati želite li generirati definirani segment ili ga prvo pregledati kako biste dobili drugu veličinu segmenta.

    > [!div class="mx-imgBorder"]
    > ![Naziv i procjena brzog segmenta](media/quick-segment-name.png "Naziv i procjena brzog segmenta")

5. Unesite **Naziv** segmenta. Po želji možete unijeti i **Zaslonski naziv**.

6. Odaberite **Spremi** kako biste stvorili segment.

7. Nakon dovršetka obrade segmenta možete ga pregledati kao i bilo koji drugi segment koji ste stvorili.

Za sljedeće scenarije savjetujemo upotrebu alata za stvaranje segmenata umjesto preporučenih mogućnosti segmentacije:

- Stvaranje segmenata s filtrima na kategorijskim poljima gdje se operator razlikuje od operatora **Je**
- Stvaranje segmenata s filtrima na numeričkim poljima gdje se operator razlikuje od operatora **Između**, **Više od** i **Manje od**
- Stvaranje segmenata s filtrima na poljima vrste datuma

## <a name="next-steps"></a>Sljedeći koraci

[Izvezite segment](export-destinations.md) i istražite [Korisničku karticu](customer-card-add-in.md) i [Poveznike](export-power-bi.md) da biste dobili uvide na razini klijenta.
