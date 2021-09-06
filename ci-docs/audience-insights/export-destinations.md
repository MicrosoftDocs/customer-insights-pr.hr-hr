---
title: Izvoz podataka iz Customer Insights
description: Upravljajte izvozima da biste dijelili podatke.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: be4d142e0f9f422cac459f603aa5dd8bb490321cfe1b2de58f4a128ae56f4ba3
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034673"
---
# <a name="exports-preview-overview"></a>Pregled izvoza (pretpregled)

Stranica **Izvozi** prikazuje sve konfigurirane izvoze. Izvozi dijele određene podatke s različitim aplikacijama. Mogu uključivati profile ili entitete klijenata, sheme i pojedinosti mapiranja. Svaki izvoz zahtijeva [vezu koju je postavio administrator za upravljanje provjerom autentičnosti i pristupom](connections.md).

Idite na **Podaci** > **Izvozi** za prikaz stranice izvoza. Sve korisničke uloge mogu pregledavati konfigurirane izvoze. Koristite polje za pretraživanje na naredbenoj traci da biste pronašli izvoze prema njihovu nazivu, nazivu veze ili vrsti veze.

## <a name="set-up-a-new-export"></a>Postavljanje novog izvoza

Da biste postavili ili uredili izvoz, trebate imati dostupne veze. Veze ovise o vašoj [korisničkoj ulozi](permissions.md):
- Administratori imaju pristup svim vezama. Također mogu stvoriti nove veze prilikom postavljanja izvoza.
- Suradnici mogu imati pristup određenim vezama. Ovise o administratorima za konfiguriranje i dijeljenje veza. Popis izvoza pokazuje suradnicima mogu li uređivati ili samo pregledavati izvoz u stupcu **Vaše dozvole**. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Gledatelji mogu samo pregledavati postojeće izvoze, ali ne mogu ih stvarati.

### <a name="define-a-new-export"></a>Definiranje novog izvoza

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz** za stvaranje novog izvoza.

1. U oknu **Postavi izvoz** odaberite koju ćete vezu koristiti. [Vezama](connections.md) upravljaju administratori. 

1. Navedite potrebne pojedinosti i odaberite **Spremi** da biste stvorili izvoz.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definiranje novog izvoza na temelju postojećeg

1. Idite na **Podaci** > **Izvozi**.

1. Na popisu izvoza odaberite izvoz koji želite duplicirati.

1. Odaberite **Stvori duplikat** na naredbenoj traci za otvaranje okna **Postavi izvoz** s pojedinostima odabranog izvoza.

1. Pregledajte i prilagodite izvoz te odaberite **Spremi** za stvaranje novog izvoza.

### <a name="edit-an-export"></a>Uređivanje izvoza

1. Idite na **Podaci** > **Izvozi**.

1. Na popisu izvoza odaberite izvoz koji želite urediti.

1. Odaberite **Uredi** na naredbenoj traci.

1. Promijenite vrijednosti koje želite ažurirati i odaberite **Spremi**.

## <a name="view-exports-and-export-details"></a>Prikaz izvoza i pojedinosti o izvozu

Nakon stvaranja izvoznih odredišta ona su navedena u odjeljku **Podaci** > **Izvozi**. Svi korisnici mogu vidjeti koji se podaci dijele i njihov najnoviji status.

1. Idite na **Podaci** > **Izvozi**.

1. Korisnicie bez dozvole za uređivanje odabiru **Prikaži** umjesto **Uredi** kako bi vidjeli pojedinosti o izvozu.

1. Bočno okno prikazuje konfiguraciju izvoza. Bez dozvola za uređivanje ne možete promijeniti vrijednosti. Odaberite **Zatvori** za povratak na stranicu izvoza.

## <a name="schedule-and-run-exports"></a>Zakazivanje i pokretanje izvoza

Svaki izvoz koji konfigurirate ima raspored osvježavanja. Tijekom osvježavanja sustav traži nove ili ažurirane podatke koje će uključiti u izvoz. Prema zadanim postavkama izvozi se izvode kao dio svakog [zakazanog osvježavanja sustava](system.md#schedule-tab). Raspored osvježavanja možete prilagoditi ili ga isključiti za ručno pokretanje izvoza.

Rasporedi izvoza ovise o stanju vašeg okruženja. Ako su u tijeku ažuriranja na [ovisnostima](system.md#refresh-policies) kada bi trebao započeti planirani izvoz, sustav će prvo dovršiti ažuriranja, a zatim pokrenuti izvoz. U stupcu **Osvježeno** možete vidjeti kad je izvoz zadnji put bio osvježen.

### <a name="schedule-exports"></a>Zakazivanje izvoza

Možete definirati prilagođene rasporede osvježavanja za pojedinačne izvoze ili više izvoza odjednom. Trenutno definirani raspored naveden je u stupcu **Raspored** na popisu izvoza. Dozvola za promjenu rasporeda je ista kao i za [uređivanje i definiranje izvoza](export-destinations.md#set-up-a-new-export). 

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite izvoz koji želite zakazati.

1. Odaberite **Raspored** na naredbenoj traci.

1. U oknu **Zakazivanje izvoza** postavite **Pokretanje rasporeda** na **Uključeno** za automatsko pokretanje izvoza. Postavite na **Isključeno** da ga osvježite ručno.

1. Za automatski osvježene izvoze odaberite vrijednost **Ponavljanje** i za nju navedite pojedinosti. Definirano vrijeme odnosi se na sve slučajeve ponavljanja. To je vrijeme kada bi se izvoz trebao početi osvježavati.

1. Primijenite i aktivirajte promjene odabirom mogućnosti **Spremi**.

Pri uređivanju rasporeda za nekoliko izvoza, morate izvršiti odabir u odjeljku **Sačuvaj ili zamijeni rasporede**:
- **Sačuvaj pojedinačne rasporede**: Zadržite prethodno definirani raspored za odabrane izvoze i samo ih onemogućite ili omogućite.
- **Definiraj novi raspored za sve odabrane izvoze**: Zamijenite postojeće rasporede odabranih izvoza.

### <a name="run-exports-on-demand"></a>Pokretanje izvoza na zahtjev

Da biste izvezli podatke bez čekanja na zakazano osvježavanje, idite na **Podaci** > **Izvozi**.

- Da biste pokrenuli sve izvoze, odaberite **Pokreni sve** na naredbenoj traci. Ovom akcijom pokrenut će se samo izvozi sa aktivnim rasporedom.
- Da biste pokrenuli jedan izvoz, odaberite ga na popisu i odaberite **Pokreni** na naredbenoj traci. Tako pokrećete izvoz bez aktivnog rasporeda. 

## <a name="remove-an-export"></a>Uklanjanje Izvoza

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite izvoz koji želite ukloniti.

1. Odaberite **Ukloni** na naredbenoj traci.

1. Potvrdite uklanjanje odabirom opcije **Ukloni** na zaslonu za potvrdu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
