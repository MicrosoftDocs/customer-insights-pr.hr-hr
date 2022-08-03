---
title: Stvaranje mjera pomoću sastavljača mjera
description: Izradite mjere od nule kako biste analizirali ključne mjerne podatke o svom poslovanju.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170840"
---
# <a name="create-measures-with-measure-builder"></a>Stvaranje mjera pomoću sastavljača mjera

Sastavljač mjera omogućuje definiranje izračuna pomoću matematičkih operatora, funkcija zbrajanja i filtara. Definišite mjere pomoću atributa entiteta koji su povezani s jedinstvenim *entitetom Klijent*.

Stvaranje mjera u okruženjima od B do C i B-do-B funkcionira na isti način. Međutim, ako vaše okruženje [od B do B koristi račune s hijerarhijama](relationships.md#set-up-account-hierarchies), odaberite želite li grupirati mjeru na povezane podračune.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

Kreirajte mjere na razini pojedinačnih kupaca (atribut kupca, mjera kupca) ili na razini poslovanja/organizacije (poslovna mjera). Atribut kupca i mjera kupca omogućuju vam praćenje performansi po kupcu. Na primjer, ukupna potrošnja svakog kupca. Poslovne mjere prate uspješnost po poduzeću. Na primjer, ukupni prihod tvrtke.

- Atribut klijenta: generira izlaz kao novi atribut koji se sprema kao novi stupac u sistemski generiranom entitetu pod nazivom *Customer_Measure*. Prilikom osvježavanja atributa kupca, svi ostali atributi klijenta u entitetu *Customer_Measure* istovremeno osvježavaju. Osim toga, atributi kupaca prikazani su na kartici profila kupca. Nakon pokretanja ili spremanja atribut klijenta ne možete promijeniti u mjeru klijenta.

- Mjera za kupca: generira izlaz kao vlastiti entitet i ne možete ga promijeniti u atribut kupca nakon pokretanja ili spremanja. Mjere za korisnike ne prikazuju se na kartici korisničkog profila.

- Poslovna mjera: generira izlaz kao vlastiti entitet i prikazuje se na početnoj stranici okruženja Customer Insights.

1. Idite na **Mjere**.

1. Odaberite **Novo** > **Izgradi vlastiti**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Prazan konfiguracijski zaslon za mjeru B-do C." lightbox="media/measure-b2c.png":::

1. Uz stavku Mjera bez naslova odaberite **Uredi detalje**. Navedite naziv mjere. Po želji dodajte [oznake](work-with-tags-columns.md#manage-tags) mjeri.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dijaloški okvir Uređivanje detalja.":::

1. Odaberite **Gotovo**.

1. Da biste pratili performanse na razini poslovanja, preklopite **vrstu** mjere na **poslovnu razinu**. **Razina** klijenta odabrana je prema zadanim postavkama. **Razina** kupca automatski dodaje *atribut CustomerId* Dimenzijama dok **ga razina** tvrtke automatski uklanja.

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

1. Odaberite **Dodaj atribut** da biste odabrali podatke za stvaranje ove mjere.

   1. Odaberite karticu **Atributi**.
   1. Entitet podataka: odaberite entitet koji uključuje atribut koji želite mjeriti.
   1. Atribut podataka: Odaberite atribut koji želite koristiti u funkciji skupljanja za izračunavanje mjere. Odjednom možete odabrati samo jedan atribut.
   1. Po želji odaberite atribut podataka iz postojeće mjere odabirom kartice **Mjere** ili traženjem naziva entiteta ili mjere.
   1. Odaberite **Dodaj**.

1. Da biste izradili složenije mjere, dodajte više atributa ili koristite matematičke operatore na funkciji mjere.

1. Da biste dodali filtre, odaberite **Filtar** u području konfiguracije. Primjena filtara koristit će samo zapise koji odgovaraju filtrima za izračun mjere.
  
   1. U odjeljku **Dodavanje atributa** okna **Filtri** odaberite atribut koji želite koristiti za stvaranje filtara.
   1. Postavite operatore filtra da definiraju filtar za svaki odabrani atribut.
   1. Odaberite **Primijeni**.

1. Odaberite **Dimenzija** da biste odabrali više polja koja želite dodati kao stupce u izlazni entitet mjere.

   1. Odaberite **Uredi dimenzije** za dodavanje atributa podataka po kojima želite grupirati vrijednosti mjere. Na primjer, grad ili spol.
      > [!TIP]
      > Ako ste kao vrstu Mjera odabrali **razinu** kupca **·**, atribut CustomerId *već je dodan.* Ako uklonite atribut, **vrsta** mjere prebacuje se na poslovnu **razinu**.
   1. Odaberite **Gotovo**.

1. Ako u vašim podacima postoje vrijednosti koje se moraju zamijeniti cijelim brojem, odaberite **Pravila**. Konfigurirajte pravilo i obavezno odaberite samo cijele brojeve kao zamjene. Na primjer, zamijenite *nula* s *0*.

1. Ako postoji više putova između podatkovnog entiteta koji ste mapirali i entiteta *Klijent, odaberite jedan od identificiranih* putova odnosa [entiteta](relationships.md). Rezultati mjerenja mogu se razlikovati ovisno o odabranoj putanji.

   1. Odaberite **Putanja odnosa** i odaberite putanju entiteta koji bi se trebao koristiti za identifikaciju mjere. Ako postoji samo jedna putanja do entiteta *Klijent*, ova se kontrola neće prikazati.
   1. Odaberite **Gotovo**.

1. Da biste dodali više izračuna za mjeru, odaberite **Novi izračun**. Za nove izračune koristite entitete na istom putu entiteta. Više će se izračuna prikazati kao novi stupci u entitetu izlazne vrijednosti mjere. Po želji odaberite **Uredi naziv** da biste stvorili naziv izračuna.

1. Odaberite okomitu trotočje (&vellip;) na izračunu da biste **duplicirali** ili **uklonili** izračun iz mjere.

1. U području **Pretpregled** vidjet ćete shemu podataka entiteta izlazne vrijednosti mjere, uključujući filtre i dimenzije. Pretpregled dinamički reagira na promjene u konfiguraciji.

1. Odaberite **Pokreni** za izračunavanje rezultata za konfiguriranu mjeru. Odaberite **Spremi i zatvori** ako želite zadržati trenutnu konfiguraciju i kasnije pokrenuti mjeru. Prikazuje se **stranica Mjere**.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

Kreirajte mjere na razini pojedinačnih računa (mjera za kupca) ili na razini svih računa (poslovna mjera).

- Mjera kupca: Generira izlaz kao vlastiti entitet. Mjere za korisnike ne prikazuju se na kartici korisničkog profila.

- Poslovna mjera: generira izlaz kao vlastiti entitet i prikazuje se na početnoj stranici okruženja Customer Insights.

1. Idite na **Mjere**.

1. Odaberite **Novo**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Prazan konfiguracijski zaslon za mjeru B-do B.":::

1. Uz stavku Mjera bez naslova odaberite **Uredi detalje**. Navedite naziv mjere. Po želji dodajte [oznake](work-with-tags-columns.md#manage-tags) mjeri. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Dijaloški okvir Uređivanje detalja.":::

1. Odaberite **Gotovo**.

1. U području konfiguracije odaberite funkciju zbrajanja s padajućeg izbornika **Odabir funkcije**. Funkcije skupljanja uključuju:
   - **Zbroj**
   - **Prosječno**
   - **Brojanje**
   - **Jedinstveni broj**
   - **Max**
   - **Min**
   - **Prvi**: uzima prvu vrijednost zapisa podataka
   - **Posljednji**: uzima posljednju vrijednost koja je dodana u zapis podataka

1. Odaberite **Dodaj atribut** da biste odabrali podatke za stvaranje ove mjere.

   1. Odaberite karticu **Atributi**.
   1. Entitet podataka: odaberite entitet koji uključuje atribut koji želite mjeriti.
   1. Atribut podataka: Odaberite atribut koji želite koristiti u funkciji skupljanja za izračunavanje mjere. Odjednom možete odabrati samo jedan atribut.
   1. Po želji odaberite atribut podataka iz postojeće mjere odabirom kartice **Mjere** ili traženjem naziva entiteta ili mjere.
   1. Odaberite **Dodaj** za dodavanje odabranog atributa mjeri.

1. Da biste izradili složenije mjere, dodajte više atributa ili koristite matematičke operatore na funkciji mjere.

1. Da biste dodali filtre, odaberite **Filtar** u području konfiguracije. Primjena filtara koristit će samo zapise koji odgovaraju filtrima za izračun mjere.
  
   1. U odjeljku **Dodavanje atributa** okna **Filtri** odaberite atribut koji želite koristiti za stvaranje filtara.
   1. Postavite operatore filtra da definiraju filtar za svaki odabrani atribut.
   1. Odaberite **Primijeni** za dodavanje filtara mjeri.

1. Odaberite **Dimenzija** da biste odabrali više polja koja želite dodati kao stupce u izlazni entitet mjere.

   1. Odaberite **Uredi dimenzije** za dodavanje atributa podataka po kojima želite grupirati vrijednosti mjere. Na primjer, grad ili spol.
      > [!TIP]
      > Atribut *CustomerId* već je dodan što znači da je riječ o vrsti mjere na razini kupca. Ako uklonite atribut, vrsta mjere promijenit će se u poslovnu razinu.
   1. Odaberite **Gotovo** za dodavanje dimenzija mjeri.

1. Ako u vašim podacima postoje vrijednosti koje se moraju zamijeniti cijelim brojem, odaberite **Pravila**. Konfigurirajte pravilo i obavezno odaberite samo cijele brojeve kao zamjene. Na primjer, zamijenite *nula* s *0*.

1. Ako koristite [račune s hijerarhijama](relationships.md#set-up-account-hierarchies), pregledajte **kumulativne podračune**.
   - Ako je postavljeno na **Isključeno**, mjera se izračunava za svaki račun. Svaki račun dobiva svoj rezultat.
   - Ako je postavljeno na **Uključeno**, odaberite **Uredi** za odabir hijerarhije računa prema unesenoj hijerarhiji. Mjera će dati samo jedan rezultat jer je agregirana s podračunima.

1. Ako postoji više putova između podatkovnog entiteta koji ste mapirali i entiteta *Klijent, odaberite jedan od identificiranih* putova odnosa [entiteta](relationships.md). Rezultati mjerenja mogu se razlikovati ovisno o odabranoj putanji.

   1. Odaberite **Putanja odnosa** i odaberite putanju entiteta koji bi se trebao koristiti za identifikaciju mjere. Ako postoji samo jedna putanja do entiteta *Klijent*, ova se kontrola neće prikazati.
   1. Odaberite **Gotovo** da biste primijenili svoj odabir.

1. Odaberite okomitu trotočje (&vellip;) na izračunu da biste **duplicirali** ili **uklonili** izračun iz mjere.

1. U području **Pretpregled** vidjet ćete shemu podataka entiteta izlazne vrijednosti mjere, uključujući filtre i dimenzije. Pretpregled dinamički reagira na promjene u konfiguraciji.

1. Odaberite **Pokreni** za izračunavanje rezultata za konfiguriranu mjeru. Odaberite **Spremi i zatvori** ako želite zadržati trenutnu konfiguraciju i kasnije pokrenuti mjeru. Prikazuje se **stranica Mjere**.

---

## <a name="next-step"></a>Sljedeći korak

Koristite postojeće mjere da biste kreirali [segment kupca](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
