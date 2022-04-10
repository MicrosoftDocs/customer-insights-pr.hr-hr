---
title: Stvaranje novih mjera pomoću sastavljača mjera
description: Izradite mjere od nule da biste analizirali ključne mjerne podatke o svojoj tvrtki.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: 5329aea240ba40ec8698b3ddeb67fb5f21c62bbd
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359945"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Stvaranje mjera od nule pomoću sastavljača mjera

U ovom se članku objašnjava kako stvoriti novu [mjeru](measures.md) od nule. Sastavljač mjera omogućuje vam definiranje izračuna pomoću matematičkih operatora, funkcija zbrajanja i filtara. Mjeru možete izraditi s atributima entiteta koji su povezani s objedinjenim *entitetom Kupac*. 

Stvaranje mjera u okruženjima B-to-C i B-to-B funkcionira na isti način. Međutim, ako okruženje [B-to-B koristi račune s hijerarhijama](relationships.md#set-up-account-hierarchies), mjeru možete agregirati na sve povezane podračune.

Mjeru možete brzo kreirati i odabirom skupa najčešće korištenih i unaprijed definiranih mjera. Dodatne informacije potražite u članku [Stvaranje mjere pomoću predloška](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

Mjere možete kreirati na razini pojedinačnih kupaca (atribut kupca, mjera kupca) ili na razini tvrtke/organizacije (poslovna mjera). Atribut kupca i mjera kupca dvije su vrste koje vam omogućuju praćenje performansi po kupcu. Na primjer, ukupna potrošnja svakog kupca. Poslovne mjere omogućuju praćenje uspješnosti po tvrtki. Na primjer, ukupni prihod tvrtke.

- Atribut klijenta: Generira izlaz kao novi atribut koji se sprema kao novi stupac u sistemski generiranom entitetu pod nazivom *Customer_Measure*. Prilikom osvježavanja atributa klijenta svi ostali atributi klijenta u entitetu *Customer_Measure* istovremeno se osvježavaju. Osim toga, atributi kupca prikazani su na kartici profila kupca. Nakon pokretanja ili spremanja, atribut kupca ne možete ga promijeniti u mjeru kupca.

- Mjera kupca: Generira izlaz kao vlastiti entitet i ne možete ga promijeniti u atribut klijenta nakon pokretanja ili spremanja. Mjere kupca ne prikazuju se na kartici profila kupca.

- Poslovna mjera: generira izlaz kao vlastiti entitet i prikazuje se na početnoj stranici okruženja Customer Insights.

1. Idite na **Mjere**.

1. Odaberite **Novo** i odaberite **Izradi vlastiti**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Prazan konfiguracijski zaslon za mjeru B-na-C.":::

1. Odaberite **Uredi naziv** i navedite **Naziv** za mjeru. 

1. U području konfiguracije odaberite funkciju zbrajanja s padajućeg izbornika **Odabir funkcije**. Funkcije skupljanja uključuju: 
   - **Zbroj**
   - **Prosječno**
   - **Brojanje**
   - **Jedinstveni broj**
   - **Max**
   - **Min**
   - **Prvi**: uzima prvu vrijednost zapisa podataka
   - **Posljednji**: uzima posljednju vrijednost koja je dodana u zapis podataka
   - **ArgMax**: pronalazi zapis podataka koji daje maksimalnu vrijednost iz ciljne funkcije
   - **ArgMin**: pronalazi zapis podataka koji daje minimalnu vrijednost iz ciljne funkcije

1. Odaberite **Dodaj atribut** za odabir podataka koji su vam potrebni za stvaranje ove mjere.
   
   1. Odaberite karticu **Atributi**. 
   1. Entitet podataka: odaberite entitet koji uključuje atribut koji želite mjeriti. 
   1. Atribut podataka: Odaberite atribut koji želite koristiti u funkciji skupljanja za izračunavanje mjere. Odjednom možete odabrati samo jedan atribut.
   1. Možete odabrati i atribut podataka iz postojeće mjere odabirom kartice **Mjere** ili možete tražiti naziv entiteta ili mjere. 
   1. Odaberite **Dodaj** za dodavanje odabranog atributa mjeri.

1. Da biste izradili složenije mjere, možete dodati više atributa ili koristiti matematičke operatore u svojoj funkciji mjere.

1. Da biste dodali filtre, odaberite **Filtar** u području konfiguracije. Primjena filtara koristit će samo zapise koji odgovaraju filtrima za izračun mjere.
  
   1. U odjeljku **Dodavanje atributa** okna **Filtri** odaberite atribut koji želite koristiti za stvaranje filtara.
   1. Postavite operatore filtra da definiraju filtar za svaki odabrani atribut.
   1. Odaberite **Primijeni** za dodavanje filtara mjeri.

1. Odaberite **Dimenzija** da biste odabrali više polja koja se dodaju kao stupci izlaznom entitetu mjere.
 
   1. Odaberite **Uredi dimenzije** za dodavanje atributa podataka po kojima želite grupirati vrijednosti mjere. Na primjer, grad ili spol. Prema zadanim postavkama dimenzija *CustomerID* odabrana je za stvaranje *mjera na razini klijenta*. Možete ukloniti zadanu dimenziju ako želite stvoriti *mjere na poslovnoj razini*.
   1. Odaberite **Gotovo** za dodavanje dimenzija mjeri.

1. Ako u vašim podacima postoje vrijednosti koje morate zamijeniti cijelim brojem, odaberite **Pravila**. Konfigurirajte pravilo i obavezno odaberite samo cijele brojeve kao zamjene. Na primjer, zamijenite *nula* s *0*.

1. Ako postoji više putanja između entiteta podataka koji ste mapirali i entiteta *Klijent*, morate odabrati jednu od identificiranih [putanja odnosa entiteta](relationships.md). Rezultati mjerenja mogu se razlikovati ovisno o odabranoj putanji. 
   
   1. Odaberite **Putanja odnosa** i odaberite putanju entiteta koji bi se trebao koristiti za identifikaciju mjere. Ako postoji samo jedna putanja do entiteta *Klijent*, ova se kontrola neće prikazati.
   1. Odaberite **Gotovo** da biste primijenili svoj odabir. 

1. Da biste dodali više izračuna za mjeru, odaberite **Novi izračun**. Za nove izračune možete koristiti samo entitete na istoj putanji entiteta. Više će se izračuna prikazati kao novi stupci u entitetu izlazne vrijednosti mjere.

1. Odaberite **...** na izračunu da biste proveli **Dupliciraj**, **Preimenuj** ili **Ukloni** izračun iz mjere.

1. U području **Pretpregled** vidjet ćete shemu podataka entiteta izlazne vrijednosti mjere, uključujući filtre i dimenzije. Pretpregled dinamički reagira na promjene u konfiguraciji.

1. Odaberite **Pokreni** za izračunavanje rezultata za konfiguriranu mjeru. Odaberite **Spremi i zatvori** ako želite zadržati trenutnu konfiguraciju i kasnije pokrenuti mjeru.

1. Idite na **Mjere** da biste na popisu vidjeli novostvorenu mjeru.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)


Mjere možete kreirati na razini pojedinačnih računa (mjera kupca) ili na razini svih računa (poslovna mjera). 

- Mjera kupca: Generira izlaz kao vlastiti entitet. Mjere kupca ne prikazuju se na kartici profila kupca.

- Poslovna mjera: generira izlaz kao vlastiti entitet i prikazuje se na početnoj stranici okruženja Customer Insights.

1. Idite na **Mjere**.

1. Odaberite **Novo**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Prazan konfiguracijski zaslon za mjeru B-to-B.":::

1. Odaberite **Uredi naziv** i navedite **Naziv** za mjeru. 

1. U području konfiguracije odaberite funkciju zbrajanja s padajućeg izbornika **Odabir funkcije**. Funkcije skupljanja uključuju: 
   - **Zbroj**
   - **Prosječno**
   - **Brojanje**
   - **Jedinstveni broj**
   - **Max**
   - **Min**
   - **Prvi**: uzima prvu vrijednost zapisa podataka
   - **Posljednji**: uzima posljednju vrijednost koja je dodana u zapis podataka

1. Odaberite **Dodaj atribut** za odabir podataka koji su vam potrebni za stvaranje ove mjere.
   
   1. Odaberite karticu **Atributi**. 
   1. Entitet podataka: odaberite entitet koji uključuje atribut koji želite mjeriti. 
   1. Atribut podataka: Odaberite atribut koji želite koristiti u funkciji skupljanja za izračunavanje mjere. Odjednom možete odabrati samo jedan atribut.
   1. Možete odabrati i atribut podataka iz postojeće mjere odabirom kartice **Mjere** ili možete tražiti naziv entiteta ili mjere. 
   1. Odaberite **Dodaj** za dodavanje odabranog atributa mjeri.

1. Da biste izradili složenije mjere, možete dodati više atributa ili koristiti matematičke operatore u svojoj funkciji mjere.

1. Da biste dodali filtre, odaberite **Filtar** u području konfiguracije. Primjena filtara koristit će samo zapise koji odgovaraju filtrima za izračun mjere.
  
   1. U odjeljku **Dodavanje atributa** okna **Filtri** odaberite atribut koji želite koristiti za stvaranje filtara.
   1. Postavite operatore filtra da definiraju filtar za svaki odabrani atribut.
   1. Odaberite **Primijeni** za dodavanje filtara mjeri.

1. Odaberite **Dimenzija** da biste odabrali više polja koja se dodaju kao stupci izlaznom entitetu mjere.
 
   1. Odaberite **Uredi dimenzije** za dodavanje atributa podataka po kojima želite grupirati vrijednosti mjere. Na primjer, grad ili spol. Prema zadanim postavkama dimenzija *CustomerID* odabrana je za stvaranje *mjera na razini klijenta*. Možete ukloniti zadanu dimenziju ako želite stvoriti *mjere na poslovnoj razini*.
   1. Odaberite **Gotovo** za dodavanje dimenzija mjeri.

1. Ako u vašim podacima postoje vrijednosti koje morate zamijeniti cijelim brojem, odaberite **Pravila**. Konfigurirajte pravilo i obavezno odaberite samo cijele brojeve kao zamjene. Na primjer, zamijenite *nula* s *0*.

1. Možete koristiti preklopni gumb **Prikupljanje podračuna** ako [koristite račune s hijerarhijom](relationships.md#set-up-account-hierarchies).
   - Ako je postavljeno na **Isključeno**, mjera se izračunava za svaki račun. Svaki račun ima svoj rezultat.
   - Ako je postavljeno na **Uključeno**, odaberite **Uredi** za odabir hijerarhije računa prema unesenoj hijerarhiji. Mjera će dati samo jedan rezultat jer je agregirana s podračunima.

1. Ako postoji više putanja između entiteta podataka koji ste mapirali i entiteta *Klijent*, morate odabrati jednu od identificiranih [putanja odnosa entiteta](relationships.md). Rezultati mjerenja mogu se razlikovati ovisno o odabranoj putanji. 
   
   1. Odaberite **Putanja odnosa** i odaberite putanju entiteta koji bi se trebao koristiti za identifikaciju mjere. Ako postoji samo jedna putanja do entiteta *Klijent*, ova se kontrola neće prikazati.
   1. Odaberite **Gotovo** da biste primijenili svoj odabir. 

1. Odaberite **...** na izračunu da biste proveli **Dupliciraj**, **Preimenuj** ili **Ukloni** izračun iz mjere.

1. U području **Pretpregled** vidjet ćete shemu podataka entiteta izlazne vrijednosti mjere, uključujući filtre i dimenzije. Pretpregled dinamički reagira na promjene u konfiguraciji.

1. Odaberite **Pokreni** za izračunavanje rezultata za konfiguriranu mjeru. Odaberite **Spremi i zatvori** ako želite zadržati trenutnu konfiguraciju i kasnije pokrenuti mjeru.

1. Idite na **Mjere** da biste na popisu vidjeli novostvorenu mjeru.

---