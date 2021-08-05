---
title: Stvaranje i upravljanje segmentima
description: Izradite segmente klijenata da biste ih grupirali na temelju različitih atributa.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a19661abea42618ef1848110c05d635a925c68f
ms.sourcegitcommit: c45b094072cbe3fbf61d1e9e7d220e1f29ffebd0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/29/2021
ms.locfileid: "6685453"
---
# <a name="create-and-manage-segments"></a>Stvaranje i upravljanje segmentima

> [!IMPORTANT]
> U iskustvo stvaranja segmenata u rujnu 2021. uvodi se nekoliko promjena: 
> - Sastavljač segmenata izgledat će malo drugačije s elementima novog stila i poboljšanim korisničkim tokom.
> - U sastavljaču segmenata omogućeni su novi operatori datuma i vremena te poboljšani birač datuma.
> - Moći ćete dodavati uvjete i pravila u segmente te ih uklanjati. 
> - Bit će dostupna ugniježđena pravila koja počinju uvjetom OR. Uvjet AND više nije potreban u krajnjem vanjskom sloju.
> - Bočno okno za odabir atributa bit će stalno dostupno.
> - Mogućnost odabira putanja odnosa entiteta.
> Da biste isprobali novi alat za stvaranje segmenata, pošaljite e-poštu s predmetom „Zahtjev za omogućavanje novog alata za stvaranje segmenata” na cihelp [at] microsoft.com. Uključite naziv vaše tvrtke ili ustanove i ID vašeg okruženja sigurnosne ograde.

Definirajte složene filtre oko objedinjenog entiteta klijenta i s njime povezanih entiteta. Nakon obrade, svaki segment stvara skup zapisa o klijentima koji možete izvesti i koristiti za rad. Segmentima se upravlja na stranici **Segmenti**. 

Sljedeći primjer prikazuje način upotrebe segmentacije. Definirali smo segment za klijente koji su naručili najmanje $500 robe u posljednjih 90 dana *i* koji su bili uključeni u poziv službe za korisnike koji je eskalirao.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Snimka zaslona korisničkog sučelja sastavljača segmenata s dvije grupe koje određuju segment klijenta.":::

## <a name="create-a-new-segment"></a>Izrada novog segmenta

Postoji više načina za stvaranje novog segmenta. U ovom odjeljku je opisano kako stvoriti *prazan segment* od početka. Također možete stvoriti *brzi segment* na temelju postojećih entiteta ili iskoristiti modele strojnog učenja da biste dobili *predložene segmente*. Dodatne informacije: [Pregled segmenata](segments.md).

Tijekom izrade segmenta možete spremiti skicu. Spremit će se kao neaktivni segment i ne može se aktivirati, završava valjanom konfiguracijom.

1. Idite na stranicu **Segmenti**.

1. Odaberite **Novo** > **Prazni segment**.

1. U oknu **Novi segment** odaberite vrstu segmenta:

   - **Dinamički segmenti** [osvježavaju se](segments.md#refresh-segments) prema ponavljajućem rasporedu.
   - **Statički segmenti** pokreću se jednom kad ih stvorite.

1. Navedite **Naziv izlaznog entiteta** za segment. Po želji navedite zaslonski naziv i opis koji pomaže u prepoznavanju segmenta.

1. Odaberite **Dalje** da biste pristupili stranici **Alat za sastavljanje segmenata** na kojoj definirate grupu. Grupa je skup klijenata.

1. Odaberite entitet koji uključuje atribut za koji želite segmentiranje.

1. Odaberite atribut za segmentaciju. Ovaj atribut može imati jednu od četiri vrste vrijednosti: numeričku, niz, datum ili Booleov izraz.

1. Odaberite operatora i vrijednost za odabrani atribut.

   > [!div class="mx-imgBorder"]
   > ![Prilagođeni filtar grupe.](media/customer-group-numbers.png "Filtar grupe klijenata")

   |Broj |Definicija  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribut          |
   |3    |Operater         |
   |4    |Value         |

   1. Da biste grupi dodali više uvjeta, možete upotrijebiti dva logička operatora:

      - Operator **I**: oba uvjeta moraju biti ispunjena kao dio postupka segmentacije. Ova je mogućnost najkorisnija kada definirate uvjete u različitim entitetima.

      - Operator **ILI**: jedan od uvjeta mora biti ispunjen kao dio postupka segmentacije. Ova je mogućnost najkorisnija kada definirate više uvjeta za isti entitet.

      > [!div class="mx-imgBorder"]
      > ![Operator OR ako je potrebno ispuniti bilo koji uvjet.](media/segmentation-either-condition.png "Operator ILI ako je potrebno ispuniti bilo koji uvjet")

      Trenutačno je moguće ugnijezditi operator **ILI** pod operatorom **I**, ali ne i obratno.

   1. Svaka grupa odgovara skupu klijenata. Možete kombinirati grupe da biste uključili klijente potrebne za vaš poslovni slučaj.    
   Odaberite **Dodaj grupu**.

      > [!div class="mx-imgBorder"]
      > ![Grupa za dodavanje grupe klijenata.](media/customer-group-add-group.png "Grupa za dodavanje grupe klijenata")

   1. Odaberite jednog od postavljenih operatora: **Unija**, **Unakrsno** ili **Izuzmi**.

   > [!div class="mx-imgBorder"]
   > ![Unija za dodavanje grupe klijenata.](media/customer-group-union.png "Unija za dodavanje grupe klijenata")

   - **Unija** objedinjuje dvije grupe.

   - **Unakrsno** preklapa dvije grupe. Samo podaci koji su *zajednički* u obje grupe zadržavaju se u objedinjenoj grupi.

   - **Izuzmi** kombinira dvije grupe. Zadržavaju se samo podaci u grupi A koji *nisu zajednički* s podacima grupe B.

1. Ako je entitet povezan s objedinjenim entitetom klijenta putem [odnosa](relationships.md), morate definirati putanju odnosa za stvaranje valjanog segmenta. Dodajte entitete s putanje odnosa sve dok ne možete odabrati entitet **Klijent: CustomerInsights** s padajućeg izbornika. Zatim odaberite **Svi zapisi** za svaki korak.

   > [!div class="mx-imgBorder"]
   > ![Putanja odnosa tijekom stvaranja segmenta.](media/segments-multiple-relationships.png "Putanja odnosa tijekom stvaranja segmenta")

1. Prema zadanim postavkama, segmenti generiraju izlazni entitet koji sadrži sve atribute profila klijenata koji odgovaraju definiranim filtrima. Ako se segment temelji na drugim entitetima osim na entitetu *Klijent*, izlaznom entitetu možete dodati više atributa iz tih entiteta. Odaberite stavku **Atributi projekta** za odabir atributa koji će se dodati izlaznom entitetu.  
  
   Primjer: Segment se temelji na entitetu koji sadrži podatke o aktivnostima klijenta koji su povezani s entitetom *Klijent*. Segment traži sve klijente koji su nazvali službu za pomoć u posljednjih 60 dana. Možete odabrati dodavanje trajanja poziva i broja poziva svim odgovarajućim zapisima klijenata u izlaznom entitetu. Ove bi informacije mogle biti korisne za slanje e-pošte s korisnim vezama do članaka za pomoć na mreži i najčešćih pitanja klijentima koji su često zvali.

   > [!NOTE]
   > - Projicirani atributi funkcioniraju samo za entitete koji imaju odnos jedan-prema-više s entitetom klijenta. Na primjer, jedan klijent može imati više pretplata.
   > - Atribute možete projicirati samo iz entiteta koji se koristi u svakoj grupi upita segmenta koji gradite.
   > - Projicirani atributi uzimaju se u obzir pri korištenju postavljenih operatora.

1. Odaberite **Spremi** da biste spremili segment. Segment će se spremiti i obraditi ako su potvrđeni svi zahtjevi. U protivnom će se spremiti kao skica.

1. Odaberite **Natrag na segmente** za povratak na stranicu **Segmenti**.



## <a name="quick-segments"></a>Brzi segmenti

Brzi segmenti omogućuju vam brzu izgradnju jednostavnih segmenata s jednim operatorom za brži uvid.

1. Na stranici **Segmenti** odaberite **Novo** > **Stvori iz**.

   - Odaberite mogućnost **Profili** za stvaranje segmenta koji se temelji na entitetu *jedinstvenog klijenta*.
   - Odaberite mogućnost **Mjere** za stvaranje segmenta prema mjerama koje ste prethodno stvorili.
   - Odaberite mogućnost **Inteligencija** za izgradnju segmenta oko jednog od izlaznih entiteta koje ste generirali pomoću mogućnosti **Predviđanja** ili **Prilagođeni modeli**.

2. U dijaloškom okviru **Novi brzi segment** odaberite atribut iz padajućeg izbornika **Polje**.

3. Sustav će pružiti neke dodatne uvide koji će vam pomoći stvoriti bolje segmente svojih klijenata.
   - Za kategorijska polja prikazat ćemo 10 brojeva najboljih kupaca. Odaberite **Vrijednost** te **Pregled**.

   - Za numerički atribut sustav će pokazati koja vrijednost atributa spada pod svaki postotak klijenta. Odaberite **Operator** i **Vrijednost**, a zatim odaberite **Pregled**.

4. Sustav će vam pružiti **Procijenjenu veličinu segmenta**. Možete odabrati želite li generirati definirani segment ili ga prvo pregledati kako biste dobili drugu veličinu segmenta.

    > [!div class="mx-imgBorder"]
    > ![Naziv i procjena brzog segmenta.](media/quick-segment-name.png "Naziv i procjena brzog segmenta")

5. Unesite **Naziv** segmenta. Po želji možete unijeti i **Zaslonski naziv**.

6. Odaberite **Spremi** kako biste stvorili segment.

7. Nakon dovršetka obrade segmenta možete ga pregledati kao i bilo koji drugi segment koji ste stvorili.

## <a name="next-steps"></a>Sljedeći koraci

[Izvezite segment](export-destinations.md) i istražite [Korisničku karticu](customer-card-add-in.md) i [Poveznike](export-power-bi.md) da biste dobili uvide na razini klijenta.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
