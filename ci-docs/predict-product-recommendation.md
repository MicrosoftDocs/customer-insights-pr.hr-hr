---
title: Predviđanje preporuka proizvoda
description: Predvidite proizvode koje će klijent vjerojatno kupiti ili s kojima će biti u interakciji.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610273"
---
# <a name="predict-product-recommendations"></a>Predviđanje preporuka proizvoda

Model preporuke proizvoda stvara skupove prediktivnih preporuka proizvoda. Preporuke se temelje na prethodnom ponašanju pri kupnji i klijentima sa sličnim obrascima kupnje. Ovaj model je namijenjen pojedinačnim potrošačima (B-do-C).

Morate imati poslovno znanje o različitim vrstama proizvoda za svoju tvrtku i načinu na koji vaši kupci stupaju u interakciju s njima. Podržavamo preporučivanje proizvoda koje su prethodno kupili vaši klijenti ili preporuke za nove proizvode.

Preporuke proizvoda mogu podlijegati lokalnim zakonima, uredbama i očekivanjima klijenata čiji model nije napravljen da bi ga se posebno uzelo u obzir. Stoga **morate pregledati preporuke prije nego što ih dostavite svojim kupcima** kako biste bili sigurni da se pridržavate svih primjenjivih zakona ili propisa i očekivanja kupaca za ono što možete preporučiti.

Izlaz ovog modela daje preporuke na temelju ID-a proizvoda. Vaš mehanizam isporuke mora mapirati predviđene ID-ove proizvoda na odgovarajući sadržaj kako bi vaši kupci uzeli u obzir lokalizaciju, slikovni sadržaj i drugi sadržaj ili ponašanje specifičn za tvrtku.

> [!TIP]
> Isprobajte preporuku proizvoda predviđanje pomoću uzoraka podataka: [Preporuka proizvoda predviđanje vodič za uzorke](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Preduvjeti

- Najmanje [suradnik dozvola](permissions.md)
- Najmanje 100 kupaca, po mogućnosti više od 10.000 kupaca.
- Identifikator kupca, jedinstveni identifikator za podudaranje transakcija s pojedinačnim kupcem
- Najmanje jedna godina transakcijskih podataka, po mogućnosti dvije do tri godine kako bi se uključila određena sezonalnost. U idealnom slučaju, najmanje tri ili više transakcija po ID-u kupca. Povijest transakcija mora sadržavati:
  - **ID** transakcije: jedinstveni identifikator kupnje ili transakcije.
  - **Datum** transakcije: Datum kupnje ili transakcije.
  - **Vrijednost transakcije**: Numerička vrijednost kupnje ili transakcije.
  - **Jedinstveni ID** proizvoda: ID proizvoda ili usluge kupljene ako su vaši podaci na razini stavke retka.
  - **Kupnja ili povrat**: booleova vrijednost true/false ako *true* identificira da je transakcija bila povrat. Ako podaci o kupnji ili povratu nisu navedeni u modelu, a **vrijednost transakcije** je negativna, zaključujemo povrat.
- Podatkovni entitet kataloga proizvoda koji će se koristiti kao filtar proizvoda.

> [!NOTE]
> - Model zahtijeva povijest transakcija vaših kupaca gdje je transakcija bilo koji podatak koji opisuje interakciju između korisnika i proizvoda. Na primjer, kupnja proizvoda, pohađanje nastave ili prisustvovanje događaju.
> - Može se konfigurirati samo jedan entitet povijesti transakcija. Ako postoji više subjekata nabave, kombinirajte ih Power Query prije gutanja podataka.
> - Ako su narudžba i pojedinosti o narudžbi različiti entiteti, spojite ih prije korištenja u modelu. Model ne funkcionira samo s ID-jem narudžbe ili ID-jem potvrde u entitetu.

## <a name="create-a-product-recommendation-prediction"></a>Stvaranje predviđanja preporuka proizvoda

U bilo kojem trenutku odaberite **Spremi skicu** da biste predviđanje spremili kao skicu. Skica predviđanje prikazuje se na **kartici Moja predviđanja**.

1. Idite na **Obavještajna** > **predviđanja**.

1. Na kartici **Stvaranje** na pločici **Preporuke proizvoda (pretpregleda)** odaberite **Koristi model**.

1. Odaberite **Početak rada**.

1. **Nazovite ovaj model** i **Naziv izlaznog entiteta** kako bi se razlikovali od ostalih modela ili entiteta.

1. Odaberite **Dalje**.

### <a name="define-product-recommendation-preferences"></a>Definiranje preferenci preporuke proizvoda

1. **Postavite broj proizvoda** koje želite preporučiti kupcu. Ova vrijednost ovisi o tome kako vaš način isporuke ispunjava podatke.

1. Odaberite želite li uključiti proizvode koje su kupci prethodno kupili u **polje Ponovi očekivane** nabave.

1. **Postavite prozor** Pogledaj unatrag s vremenski okvir model uzme u obzir prije nego što ponovno preporuči proizvod korisniku. Na primjer, naznačite da klijent kupuje prijenosno računalo svake dvije godine. Model gleda povijest kupnje za posljednje dvije godine, a ako pronađe stavku, stavka se filtrira iz preporuka.

1. Odaberite **Sljedeće**

### <a name="add-purchase-history"></a>Dodajte povijest kupnje

1. Odaberite **Dodaj podatke** za **povijest** transakcija kupca.

1. Odaberite vrstu semantičke aktivnosti **SalesOrderLine** koja sadrži potrebne podatke o transakciji ili povijesti nabave. Ako aktivnost nije postavljena, odaberite ovdje **i** stvorite je.

1. U odjeljku **Aktivnosti**, ako su atributi aktivnosti semantički mapirani prilikom stvaranja aktivnosti odaberite određene atribute ili entitet na koji želite da se izračun usredotoči. Ako nije došlo do semantičkog mapiranja, odaberite **Uređivanje** i mapiranje podataka.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Bočno okno koje prikazuje odabir određenih aktivnosti prema semantičkoj vrsti.":::

1. Odaberite **Dalje** i pregledajte atribute potrebne za ovaj model.

1. Odaberite **Spremi**.

1. Odaberite **Dalje**.

### <a name="add-product-information-and-filters"></a>Dodavanje informacija o proizvodu i filtara

Ponekad su samo određeni proizvodi korisni ili prikladni za vrstu predviđanja koju izrađujete. Pomoću filtara proizvoda identificirajte podskup proizvoda s određenim karakteristikama koje ćete preporučiti kupcima. Model će koristiti sve dostupne proizvode za učenje uzoraka, ali će koristiti samo proizvode koji odgovaraju filtru proizvoda u svojem izlazu.

1. Dodajte entitet kataloga proizvoda koji sadrži informacije za svaki proizvod. Mapirajte potrebne informacije i odaberite **Spremi**.

1. Odaberite **Dalje**.

1. Odaberite **filtre** proizvoda:

   - **Bez filtara**: Koristite sve proizvode u predviđanju preporuke za proizvod.

   - **Definirajte određene filtre proizvoda**: Koristite određene proizvode u predviđanju preporuke za proizvod. **U oknu atributa kataloga** proizvoda odaberite atribute iz entiteta kataloga proizvoda koje želite uključiti u filtar.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Bočno okno prikazuje atribut u entitetu kataloga proizvoda za odabir za filtre proizvoda.":::

1. Odaberite želite li da filtar proizvoda koristi **i** ili **da** logički kombinira vaš odabir atributa iz kataloga proizvoda.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Uzorak konfiguracije filtara proizvoda u kombinaciji s logičkim AND poveznicima.":::

1. Odaberite **Dalje**.

### <a name="set-update-schedule"></a>Postavljanje rasporeda ažuriranja

1. Odaberite frekvenciju za prekvalifikaciju modela. Ova je postavka važna za ažuriranje točnosti predviđanja jer se novi podaci unose u Customer Insights. Većina tvrtki može ponovno uvježbavati jednom mjesečno i steći dobru točnost predviđanja.

1. Odaberite **Dalje**.

### <a name="review-and-run-the-model-configuration"></a>Pregled i pokretanje konfiguracije modela

Korak **Pregled i izvođenje** prikazuje sažetak konfiguracije i pruža priliku za promjene prije stvaranja predviđanje.

1. Na **bilo kojem od koraka za pregled i unos promjena odaberite Uredi**.

1. Ako ste zadovoljni odabirom, odaberite **Spremi i pokreni** da biste započeli s pokretanjem modela. Odaberite **Gotovo**. Kartica **Moja predviđanja** prikazuje se tijekom stvaranja predviđanje. Proces može potrajati nekoliko sati ovisno o količini podataka korištenih za predviđanje.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prikaz rezultata predviđanje

1. Idite na **Obavještajna** > **predviđanja**.

1. Na kartici **Moja predviđanja** odaberite predviđanje koji želite pregledati.

Na stranici rezultata nalazi se pet primarnih odjeljaka podataka.

- **Izvedba modela:** razredi A, B ili C označavaju performanse predviđanje i mogu vam pomoći u donošenju odluke o korištenju rezultata pohranjenih u izlaznom entitetu.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Slika rezultata performansi modela s ocjenom A.":::

  Ocjene se određuju na temelju sljedećih pravila:
  - **A** kada je mjerni podatak "Uspjeh @ K" najmanje 10% veći od polazne vrijednosti.
  - **B** kada je mjerni podatak "Uspjeh @ K" 0% do 10% veći od polazne vrijednosti.
  - **C** kada je mjerni podatak "Uspjeh @ K" manji od osnovnog retka.
  - **Polazna vrijednost**: Najpreporučljiviji proizvodi po broju kupnji kod svih kupaca + naučena pravila utvrđena modelom = skup preporuka za kupce. Predviđanja se zatim uspoređuju s najboljim proizvodima, što se računa brojem klijenata koji su kupili proizvod. Ako klijent ima barem jedan proizvod u preporučenim proizvodima, što se također vidi u najčešće kupljenim proizvodima, smatra se dijelom osnovne vrijednosti. Na primjer, ako je 10 od tih kupaca imalo kupljen preporučeni proizvod od ukupno 100 kupaca, polazna vrijednost iznosi 10%.
  - **Uspjeh @ K**: Preporuke se kreiraju za sve kupce i uspoređuju s validacijskim skupom vremenskog razdoblja transakcija. Na primjer, u razdoblju od 12 mjeseci 12. mjesec izdvaja se kao skup podataka za provjeru valjanosti. Ako model predvidi barem jednu stvar koju biste kupili u 12. mjesecu na temelju onoga što je naučio iz prethodnih 11 mjeseci, klijent će povećati metriku "Uspjeh @ K".

- **Najčešće predlagani proizvodi (s brojačem):** Pet najboljih proizvoda predviđenih za vaše klijente.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Grafikon koji prikazuje 5 najviše preporučenih proizvoda.":::

- **Ključni čimbenici preporuke:** Model koristi povijest transakcija klijenata za davanje preporuka za proizvode. Uči uzorke na temelju prošlih kupnji i pronalazi sličnosti između klijenata i proizvoda. Te se sličnosti zatim koriste za generiranje preporuka za proizvode.
  Sljedeći čimbenici mogli bi utjecati na preporuku proizvoda koju generira model.
  - **Prošle transakcije**: Preporučeni proizvod temeljio se na prošlim obrascima kupnje. Na primjer, model može preporučiti *Miš s površinskim lukom* ako je netko nedavno kupio *Surface Book 3* i *Surface Pen*. Model je naučio da su u prošlosti mnogi klijenti kupili *Miš s površinskim lukom* nakon kupnje *Surface Book 3* i *Surface Pen*.
  - **Sličnost klijenata**: Preporučeni proizvod u prošlosti su kupovali drugi klijenti koji pokazuju slične uzorke kupnje. Na primjer, Ivanu su preporučene slušalice *Surface Headphones 2* jer su Marica i Branko nedavno kupili slušalice *Surface Headphones 2*. Model vjeruje da je Ivan sličan Marici i Branku jer su u prošlosti imali slične uzorke kupnje.
  - **Sličnost proizvoda**: Preporučeni proizvod sličan je ostalim proizvodima koje je klijent ranije kupio. Model smatra da su dva proizvoda slična ako su kupljeni zajedno ili ako su ih kupili slični klijenti. Na primjer, netko dobije preporuku za *USB pogon za pohranu* jer je ranije kupio *USB-C za USB prilagodnik* i model vjeruje da je *USB pogon za pohranu* sličan *USB-C za USB prilagodnik* na temelju povijesnih uzoraka kupnje.

  Na svaku preporuku za proizvod utječe jedan ili više ovih čimbenika. Postotak preporuka u kojima je svaki čimbenik utjecaja igrao ulogu prikazan je na grafikonu. U sljedećem primjeru na 100 % preporuka utjecale su prošle transakcije, 60 % sličnost klijenata i 22 % sličnost proizvoda. Zadržite pokazivač iznad traka na grafikonu da biste vidjeli točan postotak doprinosa čimbenika utjecaja.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Ključni čimbenici preporuke koje je model naučio za generiranje preporuka proizvoda.":::

- **Statistika** podataka: Pregled broja transakcija, kupaca i proizvoda koje je model razmatrao. Temelji se na ulaznim podacima koji su korišteni za učenje uzoraka i generiranje preporuka za proizvode.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Statistika podataka o ulaznim podacima koje model koristi za učenje uzoraka.":::
  
  Model koristi sve dostupne podatke za učenje uzoraka. Stoga, ako koristite filtriranje proizvoda u konfiguraciji modela, ovaj odjeljak prikazuje ukupan broj proizvoda koje je model analizirao kako bi naučio uzorke, koji se mogu razlikovati od broja proizvoda koji odgovaraju definiranim kriterijima filtriranja. Filtriranje se primjenjuje na izlaz koji generira model.

- **Preporuke za ogledne proizvode:** uzorak preporuka za koje model smatra da će ih kupac vjerojatno kupiti. Ako se doda katalog proizvoda, ID-ovi proizvoda zamjenjuju se nazivima proizvoda.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Popis koji prikazuje prijedloge visoke pouzdanosti za odabrani skup pojedinačnih klijenata.":::

> [!NOTE]
> U izlaznom entitetu za ovaj model *Ocjena* prikazuje kvantitativnu mjeru preporuke. Model preporučuje proizvode s višom ocjenom u odnosu na proizvode s nižom ocjenom. Da biste prikazali rezultat, idite na **Entiteti** > **podataka** i pogledajte karticu podataka za izlazni entitet koji ste definirali za ovaj model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
