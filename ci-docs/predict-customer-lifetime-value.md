---
title: Predviđanje cjeloživotne vrijednosti klijenta (CLV)
description: Predvidite potencijalni prihod za aktivne klijente u budućnosti.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610365"
---
# <a name="predict-customer-lifetime-value-clv"></a>Predviđanje cjeloživotne vrijednosti klijenta (CLV)

Predvidite potencijalnu vrijednost (prihod) koju će pojedini aktivni klijenti donijeti u vašu tvrtku u definiranom vremenskom razdoblju u budućnosti. Ovaj predviđanje vam pomaže:

- Identificirajte kupce visoke vrijednosti i obradite taj uvid.
- Izradite strateške segmente kupaca na temelju njihove potencijalne vrijednosti za pokretanje personaliziranih kampanja s ciljanim naporima prodaje, marketinga i podrške.
- Usmjerite razvoj proizvoda usredotočujući se na značajke koje povećavaju vrijednost kupca.
- Optimizirajte prodajnu ili marketinšku strategiju i preciznije alocirajte proračun za doseg kupaca.
- Prepoznajte i nagradite visokovrijedne kupce putem programa lojalnosti ili nagrađivanja.

Odredite što CLV znači za vaše poslovanje. Podržavamo CLV predviđanje temeljene na transakcijama. Predviđena vrijednost kupca temelji se na povijesti poslovnih transakcija. Razmislite o stvaranju nekoliko modela s različitim ulaznim preferencijama i usporedite rezultate modela kako biste vidjeli koji scenarij modela najbolje odgovara vašim poslovnim potrebama.

> [!TIP]
> Isprobajte CLV predviđanje koristeći ogledne podatke: [Vrijednost životnog vijeka kupca (CLV) predviđanje vodič za uzorke](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Preduvjeti

- Najmanje [suradnik](permissions.md) dozvola
- Najmanje 100 jedinstvenih kupaca, po mogućnosti više od 10.000 kupaca
- Identifikator kupca, jedinstveni identifikator za podudaranje transakcija s pojedinačnim kupcem
- Najmanje godinu dana povijesti transakcija, po mogućnosti dvije do tri godine. U idealnom slučaju, najmanje dvije do tri transakcije po ID-u kupca, po mogućnosti na više datuma. Povijest transakcija mora sadržavati:
  - **ID transakcije**: jedinstveni identifikator svake transakcije
  - **Datum** transakcije: datumska ili vremenska oznaka svake transakcije
  - **Iznos transakcije**: novčana vrijednost (na primjer, prihod ili marža) svake transakcije
  - **Oznaka dodijeljena povratima**: Booleova vrijednost true/false koja označava je li transakcija povrat
  - **ID** proizvoda: ID proizvoda proizvoda uključenog u transakciju
- Podaci o aktivnostima klijenta:
  - **Primarni ključ**: jedinstveni identifikator aktivnosti
  - **Vremenska oznaka**: Datum i vrijeme događaja identificirani primarnim ključem
  - **Događaj (naziv aktivnosti)**: Naziv događaja koji želite koristiti
  - **Pojedinosti (iznos ili vrijednost)**: pojedinosti o aktivnosti klijenta
- Dodatni podaci kao što su:
  - Web-aktivnosti: povijest posjeta web-mjestu ili povijest e-pošte
  - Aktivnosti vjernosti: Povijest prikupljanja nagradnih bodova vjernosti i otkupa
  - Služba za korisnike zapisnik: servisni poziv, pritužba ili povijest vraćanja
  - Podaci o profilu kupca
- Manje od 20% nedostajućih vrijednosti u obaveznim poljima

> [!NOTE]
> Može se konfigurirati samo jedan entitet povijesti transakcija. Ako postoji više subjekata za nabavu Power Query ili transakcije, kombinirajte ih prije gutanja podataka.

## <a name="create-a-customer-lifetime-value-prediction"></a>Stvaranje predviđanja cjeloživotne vrijednosti klijenta

U bilo kojem trenutku odaberite **Spremi skicu** da biste predviđanje spremili kao skicu. Skica predviđanje prikazuje se na **kartici Moja predviđanja**.

1. Idite na **Obavještajna** > **predviđanja**.

1. Na kartici **Stvaranje** odaberite **Koristi model** na pločici Vrijednost životnog vijeka **kupca**.

1. Odaberite **Početak rada**.

1. **Nazovite ovaj model** i **Naziv izlaznog entiteta** kako bi se razlikovali od ostalih modela ili entiteta.

1. Odaberite **Dalje**.

### <a name="define-model-preferences"></a>Definiranje preferencija modela

1. Postavite **Vremensko razdoblje predviđanja** kako biste definirali koliko daleko u budućnosti želite predvidjeti CLV. Prema zadanim postavkama jedinica se postavlja kao mjeseci.

   > [!TIP]
   > Za točno predviđanje CLV-a za određeno vremensko razdoblje potrebno je usporedivo razdoblje povijesnih podataka. Na primjer, ako želite predvidjeti CLV za sljedećih 12 mjeseci, imate najmanje 18 - 24 mjeseca povijesnih podataka.

1. Postavite vremenski okvir u kojem je klijent morao imati barem jednu transakciju da bi se smatrao aktivnim. Model predviđa CLV samo za **aktivne kupce**.
   - **Neka model izračuna interval kupnje (preporučeno)**: Model analizira vaše podatke i određuje vremensko razdoblje na temelju povijesnih kupnji.
   - **Ručno postavite interval: vremensko** razdoblje za definiciju aktivnog kupca.

1. Definirajte percentil kupca **visoke** vrijednosti.
    - **Izračun modela (preporučeno)**: Model koristi pravilo 80/20. Postotak klijenata koji su u povijesnom razdoblju vašoj tvrtki donijeli 80 % kumulativnog prihoda smatra se visokovrijednim klijentima. Obično, manje od 30-40 % klijenata donosi 80 % kumulativnog prihoda. Međutim, ovaj se broj može razlikovati ovisno o vašem poslu i grani industrije.
    - **Postotak najboljih aktivnih kupaca**: specifičan percentil za kupca visoke vrijednosti. Na primjer, unesite **25** da biste definirali kupce visoke vrijednosti kao prvih 25% budućih kupaca koji plaćaju.

    Ako vaša tvrtka na drugačiji način definira visokovrijedne klijente, [javite nam jer bismo to htjeli znati](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Odaberite **Dalje**.

### <a name="add-required-data"></a>Dodavanje obaveznih podataka

1. Odaberite **Dodaj podatke** za **povijest** transakcija kupca.

1. Odaberite vrstu semantičke aktivnosti, **SalesOrder ili** **SalesOrderLine**, koja sadrži povijest transakcija. Ako aktivnost nije postavljena, odaberite ovdje **i** stvorite je.

1. U odjeljku **Aktivnosti**, ako su atributi aktivnosti semantički mapirani prilikom stvaranja aktivnosti odaberite određene atribute ili entitet na koji želite da se izračun usredotoči. Ako nije došlo do semantičkog mapiranja, odaberite **Uređivanje** i mapiranje podataka.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Dodavanje potrebnih podataka za CLV model":::

1. Odaberite **Dalje** i pregledajte atribute potrebne za ovaj model.

1. Odaberite **Spremi**.

1. Dodajte još aktivnosti ili odaberite **Dalje**.

### <a name="add-optional-activity-data"></a>Dodavanje neobaveznih podataka o aktivnostima

Podaci koji odražavaju ključne interakcije klijenata (poput weba, službe za korisnike i zapisnika događaja) dodaju kontekst zapisima transakcija. Više obrazaca pronađenih u podacima o aktivnostima klijenata može poboljšati točnost predviđanja.

1. U odjeljku Povećaj uvide modela pomoću **dodatnih podataka o** aktivnostima odaberite **Dodaj podatke**.

1. Odaberite vrstu aktivnosti koja odgovara vrsti aktivnosti klijenta koju dodajete. Ako aktivnost nije postavljena, odaberite ovdje **i** stvorite je.

1. U odjeljku **Aktivnosti**, ako su atributi aktivnosti mapirani prilikom stvaranja aktivnosti odaberite određene atribute ili entitet na koji želite da se izračun usredotoči. Ako do mapiranja nije došlo, odaberite **Uređivanje** i mapiranje podataka.

1. Odaberite **Dalje** i pregledajte atribute potrebne za ovaj model.

1. Odaberite **Spremi**.

1. Odaberite **Dalje**.

1. [Dodajte neobavezne podatke o klijentima](#add-optional-customer-data) ili odaberite **Dalje** i idite na [Postavljanje rasporeda](#set-update-schedule) ažuriranja.

### <a name="add-optional-customer-data"></a>Dodavanje neobaveznih podataka o klijentima

Odaberite jednu od 18 najčešće korištenih atributa korisničkog profila koje želite uključiti kao unos u model. Ti atributi mogu dovesti do personaliziranijih, relevantnijih i djelotvornijih rezultata modela za slučajeve vaše poslovne upotrebe.

Na primjer: Contoso Coffee želi predvidjeti životnu vrijednost kupca kako bi ciljao kupce visoke vrijednosti personaliziranom ponudom povezanom s lansiranjem njihovog novog aparata za espresso. Contoso koristi model CLV i dodaje svih 18 atributa korisničkog profila kako bi vidjeli koji čimbenici utječu na njihove kupce najviše vrijednosti. Smatraju da je lokacija kupca najutjecajniji čimbenik za te kupce.
Ovim informacijama organiziraju lokalni događaj za pokretanje aparata za espresso i udružuju se s lokalnim dobavljačima za personalizirane ponude i poseban doživljaj na događaju. Bez tih informacija, Contoso možda su slali samo generičke marketinške e-poruke i propustili priliku personalizirati za ovaj lokalni segment svojih visokovrijednih kupaca.

1. U **odjeljku Povećajte uvide modela još više odaberite** Dodaj podatke **uz dodatne podatke o kupcima**.

1. Za **entitet** odaberite **Kupac: CustomerInsights da biste odabrali** jedinstveni korisnički profil koji mapira na podatke atributa klijenta. Za **ID** klijenta odaberite **System.Customer.Customer.CustomerId**.

1. Mapirajte više polja ako su podaci dostupni u vašim jedinstvenim profilima kupaca.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Primjer mapiranih polja za podatke profila korisnika.":::

1. Odaberite **Spremi**.

1. Odaberite **Dalje**.

### <a name="set-update-schedule"></a>Postavljanje rasporeda ažuriranja

1. Odaberite učestalost prekvalifikacije modela na temelju najnovijih podataka. Ova je postavka važna za ažuriranje točnosti predviđanja jer se novi podaci unose u Customer Insights. Većina tvrtki može ponovno uvježbavati jednom mjesečno i steći dobru točnost predviđanja.

1. Odaberite **Dalje**.

### <a name="review-and-run-the-model-configuration"></a>Pregled i pokretanje konfiguracije modela

Korak **Pregled i izvođenje** prikazuje sažetak konfiguracije i pruža priliku za promjene prije stvaranja predviđanje.

1. Na **bilo kojem od koraka za pregled i unos promjena odaberite Uredi**.

1. Ako ste zadovoljni odabirom, odaberite **Spremi i pokreni** da biste započeli s pokretanjem modela. Odaberite **Gotovo**. Kartica **Moja predviđanja** prikazuje se tijekom stvaranja predviđanje. Proces može potrajati nekoliko sati ovisno o količini podataka korištenih za predviđanje.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prikaz rezultata predviđanje

1. Idite na **Obavještajna** > **predviđanja**.

1. Na kartici **Moja predviđanja** odaberite predviđanje koji želite pregledati.

Postoje tri primarna odjeljka podataka na stranici s rezultatima.

- **Izvedba** modela vježbanja: razredi A, B ili C označavaju izvedbu predviđanje i mogu vam pomoći u donošenju odluke o korištenju rezultata pohranjenih u izlaznom entitetu.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Slika okvira s informacijama o ocjeni modela s ocjenom A.":::

  Customer Insights procjenjuje kako je AI model funkcionirao u predviđanju kupaca visoke vrijednosti u usporedbi s osnovnim modelom.

  Ocjene se određuju na temelju sljedećih pravila:
  - **A** kada je model točno predvidio najmanje 5 % više visokovrijednih klijenata u usporedbi s osnovnim modelom.
  - **B** kada je model točno predvidio od 0 do 5 % više visokovrijednih klijenata u usporedbi s osnovnim modelom.
  - **C** kada je model točno predvidio manje visokovrijednih klijenata u usporedbi s osnovnim modelom.
  
  Odaberite [**Saznajte više o ovom rezultatu**](#learn-about-the-score) da biste otvorili okno s ocjenom **Model** koje prikazuje dodatne pojedinosti o performansama modela umjetne inteligencije i osnovnom modelu. To će vam pomoći da bolje razumijete temeljne mjerne podatke o performansama modela i kako je izvedena konačna ocjena performansi modela. Osnovni model koristi pristup koji se ne temelji na umjetnoj inteligenciji za izračunavanje cjeloživotne vrijednosti klijenta prvenstveno na temelju povijesnih kupnji koje su obavili klijenti.

- **Vrijednost kupaca po percentilu**: kupci male vrijednosti i visoke vrijednosti prikazuju se na grafikonu. Zadržite pokazivač miša iznad traka u histogramu da biste vidjeli broj kupaca u svakoj grupi i prosječni CLV te grupe. Po želji stvorite [segmente kupaca](prediction-based-segment.md) na temelju njihovih CLV predviđanja.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Vrijednost kupaca po percentilu za CLV model":::

- **Najutjecajniji faktori**: Prilikom stvaranja vašeg CLV predviđanja na temelju ulaznih podataka pruženih modelu umjetne inteligencije uzimaju se u obzir različiti faktori. Svaki od tih faktora ima svoju važnost izračunatu za skupna predviđanja koja model stvara. Pomoću tih čimbenika provjerite predviđanje rezultate. Ovi faktori također pružaju bolji uvid u najutjecajnije faktore koji su pridonijeli predviđanju CLV-a za sve vaše klijente.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Najutjecajniji čimbenici za CLV model":::

### <a name="learn-about-the-score"></a>Saznajte više o rezultatu

Standardna formula koja se koristi za izračunavanje CLV-a po osnovnom modelu:

 _**CLV za svakog kupca** = Prosječna mjesečna kupnja kupca u aktivnom prozoru kupca * Broj mjeseci u CLV predviđanje razdoblju * Ukupna stopa zadržavanja svih kupaca_

Model umjetne inteligencije uspoređuje se s osnovnim modelom na temelju dva mjerila performansi modela.
  
- **Stopa uspješnosti u predviđanju visokovrijednih klijenata**

  Pogledajte razliku u predviđanju visokovrijednih klijenata pomoću modela umjetne inteligencije u usporedbi s osnovnim modelom. Na primjer, stopa uspješnosti od 84 % znači da je od svih visokovrijednih klijenata u podacima obuke model umjetne inteligencije uspio točno zabilježiti 84 %. Zatim uspoređujemo ovu stopu uspješnosti sa stopom uspješnosti osnovnog modela kako bismo izvijestili o relativnoj promjeni. Ova se vrijednost koristi za dodjeljivanje ocjene modelu.

- **Metrike pogreške**

  Pogledajte ukupne performanse modela u smislu pogreške u predviđanju budućih vrijednosti. Za procjenu ove pogreške koristimo ukupnu metriku korijenske srednje kvadratne pogreške (RMSE). RMSE je standardni način mjerenja pogreške modela u predviđanju kvantitativnih podataka. RMSE modela umjetne inteligencije uspoređuje se s RMSE-om osnovnog modela i dobiva se izvješće o relativnoj razlici.

Model umjetne inteligencije daje prednost točnom rangiranju klijenata prema vrijednosti koju oni donose vašem poslovanju. Dakle, za dobivanje konačne ocjene modela koristi se samo se stopa uspješnosti predviđanja visokovrijednih klijenata. Metrika RMSE je osjetljiva na netipične vrijednosti. U scenarijima gdje imate mali postotak klijenata s izvanredno visokim vrijednostima kupnje, ukupna metrika RMSE možda neće dati cjelovitu sliku performansi modela.

[!INCLUDE [footer-include](includes/footer-banner.md)]
