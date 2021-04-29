---
title: Izvoz podataka iz Customer Insights
description: Upravljajte izvozima da biste dijelili podatke.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896134"
---
# <a name="exports-preview-overview"></a>Pregled izvoza (pretpregled)

Stranica **Izvozi** prikazuje sve konfigurirane izvoze. Izvozi dijele određene podatke s različitim aplikacijama. Mogu uključivati profile ili entitete klijenata, sheme i pojedinosti mapiranja. Svaki izvoz zahtijeva [vezu koju je postavio administrator za upravljanje provjerom autentičnosti i pristupom](connections.md).

> [!NOTE]
> Do ožujka 2021. izvozi su automatski stvarali vezu s odgovarajućom uslugom. Izvozi sada zahtijevaju [vezu koju je stvorio i podijelio administrator](connections.md) prije nego što ih možete stvoriti.

Idite na **Podaci** > **Izvozi** za prikaz stranice izvoza. Sve korisničke uloge imaju pristup za prikaz konfiguriranih izvoza. Korištenje polja za pretraživanje na naredbenoj traci za pronalaženje izvoza prema njihovu nazivu, nazivu veze ili vrsti veze.

## <a name="set-up-a-new-export"></a>Postavljanje novog izvoza

Da biste postavili ili uredili izvoz, trebate imati dostupne veze. Veze ovise o vašoj [korisničkoj ulozi](permissions.md):
- Administratori imaju pristup svim vezama. Također mogu stvoriti nove veze prilikom postavljanja izvoza.
- Suradnici mogu imati pristup određenim vezama. Ovise o administratorima za konfiguriranje i dijeljenje veza. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Gledatelji mogu samo pregledavati postojeće izvoze, ali ne mogu ih stvarati.

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz** da biste stvorili novo izvozno odredište.

1. U oknu **Postavi izvoz** odaberite koju ćete vezu koristiti. [Vezama](connections.md) upravljaju administratori. 

1. Navedite potrebne pojedinosti i odaberite **Spremi** da biste stvorili izvoz.

### <a name="edit-an-export"></a>Uređivanje izvoza

1. Odaberite okomitu elipsu za izvozno odredište koje želite urediti.

1. Odaberite **Uredi** na padajućem izborniku.

1. Promijenite vrijednosti koje želite ažurirati i odaberite **Spremi**.

## <a name="view-exports-and-export-details"></a>Prikaz Izvoza i pojedinosti o izvozu

Nakon stvaranja izvoznih odredišta ona se navode na **Podaci** > **Izvozi**. Svi korisnici mogu vidjeti koji se podaci dijele i njihov najnoviji status.

1. Idite na **Podaci** > **Izvozi**.

1. Korisnici bez dozvola za uređivanje odabiru **Prikaz** umjesto **Uredi** da bi vidjeli pojedinosti o izvozu.

1. To bočno okno prikazuje postavku tog izvoza. Bez dozvola za uređivanje ne možete promijeniti vrijednosti. Odaberite **Zatvori** za povratak na stranicu izvoza.

## <a name="run-exports-on-demand"></a>Pokretanje izvoza na zahtjev

Nakon konfiguriranja izvoza pokrenut će se sa svakim [zakazanim osvježavanjem](system.md#schedule-tab) sve dok ima funkcionalnu vezu.

Da biste izvezli podatke bez čekanja na zakazano osvježavanje, idite na **Podaci** > **Izvozi**. Postoje dvije mogućnosti:

- Da biste pokrenuli sve izvoze, odaberite **Pokreni sve** na naredbenoj traci. 
- Da biste pokrenuli pojedinačni izvoz, odaberite elipsu (...) na stavci popisa, a zatim odaberite **Pokreni**.

## <a name="remove-an-export"></a>Uklanjanje Izvoza

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite okomitu elipsu za Izvoz koji želite ukloniti.

1. Na padajućem popisu odaberite **Ukloni**.

1. Potvrdite uklanjanje odabirom opcije **Ukloni** na zaslonu za potvrdu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
