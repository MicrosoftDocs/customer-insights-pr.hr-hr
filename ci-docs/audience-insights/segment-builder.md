---
title: Stvaranje segmenata pomoću graditelja segmenata
description: Izradite segmente klijenata da biste ih grupirali na temelju različitih atributa.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494485"
---
# <a name="create-segments"></a>Stvaranje segmenata

Definirajte složene filtre oko objedinjenog entiteta klijenta i s njime povezanih entiteta. Nakon obrade, svaki segment stvara skup zapisa o klijentima koji možete izvesti i koristiti za rad. Segmentima se upravlja na stranici **Segmenti**. Možete [stvoriti nove segmente](#create-a-new-segment) pomoću [graditelja segmenata](#segment-builder) ili [stvoriti brze segmente](#quick-segments) iz drugih područja aplikacije.

## <a name="segment-builder"></a>Graditelj segmenata

Sljedeća slika prikazuje različite aspekte graditelja segmenata. Prikazuje segment koji rezultira grupom klijenata. Klijenti su naručivali robu u određenom vremenskom okviru i prikupili brojne nagradne bodove ili potrošili određeni iznos novca. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementi sastavljača segmenata." lightbox="media/segment-builder-overview.png":::

1 – Organizirajte svoj segment pravilima i podpravilima. Svako pravilo ili podpravilo sastoji se od uvjeta. Kombinirajte uvjete s logičkim operatorima

2 – Odaberite [putanju odnosa](relationships.md) između entiteta koja se primjenjuje na pravilo. Putanja odnosa određuje koji se atributi mogu koristiti u uvjetu.

3 – Upravljajte pravilima i podpravilima. Promijenite položaj pravila ili ga izbrišite.

4 – Dodajte uvjete i izgradite odgovarajuću razinu ugnježđivanja pomoću podpravila.

5 - Primijenite zadane operacije na povezana pravila.

6 – Pomoću okna atributa dodajte dostupne atribute entiteta ili izradite uvjete na temelju atributa. Okno prikazuje popis entiteta i atributa na temelju odabrane putanje odnosa koji su dostupni za odabrano pravilo.

7 – Dodajte uvjete na temelju atributa postojećim pravilima i podpravilima ili ih dodajte novom pravilu.

8 – Poništite i ponovite promjene tijekom sastavljanja segmenta.

Gornji primjer ilustrira sposobnost segmentacije. Definirali smo segment za klijente koji su na mreži kupili najmanje $500 robe *i* imaju interes za razvoj softvera.

## <a name="create-a-new-segment"></a>Izrada novog segmenta

Postoji više načina za stvaranje novog segmenta. Ovaj odjeljak opisuje kako izgraditi vlastiti segment od nule. Također možete stvoriti *brzi segment* na temelju postojećih entiteta ili iskoristiti modele strojnog učenja da biste dobili *predložene segmente*. Dodatne informacije: [Pregled segmenata](segments.md).

Tijekom izrade segmenta možete spremiti skicu. Spremit će se kao neaktivni segment i ne može se aktivirati, završava valjanom konfiguracijom.

1. Idite na stranicu **Segmenti**.

1. Odaberite **Novo** > **Izgradi vlastiti**.

1. Na stranici graditelja segmenata definirate prvo pravilo. Pravilo se sastoji od jednog ili više uvjeta i definira skup klijenata.

1. U odjeljku **Pravilo1** odaberite atribut entiteta prema kojem želite filtrirati klijente. Postoje dva načina za odabir atributa: 
   - Pregledajte popis dostupnih entiteta i atributa u oknu **Dodaj u pravilo** i odaberite ikonu **+** pored atributa za dodavanje. Odaberite želite li atribut dodati postojećem pravilu ili ga koristiti za stvaranje novog pravila.
   - Upišite naziv atributa u odjeljak pravila da biste vidjeli odgovarajuće prijedloge.

1. Odaberite operatore za navođenje podudarnih vrijednosti uvjeta. Atribut može imati jednu od četiri vrste podataka kao vrijednost: numeričku, niz, datum ili Booleovu vrijednost. Ovisno o vrsti podataka atributa, za navođenje uvjeta dostupni su različiti operatori. 

1. Odaberite **Dodaj uvjet** za dodavanje više uvjeta u pravilo. Da biste stvorili pravilo prema trenutnom pravilu, odaberite **Dodaj pod-pravilo**.

1. Ako pravilo koristi druge entitete osim entiteta *Klijent*, morate postaviti putanju odnosa. Putanja odnosa potrebna je kako bi obavijestila sustav preko kojih odnosa želite pristupiti objedinjenom entitetu klijenta. Odaberite **Postavi putanju odnosa** za mapiranje odabranog entiteta u objedinjeni entitet klijenta. Ako postoji samo jedna moguća putanja odnosa, sustav će je automatski odabrati. Različite putanje odnosa mogu dati različite rezultate. Svako pravilo može imati svoju vlastitu putanju odnosa.

   :::image type="content" source="media/relationship-path.png" alt-text="Potencijalna putanja odnosa prilikom stvaranja pravila na temelju entiteta mapiranog u objedinjeni entitet klijenta.":::

   Na primjer, entitet *eCommerce_eCommercePurchases* na snimci zaslona ima četiri mogućnosti za mapiranje entiteta *Klijent*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Klijent
   - eCommerce_eCommercePurchases> Klijent
   - eCommerce_eCommercePurchases> eCommerce_eCommerceContacts> POS_posPurchases> Klijent
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Klijent Prilikom odabira posljednje mogućnosti u uvjete pravila možemo uključiti atribute svih navedenih entiteta. Vjerojatno ćemo dobiti manje rezultata jer podudarni zapisi o klijentima moraju biti dio svih entiteta. U ovom primjeru kupili su robu putem e-trgovine(*eCommerce_eCommercePurchases*), na prodajnom mjestu(*POS_posPurchases*) i sudjelovali u našem programu vjernosti (*loyaltyScheme_loyCustomers*). Prilikom odabira druge mogućnosti možemo odabrati samo atribute iz *eCommerce_eCommercePurchases* i entiteta *Klijent*. To vjerojatno rezultira većim brojem rezultirajućih profila klijenata.

1. Ako u pravilu imate više uvjeta, možete odabrati koji ih logički operator povezuje.

   - Operator **AND**: Svi uvjeti moraju biti ispunjeni za uključivanje zapisa u segment. Ova je mogućnost najkorisnija kada definirate uvjete u različitim entitetima.

   - Operator **OR**: Svi uvjeti moraju biti ispunjeni za uključivanje zapisa u segment. Ova je mogućnost najkorisnija kada definirate više uvjeta za isti entitet.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Pravilo s dva uvjeta AND.":::

   Prilikom korištenja operatora OR svi se uvjeti moraju temeljiti na entitetima uključenima u putanju odnosa.

   1. Možete stvoriti više pravila za stvaranje različitih skupova zapisa klijenta. Možete kombinirati grupe da biste uključili klijente potrebne za vaš poslovni slučaj. Da biste stvorili novo pravilo, odaberite **Dodaj pravilo**. Konkretno, ako ne možete uključiti entitet u pravilo zbog navedene putanje odnosa, morate stvoriti novo pravilo kako biste odabrali atribute koji ga čine.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Dodajte novo pravilo segmentu i odaberite operator skupa.":::

   1. Odaberite jednog od postavljenih operatora: **Unija**, **Unakrsno** ili **Izuzmi**.

   - **Unija** objedinjuje dvije grupe.

   - **Unakrsno** preklapa dvije grupe. Samo podaci koji su *zajednički* u obje grupe zadržavaju se u objedinjenoj grupi.

   - **Izuzmi** kombinira dvije grupe. Zadržavaju se samo podaci u grupi A koji *nisu zajednički* s podacima grupe B.

1. Prema zadanim postavkama segmenti generiraju izlazni entitet koji sadrži sve atribute profila klijenata koji odgovaraju definiranim filtrima. Ako se segment temelji na drugim entitetima osim na entitetu *Klijent*, izlaznom entitetu možete dodati više atributa iz tih entiteta. Odaberite stavku **Atributi projekta** za odabir atributa koji će se dodati izlaznom entitetu.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Primjer projiciranih atributa odabranih u bočnom oknu za dodavanje izlaznom entitetu.":::
  
   Primjer: segment se temelji na entitetu koji sadrži podatke o kupnji, a koji su povezani s entitetom *Klijent*. Segment traži sve klijente iz Španjolske koji su kupili robu u tekućoj godini. Možete odabrati dodavanje atributa poput cijene robe ili datuma kupnje svim odgovarajućim zapisima klijenata u izlaznom entitetu. Ove informacije mogu biti korisne za analizu sezonskih korelacija s ukupnom potrošnjom.

   > [!NOTE]
   > - Projicirani atributi funkcioniraju samo za entitete koji imaju odnos jedan-prema-više s entitetom klijenta. Na primjer, jedan klijent može imati više pretplata.
   > - Atribute možete projicirati samo iz entiteta koji se koristi u svakom pravilu segmenta upita koji gradite.
   > - Projicirani atributi uzimaju se u obzir pri korištenju postavljenih operatora.

1. Prije nego spremite i pokrenete segment, odaberite **Uredi pojedinosti** pored naziva segmenta. Navedite naziv za svoj segment i ažurirajte predloženi **Naziv izlaznog entiteta** za segment. Segmentu možete dodati i opis.

1. Odaberite **Pokreni** za spremanje i obradu vašeg segmenta ako su svi zahtjevi potvrđeni. U suprotnome će se spremiti kao neaktivna skica segmenta.

1. Odaberite **Natrag na segmente** za povratak na stranicu **Segmenti**.

> [!TIP]
> - Graditelj segmenata neće predlagati valjane vrijednosti entiteta prilikom postavljanja operatora za uvjete. Možete otići na **Podaci** > **Entiteti** i preuzeti podatke entiteta kako biste vidjeli koje su vrijednosti dostupne.
> - Uvjeti koji se temelje na datumima omogućuju vam prebacivanje između fiksnih datuma i promjenjivog datumskog raspona.
> - Ako imate više pravila za svoj segment, pronaći ćete plavu traku oko pravila koje uređujete.
> - Pravila i uvjete možete premjestiti na druga mjesta u definiciji segmenta. Odaberite [...] pored pravila ili uvjeta i odaberite kako i gdje ga premjestiti.
> - Kontrole **Poništi** i **Ponovi** na naredbenoj traci omogućuju vam vraćanje promjena.

## <a name="quick-segments"></a>Brzi segmenti

Brzi segmenti omogućuju vam brzu izgradnju jednostavnih segmenata s jednim operatorom za brži uvid.

1. Na stranici **Segmenti** odaberite **Novo** > **Stvori iz**.

   - Odaberite mogućnost **Profili** za stvaranje segmenta koji se temelji na entitetu *jedinstvenog klijenta*.
   - Odaberite mogućnost **Mjere** za stvaranje segmenta prema mjerama koje ste prethodno stvorili.
   - Odaberite mogućnost **Inteligencija** za izgradnju segmenta oko jednog od izlaznih entiteta koje ste generirali pomoću mogućnosti **Predviđanja** ili **Prilagođeni modeli**.

2. U dijaloškom okviru **Novi brzi segment** odaberite atribut iz padajućeg izbornika **Polje**.

3. Sustav će pružiti više uvida koji će vam pomoći stvoriti bolje segmente svojih klijenata.
   - Za kategorijska polja prikazat ćemo 10 brojeva najboljih kupaca. Odaberite **Vrijednost** te **Pregled**.

   - Za numerički atribut sustav će pokazati koja vrijednost atributa spada pod svaki postotak klijenta. Odaberite **Operator** i **Vrijednost**, a zatim odaberite **Pregled**.

4. Sustav će vam pružiti **Procijenjenu veličinu segmenta**. Možete odabrati želite li generirati definirani segment ili ga prvo pregledati kako biste dobili drugu veličinu segmenta.

    > [!div class="mx-imgBorder"]
    > ![Naziv i procjena brzog segmenta.](media/quick-segment-name.png "Naziv i procjena brzog segmenta")

5. Unesite **Naziv** segmenta. Po želji možete unijeti i **Zaslonski naziv**.

6. Odaberite **Spremi** kako biste stvorili segment.

7. Nakon dovršetka obrade segmenta možete ga pregledati kao i bilo koji drugi segment koji ste stvorili.

## <a name="next-steps"></a>Sljedeći koraci

[Izvezite segment](export-destinations.md) i istražite [integraciju usluge Customer Card](customer-card-add-in.md) za upotrebu segmenata u drugim aplikacijama.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
