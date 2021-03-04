---
title: Stvaranje i upravljanje mjerama
description: Definirajte mjere za analizu i odražavanje uspješnosti svojeg poslovanja.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269919"
---
# <a name="define-and-manage-measures"></a>Definiranje i upravljanje mjerama

Mjere vam pomažu da bolje razumijete ponašanje klijenata i poslovne performanse dohvaćanjem relevantnih vrijednosti iz [objedinjenih profila](data-unification.md). Na primjer, tvrtka želi vidjeti *ukupnu potrošnju po klijentu* da bi razumjela povijest kupnje pojedinog klijenta. Ili izmjeriti *ukupnu prodaju tvrtke* da bi razumjela ukupnu razinu prihoda u cijelom poslovanju.  

Mjere se stvaraju pomoću alata za izradu mjera, platforme za upite podataka s različitim operatorima i jednostavnim mogućnostima mapiranja. Omogućuje vam filtriranje podataka, grupiranje rezultata, otkrivanje [putanja odnosa entiteta](relationships.md) i pretpregled izlazne vrijednosti.

Koristite alat za izradu mjera za planiranje poslovnih aktivnosti ispitivanjem podataka o klijentima i izvozom uvida. Na primjer, stvaranje mjere *ukupna potrošnja po klijentu* i *ukupan povrat po klijentu* pomaže identificirati grupu klijenata s visokom potrošnjom, ali i visokim povratom. Možete [stvoriti segment](segments.md) za pokretanje sljedećih najboljih radnji. 

## <a name="create-a-measure"></a>Izrada mjere

Ovaj vas odjeljak vodi kroz stvaranje nove mjere od početka. Možete izraditi mjeru s atributima podataka iz podatkovnih entiteta koji imaju uspostavljen odnos za povezivanje s entitetom Klijent. 

1. U uvidima u ciljnu skupinu idite na **Mjere**.

1. Odaberite **Novo**.

1. Odaberite **Uredi naziv** i navedite **Naziv** za mjeru. 
   > [!NOTE]
   > Ako vaša nova konfiguracija mjere ima samo dva polja, za primjer, CustomerID i jedan izračun, izlazna će se vrijednost dodati kao novi stupac entitetu koji je generirao sustav pod nazivom Customer_Measure. Vrijednost mjere moći ćete vidjeti u objedinjenom profilu klijenta. Ostale će mjere generirati vlastite entitete.

1. U području konfiguracije odaberite funkciju skupljanja u padajućem izborniku **Odabir funkcije**. Funkcije skupljanja uključuju: 
   - **Zbroj**
   - **Prosječno**
   - **Brojanje**
   - **Jedinstveni broj**
   - **Max**
   - **Min**
   - **Prvi**: uzima prvu vrijednost zapisa podataka
   - **Posljednji**: uzima posljednju vrijednost koja je dodana u zapis podataka

   :::image type="content" source="media/measure-operators.png" alt-text="Operatori za izračun mjera.":::

1. Odaberite **Dodaj atribut** za odabir podataka koji su vam potrebni za stvaranje ove mjere.
   
   1. Odaberite karticu **Atributi**. 
   1. Entitet podataka: odaberite entitet koji uključuje atribut koji želite mjeriti. 
   1. Atribut podataka: Odaberite atribut koji želite koristiti u funkciji skupljanja za izračunavanje mjere. Odjednom možete odabrati samo jedan atribut.
   1. Možete odabrati i atribut podataka iz postojeće mjere odabirom kartice **Mjere**. Ili možete tražiti naziv entiteta ili mjere. 
   1. Odaberite **Dodaj** za dodavanje odabranog atributa mjeri.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Odaberite atribut koji ćete koristiti u izračunima.":::

1. Da biste izradili složenije mjere, možete dodati više atributa ili koristiti matematičke operatore u svojoj funkciji mjere.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Stvorite složenu mjeru s matematičkim operatorima.":::

1. Da biste dodali filtre, odaberite **Filtar** u području konfiguracije. 
  
   1. U odjeljku **Dodaj atribut** okna **Filtri** odaberite atribut koji želite koristiti za stvaranje filtara.
   1. Postavite operatore filtra da definiraju filtar za svaki odabrani atribut.
   1. Odaberite **Primijeni** za dodavanje filtara mjeri.

1. Da biste dodali dimenzije, odaberite **Dimenzija** u području konfiguracije. Dimenzije će se prikazati kao stupci u entitetu izlazne vrijednosti mjere.
   1. Odaberite **Uredi dimenzije** za dodavanje atributa podataka po kojima želite grupirati vrijednosti mjere. Na primjer, grad ili spol. Prema zadanim postavkama dimenzija *CustomerID* odabrana je za stvaranje *mjera na razini klijenta*. Možete ukloniti zadanu dimenziju ako želite stvoriti *mjere na poslovnoj razini*.
   1. Odaberite **Gotovo** za dodavanje dimenzija mjeri.

1. Ako postoji više putanja između entiteta podataka koji ste mapirali i entiteta Klijent, morate odabrati jednu od identificiranih [putanja odnosa entiteta](relationships.md). Rezultati mjerenja mogu se razlikovati ovisno o odabranoj putanji.
   1. Odaberite **Preference podataka** i odaberite putanju entiteta koju treba koristiti za identificiranje vaše mjere.
   1. Odaberite **Gotovo** da biste primijenili svoj odabir. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Odaberite putanju entiteta za mjeru.":::

1. Da biste dodali više izračuna za mjeru, odaberite **Novi izračun**. Za nove izračune možete koristiti samo entitete na istoj putanji entiteta. Više će se izračuna prikazati kao novi stupci u entitetu izlazne vrijednosti mjere.

1. Odaberite **...** na izračunu da biste proveli **Dupliciraj**, **Preimenuj** ili **Ukloni** izračun iz mjere.

1. U području **Pretpregled** vidjet ćete shemu podataka entiteta izlazne vrijednosti mjere, uključujući filtre i dimenzije. Pretpregled dinamički reagira na promjene u konfiguraciji.

1. Odaberite **Pokreni** za izračunavanje rezultata za konfiguriranu mjeru. Odaberite **Spremi i zatvori** ako želite zadržati trenutnu konfiguraciju i kasnije pokrenuti mjeru.

1. Idite na **Mjere** da biste na popisu vidjeli novostvorenu mjeru.

## <a name="manage-your-measures"></a>Upravljanje mjerama

Nakon [stvaranja mjere](#create-a-measure) vidjet ćete popis mjera na stranici **Mjere**.

Pronaći ćete informacije o vrsti mjere, autoru, datumu stvaranja, statusu i stanju. Kada odaberete mjeru s popisa, možete pretpregledati izlaznu vrijednost i preuzeti .CSV datoteku.

Da biste istovremeno osvježili sve svoje mjere, odaberite **Osvježi sve** bez odabiranja određene mjere.

> [!div class="mx-imgBorder"]
> ![Radnje za upravljanje jedinstvenim mjerama](media/measure-actions.png "Radnje za upravljanje jedinstvenim mjerama")

Odaberite mjeru s popisa za sljedeće mogućnosti:

- Odaberite naziv mjere da biste vidjeli njezine pojedinosti.
- Odaberite **Uredi** konfiguraciju mjere.
- **Osvježi** mjeru na temelju najnovijih podataka.
- Odaberite **Preimenuj** mjeru.
- Odaberite **Izbriši** mjeru.
- **Aktiviraj** ili **Deaktiviraj**. Neaktivne mjere neće se osvježavati tijekom [zakazanog osvježavanja](system.md#schedule-tab).

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies). Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla. Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.

## <a name="next-step"></a>Sljedeći korak

Možete koristit postojeće mjere da biste stvorili [segment klijenta](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]