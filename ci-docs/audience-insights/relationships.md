---
title: Odnosi među entitetima i putanjama entiteta
description: Stvorite i upravljajte odnosima između entiteta iz više izvora podataka.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405340"
---
# <a name="relationships-between-entities"></a>Odnosi među entitetima

Odnosi pomažu pri povezivanju entiteta i generiranju grafikona vaših podataka kada entiteti dijele zajednički identifikator (strani ključ) koji se može uputiti iz jednog entiteta u drugi. Povezani entiteti omogućuju vam definiranje segmenata i mjera na temelju više izvora podataka.

Postoje dvije vrste odnosa. Sistemski odnosi koji se ne mogu uređivati, a koji se izrađuju automatski i prilagođeni odnosi koje izrađuju i konfiguriraju korisnici.

Tijekom procesa uparivanja i spajanja, sistemski odnosi izrađuju se iza scene na temelju inteligentnog uparivanja. Ovi odnosi pomažu pri povezivanju zapisa profila klijenta s ostalim odgovarajućim zapisima entiteta. Sljedeći dijagram ilustrira izradu triju sistemskih odnosa kada se entitet klijenta uparuje s dodatnim entitetima radi izrade konačnog entiteta Profil klijenta.

> [!div class="mx-imgBorder"]
> ![Izrada odnosa](media/relationships-entities-merge.png "Izrada odnosa")

- ***CustomerToContact* odnos** izrađen je između entiteta Klijent i entiteta Kontakt. Entitet Klijent dobiva polje ključa **Contact_contactId** za povezivanje s poljem ključa **contactId** entiteta Kontakt.
- **_CustomerToAccount_ odnos** izrađen je između entiteta Klijent i entiteta Račun. Entitet Klijent dobiva polje ključa **Account_accountId** za povezivanje s poljem ključa **accountId** entiteta Račun.
- **_CustomerToWebAccount_ odnos** izrađen je između entiteta Klijent i entiteta Web-račun. Entitet Klijent dobiva polje ključa **WebAccount_webaccountId** za povezivanje s poljem ključa **webaccountId** entiteta Web-račun.

## <a name="create-a-relationship"></a>Izrada odnosa

Definirajte prilagođene odnose na stranici **Odnosi**. Svaki se odnos sastoji od entiteta izvora (entitet koji drži vanjski ključ) i entiteta cilja (entitet na koji ukazuje vanjski ključ entiteta izvora).

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Odnosi**.

2. Odaberite **Novi odnos**.

3. U oknu **Dodaj odnos** navedite sljedeće informacije:

   > [!div class="mx-imgBorder"]
   > ![Unos pojedinosti o odnosu](media/relationships-add.png "Unos pojedinosti o odnosu")

   - **Naziv odnosa**: Naziv koji odražava svrhu odnosa (na primjer, **AccountWebLogs**).
   - **Opis**: Opis odnosa.
   - **Entitet Izvor** : Odaberite entitet koji se koristi kao izvor u odnosu (na primjer, WebLog).
   - **Kardinalnost**: Odaberite kardinalnost zapisa entiteta izvor. Na primjer, „mnogo” znači da je više zapisa web-zapisnika povezano s jednim web-računom.
   - **Polje ključa izvora**: Ovo predstavlja polje stranog ključa u entitetu izvor. Na primjer, WebLog ima **accountId** polje stranog ključa.
   - **Entitet Cilj** : Odaberite entitet koji se koristi kao cilj u odnosu (na primjer, WebAccount).
   - **Kardinalnost cilja**: Odaberite kardinalnost zapisa entiteta cilja. Na primjer, „jedan” znači da je više zapisa web-zapisnika povezano s jednim web-računom.
   - **Polje ključa cilja**: Ovo polje predstavlja polje ključa entiteta cilj. Na primjer, WebAccount ima **accountId** polje ključa.

> [!NOTE]
> Podržani su samo odnosi mnogi na jedan i jedan na jedan. Odnosi mnogi na mnogi mogu se izraditi s pomoću dva odnosa mnogi na jedan i entiteta veze (entitet koji se koristi za povezivanje entiteta izvor i entiteta cilj).

## <a name="delete-a-relationship"></a>Brisanje odnosa

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Odnosi**.

2. Potvrdite okvire za odnose koje želite izbrisati.

3. Odaberite **Izbriši** na vrhu tablice **Odnosi**.

4. Potvrdite brisanje.

## <a name="next-step"></a>Sljedeći korak

Sistemski i prilagođeni odnosi koriste se za izradu segmenata na temelju više izvora podataka koji se više ne biraju. Dodatne informacije potražite u dijelu [Segmenti](segments.md).
