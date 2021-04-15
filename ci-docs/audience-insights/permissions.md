---
title: Upravljanje korisničkim dozvolama
description: Saznajte više o dozvolama i korisničkim ulogama.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e58bb1a3bd4c0920ff984daffabbf16162185f3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595693"
---
# <a name="user-permissions"></a>Korisničke dozvole

Stranica **Dozvole** mjesto je gdje ćete postaviti uloge i dozvole za korištenje uvida u ciljnu skupinu.

Za pregled stranice morate imati administratorske dozvole. Da biste pristupili stranici s dozvolama u uvidima u ciljnu skupinu, idite na **Admin** > **Dozvole**.

Postoje tri vrste uloga:

## <a name="viewer"></a>Gledatelj

- Istražite uvide i segmente unutar stranica **Početna stranica** i **Segmenti**.
- Pretražite i filtrirajte profile klijenata s pomoću stranice **Klijenti**. Polja moraju biti pretraživa.
- Prikaži i istraži stranicu **Obogaćivanje**.
- Istražujte i izvozite entitete s pomoću stranice **Entiteti**.
- Pregledajte status procesnih sustava s pomoću stranice **Sustav**.
- Izvezite segmente sa stranice **Segmenti**.
- Instalirajte i koristite nadzornu ploču **Power BI Customer Insights**.

## <a name="contributor"></a>Suradnik

- Sve dozvole koje su dostupne Gledatelju.
- Učitavajte i pretvarajte podatke pomoću stranice **Izvori podataka**.
- Dovršite odjeljke *Objedinjavanje podataka* (**Mapiranje**, **Podudaranje** i **Spajanje**) koji rezultiraju objedinjenim entitetom profila klijenta.
- Definirajte **Odnosi** i **Aktivnosti**.
- Stvorite segmente pomoću stranice **Segmenti**.
- Izradite mjere s pomoću stranice **Mjere**.
- Upravljajte konfiguracijom i obogaćujte korisničke profile sa stranice **Obogaćivanje** (samo za obogaćivanja prve strane).

## <a name="administrator"></a>Administrator

- Sve dozvole koje su dostupne Suradniku.
- Promijenite postavke na stranici **Sustav**, uključujući radni jezik i rasporede osvježavanja za vaše sistemske procese.
- Pregledajte i dodajte dozvole koristeći stranicu **Dozvole**.
- Postavite definicije pretraživanja i filtriranja za stranicu Klijenti pomoću stranice **Indeks pretraživanja i filtriranja** (dostupna putem stranice **Klijenti**).
- Definirajte odredišta segmenta u sustavu Dynamics 365 Sales putem stranice **Odredišta izvoza**.
- Upravljajte konfiguracijom i obogaćujte korisničke profile sa stranice **Obogaćivanje** (za sva obogaćivanja).
- Instalirajte i koristite **Dodatak za karticu klijenta**.
- Dodajte i koristite **Power Apps poveznik**.
- Omogućite korištenje [API-jeva za Customer Insights](apis.md).

## <a name="assign-roles-and-permissions"></a>Dodjela uloga i dozvola

1. U uvidima u ciljnu skupinu idite na **Admin** > **Dozvole**.

1. Odaberite **Dodaj korisnike** da biste otvorili okno **Dodaj/uredi dozvole**.

1. Koristite polje **Pretraži** da biste pronašli Azure Active Directory korisnika ili grupu čije dozvole želite prilagoditi. Odaberite mogućnost **Uloga** za dodjelu tom korisniku ili grupi.

1. Odaberite **Spremi**. Trenutno okruženje automatski će se dijeliti s korisnikom ili članovima grupe čije ste dozvole promijenili. Korisnici mogu pristupiti aplikaciji Customer Insights i raditi u skladu s njihovom zadanom ulogom.

## <a name="view-current-permissions"></a>Pregledaj trenutačne dozvole

U uvidima u ciljnu skupinu idite na **Admin** > **Dozvole** da biste vidjeli koji su zadaci uloga trenutno aktivni.

- Stupac **Vrsta** navodi jednog korisnika, grupu ili aplikaciju. Sustav podržava pojedinačne korisnike i grupe.
- Uloge su navedene u stupcu **Uloga**.
- Odaberite bilo koji naziv stupca da biste rezultate sortirali prema vrijednosti stupca.
- Upotrijebite polje **Pretraživanje** na vrhu stranice kako biste pronašli određene korisnike.


[!INCLUDE[footer-include](../includes/footer-banner.md)]