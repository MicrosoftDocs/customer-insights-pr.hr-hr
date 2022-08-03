---
title: Semantička mapiranja (pretpregled)
description: Pregled semantičkih mapiranja i njihove upotrebe.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183622"
---
# <a name="semantic-mappings-preview"></a>Semantička mapiranja (pretpregled)

Semantičko mapiranje omogućuje vam mapiranje podataka o neaktivnosti u unaprijed definirane sheme. Te sheme pomažu Customer Insightsu da bolje razumiju vaše atribute podataka. Semantičko mapiranje i pruženi podaci omogućuju nove uvide i značajke u Customer Insights. Da biste svoje aktivnosti mapirali u sheme, pregledajte dokumentaciju [aktivnosti](activities.md).

**Semantičko mapiranje trenutačno je omogućeno za okruženja temeljena na poslovnim računima**. *ContactProfile* jedina je vrsta semantičkog mapiranja koja je trenutno dostupna u Customer Insights.

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

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Stvaranje aktivnosti na razini kontakta pomoću preslikavanja semantičkog entiteta ContactProfile

Nakon stvaranja mapiranja *semantičkog entiteta ContactProfile* možete snimiti aktivnosti kontakata. Omogućuje vam da vidite na vremenskoj traci aktivnosti za poslovni subjekt koji je kontakt odgovoran za svaku aktivnost. Većina koraka slijedi uobičajenu konfiguraciju mapiranja aktivnosti.

   > [!NOTE]
   > Da bi aktivnosti na razini kontakta funkcionirale, morate imati atribute **ID Poslovnog** subjekta i **ID-a** kontakta za svaki zapis unutar podataka o aktivnostima.

1. [*Definirajte mapiranje* semantičkog entiteta ContactProfile i pokrenite semantičko mapiranje](#define-a-contactprofile-semantic-entity-mapping).

1. Otvorite **Podatkovne** > **aktivnosti**.

1. Odaberite **Dodaj aktivnost** da biste stvorili novu aktivnost.

1. Imenujte aktivnost, odaberite entitet izvorne aktivnosti i odaberite primarni ključ entiteta aktivnosti.

1. **U Odnosi** koraku stvorite neizravan odnos između podataka izvora aktivnosti s poslovnim subjektima pomoću podataka za kontakt kao posredničkog entiteta. Dodatne informacije potražite u izravnim [i neizravnim putovima](relationships.md#relationship-paths) odnosa.
   - Primjer odnosa za aktivnost pod nazivom *Nabava*:
      - **Kupnja Podaci o kontaktima** > **podataka o izvornoj** aktivnosti na atributu **ID kontakta**
      - **Podaci** > **podatkovnog** računa za kontakt na atributu **ID poslovnog subjekta**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Primjer postavljanja odnosa.":::

1. Nakon postavljanja Odnosi odaberite **Dalje** i dovršite konfiguraciju mapiranja aktivnosti. Detaljne korake u vezi sa stvaranjem aktivnosti potražite [u članku Definiranje aktivnosti](activities.md).

1. Pokrenite mapiranja aktivnosti.

1. Nakon pokretanja mapiranja aktivnosti na razini kontakta odaberite **Kupci**. Aktivnosti na razini kontakta prikazuju se na vremenskoj traci klijenta.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Konačni rezultat nakon konfiguriranja aktivnosti kontakta":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtriranje vremenske trake aktivnosti na razini kontakta

Vremenska traka aktivnosti za vaše klijente uključuje njihove ID-ove ili nazive, ovisno *o konfiguraciji ContactProfile*, za aktivnosti na koje su djelovali. Filtrirajte aktivnosti po kontaktima na vremenskoj traci da biste vidjeli određene kontakte koji vas zanimaju. Da biste prikazali sve aktivnosti koje nisu dodijeljene određenom kontaktu, odaberite **Aktivnosti koje nisu mapirane u kontakt**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Mogućnosti filtriranja dostupne za aktivnosti na razini kontakta.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
