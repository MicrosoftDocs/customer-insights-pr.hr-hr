---
title: Odabir izvorišnih polja za objedinjavanje podataka
description: Prvi korak u procesu ujedinjenja je odabir entiteta, atributa, primarnih ključeva i semantičkih vrsta za mapiranje podataka u jedinstveni profil klijenta.
recommendations: false
ms.date: 04/22/2022
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
ms.openlocfilehash: a75218c996b277e00924f2b7b38ea686a1f4dc38
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139773"
---
# <a name="select-source-fields-for-data-unification"></a>Odabir izvorišnih polja za objedinjavanje podataka

Prvi korak u ujedinjenju je odabir entiteta i polja unutar skupova podataka koje želite objediniti. Odaberite entitete koji sadrže detalje vezane uz klijenta kao što su ime, adresa, telefonski broj i e-pošta. Možete odabrati jedan ili više entiteta.

## <a name="select-entities-and-fields"></a>Odaberite entitete i polja

1. Otvorite Objedinjavanje **podataka** > **·**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Snimka zaslona objedinjavanja odredišne stranice za doživljaj prvog pokretanja s istaknutim prvim pokretanjem.":::

1. Odaberite **Početak rada**.

1. Na stranici Izvorna **polja** odaberite **Odabir entiteta i polja**. Prikazuje se **okno Odabir entiteta i polja**.

1. Odaberite barem jedan entitet.

1. Za svaki odabrani entitet identificirajte polja koja želite koristiti za podudaranje zapisa o klijentima i polja koja želite uključiti u jedinstveni profil. Ta se polja nazivaju *Atributi*. Obavezne atribute možete odabrati pojedinačno iz entiteta ili uključiti sve atribute iz entiteta tako da potvrdite okvir na razini entiteta. Ključne riječi možete pretraživati po svim atributima i entitetima kako biste odabrali potrebne atribute koje želite mapirati.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Snimka zaslona odabranih entiteta i atributa.":::

   U ovom primjeru dodajemo entitete **Kontakti** i **CustomerLoyalty**. Odabirom ovih entiteta možete steći uvid u to koji su od internetskih poslovnih klijenata članovi programa vjernosti.

1. Odaberite **Primijeni** za potvrdu odabira. Prikazuju se odabrani entiteti i atributi.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Odaberite primarni ključ i semantičku vrstu za atribute

   :::image type="content" source="media/m3_select_primary.png" alt-text="Snimka zaslona odabranih entiteta s primarnim ključem koji nije odabran." lightbox="media/m3_select_primary.png":::

Za svaki entitet izvedi sljedeće korake.

1. Odaberite primarni **ključ**. Primarni ključ je atribut jedinstven za entitet. Da bi atribut bio važeći primarni ključ, on ne bi trebao uključivati dvostruke vrijednosti, vrijednosti koje nedostaju ili vrijednosti nula. Atributi vrste podataka nizova, cijelog broja i GUID-a podržani su kao primarni ključevi.

1. Da biste koristili AI modele za pametne predviđanje semantike, uštedjeli vrijeme i poboljšali točnost, osigurajte da **je uključeno inteligentno mapiranje**. Inteligentno mapiranje ističe preporuke o semantici koje se temelje na umjetnoj iteligenciji u polju **Vrsta**. Predloženi odabir možete nadjačati odabirom bilo koje semantičke vrste s dostupnog popisa mogućnosti.

1. Za svaki atribut odaberite semantičku **vrstu** koja najbolje opisuje taj atribut, kao što su ime, grad ili adresa e-pošte.

   > [!NOTE]
   > Jedno polje treba mapirati na semantičku vrstu *Person.FullName* da bi se ime kupca popunilo karticom kupca. U suprotnom će se kartice klijenta prikazati bez naziva.

   1. Da biste promijenili vrstu atributa koju je identificirao sustav, odaberite drugu vrstu. Ako vrsta ne postoji, stvorite prilagođenu semantičku vrstu tako **da odaberete polje Vrsta** za atribut i unesete prilagođeni naziv semantičke vrste.

   1. Da biste dodali atribut koji sadrži URL javno dostupnim slikama ili logotipima profila, odaberite entitet i polje koje sadrži URL. **U polje Vrsta** unesite sljedeće:
      - Za osobu: Person.ProfileImage
      - Za tvrtku ili ustanovu: Organization.LogoImage

   1. Za atribut naziva računa unesite "Organization.Name" u **polje Vrsta**.

1. Pregledajte atribute na kojima se automatski identificira semantički tip. Ti su atributi navedeni u odjeljku **Pregled mapiranih polja**. U koraku Jedinstvena polja **klijenta mogu se kombinirati** samo atributi iste vrste. Semantički tipovi koriste se za automatsko predlaganje uvida. Provjerite jesu li odabrane vrste dosljedne u svim odabranim entitetima.

1. Za atribute koji nisu automatski mapirani u semantičku vrstu odaberite polje semantičke vrste, unesite prilagođeni naziv vrste atributa ili ih ostavite nepreslikane. Ti su atributi navedeni u odjeljku **Definiranje podataka u nepreslikanim poljima**.

1. Nakon dovršetka koraka za svaki entitet odaberite **Spremi izvorišna polja**.

1. Odaberite **Dalje**.

> [!div class="nextstepaction"]
> [Sljedeći korak: Uklanjanje duplikata](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
