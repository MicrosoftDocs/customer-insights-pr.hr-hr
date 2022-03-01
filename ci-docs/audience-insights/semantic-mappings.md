---
title: Semantička mapiranja (pretpregled)
description: Pregled semantičkih mapiranja i njihove upotrebe.
ms.date: 09/28/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: b0884b8b6a2c5abe4b3967d1b57d11a3a6d65c5b
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622926"
---
# <a name="semantic-mappings"></a>Semantička mapiranja

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

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Osim toga, većina procesa [ovisi o ostalim procesima](system.md#refresh-policies). Možete odabrati status procesa da biste vidjeli pojedinosti o tijeku cijelog posla. Nakon odabira mogućnosti **Pogledaj pojedinosti** za jedan od zadataka posla pronaći ćete dodatne informacije: vrijeme obrade, zadnji datum obrade te sve pogreške i upozorenja povezana sa zadatkom.

## <a name="manage-existing-semantic-mappings"></a>Upravljanje postojećim semantičkim mapiranjima

U opciji **Podaci** > **Semantička mapiranja (pretpregled)** možete pregledati sva spremljena semantička mapiranja i upravljati njima. Svako semantičko mapiranje predstavljeno je zasebnim retkom. Pronaći ćete pojedinosti o izvornom entitetu, semantičkoj vrsti, vrsti mapiranja i statusu.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opcije za upravljanje semantičkim mapiranjem.":::

- **Uredi**: Otvara postavku konfiguracije semantičkog mapiranja u koraku pregleda. Možete promijeniti trenutačnu konfiguraciju. Odaberite **Spremi** i **Pokreni** za obradu promjena.

- **Osvježi**: Osvježava odabrano semantičko mapiranje najnovijim podacima iz entiteta koji su dio njegove konfiguracije. Osvježavanje bilo kojeg semantičkog mapiranja osvježit će sva semantička mapiranja iste vrste.

- **Preimenuj**: Otvara dijaloški okvir u koji možete unijeti drugačiji naziv za odabrano semantičko mapiranje. Odaberite **Spremi** za primjenu izmjena.

- **Izbriši**: Otvara dijaloški okvir za potvrdu brisanja odabranog semantičkog mapiranja. Također možete izbrisati više od jednog semantičkog mapiranja odjednom tako da odaberete semantička mapiranja i ikonu za brisanje. Odaberite **Izbriši** da biste potvrdili brisanje.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
