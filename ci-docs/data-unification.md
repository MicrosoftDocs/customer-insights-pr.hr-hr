---
title: Stvaranje objedinjenog prikaza klijenata
description: Prođite kroz postupak objedinjavanja podataka sa svojim podacima da biste stvorili jedan glavni skup podataka profila računa ili kupaca.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304418"
---
# <a name="data-unification-overview"></a>Pregled objedinjavanja podataka

Nakon [postavljanja izvora podataka](data-sources.md) možete objediniti podatke. Objedinjavanje podataka omogućuje vam objedinjavanje jednom različitih izvora podataka u jedan skup glavnih podataka koji pruža jedinstveni prikaz tih podataka.

Za pojedinačne potrošače (B-do-C) gdje su podaci usredotočeni na pojedince, ujedinjenje pruža jedinstven prikaz vaših kupaca. Za poslovne račune (B-do-B) na kojima su podaci centrirani na račune, objedinjavanje pruža jedinstveni prikaz vaših računa. [Objedinjavanje kontakata (pretpregled)](data-unification-contacts.md) omogućuje kontaktima da se ti računi zasebno ujedine i povežu s poslovnim subjektima.

Podaci se mogu objediniti u jednom entitetu ili više entiteta.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

Postupak ujedinjenja mapira podatke o klijentima iz vaših izvora podataka, uklanja duplikate, podudara podatke među entitetima i stvara jedinstveni profil. Ujedinjenje se vrši sljedećim redoslijedom:

1. [Izvorna polja](map-entities.md) (prethodno nazvana Karta): U koraku izvorišnih polja odaberite entitete i polja koja želite uključiti u proces objedinjavanja. Preslikajte polja na uobičajenu semantičku vrstu koja opisuje svrhu polja.

1. [Duplicirani zapisi](remove-duplicates.md) (prethodno dio podudaranja): u koraku dupliciranih zapisa po želji definirajte pravila za uklanjanje dupliciranih zapisa o klijentima iz svakog entiteta.

1. [Odgovarajući uvjeti](match-entities.md) (prethodno nazvani Podudaranje): u koraku podudarnih uvjeta definirajte pravila koja odgovaraju zapisima klijenata između entiteta. Kada se klijent pronađe u dva ili više entiteta, kreira se jedan konsolidirani zapis sa svim stupcima i podacima iz svakog entiteta.

1. [Objedinjena polja kupca](merge-entities.md) (prethodno nazvana Spoji): U koraku objedinjenih polja kupaca odredite koja izvorna polja treba uključiti, isključiti ili spojiti u jedinstveni profil kupca.  

1. [Pregledajte](review-unification.md) i stvorite jedinstveni profil.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

Proces ujedinjenja mapira podatke računa iz vaših izvora podataka, uklanja duplikate, podudara podatke među entitetima i stvara jedinstveni profil. Ujedinjenje se vrši sljedećim redoslijedom:

1. [Izvorišna polja](map-entities.md) (prethodno nazvana Karta): u koraku izvorišnih polja odaberite entitete i polja koja želite uključiti u postupak objedinjavanja računa. Preslikajte polja na uobičajenu semantičku vrstu koja opisuje svrhu polja.

1. [Duplicirani zapisi](remove-duplicates.md) (prethodno dio Podudaranja): u koraku dupliciranih zapisa po želji definirajte pravila za uklanjanje dupliciranih zapisa o poslovnim kontaktima iz svakog entiteta.

1. [Odgovarajući uvjeti](match-entities.md) (prethodno nazvani Podudaranje): u koraku podudarnih uvjeta definirajte pravila koja odgovaraju zapisima računa između entiteta. Kada se poslovni kontakt pronađe u dva ili više entiteta, stvara se jedan konsolidirani zapis sa svim stupcima i podacima iz svakog entiteta.

1. [Objedinjena polja kupca](merge-entities.md) (prethodno nazvana Spoji): U koraku objedinjenih polja kupaca odredite koja izvorna polja treba uključiti, isključiti ili spojiti u jedinstveni profil kupca.  

1. [Pregledajte](review-unification.md) i stvorite jedinstveni profil.

Nakon objedinjavanja poslovnih subjekata po želji [možete objediniti kontakte (pretpregled)](data-unification-contacts.md) za te poslovne subjekte i povezati objedinjene kontakte s objedinjenim poslovnim subjektima.

---

Nakon dovršetka objedinjavanja podataka po želji možete:

- [Postavite Odnosi između entiteta](relationships.md) da biste kreirali sofisticirane segmente.
- [Obogatite svoje podatke](enrichment-hub.md) kako biste dobili širi raspon uvida o svojim klijentima.
- [Definirajte aktivnosti](activities.md) iz nekih od unesenih atributa.
- [Izradite mjere](measures.md) za bolje razumijevanje ponašanja kupaca i poslovnih rezultata.

[!INCLUDE [footer-include](includes/footer-banner.md)]
