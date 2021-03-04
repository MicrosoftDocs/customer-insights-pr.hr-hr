---
title: Mapiranje entiteta za objedinjavanje podataka
description: Mapirajte podatke da biste stvorili objedinjene profile klijenata.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267026"
---
# <a name="map-entities-and-attributes"></a>Entiteti i atributi karte

**Mapiranje** je prva faza u procesu objedinjavanja podataka uvida u ciljnu skupinu. Mapiranje se sastoji od tri faze:

- *Odabir entiteta*: identificirajte entitete koji se mogu kombinirati koji vode do skupa podataka s više potpunih informacija o vašim klijentima.
- *Odabir atributa*: za svaki entitet identificirajte stupce koje želite kombinirati i uskladiti u fazama *uspoređivanja* i *spajanja*. Ti se stupci nazivaju *Atributi*.
- *Odabir primarnog ključa i semantičkog tipa*: Za svaki entitet identificirajte atribut koji želite definirati kao primarni ključ za taj entitet, a za svaki atribut identificirajte semantički tip koji najbolje opisuje taj atribut.

Za više informacija o općenitom tijeku objedinjavanja podataka pogledajte dio [Objedinjavanje](data-unification.md).

## <a name="select-the-first-entities"></a>Odabir prvog entiteta

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Objedini** > **Mapiraj**.

2. Pokrenite fazu mapiranja odabirom stavke **Odaberi entitete**.

3. Odaberite entitete i atribute koje želite koristiti u fazama *uskladi* i *spoji*. Možete pojedinačno odabrati potrebne atribute iz entiteta ili uključiti sve atribute iz entiteta odabirom potvrdnog okvira **Uključi sva polja** na razini entiteta. Preporučujemo vam da odaberete barem dva entiteta kako biste imali koristi od postupka objedinjavanja podataka.

   > [!div class="mx-imgBorder"]
   > ![Dodavanje primjera entiteta](media/data-manager-configure-map-add-entities-example.png "Dodavanje primjera entiteta")

   U ovom primjeru dodajemo entitete **eCommerceContacts** i **loyCustomers**. Odabirom ovih entiteta možete steći uvid u to koji su od internetskih poslovnih klijenata članovi programa vjernosti.
   
   Ključne riječi možete pretraživati po svim atributima i entitetima kako biste odabrali potrebne atribute koje želite mapirati.
   
     > [!div class="mx-imgBorder"]
   > ![Primjer polja za pretraživanje](media/data-manager-configure-map-search-fields-example.png "Primjer polja za pretraživanje")

4. Odaberite **Primijeni** za potvrdu odabira.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Odaberite primarni ključ i semantičku vrstu za atribute

Nakon odabira entiteta, stranica **Mapiraj** navodi odabrane entitete za pregled. Definirajte primarni ključ za entitet i identificirajte semantički tip za atribut u entitetu.

- **Primarni ključ**: odaberite jedan atribut kao primarni ključ za svaki vaš entitet. Da bi atribut bio važeći primarni ključ, on ne bi trebao uključivati dvostruke vrijednosti, vrijednosti koje nedostaju ili vrijednosti nula. Atributi vrste podataka niza, cijelog broja i GUID-a podržani su kao primarni ključevi i bit će prikazani u polju za odabir.

- **Semantički tip atributa**: kategorije vaših atributa, kao što su adresa e-pošte ili ime. Kako biste upotrebljavali modele umjetne inteligencije za pametno predviđanje semantike, uštedjeli vrijeme i poboljšali točnost, postavite mogućnost **Inteligentno mapiranje** na **UKLJUČENO**. Inteligentno mapiranje ističe preporuke o semantici koje se temelje na umjetnoj iteligenciji u polju **Vrsta**. Ako ga postavite na **ISKLJUČENO**, vidjet ćete naše redovne preporuke za mapiranje. Možete odabrati bilo koju vrstu semantike s dostupnog popisa mogućnnosti i prebrisati predloženi odabir.

> [!div class="mx-imgBorder"]
> ![Vrsta atributa i predviđanje semantike](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Vrsta atributa i predviđanje semantike")

Također je moguće dodati i prilagođeni semantički tip. Odaberite polje tipa za atribut i unesite naziv prilagođenog semantičkog tipa. Tim putem također možete promijeniti vrste atributa koje je automatski identificirao sustav.

Svi atributi za koje se semantički tip automatski identificira grupirani su u odjeljku **Pregledaj mapirana polja**. Pregledajte ove atribute i njihove semantičke tipove jer će se koristiti za kombiniranje vaših entiteta u koraku spajanja kod objedinjavanja podataka.

Atributi koji nisu automatski mapirani u semantički tip grupirani su u odjeljku **Definiraj podatke u nemapiranim poljima**. Odaberite polje semantičkog tipa za nemapirane atribute ili unesite naziv prilagođenog tipa atributa.

> [!div class="mx-imgBorder"]
> ![Primarni ključ i vrsta atributa](media/data-manager-configure-map-add-attributes.png "Primarni ključ i vrsta atributa")

> [!NOTE]
> Jedno polje treba se mapirati na semantički tip Person.FullName da bi se ime klijenta popunilo u kartici klijenta. U suprotnom će se kartice klijenta prikazati bez naziva. 

## <a name="add-and-remove-attributes-and-entities"></a>Dodavanje i uklanjanje atributa i entiteta

1. Na **Ujedini** > **Mapiraj**, odaberite **Uredi polja**.

2. U oknu **Uredi polja**, dodajte ili uklonite atribute i entitete. S pomoću pretraživanja ili pomicanja pronađite i odaberite svoje atribute i entitete od interesa. Ne možete ukloniti atribut ili entitet ako su već usklađeni.

   > [!div class="mx-imgBorder"]
   > ![Dodavanje ili uklanjanje atributa](media/configure-data-map-edit.png "Dodavanje ili uklanjanje atributa")

3. Odaberite **Primijeni**.

## <a name="add-images-to-profiles"></a>Dodavanje slika profilima

Ako entitet sadrži URL-ove javno dostupnih slika ili logotipa profila, možete ih dodati u objedinjeni profil klijenta.

Odaberite entitet i pronađite polje koje sadrži URL slike profila. U polje za unos **Tip**, ručno unesite sljedeću vrijednost: 
- Za osobu: Person.ProfileImage
- Za tvrtku ili ustanovu: Organization.LogoImage

Nastavite s koracima ujedinjavanja i osigurajte da je atribut koji sadrži URL slike također dodan u koraku [Spoji](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Postavljanje atributa za organizacije

Za organizacije (Pregled), tip atributa trebao bi se mapirati u "Organization.Name"
> [!div class="mx-imgBorder"]
> ![Primarni ključ i vrsta atributa B2B](media/configure-data-map-edit-b2b.png "Primarni ključ i vrsta atributa B2B")

## <a name="next-step"></a>Sljedeći korak

Kao dio postupka objedinjavanja podataka idite na stranicu **Podudaranje**. Otvorite dio [**Podudaranje**](match-entities.md) kako biste saznali više o ovoj fazi.

> [!TIP]
> Provjerite sljedeći videozapis: [Prvi koraci: izrada jedinstvenog profila klijenta](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]