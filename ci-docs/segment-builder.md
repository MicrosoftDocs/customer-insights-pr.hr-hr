---
title: Stvaranje složenih segmenata pomoću sastavljača segmenata
description: Pomoću sastavljača segmenata koristite za stvaranje složenih segmenata kupaca grupiranjem na temelju različitih atributa.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304740"
---
# <a name="create-complex-segments-with-segment-builder"></a>Stvaranje složenih segmenata pomoću sastavljača segmenata

Definirajte složene filtre oko jedinstvenog klijenta ili jedinstvenog kontakta i povezanih entiteta. Svaki segment, nakon obrade, kreira skup zapisa o kupcu ili kontaktima koje možete izvesti i poduzeti akciju.

> [!TIP]
> Segmenti temeljeni na **pojedinačnim klijentima** automatski uključuju dostupne podatke za kontakt za brojeve segmenta. Ako **na poslovnim poslovnim subjektima** objedinite [poslovne](data-unification.md) subjekte i kontakte, odaberite temelji li se segment na poslovnim subjektima ili poslovnim kontaktima. Da biste izvezli na odredište očekujući podatke za kontakt, koristite segment kontakata. Da biste izvezli na odredište očekujući podatke o računu, koristite segment računa.

## <a name="segment-builder"></a>Graditelj segmenata

Sljedeća slika prikazuje različite aspekte graditelja segmenata. Prikazuje segment koji rezultira grupom klijenata. Klijenti su naručili robu u određenom vremenskom okviru i prikupili nagradne bodove ili su potrošili određeni iznos novca.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementi sastavljača segmenata." lightbox="media/segment-builder-overview.png":::

1. Organizirajte svoj segment pravilima i podpravilima. Svako pravilo ili podpravilo sastoji se od uvjeta. Kombinirajte uvjete s logičkim operatorima.

1. Odaberite [putanju odnosa](relationships.md) između entiteta koja se primjenjuje na pravilo. Putanja odnosa određuje koji se atributi mogu koristiti u uvjetu.

1. Upravljajte pravilima i podpravilima. Promijenite položaj pravila ili ga izbrišite.

1. Dodajte uvjete i izgradite odgovarajuću razinu ugnježđivanja s pomoću podpravila.

1. Primijenite zadane operacije na povezana pravila.

1. S pomoću okna atributa dodajte dostupne atribute entiteta ili izradite uvjete na temelju atributa. Okno prikazuje popis entiteta i atributa na temelju odabrane putanje odnosa koji su dostupni za odabrano pravilo.

1. Dodajte uvjete na temelju atributa postojećim pravilima i podpravilima ili ih dodajte novom pravilu.

1. Poništite i ponovite promjene tijekom sastavljanja segmenta.

Gornji primjer ilustrira sposobnost segmentacije. Definirali smo segment za klijente koji su na mreži kupili najmanje $500 robe *i* imaju interes za razvoj softvera.

## <a name="create-a-new-segment-with-segment-builder"></a>Stvaranje novog segmenta pomoću sastavljača segmenata

1. Idite na **Segmenti**.

1. Odaberite **Novo** > **Izgradi vlastiti**. Na stranici sastavljača segmenata definirate ili sastavljate pravila. Pravilo se sastoji od jednog ili više uvjeta koji definiraju skup klijenata.

   > [!NOTE]
   > Za okruženja koja se temelje na poslovnim računima odaberite **Novi** > **segment poslovnih subjekata** ili **Segment kontakata (pretpregled)** na temelju vrste segmenta koji želite kreirati. Ako je hijerarhija računa [definirana i želite stvoriti pravila za filtriranje podataka na temelju podređenog](relationships.md#set-up-account-hierarchies) i nadređenog odnosa, odaberite **Koristi hijerarhiju? (pretpregled)**, odaberite hijerarhiju, a zatim **Primijeni**.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Okno hijerarhije odabranog računa segmenta.":::

1. Uz stavku Segment bez naslova odaberite **Uređivanje detalja**. Navedite naziv za svoj segment i ažurirajte predloženi **Naziv izlaznog entiteta** za segment. Po želji dodajte opis i [oznake](work-with-tags-columns.md#manage-tags) segmentu.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dijaloški okvir Uređivanje detalja.":::

1. U sekciji **Pravilo1** odaberite atribut entiteta po kojem želite filtrirati klijente. Postoje dva načina za odabir atributa:
   - Pregledajte popis dostupnih entiteta i atributa u oknu **Dodaj u pravilo** i odaberite ikonu **+** pored atributa za dodavanje. Odaberite želite li atribut dodati postojećem pravilu ili ga koristiti za stvaranje novog pravila.
   - Upišite naziv atributa u odjeljak pravila da biste vidjeli odgovarajuće prijedloge.

1. Odaberite operatore za navođenje podudarnih vrijednosti uvjeta. Atribut može imati jednu od četiri vrste podataka kao vrijednost: numeričku, niz, datum ili Booleovu vrijednost. Ovisno o vrsti podataka atributa, za navođenje uvjeta dostupni su različiti operatori.

1. Odaberite **Dodaj uvjet** za dodavanje više uvjeta u pravilo. Da biste stvorili pravilo prema trenutnom pravilu, odaberite **Dodaj pod-pravilo**.

1. Ako pravilo koristi druge entitete osim entiteta *Klijent* (ili *entiteta ContactProfile* za B-do-B), odaberite **Postavi put** odnosa da biste mapirali odabrani entitet u entitet jedinstvenog klijenta. Ako postoji samo jedan mogući put odnosa, sustav ga automatski odabire. Različiti [putovi](relationships.md#relationship-paths) odnosa mogu dati različite rezultate. Svako pravilo može imati svoju vlastitu putanju odnosa.

   :::image type="content" source="media/relationship-path.png" alt-text="Potencijalna putanja odnosa prilikom stvaranja pravila na temelju entiteta mapiranog u objedinjeni entitet klijenta.":::

1. Ako u pravilu imate više uvjeta, odaberite koji ih logički operator povezuje.  
   - Operator **AND**: Svi uvjeti moraju biti ispunjeni za uključivanje zapisa u segment. Ovu mogućnost koristite kada definirate uvjete u različitim entitetima.
   - Operator **OR**: Svi uvjeti moraju biti ispunjeni za uključivanje zapisa u segment. Ovu mogućnost koristite kada definirate više uvjeta za isti entitet.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Pravilo s dva uvjeta AND.":::

   Prilikom korištenja operatora OR svi se uvjeti moraju temeljiti na entitetima uključenima u putanju odnosa.

1. Da biste stvorili različite skupove zapisa o klijentima, stvorite više pravila. Da biste uključili kupce potrebne za vaš poslovni slučaj, kombinirajte grupe. Konkretno, ako ne možete uključiti entitet u pravilo zbog navedenog puta odnosa, stvorite novo pravilo za odabir atributa iz njega.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Dodajte novo pravilo segmentu i odaberite operator skupa.":::

   1. Odaberite **Dodaj pravilo**.
   1. Odaberite jednog od postavljenih operatora: **Unija**, **Unakrsno** ili **Izuzmi**.

      - **Unija** objedinjuje dvije grupe.
      - **Unakrsno** preklapa dvije grupe. Samo podaci koji *su zajednički* objema grupama ostaju u objedinjenoj grupi.
      - **Izuzmi** kombinira dvije grupe. Zadržavaju se samo podaci u grupi A koji *nisu zajednički* podacima u grupi B.

1. Prema zadanim postavkama izlazni entitet automatski će sadržavati sve atribute korisničkih profila koji odgovaraju definiranim filtrima. U B-do-B prilikom korištenja entiteta *ContactProfile* automatski se uključuje ID računa. Ako se segment temelji na drugim entitetima osim na entitetu *Kupac* ili da bi uključio više atributa iz *ContactProfilea*, odaberite **Atributi** Projekta da biste izlaznom entitetu dodali više atributa iz tih entiteta.
 
   Na primjer: segment se temelji na entitetu koji sadrži podatke o kupnji, koji su povezani s entitetom *Klijent*. Segment traži sve klijente iz Španjolske koji su kupili robu u tekućoj godini. Možete odabrati dodavanje atributa kao što su cijena robe ili datum nabave svim podudarnim zapisima kupaca u izlaznom entitetu. Ove informacije mogu biti korisne za analizu sezonskih korelacija s ukupnom potrošnjom.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Primjer projiciranih atributa odabranih u bočnom oknu za dodavanje izlaznom entitetu.":::
 
   Uzorak izlaza za segment koji se temelji na poslovnim računima s predviđenim atributima kontakata mogao bi izgledati ovako:

   |ID  |Ime kupca  |Prihod  |Naziv kontakta  | Uloga kontakta|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100 tisuća | [Abbie Moss, Ruth Soto]  | [Generalni direktor, Voditelj nabave]

   > [!NOTE]
   > - **Atributi projekta funkcioniraju** samo za entitete koji imaju odnos jedan-prema-više s entitetom *Kupac* ili *ContactProfile*. Na primjer, jedan klijent može imati više pretplata.
   > - Ako je atribut koji želite projicirati udaljen više od jednog skoka od *entiteta Kupac* ili *ContactProfile*, kako je definirano odnosom, taj bi se atribut trebao koristiti u svakom pravilu upita segmenta koji gradite.
   > - Ako je atribut koji želite projicirati samo jedan skok udaljen od *entiteta Customer* ili *ContactProfile*, taj atribut ne mora biti prisutan u svakom pravilu upita segmenta koji gradite.
   > - **Projicirani atributi** uzimaju se u obzir pri korištenju postavljenih operatora.

1. Odaberite **Pokreni** da biste kreirali segment. Odaberite **Spremi** ako želite zadržati trenutnu konfiguraciju i pokrenuti segment kasnije. Prikazuje se **stranica Segmenti**.

### <a name="segment-builder-tips"></a>Savjeti za izradu segmenata

Prilikom stvaranja segmenta pomoću sastavljača segmenata imajte na umu sljedeće savjete:

- Graditelj segmenata neće predlagati valjane vrijednosti entiteta prilikom postavljanja operatora za uvjete. Možete otići na **Podaci** > **Entiteti** i preuzeti podatke entiteta kako biste vidjeli koje su vrijednosti dostupne.
- Uvjeti koji se temelje na datumima omogućuju prebacivanje između fiksnih datuma i plutajućeg raspona datuma.
- Ako imate više pravila za segment, pokraj pravila koje uređujete nalazi se okomita plava linija.
- Pravila i uvjete možete premjestiti na druga mjesta u definiciji segmenta. Odaberite okomitu trotočje (&vellip;) pokraj pravila ili uvjeta i odaberite kako i gdje je premjestiti.
- Kontrole **Poništi** i **Ponovi** na naredbenoj traci omogućuju vam vraćanje promjena.
- Nakon stvaranja segmenta, neki segmenti omogućuju vam [praćenje korištenja segmenta](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Sljedeći koraci

[Izvezite segment](export-destinations.md) i istražite [integraciju usluge Customer Card](customer-card-add-in.md) za upotrebu segmenata u drugim aplikacijama.

[!INCLUDE [footer-include](includes/footer-banner.md)]
