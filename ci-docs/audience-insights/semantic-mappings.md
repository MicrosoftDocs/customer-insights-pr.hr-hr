---
title: Semantička mapiranja (pretpregled)
description: Pregled semantičkih mapiranja i njihove upotrebe.
ms.date: 12/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: 08b257b97704b219bb3277042516e00deb886a49
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881821"
---
# <a name="semantic-mappings-preview"></a>Semantička mapiranja (pretpregled)

Semantičko mapiranje omogućuje vam mapiranje podataka o neaktivnosti u unaprijed definirane sheme. Ove sheme pomažu uvidima u ciljne skupine bolje razumjeti atribute podataka. Semantičko mapiranje i navedeni podaci omogućuju nove uvide i značajke uvida u ciljne skupine. Da biste svoje aktivnosti mapirali u sheme, pregledajte dokumentaciju [aktivnosti](activities.md).

**Semantičko mapiranje trenutačno je omogućeno za okruženja temeljena na poslovnim računima**. *ContactProfile* je jedina vrsta semantičkog mapiranja koja je trenutačno dostupna u uvidima u ciljne skupine.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definirajte semantičko mapiranje entiteta ContactProfile

1. U uvidima u ciljne skupine idite na opciju **Podaci** > **Semantička mapiranja (pretpregled)**.

1. Odaberite **Dodaj semantičko mapiranje** za početak vođenog iskustva.

1. U koraku **Podaci o entitetu** postavite vrijednosti za sljedeća polja:

   - **Naziv semantičkog mapiranja entiteta**: Navedite naziv za semantičko mapiranje entiteta.
   - **Izvorni entitet**: Odaberite entitet koji uključuje podatke o kontaktu.
   - **Primarni ključ**: Odaberite polje koje jedinstveno identificira zapis kontakta. Ne smije sadržavati duplicirane vrijednosti, prazne vrijednosti ili vrijednosti koje nedostaju.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Postavite semantičko mapiranje entiteta s nazivom, izvornim entitetom i primarnim ključem.":::

1. Za nastavak odaberite **Dalje**.

1. U koraku **Odnosi** konfigurirajte pojedinosti za povezivanje podataka o kontaktu s odgovarajućim podacima o računu. Ovaj korak vizualizira vezu među entitetima.  

   Postoje dvije vrste putanja odnosa koje se mogu implementirati: **Izravni odnosi** i **Neizravni odnosi**. Dodatne informacije potražite u odjeljku o [izravnim i neizravnim putanjama odnosa](relationships.md#relationship-paths).

   1. Odaberite **Dodaj odnos** za konfiguriranje odnosa.
   1. Odaberite atribut iz izvornog entiteta koji povezuje entitet kontakta s drugim entitetom.
   1. Odaberite entitet s kojim ćete povezati svoj entitet kontakta. Entitet možete odabrati iz odjeljka **Entiteti računa** ili **Posredni entitet**. Ako odaberete posredni entitet, morate definirati drugi odnos za povezivanje s ciljanim entitetom računa.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Odaberite entitet računa ili posredni entitet.":::

   1. Navedite **Naziv odnosa**. Ako odnos između vaših entiteta već postoji, naziv odnosa je samo za čitanje. Ako ne postoji odnos, stvorit će se novi odnos s nazivom koji navedete.
   1. Odaberite **Primijeni** da biste dovršili konfiguraciju odnosa.

   > [!NOTE]
   > Možete konfigurirati više odnosa između entiteta kontakta i drugih entiteta računa s posrednim entitetima.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Vizualizacija različitih odnosa povezuje entitete kontakta s entitetima računa.":::

1. Odaberite **Dalje** kad završite s konfiguracijom odnosa.

1. U koraku **Postavi semantičku vrstu** odaberite **Semantička vrsta**. Trenutačno postoji jedna **Semantička vrsta** pod nazivom *ContactProfile*.

1. Mapirajte podatke u *ContactProfile* **Semantička vrsta** za prikazana polja.
   - Obvezno polje: ID kontakta
   - Neobvezna polja: ime, prezime, datum rođenja, spol, primarna e-pošta i primarni telefon

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mapirajte atribute svojih podataka o kontaktu s predviđenim obveznim i neobveznim poljima.":::

1. Za nastavak odaberite **Dalje**.

1. U koraku **Pregled** pogledajte konfiguraciju semantičkog mapiranja. Odaberite **Uredi** da biste unijeli izmjene u odgovarajući odjeljak.

1. Odaberite **Spremi** da biste spremili novo **Semantičko mapiranje**.

1. Nakon spremanja možete odabrati proces **Pokreni** za obradu semantičkog mapiranja ili možete odabrati **Zatvori** da biste spremili semantičko mapiranje bez obrade.

1. Za naknadno pokretanje semantičkog mapiranja odaberite semantičko mapiranje i **Osvježi**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Upravljanje postojećim semantičkim mapiranjima

U opciji **Podaci** > **Semantička mapiranja (pretpregled)** možete pregledati sva spremljena semantička mapiranja i upravljati njima. Svako semantičko mapiranje predstavljeno je zasebnim retkom. Pronaći ćete pojedinosti o izvornom entitetu, semantičkoj vrsti, vrsti mapiranja i statusu.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opcije za upravljanje semantičkim mapiranjem.":::

- **Uredi**: Otvara postavku konfiguracije semantičkog mapiranja u koraku pregleda. Možete promijeniti trenutačnu konfiguraciju. Odaberite **Spremi** i **Pokreni** za obradu promjena.

- **Osvježi**: Osvježava odabrano semantičko mapiranje najnovijim podacima iz entiteta koji su dio njegove konfiguracije. Osvježavanje bilo kojeg semantičkog mapiranja osvježit će sva semantička mapiranja iste vrste.

- **Preimenuj**: Otvara dijaloški okvir u koji možete unijeti drugačiji naziv za odabrano semantičko mapiranje. Odaberite **Spremi** za primjenu izmjena.

- **Izbriši**: Otvara dijaloški okvir za potvrdu brisanja odabranog semantičkog mapiranja. Također možete izbrisati više od jednog semantičkog mapiranja odjednom tako da odaberete semantička mapiranja i ikonu za brisanje. Odaberite **Izbriši** da biste potvrdili brisanje.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Stvaranje aktivnosti na razini kontakta pomoću mapiranja semantičkog entiteta ContactProfile

Nakon stvaranja *mapiranja* semantičkog entiteta ContactProfile možete snimiti aktivnosti kontakata. Omogućuje vam da na vremenskoj traci aktivnosti vidite poslovni subjekt koji je kontakt odgovoran za svaku aktivnost. Većina koraka slijedi uobičajenu konfiguraciju mapiranja aktivnosti.

   > [!NOTE]
   > Da bi aktivnosti na razini kontakta **funkcionirale, morate imati atribute ID poslovnog** subjekta i **ContactID** za svaki zapis unutar podataka o aktivnosti.

1. [Definirajte *mapiranje* semantičkog entiteta ContactProfile.](#define-a-contactprofile-semantic-entity-mapping) I pokrenite semantičku kartografiju.

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Aktivnosti**.

1. Odaberite **Dodaj aktivnost da biste** stvorili novu aktivnost.

1. Imenujte aktivnost, odaberite entitet izvorne aktivnosti i odaberite primarni ključ entiteta aktivnosti.

1. U **koraku Odnosi** stvorite neizravan odnos između izvornih podataka o aktivnosti s poslovnim subjektima pomoću podataka za kontakt kao posredničkog entiteta. Dodatne informacije potražite u [odjeljku Putovi izravnih i indirektnih odnosa](relationships.md#relationship-paths).
   - Ogledni odnos za aktivnost pod nazivom *Nabava*:
      - **Kupuje podatke o izvornim podacima o** > **aktivnostima podatke o** kontaktu na atributu **ContactID**
      - **Podaci o računu podataka za kontakt** > **na** atributu **ID poslovnog subjekta**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Primjer postavljanja odnosa.":::

1. Nakon postavljanja Odnosi odaberite **Dalje** i dovršite konfiguraciju mapiranja aktivnosti. Detaljne korake za kreiranje aktivnosti potražite [u članku definiranje aktivnosti](activities.md).

1. Pokrenite mapiranja aktivnosti.

1. Aktivnosti na razini kontakta sada će biti vidljive na vremenskoj crti klijenta.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Konačni rezultat nakon konfiguriranja aktivnosti kontakta":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtriranje vremenske trake aktivnosti na razini kontakta

Nakon konfiguriranja mapiranja aktivnosti na razini kontakta i pokretanja, vremenska traka aktivnosti za vaše klijente ažurirat će se. Uključuje njihove ID-ove ili imena, ovisno o *konfiguraciji ContactProfilea,* za aktivnosti na kojima su djelovali. Aktivnosti možete filtrirati prema kontaktima na vremenskoj traci da biste vidjeli određene kontakte koji vas zanimaju. Uz to, možete vidjeti sve aktivnosti koje nisu dodijeljene određenom kontaktu odabirom aktivnosti koje **nisu mapirane u kontakt**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Mogućnosti filtriranja dostupne za aktivnosti na razini kontakta.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
