---
title: Izvoz podataka usluge Customer Insights na glavna računala SFTP
description: Saznajte kako konfigurirati vezu i izvesti na SFTP lokaciju.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976884"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a>Izvoz popisa segmenata i ostalih podataka na SFTP (pretpregled)

Koristite svoje podatke o klijentima u aplikacijama trećih strana tako što ćete ih izvesti na lokaciju sigurnog protokola prijenosa datoteka (SFTP).

## <a name="prerequisites-for-connection"></a>Preduvjeti za vezu

- Dostupnost glavnog računala SFTP-a i odgovarajućih vjerodajnica.

## <a name="known-limitations"></a>Poznata ograničenja

- Vrijeme izvoza ovisi o performansama vašeg sustava. Preporučujemo dvije CPU jezgre i 1 Gb memorije kao minimalnu konfiguraciju vašeg poslužitelja. 
- Izvoz entiteta s do 100 milijuna profila klijenata može potrajati 90 minuta kada se koristi preporučena minimalna konfiguracija dviju CPU jezgri i 1 Gb memorije. 

## <a name="set-up-connection-to-sftp"></a>Postavljanje veze sa SFTP

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **SFTP** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite **Korisničko ime**, **Lozinku**, **Naziv glavnog računala** i **Mapu za izvoz** za vaš SFTP račun.

1. Odaberite **Provjeri** da biste testirali vezu.

1. Odaberite želite li izvesti svoje podatke **Komprimirane** ili **Nekomprimirane** i **graničnik polja** za izvezene datoteke.

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka SFTP. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Odaberite entitete, na primjer, segmente koje želite izvesti.

   > [!NOTE]
   > Svaki odabrani entitet podijelit će se u do pet izlaznih datoteka prilikom izvoza. 

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka putem SFTP-a, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da odredište za izvoz ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
