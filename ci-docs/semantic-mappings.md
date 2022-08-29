---
title: Semantička mapiranja (pretpregled)
description: Pregled semantičkih mapiranja i njihove upotrebe.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303867"
---
# <a name="semantic-mappings-preview"></a>Semantička mapiranja (pretpregled)

> [!NOTE]
> Stranica **Semantička mapiranja** dostupna je samo za poslovna okruženja (B-do-B) u kojima su profili kontakata već stvoreni pomoću ove stranice. Možete nastaviti stvarati pojedinačne profile kontakata i upravljati njima pomoću **stranice Semantička mapiranja**. [Ili objedinite podatke za](data-unification-contacts.md) kontakt da biste uklonili duplikate, identificirali podudaranja među entitetima i stvorili jedan jedinstveni profil kontakta. Zatim možete koristiti jedinstveni profil kontakta za stvaranje aktivnosti na razini kontakta.

Semantičko mapiranje omogućuje vam mapiranje podataka o neaktivnosti u unaprijed definirane sheme. Te sheme pomažu customer insightsu da bolje razumiju vaše atribute podataka. Semantičko mapiranje i pruženi podaci omogućuju nove uvide i značajke u Customer Insights. Da biste svoje aktivnosti mapirali u sheme, pregledajte dokumentaciju [aktivnosti](activities.md).

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definirajte semantičko mapiranje entiteta ContactProfile

1. Idite na **Mapiranja semantičkog semantičkog prijenosa podataka** > **(pretpregled)**.

1. Odaberite **Dodaj semantičko mapiranje** za početak vođenog iskustva.

1. U koraku **Podaci o entitetu** postavite vrijednosti za sljedeća polja:

   - **Naziv preslikavanja semantičkog entiteta**: naziv mapiranja semantičkog entiteta.
   - **Izvorni entitet**: entitet koji sadrži podatke o kontaktima.
   - **Primarni ključ**: polje koje jedinstveno identificira zapis kontakta. Ne smije sadržavati duplicirane vrijednosti, prazne vrijednosti ili vrijednosti koje nedostaju.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Postavite semantičko mapiranje entiteta s nazivom, izvornim entitetom i primarnim ključem.":::

1. Odaberite **Dalje**.

1. U koraku **Odnosi** konfigurirajte pojedinosti za povezivanje podataka o kontaktu s odgovarajućim podacima o računu. Ovaj korak vizualizira vezu među entitetima.  

   Postoje dvije vrste putanja odnosa koje se mogu implementirati: **Izravni odnosi** i **Neizravni odnosi**. Dodatne informacije potražite u odjeljku o [izravnim i neizravnim putanjama odnosa](relationships.md#relationship-paths).

   1. Odaberite **Dodaj odnos** da biste konfigurirali odnos.
   1. Odaberite atribut iz izvornog entiteta koji povezuje entitet kontakta s drugim entitetom.
   1. Odaberite entitet s kojim ćete povezati svoj entitet kontakta. Odaberite entitet iz entiteta Poslovnog subjekta **ili** sekcije **Srednji entitet**. Ako odaberete posrednički entitet, definiši drugi odnos koji će se povezati sa entitetom ciljnog računa.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Odaberite entitet računa ili posredni entitet.":::

   1. Navedite **Naziv odnosa**. Ako odnos između vaših entiteta već postoji, naziv odnosa je samo za čitanje. Ako ne postoji odnos, stvorit će se novi odnos s nazivom koji navedete.
   1. Odaberite **Primijeni** da biste dovršili konfiguraciju odnosa.

   > [!NOTE]
   > Možete konfigurirati više odnosa između entiteta kontakta i drugih entiteta računa s posrednim entitetima.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Vizualizacija različitih odnosa povezuje entitete kontakta s entitetima računa.":::

1. Odaberite **Dalje**.

1. U koraku **Postavi semantičku vrstu** odaberite **Semantička vrsta**. Trenutačno postoji jedna **Semantička vrsta** pod nazivom *ContactProfile*.

1. Mapirajte ID kontakta na *ID* kontakta semantičkog tipa **ContactProfile**. Po želji mapirajte druga polja kao što su ime, prezime, spol ili e-pošta.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mapirajte atribute svojih podataka o kontaktu s predviđenim obveznim i neobveznim poljima.":::

1. Odaberite **Dalje**.

1. U koraku **Pregled** pregledajte konfiguraciju semantičkog mapiranja. Da biste unijeli promjene, odaberite **Uredi** za odgovarajući odjeljak.

1. Odaberite **Spremi**.

1. Da biste obradili semantičko mapiranje, odaberite **Pokreni**. Ili odaberite **Zatvori** da biste spremili semantičko mapiranje bez obrade. Da biste ga kasnije pokrenuli, odaberite semantičko mapiranje, a zatim **Osvježi**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Upravljanje postojećim semantičkim mapiranjima

Idite na **Semantička mapiranja (pretpregled)** > **podataka** da biste vidjeli spremljena semantička mapiranja, njihov izvorni entitet, semantičku vrstu, vrstu mapiranja i status.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opcije za upravljanje semantičkim mapiranjem.":::

Odaberite semantičko mapiranje da biste vidjeli dostupne akcije.
- **Uredite** trenutnu konfiguraciju. Odaberite **Spremi** i **Pokreni** za obradu promjena.
- **Osvježite** semantičko mapiranje tako da uključuje najnovije podatke. Osvježavanje bilo kojeg semantičkog mapiranja osvježit će sva semantička mapiranja iste vrste.
- **Preimenujte** semantičko mapiranje. Odaberite **Spremi**.
- **Izbrišite** semantičko mapiranje. Da biste izbrisali više semantičkih mapiranja odjednom, odaberite semantička mapiranja i ikonu brisanja. Odaberite **Izbriši** da biste potvrdili brisanje.

[!INCLUDE [footer-include](includes/footer-banner.md)]
