---
title: Pregled izvora podataka
description: Saznajte kako uvesti ili unijeti podatke iz različitih izvora.
ms.date: 09/29/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610043"
---
# <a name="data-sources-overview"></a>Pregled izvora podataka

Dynamics 365 Customer Insights pruža veze za dovođenje podataka iz širokog skupa izvora. Povezivanje s izvorom podataka često se naziva postupkom *gutanja podataka*. Nakon unosa podataka možete [objediniti, generirati](data-unification.md) uvide i aktivirati podatke za izgradnju personaliziranih iskustava.

## <a name="add-or-edit-data-sources"></a>Dodavanje ili uređivanje izvora podataka

Možete priložiti ili uvesti izvore podataka u Customer Insights. Veze u nastavku pružaju upute za dodavanje i uređivanje izvora podataka.

**Prilaganje izvor podataka**

Ako imate pripremljene podatke u jednom od Microsoftovih podatkovnih servisa Azure, Customer Insights se može jednostavno povezati s izvor podataka bez potrebe za ponovnim unosom podataka. Odaberite jednu od sljedećih mogućnosti:
- [Azure Data Lake Storage(csv ili parketne datoteke u mapi Uobičajeni podatkovni model)](connect-common-data-model.md)
- [Azure Synapse Analytics(Baze podataka na jezeru)](connect-synapse.md)
- [Microsoft Dataverse podatkovno jezero](connect-dataverse-managed-lake.md)

**Uvoz i pretvorba**

Ako koristite lokalne izvore podataka, Microsoftove podatke ili podatke drugih proizvođača, uvezite i transformirajte podatke pomoću Power Query poveznika.
- [Power Query Priključci](connect-power-query.md)

## <a name="review-data-sources"></a>Pregled izvora podataka

Ako je vaše okruženje konfigurirano za korištenje pohrane customer insights i koristite lokalne izvore podataka, koristite Power Platform protok podataka. Pomoću Power Platform tijekova podataka možete pregledavati zajedničke izvore podataka i izvore podataka kojima upravljaju drugi. Stranica **Izvori** podataka navodi izvore podataka u tri odjeljka:
- **Zajedničko**: izvori podataka kojima mogu upravljati svi administratori customer insightsa. Power Platform tokovi podataka, vlastiti račun za pohranu i prilaganje na upravljano Dataverse jezero podataka primjeri su zajedničkih izvora podataka.
- **Upravljam ja**: Power Platform tokovi podataka koje ste stvorili i kojima upravljate samo vi. Drugi administratori customer insightsa mogu samo pregledavati te tijekove podataka, ali ih ne mogu uređivati, osvježavati ili brisati.
- **Njima upravljaju drugi** korisnici: Power Platform tijekovi podataka koje su stvorili drugi administratori. Možete ih samo vidjeti. Navodi vlasnika toka podataka za kontakt za bilo kakvu pomoć.
> [!NOTE]
> Sve entitete mogu pregledavati i koristiti drugi korisnici. Iako su izvori podataka u vlasništvu korisnika koji ih je stvorio, dobivene entitete iz unosa podataka može koristiti svaki korisnik Customer Insightsa.

Ako vaše okruženje ne koristi Power Platform tijekove podataka, **stranica Izvori** podataka sadrži samo popis svih izvora podataka. Nema prikaza sekcija.

## <a name="manage-existing-data-sources"></a>Upravljanje postojećim izvorima podataka

Idite na **izvore** > **podataka** da biste vidjeli naziv svakog unesenog izvor podataka, njegov status i posljednji put kada su podaci osvježeni za taj izvor. Popis izvora podataka možete sortirati po bilo kojem stupcu ili pomoću okvira za pretraživanje pronaći izvor podataka kojim želite upravljati.

Odaberite izvor podataka za prikaz dostupnih akcija.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Dodan je izvor podataka.":::

- [**Uredite**](#add-or-edit-data-sources) izvor podataka da biste promijenili njegova svojstva.
- [**Osvježite**](#refresh-data-sources) izvor podataka tako da uključuje najnovije podatke.
- [**Obogatite**](data-sources-enrichment.md) izvor podataka prije ujedinjenja.
- **Izbrišite** izvor podataka. Izvor podataka se može izbrisati samo ako se podaci ne koriste u bilo kojoj obradi kao što su ujedinjenje, uvidi, aktivacije ili izvoz.

## <a name="refresh-data-sources"></a>Osvježivanje izvora podataka

Izvori podataka mogu se osvježiti prema automatskom rasporedu ili ručno na zahtjev. [Lokalni izvori](connect-power-query.md#add-data-from-on-premises-data-sources) podataka osvježavaju se prema vlastitim rasporedima koji su postavljeni tijekom gutanja podataka. Savjete za otklanjanje poteškoća potražite u članku [Otklanjanje poteškoća s izvor podataka osvježavanjem utemeljenih na PPDF-u Power Query](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

Za priložene izvore podataka unos podataka troši najnovije podatke dostupne iz tog izvor podataka.

Idite na **Raspored** > **administratorskih** > [**sustava**](schedule-refresh.md) da biste konfigurirali sistemski zakazana osvježavanja unesenih izvora podataka.

Da biste osvježili izvor podataka na zahtjev:

1. Idite na **Podaci** > **Izvor podataka**.

1. Odaberite izvor podataka koje želite osvježiti, a zatim **Osvježi**. Izvor podataka sada se pokreće za ručno osvježavanje. Osvježavanje izvora podataka ažurirat će i shemu entiteta i podatke za sve entitete navedene u izvoru podataka.

1. Odaberite status da biste otvorili **okno s detaljima o** napretku i prikazali tijek. Da biste otkazali posao, pri dnu okna odaberite **Odustani od posla**.

## <a name="corrupt-data-sources"></a>Oštećeni izvori podataka

Podaci koji se unose mogu imati oštećene zapise koji mogu uzrokovati dovršavanje procesa gutanja podataka s pogreškama ili upozorenjima.

> [!NOTE]
> Ako se unos podataka dovrši pogreškama, naknadna obrada (kao što je ujedinjenje ili stvaranje aktivnosti) koja koristi ovu izvor podataka bit će preskočena. Ako je gutanje dovršeno s upozorenjima, naknadna obrada se nastavlja, ali neki zapisi možda neće biti uključeni.

Te se pogreške mogu vidjeti u detaljima zadatka.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Detalj zadatka koji prikazuje oštećenu pogrešku u podacima.":::

Oštećeni zapisi prikazuju se u sistemski stvorenim entitetima.

### <a name="fix-corrupt-data"></a>Ispravljanje oštećenih podataka

1. Da biste prikazali oštećene podatke, idite na **Entiteti** > **podataka** i potražite oštećene entitete u **odjeljku Sustav**. Shema imenovanja oštećenih entiteta: "DataSourceName_EntityName_corrupt".

1. Odaberite oštećeni entitet, a zatim karticu **Podaci**.

1. Identificirajte oštećena polja u zapisu i razlog.

   :::image type="content" source="media/corruption-reason.png" alt-text="Razlog korupcije." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Entiteti** > **podataka** prikazuju samo dio oštećenih zapisa. Da biste prikazali sve oštećene zapise, izvezite datoteke u spremnik na računu za pohranu pomoću postupka [izvoza](export-destinations.md) Customer Insights. Ako ste koristili vlastiti račun za pohranu, možete pogledati i mapu Customer Insights na računu za pohranu.

1. Popravite oštećene podatke. Na primjer, za izvore [podataka servisa Azure Data Lake popravite podatke u spremištu na servisu Data Lake Storage ili ažurirajte vrste podataka u datoteci](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data) manifest/model.json. Za Power Query izvore podataka popravite podatke u izvornoj datoteci i [ispravite vrstu podataka korak](connect-power-query.md#data-type-does-not-match-data) transformacije **Power Query na stranici - Uređivanje upita**.

Nakon sljedećeg osvježavanja izvora podataka ispravljeni zapisi unose se u Customer Insights i prosljeđuju nizvodnim procesima.

Na primjer, stupac 'rođendan' ima vrstu podataka postavljenu kao „datum”. U zapisu klijenta rođendan je unesen kao '01/01/19777'. Sustav označava ovaj zapis kao oštećen. Promijenite rođendan u izvornom sustavu u '1977'. Nakon automatskog osvježavanja izvora podataka, polje sada ima valjani oblik i zapis se uklanja iz oštećenog entiteta.

[!INCLUDE [footer-include](includes/footer-banner.md)]
