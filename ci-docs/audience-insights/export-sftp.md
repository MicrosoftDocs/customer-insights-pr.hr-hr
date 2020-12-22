---
title: Izvoz podataka usluge Customer Insights na glavna računala SFTP
description: Saznajte kako konfigurirati vezu sa SFTP računalom.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643494"
---
# <a name="connector-for-sftp-preview"></a>Poveznik za SFTP (pretpregled)

Koristite svoje korisničke podatke u aplikacijama treće strane tako da ih izvezete na glavno računalo s protokolom Secure File Transfer Protocol (SFTP).

## <a name="prerequisites"></a>Preduvjeti

- Dostupnost SFTP računala i odgovarajućih vjerodajnica.

## <a name="connect-to-sftp"></a>Povezivanje sa SFTP-om

1. Otvorite **Administrator** > **Izvozna odredišta**.

1. Pod **SFTP**, odaberite **Postavljanje**.

1. Dodijelite odredištu prepoznatljivi naziv u polju **Zaslonski naziv**.

1. Navedite **Korisničko ime**, **Lozinku** i **Naziv glavnog računala** za vaš SFTP račun. Primjer: Ako je korijenska mapa vašeg SFTP poslužitelja /root/folder, a želite da se podaci izvezu u root/folder/ci_export_destination_folder, glavno bi računalo trebalo biti sftp://<server_address>/ci_export_destination_folder".

1. Odaberite **Provjeri** da biste testirali vezu.

1. Nakon uspješne provjere, odaberite želite li izvesti svoje podatke **Komprimirane** ili **Nekomprimirane** i odaberite **razdjelnik polja** za izvezene datoteke.

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Dalje** za početak konfiguriranja izvoza.

## <a name="configure-the-connection"></a>Konfiguriranje veze

1. Odaberite **atribute klijenta** koje želite izvesti. Možete izvesti jedan ili više atributa.

1. Odaberite **Dalje**.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

## <a name="export-the-data"></a>Izvoz podataka

Možete [izvesti podatke na zahtjev](export-destinations.md). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka putem SFTP-a, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da odredište za izvoz ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
