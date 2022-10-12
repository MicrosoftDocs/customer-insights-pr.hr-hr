---
title: Predvidite prijenos pretplate (sadrži videozapis)
description: Predvidite postoji li opasnost da će klijent prestati koristiti pretplaćene proizvode ili usluge vaše tvrtke.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610227"
---
# <a name="predict-subscription-churn"></a>Predviđanje gubitaka pretplate

Predvidite postoji li opasnost da će klijent prestati koristiti pretplaćene proizvode ili usluge vaše tvrtke. Podaci o pretplati uključuju aktivne i neaktivne pretplate za svakog kupca, tako da postoji više unosa po ID-u kupca.

Morate imati poslovno znanje da biste razumjeli što bućkuriš znači za vaše poslovanje. Podržavamo definicije bućkanja temeljene na vremenu, što znači da se smatra da je kupac proizveo vremensko razdoblje nakon završetka pretplate.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Isprobajte pretplatu predviđanje pomoću oglednih podataka: [Pretplata bućka predviđanje ogledni vodič](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Preduvjeti

- Barem [Dozvole suradnika](permissions.md).
- Najmanje 10 korisničkih profila, po mogućnosti više od 1.000 jedinstvenih kupaca.
- Identifikator kupca, jedinstveni identifikator koji odgovara pretplatama s vašim klijentima.
- Podaci o pretplati barem dvostruko više od odabranog vremenskog prozora. Po mogućnosti dvije do tri godine podataka o pretplati. Povijest pretplata mora sadržavati:
  - **ID pretplate:** jedinstveni identifikator pretplate.
  - **Datum završetka pretplate:** datum isteka pretplate za kupca.
  - **Datum početka pretplate:** datum početka pretplate za kupca.
  - **Datum transakcije:** datum kada je došlo do promjene pretplate. Na primjer, klijent kupuje ili otkazuje pretplatu.
  - **Je li to ponavljajuća pretplata:** Booleovo polje true/false koje određuje hoće li se pretplata obnoviti istim ID-jem pretplate bez intervencije korisnika.
  - **Učestalost ponavljanja (u mjesecima):** za ponavljajuće pretplate mjesec obnovit će se pretplata. Na primjer, godišnja pretplata koja se klijentu automatski obnavlja svake godine na još godinu dana ima vrijednost 12.
  - **Iznos** pretplate: iznos valute koju kupac plaća za obnovu pretplate. Može vam pomoći utvrditi obrasce za različite razine pretplate.
- Najmanje dva zapisa o aktivnostima za 50% kupaca za koje želite izračunati bućkuriš. Aktivnosti kupaca moraju uključivati:
  - **Primarni ključ:** jedinstveni identifikator aktivnosti. Na primjer, posjet web-mjestu ili zapis o upotrebi koji prikazuje da je klijent gledao epizodu neke TV emisije.
  - **Vremenska oznaka:** Datum i vrijeme događaja identificirani primarnim ključem.
  - **Događaj:** naziv događaja koji želite koristiti. Na primjer, polje pod nazivom „UserAction” u usluzi strujanja videa moglo bi imati vrijednost „Prikazano”.
  - **Pojedinosti:** Detaljne informacije o događaju. Na primjer, polje pod nazivom „ShowTitle” u usluzi strujanja videa moglo bi imati vrijednost naziva videa koji je klijent pogledao.
- Manje od 20% nedostajućih vrijednosti u podatkovnom polju navedenog entiteta.

## <a name="create-a-subscription-churn-prediction"></a>Izrada predviđanja gubitaka pretplate

U bilo kojem trenutku odaberite **Spremi skicu** da biste predviđanje spremili kao skicu. Skica predviđanje prikazuje se na **kartici Moja predviđanja**.

1. Idite na **Obavještajna** > **predviđanja**.

1. Na kartici **Stvaranje** **odaberite Koristi model** na pločici Model **modela kupca**.

1. Odaberite **Pretplata** za vrstu bućkanja, a zatim **Početak rada**.

1. **Nazovite ovaj model** i **Naziv izlaznog entiteta** kako bi se razlikovali od ostalih modela ili entiteta.

1. Odaberite **Dalje**.

### <a name="define-customer-churn"></a>Definirajte gubitak klijenta

1. Unesite broj **Dana od isteka pretplate** za koju vaša tvrtka smatra da predstavlja izgubljenog klijenta. Ovo je razdoblje obično povezano s poslovnim aktivnostima poput ponuda ili drugih marketinških napora koji pokušavaju spriječiti gubitak kupca.

1. Unesite broj **dana za istraživanje budućnosti da biste predvidjeli bućkuriš**. Na primjer, predvidite rizik od gubitka klijenata tijekom sljedećih 90 dana kako biste se uskladili s vašim naporima zadržavanja marketinga. Predviđanje rizika gubitka na dulja ili kraća vremenska razdoblja može otežati adresiranje čimbenika u vašem profilu rizika gubitka, ovisno o vašim specifičnim poslovnim zahtjevima.

1. Odaberite **Dalje**.

### <a name="add-required-data"></a>Dodavanje obaveznih podataka

1. Odaberite **Dodaj podatke** za **povijest** pretplata.

1. Odaberite vrstu semantičke aktivnosti **Pretplata** koja sadrži potrebne informacije o povijesti pretplate. Ako aktivnost nije postavljena, odaberite ovdje **i** stvorite je.

1. U odjeljku **Aktivnosti**, ako su atributi aktivnosti semantički mapirani prilikom stvaranja aktivnosti odaberite određene atribute ili entitet na koji želite da se izračun usredotoči. Ako nije došlo do semantičkog mapiranja, odaberite **Uređivanje** i mapiranje podataka.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Dodavanje potrebnih podataka za model churn pretplate":::

1. Odaberite **Dalje** i pregledajte atribute potrebne za ovaj model.

1. Odaberite **Spremi**.

1. Odaberite **Dodaj podatke** za **aktivnosti** klijenta.

1. Odaberite vrstu semantičke aktivnosti koja pruža informacije o aktivnosti klijenta. Ako aktivnost nije postavljena, odaberite ovdje **i** stvorite je.

1. U odjeljku **Aktivnosti**, ako su atributi aktivnosti semantički mapirani prilikom stvaranja aktivnosti odaberite određene atribute ili entitet na koji želite da se izračun usredotoči. Ako nije došlo do semantičkog mapiranja, odaberite **Uređivanje** i mapiranje podataka.

1. Odaberite **Dalje** i pregledajte atribute potrebne za ovaj model.

1. Odaberite **Spremi**.

1. Dodajte još aktivnosti ili odaberite **Dalje**.

### <a name="set-update-schedule"></a>Postavljanje rasporeda ažuriranja

1. Odaberite učestalost prekvalifikacije modela. Ova je postavka važna za ažuriranje točnosti predviđanja jer se novi podaci unose u Customer Insights. Većina tvrtki može ponovno uvježbavati jednom mjesečno i steći dobru točnost predviđanja.

1. Odaberite **Dalje**.

### <a name="review-and-run-the-model-configuration"></a>Pregled i pokretanje konfiguracije modela

Korak **Pregled i izvođenje** prikazuje sažetak konfiguracije i pruža priliku za promjene prije stvaranja predviđanje.

1. Na **bilo kojem od koraka za pregled i unos promjena odaberite Uredi**.

1. Ako ste zadovoljni odabirom, odaberite **Spremi i pokreni** da biste započeli s pokretanjem modela. Odaberite **Gotovo**. Kartica **Moja predviđanja** prikazuje se tijekom stvaranja predviđanje. Proces može potrajati nekoliko sati ovisno o količini podataka korištenih za predviđanje.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prikaz rezultata predviđanje

1. Idite na **Obavještajna** > **predviđanja**.

1. Na kartici **Moja predviđanja** odaberite predviđanje koji želite pregledati.

Postoje tri primarna odjeljka podataka na stranici s rezultatima:

- **Izvedba** modela vježbanja: razredi A, B ili C označavaju izvedbu predviđanje i mogu vam pomoći u donošenju odluke o korištenju rezultata pohranjenih u izlaznom entitetu.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Slika okvira s informacijama o ocjeni modela s ocjenom A.":::

  Ocjene se određuju na temelju sljedećih pravila:
  - **A** kada je model točno predvidio najmanje 50% ukupnih predviđanja i kada je postotak točnih predviđanja za kupce koji su bućkali veći od povijesne prosječne stope bućkanja za najmanje 10%.
  - **B** kada je model točno predvidio najmanje 50% ukupnih predviđanja i kada je postotak točnih predviđanja za kupce koji su bućkali i do 10% veći od povijesne prosječne stope bućkanja.
  - **C** kada je model točno predvidio manje od 50% ukupnih predviđanja ili kada je postotak točnih predviđanja za kupce koji su bućkali manji od povijesne prosječne stope bućkanja.
  
- **Vjerojatnost gubitka (broj klijenata)**: Grupe klijenata na temelju njihovog predviđenog rizika da budu izgubljeni. Po želji stvorite [segmente kupaca](prediction-based-segment.md) s visokim rizikom od bućkanja. Takvi segmenti pomažu vam da shvatite gdje bi trebao biti vaš prag za članstvo u segmentu.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Grafikon koji prikazuje raspodjelu rezultata gubitka, izdijeljen na raspone od 0 – 100 %":::

- **Najutjecajniji faktori:** Mnogo je faktora koji se uzimaju u obzir prilikom izrade predviđanja. Svaki od čimbenika ima svoju važnost izračunatu za skupna predviđanja koja model stvara. Pomoću tih čimbenika provjerite predviđanje rezultate. Ili kasnije upotrijebite te podatke za [stvaranje segmenata](.//prediction-based-segment.md) koji bi mogli utjecati na rizik za kupce.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Popis pokazuje utjecajne čimbenike i njihovu važnost u predviđanju rezultata gubitka.":::

> [!NOTE]
> U izlaznom entitetu za ovaj model ChurnScore *je predviđena vjerojatnost bućkanja,* a *IsChurn* binarna oznaka koja se temelji na *ChurnScoreu* s pragom od 0,5. Ako taj zadani prag ne funkcionira za vaš scenarij, [stvorite novi segment](segments.md) s željenim pragom. Da biste prikazali rezultat, idite na **Entiteti** > **podataka** i pogledajte karticu podataka za izlazni entitet koji ste definirali za ovaj model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
