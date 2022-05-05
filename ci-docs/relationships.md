---
title: Odnosi među entitetima i putanjama entiteta
description: Stvorite i upravljajte odnosima između entiteta iz više izvora podataka.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: a7b10d985d5cba64b25595a3d7c101d6cb5c62a5
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642867"
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

1. Idite na **Podaci** > **Odnosi**.

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

## <a name="set-up-account-hierarchies"></a>Postavljanje hijerarhija računa

Okruženja koja su konfigurirana za korištenje poslovnih računa kao primarne ciljne skupine mogu konfigurirati hijerarhije računa za povezane poslovne račune. Na primjer, tvrtka koja ima zasebne poslovne jedinice. 

Tvrtke ili ustanove stvaraju hijerarhije računa za bolje upravljanje računima i njihovim međusobnim odnosima. Customer Insights podržava hijerarhije računa nadređenih i podređenih računa koje već postoje u unesenim podacima o klijentima. Na primjer, računi iz programa Dynamics 365 Sales. Te se hijerarhije mogu konfigurirati na **stranici Odnosi**.

1. Idite na **Podaci** > **Odnosi**.
1. Odaberite karticu **Hijerarhija računa**.
1. Odaberite **Nova hijerarhija računa**. 
1. U oknu **Hijerarhija računa** navedite naziv za hijerarhiju. Sustav stvara naziv za izlazni entitet. Možete promijeniti naziv entiteta izlaznog naziva.
1. Odaberite entitet koji sadrži hijerarhiju vašeg računa. Uobičajeno se nalazi u istom entitetu koji sadrži račune.
1. Odaberite **ID računa** i **Nadređeni ID računa** iz odabranog entiteta 
1. Odaberite **Spremi** kako biste primijenili postavke i dovršili hijerarhiju računa.

## <a name="view-relationships"></a>Prikaz odnosa

Na stranici Odnosi navedeni su svi stvoreni odnosi. Svaki redak predstavlja odnos, koji također uključuje pojedinosti o izvornom entitetu, ciljnom entitetu i kardinalnosti. 

:::image type="content" source="media/relationships-list.png" alt-text="Popis odnosa i mogućnosti na traci radnji stranice Odnosi.":::

Ova stranica nudi skup mogućnosti za postojeće i nove odnose: 
- **Novi odnos**: [Stvaranje prilagođenog odnosa](#create-a-custom-relationship).
- **Vizualizator**: [Istražite vizualizator odnosa](#explore-the-relationship-visualizer) da biste vidjeli mrežni dijagram postojećih odnosa i njihovu kardinalnost.
- **Filtrirati po**: Odaberite vrstu odnosa koja će se prikazivati na popisu.
- **Pretraživanje odnosa**: Upotrijebite tekstualno pretraživanje svojstava odnosa.

### <a name="explore-the-relationship-visualizer"></a>Istražite vizualizator odnosa

Vizualizator odnosa prikazuje mrežni dijagram postojećih odnosa među povezanim entitetima i njihovu kardinalnost. Njime se također vizualizira putanja odnosa.

Da biste prilagodili prikaz, možete promijeniti položaj okvira povlačenjem po radnom području.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Snimka zaslona s mrežnim dijagramom vizualizatora odnosa s vezama među povezanim entitetima.":::

Dostupne mogućnosti: 
- **Izvezi kao sliku**: Spremite trenutni prikaz kao slikovnu datoteku.
- **Promjena na vodoravni/okomiti raspored**: Promijenite poravnanje entiteta i odnosa.
- **Uređivanje**: Ažurirajte svojstva prilagođenih odnosa u oknu za uređivanje i spremite promjene.

## <a name="relationship-paths"></a>Putanje odnosa

Putanja odnosa opisuje entitete koji su povezani s odnosima između izvornog entiteta i ciljnog entiteta. Koristi se pri izradi segmenta ili mjere koja uključuje druge entitete koji nisu entitet objedinjenog profila, a postoji više mogućnosti za dosezanje entiteta objedinjenog profila. 

Putanja odnosa informira sustav preko kojeg odnosa može pristupiti jedinstvenom entitetu profila. Različite putanje odnosa mogu dati različite rezultate.

Na primjer, entitet *eCommerce_eCommercePurchases* ima sljedeći odnos s entitetom *Klijent* objedinjenog profila:

- eCommerce_eCommercePurchases> Klijent
- eCommerce_eCommercePurchases> eCommerce_eCommerceContacts> POS_posPurchases> Klijent
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Klijent 

Putanja odnosa određuje kojim se entitetima možete koristiti pri stvaranju pravila za mjere ili segmente. Odabir opcije s najdužom putanjom odnosa vjerojatno će dati manje rezultata jer podudarajući zapisi moraju biti dio svih entiteta. U ovom primjeru klijent mora kupiti robu putem e-trgovine (eCommerce_eCommercePurchases) na prodajnom mjestu (POS_posPurchases) i sudjelovati u našem programu vjernosti (loyaltyScheme_loyCustomers). Odabirom prve opcije vjerojatno biste dobili više rezultata jer kupci trebaju postojati samo u jednom dodatnom entitetu.

### <a name="direct-relationship"></a>Izravan odnos

Odnos se klasificira kao **izravan odnos** kada se izvorni entitet odnosi na ciljni entitet sa samo jednim odnosom.

Na primjer, ako se entitet aktivnosti pod nazivom *eCommerce_eCommercePurchases* povezuje sa ciljnim entitetom entitetom *eCommerce_eCommerceContacts* samo kroz *ContactId*, to je izravan odnos.

:::image type="content" source="media/direct_Relationship.png" alt-text="Izvorni entitet povezuje se izravno s ciljnim entitetom.":::

#### <a name="multi-path-relationship"></a>Odnos s više putanja

**Odnos s više putanja** posebna je vrsta izravnog odnosa koji povezuje izvorni entitet s više ciljnih entiteta.

Na primjer, ako se entitet aktivnosti pod nazivom *eCommerce_eCommercePurchases* odnosi na dva ciljna entiteta *eCommerce_eCommerceContacts* i *loyaltyScheme_loyCustomers*, to je odnos s više putanja.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Izvorni entitet povezuje se izravno s više ciljnih entiteta putem odnosa s više preskoka.":::

### <a name="indirect-relationship"></a>Neizravan odnos

Odnos se klasificira kao **neizravan odnos** kada se izvorni entitet odnosi na jedan dodatni entitet ili više dodatnih entiteta prije nego se odnosi na ciljni entitet.

#### <a name="multi-hop-relationship"></a>Odnos s više preskoka

*Odnos s više preskoka* je *neizravan odnos* koji vam omogućuje povezivanje izvornog entiteta s ciljnim entitetom putem jednog posredničkog entiteta ili više njih.

Na primjer, ako se entitet aktivnosti pod nazivom *eCommerce_eCommercePurchasesWest* povezuje s posredničkim entitetom pod nazivom *eCommerce_eCommercePurchasesEast*, a zatim se povezuje s ciljnim entitetom pod nazivom *eCommerce_eCommerceContacts*, to je odnos s više preskoka.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Izvorni entitet povezuje se izravno s ciljnim entitetom s posredničkim entitetom.":::

### <a name="multi-hop-multi-path-relationship"></a>Odnos s više preskoka, više putanja

Odnosi s više preskoka i više putanja mogu se upotrebljavati zajedno za stvaranje **odnosa s više preskoka i više putanja**. Ova posebna vrsta kombinira funkcije **odnosa s više preskoka** i **više putanja**. Omogućuje vam povezivanje s više ciljnih entiteta koristeći posredničke entitete.

Na primjer, ako se entitet aktivnosti pod nazivom  *eCommerce_eCommercePurchasesWest* povezuje s posredničkim entitetom pod nazivom *eCommerce_eCommercePurchasesEast*, a zatim se povezuje s ciljnim entitetima pod nazivom *eCommerce_eCommerceContacts* i *loyaltyScheme_loyCustomers*, to je odnos s više preskoka i više putanja.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Izvorni entitet povezuje se izravno s jednim ciljnim entitetom i povezuje se s drugim ciljnim entitetom putem posredničkog entiteta.":::

## <a name="manage-existing-relationships"></a>Upravljanje postojećim odnosima 

Na stranici Odnosi svaki je odnos predstavljen retkom. 

Odaberite odnos i odaberite jednu od sljedećih mogućnosti: 
 
- **Uređivanje**: Ažurirajte svojstva prilagođenih odnosa u oknu za uređivanje i spremite promjene.
- **Brisanje**: Izbrišite prilagođene odnose.
- **Prikaz**: Prikažite odnose koje je stvorio sustav i naslijeđene odnose. 

## <a name="next-step"></a>Sljedeći korak

Sustav i prilagođeni odnosi koriste se za [izradu segmenata](segments.md) i [mjera](measures.md) na temelju više izvora podataka koji se više ne odvajaju.

[!INCLUDE [footer-include](includes/footer-banner.md)]
