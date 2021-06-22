---
title: Odnosi među entitetima i putanjama entiteta
description: Stvorite i upravljajte odnosima između entiteta iz više izvora podataka.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171155"
---
# <a name="relationships-between-entities"></a>Odnosi među entitetima

Odnosi povezuju entitete i definiraju grafikon vaših podataka kada entiteti dijele zajednički identifikator, vanjski ključ. Ovaj se vanjski ključ može referencirati s jednog entiteta na drugi. Povezani entiteti omogućuju definiciju segmenata i mjera na temelju više izvora podataka.

Postoje tri vrste odnosa: 
- Odnosi sustava koji se ne mogu uređivati, stvara ih sustav kao dio postupka objedinjavanja podataka
- Naslijeđeni odnosi koji se ne mogu uređivati, a koji se automatski stvaraju iz unosa izvora podataka 
- Prilagođeni odnosi koji se mogu uređivati i koje stvaraju i konfiguriraju korisnici

## <a name="non-editable-system-relationships"></a>Odnosi sustava koji se ne mogu uređivati

Tijekom objedinjavanja podataka, odnosi sustava stvaraju se automatski na temelju inteligentnog podudaranja. Ovi odnosi pomažu pri povezivanju zapisa profila klijenta s odgovarajućim zapisima. Sljedeći dijagram ilustrira stvaranje tri odnosa na temelju sustava. Entitet klijenta uparuje se s drugim entitetima kako bi se dobio objedinjeni entitet *Klijent*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Dijagram s putovima odnosa za entitet klijenta s tri 1-n odnosa.":::

- ***CustomerToContact* odnos** izrađen je između entiteta *Klijent* i entiteta *Kontakt*. Entitet *Klijent* dobiva polje ključa **Contact_contactID** za povezivanje s poljem ključa **contactID** entiteta *Kontakt*.
- ***CustomerToAccount* odnos** izrađen je između entiteta *Klijent* i entiteta *Račun*. Entitet *Klijent* dobiva polje ključa **Account_accountID** za povezivanje s poljem ključa **accountID** entiteta *Račun*.
- ***CustomerToWebAccount* odnos** izrađen je između entiteta *Klijent* i entiteta *Web-račun*. Entitet *Klijent* dobiva polje ključa **WebAccount_webaccountID** za povezivanje s poljem ključa **webaccountID** entiteta *Web-račun*.

## <a name="non-editable-inherited-relationships"></a>Naslijeđeni odnosi koji se ne mogu uređivati

Tijekom postupka unosa podataka, sustav provjerava izvore podataka za postojeće odnose. Ako ne postoje odnosi, sustav ih automatski stvara. Ovi se odnosi također koriste u nizvodnim procesima.

## <a name="create-a-custom-relationship"></a>Stvaranje prilagođenog odnosa

Odnos se sastoji od *izvornog entiteta* koji sadrži vanjski ključ i *ciljnog entiteta* na koji ukazuje vanjski ključ izvornog entiteta. 

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Odnosi**.

2. Odaberite **Novi odnos**.

3. U oknu **Novi odnos** navedite sljedeće informacije:

   :::image type="content" source="media/relationship-add.png" alt-text="Bočno okno novog odnosa s praznim poljima za unos.":::

   - **Naziv odnosa**: naziv koji odražava svrhu odnosa. Primjer: CustomerToSupportCase.
   - **Opis**: Opis odnosa.
   - **Izvorni entitet**: entitet koji se koristi kao izvor u odnosu. Primjer: SupportCase.
   - **Ciljni entitet**: entitet koji se koristi kao cilj u odnosu. Primjer: Klijent.
   - **Izvorna kardinalnost**: određuje kardinalnost izvornog entiteta. Kardinalnost opisuje broj mogućih elemenata u skupu. Uvijek se odnosi na ciljnu kardinalnost. Možete birati između **Jedan** i **Više**. Podržani su samo odnosi mnogi na jedan i jedan na jedan.  
     - Više na jedan: više izvornih zapisa može se odnositi na jedan ciljni zapis. Primjer: više slučajeva podrške od jednog klijenta.
     - Jedan na jedan: jedan izvorni zapis odnosi se na jedan ciljni zapis. Primjer: jedan ID odanosti za jednog klijenta.

     > [!NOTE]
     > Odnosi jedan na više mogu se stvoriti pomoću dva odnosa više na jedan i povezujućeg entiteta koji povezuje izvorni entitet i ciljni entitet.

   - **Kardinalnost cilja**: Odaberite kardinalnost zapisa entiteta cilja. 
   - **Polje izvornog ključa**: polje vanjskog ključa u izvornom entitetu. Primjer: SupportCase bi mogao koristiti CaseID kao polje vanjskog ključa.
   - **Polje ciljnog ključa**: polje ključa ciljnog entiteta. Primjer Klijent bi mogao koristiti polje ključa **CustomerID**.

4. Odaberite **Spremi** za stvaranje prilagođenog odnosa.

## <a name="view-relationships"></a>Prikaz odnosa

Na stranici Odnosi navedeni su svi stvoreni odnosi. Svaki redak predstavlja odnos, koji također uključuje pojedinosti o izvornom entitetu, ciljnom entitetu i kardinalnosti. 

:::image type="content" source="media/relationships-list.png" alt-text="Popis odnosa i mogućnosti na traci radnji stranice Odnosi.":::

Ova stranica nudi skup mogućnosti za postojeće i nove odnose: 
- **Novi odnos**: [Stvaranje prilagođenog odnosa](#create-a-custom-relationship).
- **Vizualizator**: [Istražite vizualizator odnosa](#explore-the-relationship-visualizer) da biste vidjeli mrežni dijagram postojećih odnosa i njihovu kardinalnost.
- **Filtrirati po**: Odaberite vrstu odnosa koja će se prikazivati na popisu.
- **Pretraživanje odnosa**: Upotrijebite tekstualno pretraživanje svojstava odnosa.

### <a name="explore-the-relationship-visualizer"></a>Istražite vizualizator odnosa

Vizualizator odnosa prikazuje mrežni dijagram postojećih odnosa među povezanim entitetima i njihovu kardinalnost.

Da biste prilagodili prikaz, možete promijeniti položaj okvira povlačenjem po radnom području.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Snimka zaslona s mrežnim dijagramom vizualizatora odnosa s vezama među povezanim entitetima.":::

Dostupne mogućnosti: 
- **Izvezi kao sliku**: Spremite trenutni prikaz kao slikovnu datoteku.
- **Promjena na vodoravni/okomiti raspored**: Promijenite poravnanje entiteta i odnosa.
- **Uređivanje**: Ažurirajte svojstva prilagođenih odnosa u oknu za uređivanje i spremite promjene.

## <a name="manage-existing-relationships"></a>Upravljanje postojećim odnosima 

Na stranici Odnosi svaki je odnos predstavljen retkom. 

Odaberite odnos i odaberite jednu od sljedećih mogućnosti: 
 
- **Uređivanje**: Ažurirajte svojstva prilagođenih odnosa u oknu za uređivanje i spremite promjene.
- **Brisanje**: Izbrišite prilagođene odnose.
- **Prikaz**: Prikažite odnose koje je stvorio sustav i naslijeđene odnose. 

## <a name="next-step"></a>Sljedeći korak

Odnosi sustava i prilagođeni odnosi koriste se za [izradu segmenata](segments.md) na temelju više izvora podataka koji se više ne biraju.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
