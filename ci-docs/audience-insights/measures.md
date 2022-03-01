---
title: Stvaranje i uređivanje mjera
description: Definirajte mjere povezane s klijentima kako biste analizirali i odrazili performanse određenih poslovnih područja.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405337"
---
# <a name="define-and-manage-measures"></a>Definiranje i upravljanje mjerama

**Mjere** predstavljaju ključne pokazatelje uspješnosti (KPI-jeve) koji odražavaju performanse i stanje specifičnog poslovnog područja. Uvidi u ciljnu skupinu pružaju intuitivno iskustvo za izgradnju različitih vrsta mjera pomoću sastavljača upita koji ne zahtijeva ručno kodiranje ili provjeru valjanosti mjera. Poslovne mjere možete pratiti na stranici **Početna**, pregledati mjere za određene klijente na stavci **Kartica klijenta** i koristiti mjere za definiranje segmenata klijenata na stranici **Segmenti**.

## <a name="create-a-measure"></a>Izrada mjere

Ovaj vas dio vodi kroz izradu mjere od početka. Možete izraditi mjere s podacima iz više izvora podataka koji su povezani putem entiteta Klijent. Primjenjuju se neka [ograničenja usluge](service-limits.md).

1. U uvidima u ciljnu skupinu idite na **Mjere**.

2. Odaberite **Nova mjera**.

3. Odaberite mjeru **Vrsta**:

   - **Atribut klijenta**: jedno polje po klijentu koje odražava ocjenu, vrijednost ili stanje za klijenta. Atributi klijenta izrađeni su kao atributi u novom entitetu koji generira sustav naziva **Mjera klijenta**.

   - **Mjera klijenta**: uvidi o klijentu o ponašanju klijenta s raščlambom odabranih dimenzija. Novi se entitet generira za svaku mjeru, potencijalno s više zapisa po klijentu.

   - **Poslovna mjera**: prati poslovanje vaše tvrtke i stanje poslovnog odnosa. Poslovne mjere mogu imati dva različita rezultata: numerički rezultat koji se prikazuje na stranici **Početna** ili novi entitet koji možete pronaći na stranici **Entiteti**.

4. Navedite **Naziv** i opcionalni **Zaslonski naziv** i zatim odaberite **Dalje**.

5. U odjeljku **Entiteti** odaberite prvi entitet na padajućem izborniku. Ovdje biste trebali odlučiti jesu li dodatni entiteti potrebni kao dio definicije mjerenja.

   > [!div class="mx-imgBorder"]
   > ![Definicija mjerila](media/measure-definition.png "Definicija mjerila")

   Za dodavanje više entiteta odaberite **Dodaj entitet** i odaberite entitete koje želite koristiti za mjerenje.

   > [!NOTE]
   > Možete odabrati samo entitete koji su u odnosu s vašim početnim entitetom. Za više informacija o definiranju odnosa pogledajte dio [Odnosi](relationships.md).

6. Opcionalno možete konfigurirati varijable. U odjeljku **Varijable** odaberite **Nova varijabla**.

   Varijable su izračuni koji se izvode za svaki vaš odabrani zapis. Na primjer, zbrajanje prodajnog mjesta (POS) i internetskih prodaja za svaki zapis vašeg klijenta.

7. Navedite **Naziv** za varijablu.

8. U dijelu **Izraz** odaberite polje s kojim čete započeti izračun.

9. Upišite izraz u polje **Izraz** i pritom odaberite više polja koja će se uključiti u vaš izračun.

   > [!NOTE]
   > Trenutno su podržani samo aritmetički izrazi. Osim toga, izračun varijabli nije podržan za entitete s različitih [putova entiteta](relationships.md).

10. Odaberite **Gotovo**.

11. U odjeljku **Definicija mjere** definirat ćete kako se vaši odabrani entiteti i izračunate varijable agregiraju u novi entitet ili atribut mjere.

12. Odaberite **Nova dimenzija**. Dimenzije možete shvatiti kao funkciju *grupiraj kao*. Rezultat podataka vašeg entiteta ili atributa Mjera bit će grupiran prema svim vašim definiranim dimenzijama.

    > [!div class="mx-imgBorder"]
    > ![Odaberite skupni ciklus](media/measures-businessreport-measure-definition2.png "Odaberite skupni ciklus")

    Odaberite ili unesite sljedeće informacija kao dio definicije dimenzije:

    - **EntitetEntity**: ako definirate entitet Mjera, on bi trebao uključivati barem jedan atribut. Ako definirate atribut Mjera, on će uključivati samo jedan atribut prema zadanim postavkama. Pri ovom se odabiru radi o odabiru entiteta koji uključuje taj atribut.
    - **Polje**: odaberite specifični atribut koji će se uključiti u vaš entitet ili atribut Mjera.
    - **Grupa**: odaberite želite li agregirati podatke na dnevnoj, mjesečnoj ili godišnjoj osnovi. To je obavezan odabir samo ako ste odabrali atribut vrste Datum.
    - **Kao**: definira naziv vašeg novog polja.
    - **Zaslonski naziv**: definira zaslonski naziv vašeg polja.

    > [!NOTE]
    > Vaša poslovna mjera bit će spremljena kao entitet s jednim brojem i prikazat će se na stranici **Početna**, osim ako ne dodate više dimenzija za svoju mjeru. Nakon što dodate više dimenzija, mjera se *neće* prikazati na stranici **Početna**.

13. Izborno možete dodati funkcije agregacije. Svaka agregacija koje izradite može rezultirati novom vrijednosti unutar entiteta ili atributa Mjera. Podržane funkcije agregacije su: **Min**, **Maks**, **Prosjek**, **Medijan**, **Zbroj**, **Jedinstveni broj**, **Prvo** (uzima prvi zapis vrijednosti dimenzije) i **Posljednje** (uzima posljednji zapis dodan za vrijednost dimenzije).

14. Odaberite **Spremi** kako biste spremili izmjene mjere.

## <a name="manage-your-measures"></a>Upravljanje mjerama

Nakon što stvorite barem jednu mjeru, vidjet ćete popis mjera na stranici **Mjere**.

Tu možete pronaći informacije o vrsti mjere, autoru, datumu i vremenu izrade, datumu i vremenu posljednjeg ažuriranja, statusu (je li mjera aktivna, neaktivna ili nije uspjela) i posljednjem datumu i vremenu osvježavanja. Kada s popisa odaberete mjeru, možete vidjeti pretpregled njezina izlaza.

Da biste istovremeno osvježili sve svoje mjere, odaberite **Osvježi sve** bez odabiranja određene mjere.

> [!div class="mx-imgBorder"]
> ![Radnje za upravljanje jedinstvenim mjerama](media/measure-actions.png "Radnje za upravljanje jedinstvenim mjerama")

Ili odaberite mjeru s popisa i izvršite jednu od sljedećih radnji:

- Odaberite naziv mjere da biste vidjeli njezine pojedinosti.
- Odaberite **Uredi** konfiguraciju mjere.
- Odaberite **Preimenuj** mjeru.
- Odaberite **Izbriši** mjeru.
- Odaberite trotočku (...) i zatim **Osvježi** da biste započeli postupak osvježavanja mjere.
- Odaberite trotočku (...) i zatim **Preuzmi** da biste dobili .CSV datoteku mjere.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies). Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla. Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.

## <a name="next-step"></a>Sljedeći korak

Možete upotrebljavati postojeće mjere za izradu prvog segmenta klijenta na stranici **Segmenti**. Dodatne informacije potražite u dijelu [Segmenti](segments.md).
