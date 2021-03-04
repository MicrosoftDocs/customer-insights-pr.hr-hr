---
title: Izvoz podataka usluge Customer Insights na glavna računala SFTP
description: Saznajte kako konfigurirati vezu sa SFTP računalom.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267989"
---
# <a name="connector-for-sftp-preview"></a>Poveznik za SFTP (pretpregled)

Koristite svoje korisničke podatke u aplikacijama treće strane tako da ih izvezete na glavno računalo s protokolom Secure File Transfer Protocol (SFTP).

## <a name="prerequisites"></a>Preduvjeti

- Dostupnost glavnog računala SFTP-a i odgovarajućih vjerodajnica.

## <a name="connect-to-sftp"></a>Povezivanje s SFTP-om

1. Otvorite **Administrator** > **Izvozna odredišta**.

1. Pod **SFTP**, odaberite **Postavljanje**.

1. Dodijelite odredištu prepoznatljivi naziv u polju **Zaslonski naziv**.

1. Navedite **Korisničko ime**, **Lozinku**, **Naziv glavnog računala** i **Mapu za izvoz** za vaš SFTP račun.

1. Odaberite **Provjeri** da biste testirali vezu.

1. Nakon uspješne provjere valjanosti odaberite želite li izvesti svoje podatke kao **Komprimirane** ili **Raspakirane** i odaberite **graničnik polja** za izvezene datoteke.

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Dalje** za početak konfiguriranja izvoza.

## <a name="configure-the-export"></a>Konfiguracija izvoza

1. Odaberite entitete, na primjer, segmente koje želite izvesti.

   > [!NOTE]
   > Svaki odabrani entitet imat će do pet izlaznih datoteka prilikom izvoza. 

1. Odaberite **Spremi**.

## <a name="export-the-data"></a>Izvoz podataka

Možete [izvesti podatke na zahtjev](export-destinations.md). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).

## <a name="known-limitations"></a>Poznata ograničenja

- Vrijeme izvoza ovisi o performansama vašeg sustava. Preporučujemo dvije CPU jezgre i 1 Gb memorije kao minimalnu konfiguraciju vašeg poslužitelja. 
- Izvoz entiteta s do 100 milijuna profila klijenata može potrajati 90 minuta kada se koristi preporučena minimalna konfiguracija dviju CPU jezgri i 1 Gb memorije. 

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka putem SFTP-a, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da odredište za izvoz ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE[footer-include](../includes/footer-banner.md)]