---
title: Pregled objedinjavanja podataka
description: Prođite kroz postupak objedinjavanja podataka sa svojim podacima da biste stvorili jedan skup podataka jedinstvenih korisničkih profila.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139472"
---
# <a name="data-unification-overview"></a>Pregled objedinjavanja podataka

Nakon [postavljanja izvora podataka](data-sources.md) možete objediniti podatke. Objedinjavanje podataka omogućuje vam objedinjavanje jednom različitih izvora podataka u jedan skup glavnih podataka koji pruža jedinstveni prikaz tih podataka. Za pojedinačne potrošače (B-do-C) gdje su podaci usredotočeni na pojedince, ujedinjenje pruža jedinstven prikaz vaših kupaca. Za poslovne račune (B-do-B) na kojima su podaci centrirani na račune, objedinjavanje pruža jedinstveni prikaz vaših računa.

Podaci se mogu objediniti u jednom entitetu ili više entiteta. Ujedinjenje se vrši sljedećim redoslijedom:

1. [Izvorna polja](map-entities.md) (prethodno nazvana Karta): U koraku izvorišnih polja odaberite entitete i polja koja želite uključiti u proces objedinjavanja. Preslikajte polja na uobičajenu semantičku vrstu koja opisuje svrhu polja.

1. [Duplicirani zapisi](remove-duplicates.md) (prethodno dio podudaranja): u koraku dupliciranih zapisa po želji definirajte pravila za uklanjanje dupliciranih zapisa o klijentima iz svakog entiteta.

1. [Odgovarajući uvjeti](match-entities.md) (prethodno nazvani Podudaranje): u koraku podudarnih uvjeta definirajte pravila koja odgovaraju zapisima klijenata između entiteta. Kada se klijent pronađe u dva ili više entiteta, kreira se jedan konsolidirani zapis sa svim stupcima i podacima iz svakog entiteta.

1. [Objedinjena polja kupca](merge-entities.md) (prethodno nazvana Spoji): U koraku objedinjenih polja kupaca odredite koja izvorna polja treba uključiti, isključiti ili spojiti u jedinstveni profil kupca.  

1. [Pregledajte](review-unification.md) i stvorite jedinstveni profil.

Nakon dovršetka objedinjavanja podataka po želji možete:

- [Postavite Odnosi između entiteta](relationships.md) da biste kreirali sofisticirane segmente.
- [Obogatite svoje podatke](enrichment-hub.md) kako biste dobili širi raspon uvida o svojim klijentima.
- [Definirajte aktivnosti](activities.md) iz nekih od unesenih atributa.
- [Izradite mjere](measures.md) za bolje razumijevanje ponašanja kupaca i poslovnih rezultata.

[!INCLUDE [footer-include](includes/footer-banner.md)]
