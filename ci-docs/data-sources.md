---
title: Pregled izvora podataka
description: Saznajte kako uvesti ili unijeti podatke iz različitih izvora.
ms.date: 07/26/2022
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
ms.openlocfilehash: 6ab97c535454e84c1bb18aca00bca2568eb65a2a
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207082"
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

Izvori podataka mogu se osvježiti prema automatskom rasporedu ili ručno na zahtjev. [Lokalni izvori](connect-power-query.md#add-data-from-on-premises-data-sources) podataka osvježavaju se prema vlastitim rasporedima koji su postavljeni tijekom gutanja podataka. Za priložene izvore podataka unos podataka troši najnovije podatke dostupne iz tog izvor podataka.

Idite na **Raspored** > **administratorskih** > [**sustava**](system.md#schedule-tab) da biste konfigurirali sistemski zakazana osvježavanja unesenih izvora podataka.

Da biste osvježili izvor podataka na zahtjev:

1. Idite na **Podaci** > **Izvor podataka**.

1. Odaberite izvor podataka želite osvježiti, a zatim odaberite **Osvježi**. Izvor podataka sada se pokreće za ručno osvježavanje. Osvježavanje izvora podataka ažurirat će i shemu entiteta i podatke za sve entitete navedene u izvoru podataka.

1. Odaberite status da biste otvorili **okno s detaljima o** napretku i prikazali tijek. Da biste otkazali posao, pri dnu okna odaberite **Odustani od posla**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
