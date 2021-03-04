---
title: Predviđanje cjeloživotne vrijednosti klijenta (CLV)
description: Predvidite potencijalni prihod za aktivne klijente u budućnosti.
ms.date: 02/05/2021
ms.reviewer: wameng
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 363a46c81b5bb737d274998f9a699dc662e38d7c
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268585"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a>Cjeloživotna vrijednost klijenta (CLV) (Pretpregled)

Predvidite potencijalnu vrijednost (prihod) koju će pojedini aktivni klijenti donijeti u vašu tvrtku u definiranom vremenskom razdoblju u budućnosti. Ova vam značajka može pomoći u postizanju različitih ciljeva: 
- Prepoznati visokovrijedne klijente i obraditi ovaj uvid
- Stvoriti strateške segmente klijenata na temelju njihove potencijalne vrijednosti za vođenje personaliziranih kampanja s ciljanim naporima prodaje, marketinga i podrške
- Voditi razvoj proizvoda usredotočujući se na značajke koje povećavaju vrijednost za klijente
- Optimizirati prodajnu ili marketinšku strategiju i preciznije rasporediti proračun za dosezanje klijenata
- Prepoznati i nagraditi visokovrijedne klijente kroz programe vjernosti ili nagrađivanja 

## <a name="prerequisites"></a>Preduvjeti

Prije početka razmislite što CLV znači za vaše poslovanje. Trenutno podržavamo CLV predviđanje na temelju transakcija. Predviđena vrijednost klijenta temelji se na povijesti poslovnih transakcija. Da biste stvorili predviđanje, treba vam barem dozvola [Suradnik](permissions.md).

Budući da za konfiguriranje i pokretanje CLV modela ne treba puno vremena, razmislite o stvaranju nekoliko modela s različitim preferencijama unosa i usporedite rezultate modela da biste vidjeli koji scenarij modela najbolje odgovara vašim poslovnim potrebama.

###  <a name="data-requirements"></a>Preduvjeti za podatke

Potrebni su sljedeći podaci i ako su označeni kao neobavezni, preporučuju se za veće performanse modela. Što više podataka model može obraditi, to će predviđanje biti preciznije. Stoga vam preporučujemo da unesete više podataka o aktivnostima klijenata, ako su dostupni.

- Identifikator klijenta: jedinstveni identifikator koji povezuje transakcije s pojedinačnim klijentom

- Povijest transakcija: povijesni zapisnik transakcija sa semantičkom shemom podataka ispod
    - ID transakcije: jedinstveni identifikator svake transakcije
    - Datum transakcije: datum, po mogućnosti vremenska oznaka svake transakcije
    - Iznos transakcije: monetarna vrijednost (na primjer, prihod ili marža) svake transakcije
    - Oznaka koja se dodjeljuje povratima (neobavezno): Booleova vrijednost koja označava je li transakcija povrat 
    - ID proizvoda (neobavezno): ID proizvoda za proizvod koji je uključen u transakciju

- Dodatni podaci (neobavezno), na primjer
    - Web-aktivnosti: povijest posjeta web-mjestu, povijest e-pošte
    - Aktivnosti vjernosti: povijest akumulacije i iskorištavanja nagradnih bodova za vjernost
    - Povijest zapisnika službe za korisnike, servisnih poziva, pritužbi ili povrata
- Podaci o aktivnostima klijenata (neobavezno):
    - Identifikatori aktivnosti za razlikovanje aktivnosti iste vrste
    - Identifikatori klijenata za spajanje aktivnosti s klijentima
    - Podaci o aktivnosti koji sadrže naziv i datum aktivnosti
    - Shema semantičkih podataka za aktivnosti uključuje: 
        - Primarni ključ: jedinstveni identifikator aktivnosti
        - Vremenska oznaka: datum i vrijeme događaja identificirani pomoću primarnog ključa
        - Događaj (naziv aktivnosti): naziv događaja koji želite koristiti
        - Pojedinosti (iznos ili vrijednost): pojedinosti o aktivnosti klijenta

## <a name="create-a-customer-lifetime-value-prediction"></a>Stvaranje predviđanja cjeloživotne vrijednosti klijenta

1. U uvidima u ciljnu skupinu idite na **Obavještavanje** > **Predviđanja**.

1. Odaberite pločicu **Cjeloživotna vrijednost klijenta** pa odaberite **Koristi model**. 

1. U oknu **Cjeloživotna vrijednost klijenta (pretpregled)** odaberite **Početak**.

1. **Nazovite ovaj model** i **Naziv izlaznog entiteta** kako bi se razlikovali od ostalih modela ili entiteta.

1. Odaberite **Dalje**.

### <a name="define-model-preferences"></a>Definiranje preferencija modela

1. Postavite **Vremensko razdoblje predviđanja** kako biste definirali koliko daleko u budućnosti želite predvidjeti CLV.    
   Prema zadanim postavkama jedinica se postavlja kao mjeseci. Možete je promijeniti u godine za pogled dalje u budućnosti.

   > [!TIP]
   > Da biste točno predvidjeli CLV za vremensko razdoblje koje ste postavili, trebate usporedivo razdoblje povijesnih podataka. Na primjer, ako želite predvidjeti za sljedećih 12 mjeseci, preporučuje se da imate najmanje 18 – 24 mjeseca povijesnih podataka.

1. Navedite što **Aktivni klijenti** znači za vaše poslovanje. Postavite vremenski okvir u kojem je klijent morao imati barem jednu transakciju da bi se smatrao aktivnim. Model će predvidjeti CLV samo za aktivne klijente. 
   - **Neka model izračuna interval kupnje (preporučeno)**: Model analizira vaše podatke i određuje vremensko razdoblje na temelju povijesnih kupnji.
   - **Ručno postavljanje intervala**: Ako imate specifičnu poslovnu definiciju aktivnog klijenta, odaberite ovu mogućnost i u skladu s tim postavite vremensko razdoblje.

1. Definirajte percentil **Visokovrijednog klijenta** da biste model omogućili za pružanje rezultata koji odgovaraju vašoj poslovnoj definiciji.
    - **Izračun modela (preporučeno)**: Model analizira vaše podatke i na temelju povijesti transakcija vaših klijenata određuje što bi visokovrijedni klijent mogao biti za vaše poslovanje. Model koristi heurističko pravilo (inspirirano pravilom 80/20 ili Paretovim načelom) za pronalaženje udjela visokovrijednih klijenata. Postotak klijenata koji su u povijesnom razdoblju vašoj tvrtki donijeli 80 % kumulativnog prihoda smatra se visokovrijednim klijentima. Obično, manje od 30-40 % klijenata donosi 80 % kumulativnog prihoda. Međutim, ovaj se broj može razlikovati ovisno o vašem poslu i grani industrije.    
    - **Postotak najaktivnijih klijenata**: Definirajte visokovrijedne klijente za svoju tvrtku kao percentil klijenata koji su najaktivniji u plaćanju. Na primjer, ovu mogućnost možete koristiti za definiranje visokovrijednih klijenata kao prvih 20 % budućih klijenata koji plaćaju.

    Ako vaša tvrtka na drugačiji način definira visokovrijedne klijente, [javite nam jer bismo to htjeli znati](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Odaberite **Sljedeće** kako biste prešli na sljedeći korak.

### <a name="add-required-data"></a>Dodajte potrebne podatke

1. U koraku **Potrebni podaci**, odaberite **Dodaj podatke** za **Povijest transakcija klijenta** i odaberite entitet koji pruža informacije o povijesti transakcija kao što je opisano u [preduvjetima](#prerequisites).

1. Mapirajte semantička polja na atribute unutar entiteta povijesti kupnje i odaberite **Sljedeće**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Slika koraka konfiguracije za mapiranje atributa podataka za potrebne podatke.":::
 
1. Ako polja u nastavku nisu popunjena, konfigurirajte odnos između entiteta povijesti kupnji i entiteta *Klijent* pa odaberite **Spremi**.
    1. Odaberite entitet povijesti transakcija.
    1. Odaberite polje koje identificira klijenta u entitetu povijesti kupnji. Mora se odnositi na primarni ID klijenta vašeg entiteta Klijent.
    1. Odaberite entitet koji odgovara vašem primarnom entitetu klijenta.
    1. Unesite naziv koji opisuje odnos.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Slika koraka konfiguracije za definiranje odnosa s entitetom klijenta.":::

1. Odaberite **Dalje**.

### <a name="add-optional-data"></a>Dodavanje neobaveznih podataka

Podaci koji odražavaju ključne interakcije klijenata (poput weba, službe za korisnike i zapisnika događaja) dodaju kontekst zapisima transakcija. Više obrazaca pronađenih u podacima o aktivnostima klijenata može poboljšati točnost predviđanja. 

1. U koraku **Dodatni podaci (neobavezno)** odaberite **Dodaj podatke**. Odaberite entitet aktivnosti klijenata koji pruža informacije o aktivnostima klijenata kao što je opisano u [preduvjetima](#prerequisites).

1. Mapirajte semantička polja na atribute unutar entiteta aktivnosti klijenta i odaberite **Sljedeće**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Slika koraka konfiguracije za mapiranje polja za dodatne podatke.":::

1. Odaberite vrstu aktivnosti koja odgovara vrsti aktivnosti klijenta koju dodajete. Odaberite neku od postojećih vrsta aktivnosti ili dodajte novu vrstu aktivnosti.

1. Konfigurirajte odnos između entiteta aktivnosti klijenta i entiteta *Klijent*.
    
    1. Odaberite polje koje identificira klijenta u tablici aktivnosti klijenta. Može se izravno povezati s primarnim ID-jem klijenta vašeg entiteta *Klijent*.
    1. Odaberite entitet *Klijent* koji odgovara vašem primarnom entitetu *Klijent*.
    1. Unesite naziv koji opisuje odnos.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Slika koraka u tijeku konfiguracije za dodavanje dodatnih podataka i konfiguriranje aktivnosti s popunjenim primjerima.":::

1. Odaberite **Spremi**.    
    Dodajte još podataka ako postoje druge aktivnosti klijenata koje želite uključiti.

1. Odaberite **Dalje**.

### <a name="set-update-schedule"></a>Postavljanje rasporeda ažuriranja

1. U koraku **Raspored ažuriranja podataka** odaberite frekvenciju za ponovno obučavanje vašeg modela na temelju najnovijih podataka. Ova je postavka važna za ažuriranje točnosti predviđanja jer se novi podaci unose u uvide u ciljnu skupinu. Većina tvrtki može ponovno uvježbavati jednom mjesečno i steći dobru točnost predviđanja.

1. Odaberite **Dalje**.


### <a name="review-and-run-the-model-configuration"></a>Pregled i pokretanje konfiguracije modela

1. U koraku **Pregledajte pojedinosti o svom modelu** provjerite konfiguraciju predviđanja. Možete se vratiti bilo kojem dijelu konfiguracije predviđanja odabirom **Uredi** ispod prikazane vrijednosti. Korak konfiguracije možete odabrati i iz pokazatelja napretka.

1. Ako su sve vrijednosti ispravno konfigurirane, odaberite **Spremi i pokreni** za pokretanje modela. Na kartici **Moja predviđanja** možete vidjeti status postupka predviđanja. Proces može potrajati nekoliko sati ovisno o količini podataka korištenih za predviđanje.

## <a name="review-prediction-status-and-results"></a>Pregled statusa i rezultata predviđanja

### <a name="review-prediction-status"></a>Pregled statusa predviđanja

1.  Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.
2.  Odaberite predviđanje koje želite pregledati.

- **Naziv predviđanja:**: naziv predviđanja naveden pri stvaranju.
- **Vrsta predviđanja**: vrsta modela koji se koristi za predviđanje
- **Entitet rezultata**: naziv entiteta za pohranu rezultata predviđanja. Idite u odjeljak **Podaci** > **Entiteti** da biste pronašli entitet s ovim nazivom.
- **Predviđeno polje**: Ovo se polje popunjava samo za neke vrste predviđanja i ne koristi se u predviđanju cjeloživotne vrijednosti klijenta.
- **Status**: status pokretanja predviđanja.
    - **U redu čekanja**: predviđanje čeka da se drugi procesi dovrše.
    - **Osvježavanje**: predviđanje je trenutno pokrenuto za stvaranje rezultata koji će ići u izlazni entitet.
    - **Neuspjelo**: pokretanje predviđanja nije uspjelo. [Pregledajte zapisnike](#troubleshoot-a-failed-prediction) za dodatne pojedinosti.
    - **Uspjelo**: predviđanje je uspjelo. Odaberite **Prikaz** ispod vertikalnih elipsi za pregled rezultata predviđanja.
- **Uređeno**: promijenjen je datum konfiguriranja za predviđanje.
- **Zadnji put osvježeno**: datum kada je predviđanje osvježilo rezultate u izlaznom entitetu.


### <a name="review-prediction-results"></a>Pregled rezultata predviđanja

1. Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.

1. Odaberite predviđanje za koje želite pregledati rezultate.

Postoje tri primarna odjeljka podataka na stranici s rezultatima.

- **Performanse modela za obuku**: Moguće su ocjene A, B ili C. Ova ocjena označava performanse predviđanja i može vam pomoći da donesete odluku o korištenju rezultata pohranjenih u izlaznom entitetu. Odaberite **Više o ovoj ocjeni** za bolje razumijevanje osnovne metrike rezultata modela i kako je dobivena konačna ocjena performansi modela.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Slika okvira s informacijama o ocjeni modela s ocjenom A.":::

  Koristeći definiciju visokovrijednih klijenata koja se pruža tijekom konfiguriranja predviđanja, sustav procjenjuje uspješnost modela umjetne inteligencije u predviđanju visokovrijednih klijenata u usporedbi s osnovnim modelom.    

  Ocjene se određuju na temelju sljedećih pravila:
  - A kada je model točno predvidio najmanje 5 % više visokovrijednih klijenata u usporedbi s osnovnim modelom.
  - B kada je model točno predvidio od 0 do 5 % više visokovrijednih klijenata u usporedbi s osnovnim modelom.
  - C kada je model točno predvidio manje visokovrijednih klijenata u usporedbi s osnovnim modelom.

  Okno **Ocjena modela** prikazuje daljnje pojedinosti o performansama modela umjetne inteligencije i osnovnom modelu. Osnovni model koristi pristup koji se ne temelji na umjetnoj inteligenciji za izračunavanje cjeloživotne vrijednosti klijenta prvenstveno na temelju povijesnih kupnji koje su obavili klijenti.     
  Standardna formula koja se koristi za izračunavanje CLV-a po osnovnom modelu:    

  *CLV za svakog klijenta = prosječna mjesečna kupnja koju je klijent izvršio u aktivnom prozoru klijenta * broj mjeseci u CLV razdoblju predviđanja * ukupna stopa zadržavanja svih klijenata*

  Model umjetne inteligencije uspoređuje se s osnovnim modelom na temelju dva mjerila performansi modela.
  
  - **Stopa uspješnosti u predviđanju visokovrijednih klijenata**

  Pogledajte razliku u predviđanju visokovrijednih klijenata pomoću modela umjetne inteligencije u usporedbi s osnovnim modelom. Na primjer, stopa uspješnosti od 84 % znači da je od svih visokovrijednih klijenata u podacima obuke model umjetne inteligencije uspio točno zabilježiti 84 %. Zatim uspoređujemo ovu stopu uspješnosti sa stopom uspješnosti osnovnog modela kako bismo izvijestili o relativnoj promjeni. Ova se vrijednost koristi za dodjeljivanje ocjene modelu.

  - **Metrike pogreške**
    
  Drugo mjerilo omogućuje vam pregled ukupnih performansi modela u smislu pogreške u predviđanju budućih vrijednosti. Za procjenu ove pogreške koristimo ukupnu metriku korijenske srednje kvadratne pogreške (RMSE). RMSE je standardni način mjerenja pogreške modela u predviđanju kvantitativnih podataka. RMSE modela umjetne inteligencije uspoređuje se s RMSE-om osnovnog modela i dobiva se izvješće o relativnoj razlici.

  Model umjetne inteligencije daje prednost točnom rangiranju klijenata prema vrijednosti koju oni donose vašem poslovanju. Dakle, za dobivanje konačne ocjene modela koristi se samo se stopa uspješnosti predviđanja visokovrijednih klijenata. Metrika RMSE je osjetljiva na netipične vrijednosti. U scenarijima gdje imate mali postotak klijenata s izvanredno visokim vrijednostima kupnje, ukupna metrika RMSE možda neće dati cjelovitu sliku performansi modela.   

- **Vrijednost klijenata prema percentilu**: Koristeći vašu definiciju visokovrijednih klijenata, klijenti su grupirani u niskovrijedne i visokovrijedne na temelju njihovih CLV predviđanja i prikazani u grafikonu. Zadržavanjem pokazivača iznad histograma možete vidjeti broj klijenata u svakoj grupi i prosječni CLV te grupe. Ovi podaci vam mogu pomoći ako želite [stvoriti segmente klijenata](segments.md) na temelju njihovih CLV predviđanja.

- **Najutjecajniji faktori**: Prilikom stvaranja vašeg CLV predviđanja na temelju ulaznih podataka pruženih modelu umjetne inteligencije uzimaju se u obzir različiti faktori. Svaki od tih faktora ima svoju važnost izračunatu za skupna predviđanja koja model stvara. Pomoću tih faktora možete potvrditi rezultate predviđanja. Ovi faktori također pružaju bolji uvid u najutjecajnije faktore koji su pridonijeli predviđanju CLV-a za sve vaše klijente.

## <a name="refresh-a-prediction"></a>Osvježavanje predviđanja

Predviđanja se automatski osvježavaju prema istom [rasporedu prema kojem se osvježavaju podaci](system.md#schedule-tab) kako je konfigurirano u postavkama. Možete ih osvježiti i ručno.

1. Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.
2. Odaberite okomitu trotočku uz predviđanje koje želite osvježiti.
3. Odaberite **Osvježi**.

## <a name="delete-a-prediction"></a>Brisanje predviđanja

Brisanjem predviđanja uklanja se i njegov izlazni entitet.

1. Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.
2. Odaberite okomitu trotočku uz predviđanje koje želite izbrisati.
3. Odaberite **Obriši**.

## <a name="troubleshoot-a-failed-prediction"></a>Otklanjanje poteškoća s neuspjelim predviđanjem

1. Idite na **Obavještavanje** > **Predviđanja** i odaberite karticu **Moja predviđanja**.
2. Odaberite okomite elipse pored predviđanja za koje želite pregledati zapisnike pogrešaka.
3. Odaberite **Zapisnici**.
4. Pregledajte sve pogreške. Može se dogoditi nekoliko vrsta pogrešaka i one opisuju kakvo je stanje prouzročilo pogrešku. Na primjer, pogreška u kojoj nema dovoljno podataka za točno predviđanje obično se rješava učitavanjem više podataka u uvide u ciljnu skupinu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]