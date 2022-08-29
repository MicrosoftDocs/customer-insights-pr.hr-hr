---
title: Odabir izvorišnih polja za objedinjavanje podataka
description: Prvi korak u procesu ujedinjenja je odabir entiteta, atributa, primarnih ključeva i semantičkih vrsta za mapiranje podataka u jedinstveni profil klijenta.
recommendations: false
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304556"
---
# <a name="select-source-fields-for-data-unification"></a>Odabir izvorišnih polja za objedinjavanje podataka

Prvi korak u ujedinjenju je odabir entiteta i polja unutar skupova podataka koje želite objediniti. Odaberite entitete koji sadrže detalje vezane uz klijenta kao što su ime, adresa, telefonski broj i e-pošta. Možete odabrati jedan ili više entiteta.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Odaberite entitete i polja

1. Otvorite Objedinjavanje **podataka** > **·**.

   Za pojedinačne kupce (od B do C) **prikazat će se odredišna stranica Objedinjavanje** koja prikazuje **početak rada** na prvom koraku, **Polja Izvor**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Snimka zaslona objedinjavanja odredišne stranice za iskustvo prvog pokretanja za pojedinačne kupce.":::

   Za poslovne račune (B-do-B) na odredišnoj **stranici Objedinjavanje** prikazat će **se objedinjavanje računa** koji prikazuju **Početak rada** na prvom koraku, **Polja** Izvor. Koraci **objedinjavanja kontakata (pretpregleda)** nisu obavezni i čekaju dovršetak ujedinjenja računa.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Snimka zaslona objedinjavanja odredišne stranice za iskustvo prvog pokretanja za poslovne račune.":::

1. Odaberite **Početak rada**.

1. Na stranici Izvorna **polja** odaberite **Odabir entiteta i polja**. Prikazuje se **okno Odabir entiteta i polja**.

1. Odaberite barem jedan entitet.

1. Za svaki odabrani entitet identificirajte polja koja želite koristiti za podudaranje zapisa o klijentima i polja koja želite uključiti u jedinstveni profil. Ta se polja nazivaju *Atributi*. Obavezne atribute možete odabrati pojedinačno iz entiteta ili uključiti sve atribute iz entiteta tako da potvrdite okvir na razini entiteta. Ključne riječi možete pretraživati po svim atributima i entitetima kako biste odabrali potrebne atribute koje želite mapirati.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Snimka zaslona odabranih entiteta i atributa.":::

   U ovom primjeru dodajemo entitete **eCommerceContacts** i **loyCustomer**. Odabirom ovih entiteta možete steći uvid u to koji su od internetskih poslovnih klijenata članovi programa vjernosti.

1. Odaberite **Primijeni** za potvrdu odabira. Prikazuju se odabrani entiteti i atributi.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Odaberite primarni ključ i semantičku vrstu za atribute

   :::image type="content" source="media/m3_select_primary.png" alt-text="Snimka zaslona odabranih entiteta s primarnim ključem koji još nije odabran." lightbox="media/m3_select_primary.png":::

Za svaki entitet izvedi sljedeće korake.

1. Odaberite primarni **ključ**. Primarni ključ je atribut jedinstven za entitet. Da bi atribut bio važeći primarni ključ, on ne bi trebao uključivati dvostruke vrijednosti, vrijednosti koje nedostaju ili vrijednosti nula. Atributi vrste podataka nizova, cijelog broja i GUID-a podržani su kao primarni ključevi.

1. Da biste koristili AI modele za pametne predviđanje semantike koja štedi vrijeme i poboljšava točnost, osigurajte da **je uključeno inteligentno mapiranje**. Inteligentno mapiranje pruža semantičke preporuke temeljene na umjetnoj inteligenciji **u polju Vrsta**.

1. Za svaki atribut odaberite semantičku **vrstu** koja najbolje opisuje taj atribut, kao što su ime, grad ili adresa e-pošte.

   > [!NOTE]
   > U B-to-C jedno polje treba mapirati na semantički tip *Person.FullName* da bi se popunilo ime kupca na kartici kupca. U B-to-B naziv računa trebao bi se mapirati na *Organization.Name*. U suprotnom će se kartice klijenta prikazati bez naziva.

   1. Da biste nadjačali vrstu atributa koju je identificirao sustav, odaberite drugu mogućnost. Ako vrsta ne postoji, stvorite prilagođenu semantičku vrstu tako **da odaberete polje Vrsta** za atribut i unesete prilagođeni naziv semantičke vrste.

   1. Da biste dodali atribut koji sadrži URL javno dostupnim slikama ili logotipima profila, odaberite entitet i polje koje sadrži URL. **U polje Vrsta** unesite sljedeće:
      - Za osobu: Person.ProfileImage
      - Za tvrtku ili ustanovu: Organization.LogoImage

1. Pregledajte atribute na kojima se automatski identificira semantički tip. Ti su atributi navedeni u odjeljku **Pregled mapiranih polja**. U koraku Objedinjavanje polja **klijenta mogu se kombinirati** samo atributi iste vrste. Semantički tipovi koriste se za automatsko predlaganje uvida. Provjerite jesu li odabrane vrste dosljedne u svim odabranim entitetima.

1. Za atribute koji nisu automatski mapirani u semantičku vrstu odaberite polje semantičke vrste, unesite prilagođeni naziv vrste atributa ili ih ostavite bez opisa. Ti su atributi navedeni u odjeljku **Definiranje podataka u nepreslikanim poljima**.

1. Nakon dovršetka koraka za svaki entitet odaberite **Spremi izvorišna polja**.

1. Odaberite **Dalje**.

> [!div class="nextstepaction"]
> [Sljedeći korak: Uklanjanje duplikata](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
