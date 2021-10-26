---
title: Stvaranje i upravljanje mjerama
description: Definirajte mjere za analizu i odražavanje uspješnosti svojeg poslovanja.
ms.date: 09/30/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 39acca78c022bc15ebc15dc80f21fe175da04d4d
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622850"
---
# <a name="define-and-manage-measures"></a>Definiranje i upravljanje mjerama

Mjere vam pomažu da bolje razumijete ponašanja klijenata i poslovne performanse. Gledaju na relevantne vrijednosti iz [objedinjenih profila](data-unification.md). Na primjer poduzeće želi vidjeti *ukupnu potrošnju po kupcu* za razumijevanje povijesti kupca pojedinog kupca ili mjerenje *ukupne prodaje društva* kako bi se razumio ukupni prihod u cijelom poslovanju.  

Mjere se stvaraju pomoću alata za izradu mjera, platforme za upite podataka s različitim operatorima i jednostavnim mogućnostima mapiranja. Omogućuje vam filtriranje podataka, grupiranje rezultata, otkrivanje [putanja odnosa entiteta](relationships.md) i pretpregled izlazne vrijednosti.

Koristite alat za izradu mjera za planiranje poslovnih aktivnosti ispitivanjem podataka o klijentima i izvozom uvida. Na primjer, stvaranje mjere *ukupna potrošnja po klijentu* i *ukupan povrat po klijentu* pomaže identificirati grupu klijenata s visokom potrošnjom, ali i visokim povratom. Možete [stvoriti segment](segments.md) za pokretanje sljedećih najboljih radnji. 

## <a name="build-your-own-measure-from-scratch"></a>Izrada vlastitih mjera od nule

Ovaj vas odjeljak vodi kroz stvaranje nove mjere od početka. Mjeru s atributima podataka možete sastaviti iz podatkovnih entiteta koji imaju postavljen odnos za povezivanje s entitetom objedinjenog profila klijenta.

# <a name="individual-customers-b2c"></a>[Pojedinačni klijenti (B2C)](#tab/b2c)

1. U uvidima u ciljnu skupinu idite na **Mjere**.

1. Odaberite **Novo** i odaberite **Izradi vlastiti**.

1. Odaberite **Uredi naziv** i navedite **Naziv** za mjeru. 

1. U konfiguracijskom području odaberite funkciju agregacije iz padajućeg izbornika **Odabir funkcije**. Funkcije skupljanja uključuju: 
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
   1. Možete odabrati i atribut podataka iz postojeće mjere odabirom kartice **Mjere** ili možete tražiti naziv entiteta ili mjere. 
   1. Odaberite **Dodaj** za dodavanje odabranog atributa mjeri.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Odaberite atribut koji ćete koristiti u izračunima.":::

1. Da biste izradili složenije mjere, možete dodati više atributa ili koristiti matematičke operatore u svojoj funkciji mjere.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Stvorite složenu mjeru s matematičkim operatorima.":::

1. Da biste dodali filtre, odaberite **Filtar** u području konfiguracije. 
  
   1. U odjeljku **Dodavanje atributa** okna **Filtri** odaberite atribut koji želite koristiti za stvaranje filtara.
   1. Postavite operatore filtra da definiraju filtar za svaki odabrani atribut.
   1. Odaberite **Primijeni** za dodavanje filtara mjeri.

1. Da biste dodali dimenzije, odaberite **Dimenzija** u području konfiguracije. Dimenzije će se prikazati kao stupci u entitetu izlazne vrijednosti mjere.
 
   1. Odaberite **Uredi dimenzije** za dodavanje atributa podataka po kojima želite grupirati vrijednosti mjere. Na primjer, grad ili spol. Prema zadanim postavkama dimenzija *CustomerID* odabrana je za stvaranje *mjera na razini klijenta*. Možete ukloniti zadanu dimenziju ako želite stvoriti *mjere na poslovnoj razini*.
   1. Odaberite **Gotovo** za dodavanje dimenzija mjeri.

1. Ako u vašim podacima postoje vrijednosti koje morate zamijeniti cijelim brojem, odaberite **Pravila**. Konfigurirajte pravilo i obavezno odaberite samo cijele brojeve kao zamjene. Na primjer, zamijenite *nula* s *0*.

1. Ako postoji više putanja između entiteta podataka koji ste mapirali i entiteta *Klijent*, morate odabrati jednu od identificiranih [putanja odnosa entiteta](relationships.md). Rezultati mjerenja mogu se razlikovati ovisno o odabranoj putanji. 
   
   1. Odaberite **Putanja odnosa** i odaberite putanju entiteta koji bi se trebao koristiti za identifikaciju mjere. Ako postoji samo jedna putanja do entiteta *Klijent*, ova se kontrola neće prikazati.
   1. Odaberite **Gotovo** da biste primijenili svoj odabir. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Odaberite putanju entiteta za mjeru.":::

1. Da biste dodali više izračuna za mjeru, odaberite **Novi izračun**. Za nove izračune možete koristiti samo entitete na istoj putanji entiteta. Više će se izračuna prikazati kao novi stupci u entitetu izlazne vrijednosti mjere.

1. Odaberite **...** na izračunu da biste proveli **Dupliciraj**, **Preimenuj** ili **Ukloni** izračun iz mjere.

1. U području **Pretpregled** vidjet ćete shemu podataka entiteta izlazne vrijednosti mjere, uključujući filtre i dimenzije. Pretpregled dinamički reagira na promjene u konfiguraciji.

1. Odaberite **Pokreni** za izračunavanje rezultata za konfiguriranu mjeru. Odaberite **Spremi i zatvori** ako želite zadržati trenutnu konfiguraciju i kasnije pokrenuti mjeru.

1. Idite na **Mjere** da biste na popisu vidjeli novostvorenu mjeru.

# <a name="business-accounts-b2b"></a>[Poslovni računi (B2B)](#tab/b2b)

1. U uvidima u ciljnu skupinu idite na **Mjere**.

1. Odaberite **Novo** i odaberite **Izradi vlastiti**.

1. Odaberite **Uredi naziv** i navedite **Naziv** za mjeru. 

1. U konfiguracijskom području odaberite funkciju agregacije iz padajućeg izbornika **Odabir funkcije**. Funkcije skupljanja uključuju: 
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
   1. Možete odabrati i atribut podataka iz postojeće mjere odabirom kartice **Mjere** ili možete tražiti naziv entiteta ili mjere. 
   1. Odaberite **Dodaj** za dodavanje odabranog atributa mjeri.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Odaberite atribut koji ćete koristiti u izračunima.":::

1. Da biste izradili složenije mjere, možete dodati više atributa ili koristiti matematičke operatore u svojoj funkciji mjere.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Stvorite složenu mjeru s matematičkim operatorima.":::

1. Da biste dodali filtre, odaberite **Filtar** u području konfiguracije. 
  
   1. U odjeljku **Dodavanje atributa** okna **Filtri** odaberite atribut koji želite koristiti za stvaranje filtara.
   1. Postavite operatore filtra da definiraju filtar za svaki odabrani atribut.
   1. Odaberite **Primijeni** za dodavanje filtara mjeri.

1. Da biste dodali dimenzije, odaberite **Dimenzija** u području konfiguracije. Dimenzije će se prikazati kao stupci u entitetu izlazne vrijednosti mjere.
 
   1. Odaberite **Uredi dimenzije** za dodavanje atributa podataka po kojima želite grupirati vrijednosti mjere. Na primjer, grad ili spol. Prema zadanim postavkama dimenzija *CustomerID* odabrana je za stvaranje *mjera na razini klijenta*. Možete ukloniti zadanu dimenziju ako želite stvoriti *mjere na poslovnoj razini*.
   1. Odaberite **Gotovo** za dodavanje dimenzija mjeri.

1. Ako u vašim podacima postoje vrijednosti koje morate zamijeniti cijelim brojem, odaberite **Pravila**. Konfigurirajte pravilo i obavezno odaberite samo cijele brojeve kao zamjene. Na primjer, zamijenite *nula* s *0*.

1. Možete koristiti preklopni gumb **Prikupljanje podračuna** ako [koristite račune s hijerarhijom](relationships.md#set-up-account-hierarchies).
   - Ako je postavljeno na **Isključeno**, mjera se izračunava za svaki račun. Svaki račun ima svoj rezultat.
   - Ako je postavljeno na **Uključeno**, odaberite **Uredi** za odabir hijerarhije računa prema unesenoj hijerarhiji. Mjera će dati samo jedan rezultat jer je agregirana s podračunima.

1. Ako postoji više putanja između entiteta podataka koji ste mapirali i entiteta *Klijent*, morate odabrati jednu od identificiranih [putanja odnosa entiteta](relationships.md). Rezultati mjerenja mogu se razlikovati ovisno o odabranoj putanji. 
   
   1. Odaberite **Putanja odnosa** i odaberite putanju entiteta koji bi se trebao koristiti za identifikaciju mjere. Ako postoji samo jedna putanja do entiteta *Klijent*, ova se kontrola neće prikazati.
   1. Odaberite **Gotovo** da biste primijenili svoj odabir. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Odaberite putanju entiteta za mjeru.":::

1. Odaberite **...** na izračunu da biste proveli **Dupliciraj**, **Preimenuj** ili **Ukloni** izračun iz mjere.

1. U području **Pretpregled** vidjet ćete shemu podataka entiteta izlazne vrijednosti mjere, uključujući filtre i dimenzije. Pretpregled dinamički reagira na promjene u konfiguraciji.

1. Odaberite **Pokreni** za izračunavanje rezultata za konfiguriranu mjeru. Odaberite **Spremi i zatvori** ako želite zadržati trenutnu konfiguraciju i kasnije pokrenuti mjeru.

1. Idite na **Mjere** da biste na popisu vidjeli novostvorenu mjeru.

---

## <a name="use-a-template-to-build-a-measure"></a>Korištenje predloška za izradu mjera

Za njihovo stvaranje možete koristiti unaprijed definirane predloške najčešće korištenih mjera. Detaljni opisi predložaka i vođeno iskustvo pomažu vam u učinkovitom stvaranju mjera. Predlošci se nadovezuju na mapirane podatke iz entiteta *Objedinjena aktivnost*. Stoga provjerite jeste li konfigurirali [aktivnosti klijenata](activities.md) prije nego što stvorite mjeru iz predloška.

# <a name="individual-customers-b2c"></a>[Pojedinačni klijenti (B2C)](#tab/b2c)

Za njihovo stvaranje možete koristiti unaprijed definirane predloške najčešće korištenih mjera. Detaljni opisi predložaka i vođeno iskustvo pomažu vam u učinkovitom stvaranju mjera. Predlošci se nadovezuju na mapirane podatke iz entiteta *Objedinjena aktivnost*. Stoga provjerite jeste li konfigurirali [aktivnosti klijenata](activities.md) prije nego što stvorite mjeru iz predloška.

Dostupni predlošci mjera: 
- Prosječna vrijednost transakcije (ATV)
- Ukupna vrijednost transakcije
- Prosječni dnevni prihod
- Prosječni godišnji prihod
- Broj transakcija
- Zarađeni bodovi vjernosti
- Iskorišteni bodovi vjernosti
- Bilanca stanja bodova vjernosti
- Životni vijek aktivnog klijenta
- Trajanje članstva u programu vjernosti
- Vrijeme od zadnje kupnje

Sljedeći postupak opisuje korake za izradu nove mjere pomoću predloška.

1. U uvidima u ciljnu skupinu idite na **Mjere**.

1. Odaberite **Novo**, a zatim odaberite **Odaberi predložak**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Snimka zaslona padajućeg izbornika prilikom izrade nove mjere s istaknutim predloškom.":::

1. Pronađite predložak koji odgovara vašim potrebama i odaberite **Odaberi predložak**.

1. Pregledajte potrebne podatke i odaberite **Započni** ako imate sve podatke na mjestu.

1. U oknu **Uredi naziv** postavite naziv mjere i izlazni entitet. 

1. Odaberite **Gotovo**.

1. U odjeljku **Postavi vremensko razdoblje** definirajte vremenski okvir podataka koji će se koristiti. Odaberite želite li da nova mjera pokriva cijeli skup podataka odabirom **Cijelo vrijeme** ili ako želite da se mjera usredotoči na **Određeno vremensko razdoblje**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Snimka zaslona koja prikazuje odjeljak vremenskog razdoblja prilikom konfiguriranja mjere iz predloška.":::

1. U sljedećem odjeljku odaberite **Dodaj podatke** za odabir aktivnosti i mapiranje odgovarajućih podataka iz vašeg entiteta *Objedinjena aktivnost*.

    1. Korak 1 od 2: Pod **Vrsta aktivnosti** odaberite vrstu entiteta koju želite koristiti. Za **Aktivnosti** odaberite entitete koje želite mapirati.
    1. Korak 2 od 2: Odaberite atribut iz entiteta *Objedinjena aktivnost* za komponentu koju zahtijeva formula. Na primjer, za Prosječna vrijednost transakcije to je atribut koji predstavlja vrijednost Transakcije. Za **Vremenska oznaka aktivnosti** odaberite atribut iz entiteta Objedinjena aktivnost koji predstavlja datum i vrijeme aktivnosti.
   
1. Nakon što mapiranje podataka bude uspješno, možete vidjeti status kao **Dovršeno** te naziv mapiranih aktivnosti i atributa.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Snimka zaslona dovršene konfiguracije predloška mjere.":::

1. Sada možete odabrati **Pokreni** za izračunavanje rezultata mjere. Da biste je kasnije pročistili, odaberite **Spremi nacrt**.

# <a name="business-accounts-b2b"></a>[Poslovni računi (B2B)](#tab/b2b)

Ova je značajka dostupna samo za mjere stvorene u okruženjima s pojedinačnim klijentima kao primarnom ciljnom skupinom.

---

## <a name="manage-your-measures"></a>Upravljanje mjerama

Popis mjera možete pronaći na stranici **Mjere**.

Pronaći ćete informacije o vrsti mjere, autoru, datumu stvaranja, statusu i stanju. Kada odaberete mjeru s popisa, možete pretpregledati izlaz i preuzeti CSV datoteku.

Da biste istovremeno osvježili sve svoje mjere, odaberite **Osvježi sve** bez odabiranja određene mjere.

> [!div class="mx-imgBorder"]
> ![Radnje za upravljanje jedinstvenim mjerama.](media/measure-actions.png "Radnje za upravljanje jedinstvenim mjerama.")

Odaberite mjeru s popisa za sljedeće mogućnosti:

- Odaberite naziv mjere da biste vidjeli njezine pojedinosti.
- Odaberite **Uredi** konfiguraciju mjere.
- **Osvježi** mjeru na temelju najnovijih podataka.
- Odaberite **Preimenuj** mjeru.
- Odaberite **Izbriši** mjeru.
- **Aktiviraj** ili **Deaktiviraj**. Neaktivne mjere neće se osvježavati tijekom [zakazanog osvježavanja](system.md#schedule-tab).

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies). Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla. Nakon odabira **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, datum posljednje obrade i sve pogreške i upozorenja povezana sa zadatkom.

## <a name="next-step"></a>Sljedeći korak

Možete koristiti postojeće mjere za stvaranje [segmenta klijenta](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
