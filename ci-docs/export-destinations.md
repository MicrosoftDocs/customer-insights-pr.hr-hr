---
title: Pregled izvoza (pretpregled)
description: Upravljajte izvozima da biste dijelili podatke.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: c580b6c01e1b4ac6b095733193d86ebd0b4005f2
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304050"
---
# <a name="exports-preview-overview"></a>Pregled izvoza (pretpregled)

 Izvoz vam omogućuje dijeljenje određenih podataka s različitim aplikacijama. Mogu uključivati profile klijenata, entitete, sheme i pojedinosti mapiranja. Svaki izvoz zahtijeva [vezu koju je postavio administrator za upravljanje provjerom autentičnosti i pristupom](connections.md). Stranica **Izvozi** prikazuje sve konfigurirane izvoze.

## <a name="export-types"></a>Vrste izvoza

Postoje dvije glavne vrste izvoza:  

- **Izvozi za iznošenje** podataka omogućuju izvoz bilo koje vrste entiteta dostupne u customer insights. Entiteti koje odaberete za izvoz izvoze se sa svim poljima podataka, metapodacima, shemama i pojedinostima mapiranja.
- **Izvoz segmenata** omogućuje izvoz entiteta segmenta iz customer insights. Za pojedinačne potrošače (B-do-C) segmenti predstavljaju popis korisničkih profila. Za tvrtke (od B do B) [segmenti mogu predstavljati popis poslovnih subjekata ili kontakata](segment-builder.md#create-a-new-segment-with-segment-builder). Prilikom konfiguriranja izvoza odabirete uključena podatkovna polja, ovisno o ciljnom sustavu u koji izvozite podatke.

### <a name="export-segments"></a>Izvoz segmenata

**Izvoz segmenata u okruženja za poslovne račune (B2B) ili pojedinačne klijente (B2C)**  
Većina izvoznih opcija podržava obje vrste okruženja. Izvoz segmenata u različite ciljne sustave ima specifične zahtjeve. 

**Segment izvozi u okruženja za pojedinačne klijente (B2C)**  
- Segmenti u kontekstu okruženja za pojedinačne klijente sastavljeni su na entitetu *objedinjeni profil klijenta*. Svaki segment koji zadovoljava zahtjeve ciljnih sustava (na primjer, adresa e -pošte) može se izvesti.

**Izvoz segmenata u okruženjima za poslovne račune (B-do-B)**  
- Segmenti u kontekstu okruženja za poslovne račune temelje se na entitetu poslovnog subjekta *ili* entitetu *kontakta*. Za izvoz segmenata računa kakvi jesu, ciljni sustav mora podržavati čiste segmente računa. To je slučaj za [LinkedIn](export-linkedin-ads.md) kada odaberete opciju **tvrtka** prilikom definiranja izvoza.
- Svi drugi ciljni sustavi zahtijevaju polja iz entiteta kontakta.
- S dvije vrste segmenata (kontakti i računi), Customer Insights automatski identificira koja vrsta segmenata ispunjava uvjete za izvoz na temelju ciljnog sustava. Na primjer, za ciljni sustav usmjeren na kontakt kao što je Mailchimp, Customer Insights omogućuje vam samo odabir segmenata kontakata za izvoz.

**Ograničenja izvoza segmenata**  
- Ciljni sustavi trećih strana mogu ograničiti broj profila klijenata koje možete izvesti. 
- Za pojedinačne klijente vidjet ćete stvarni broj segmenta kada odaberete segment za izvoz. Dobit ćete upozorenje ako je segment prevelik. 
- Za poslovne račune vidjet ćete broj poslovnih subjekata ili kontakata, ovisno o segmentu. Dobit ćete upozorenje ako je segment prevelik. Prekoračenje granica rezultata ciljnog sustava preskočit će izvoz.

## <a name="set-up-a-new-export"></a>Postavljanje novog izvoza

Da biste postavili ili uredili izvoz, potrebne su vam odgovarajuće veze. Veze ovise o vašoj [korisničkoj ulozi](permissions.md):
- **Administratori** imaju pristup svim vezama. Također mogu stvoriti nove veze prilikom postavljanja izvoza.
- **Suradnici** mogu imati pristup određenim vezama. Ovise o administratorima za konfiguriranje i dijeljenje veza. Popis izvoza pokazuje suradnicima mogu li uređivati ili samo pregledavati izvoz u stupcu **Vaše dozvole**. Dodatne informacije potražite u odjeljku [Omogućivanje suradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Gledatelji** mogu samo pregledati postojeći izvoz – ne i stvarati.

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz** za stvaranje novog izvoza.

1. U oknu Postavljanje izvoza **odaberite** vezu koju [želite](connections.md) koristiti.

1. Navedite potrebne pojedinosti i odaberite **Spremi** da biste stvorili izvoz. Za tražene detalje pregledajte dokumentaciju Customer Insights za određeni izvoz.

## <a name="manage-existing-exports"></a>Upravljanje postojećim izvozom

Idite na **Izvoz** > **podataka** da biste vidjeli izvoz, njihov naziv veze, vrstu veze i status. Sve korisničke uloge mogu pregledavati konfigurirane izvoze. Popis izvoza možete sortirati po bilo kojem stupcu ili pomoću okvira za pretraživanje pronaći izvoz kojim želite upravljati.

Odaberite izvoz da biste vidjeli dostupne akcije.

:::image type="content" source="media/exports_showmore.png" alt-text="Stranica izvoza.":::

- **Prikažite** ili **uredite** izvoz. Korisnicie bez dozvole za uređivanje odabiru **Prikaži** umjesto **Uredi** kako bi vidjeli pojedinosti o izvozu.
- **Pokrenite** izvoz da biste izvezli najnovije podatke.
- **Stvorite duplikat** izvoza.
- **[Zakažite](#schedule-and-run-exports)** izvoz.
- **Odvojite vezu** da biste uklonili vezu za ovaj izvoz. Detach ne uklanja vezu, ali deaktivira izvoz. Stupac Korištena **veza** prikazuje nema veze.
- **Uklonite** izvoz.

## <a name="schedule-and-run-exports"></a>Zakazivanje i pokretanje izvoza

Svaki izvoz koji konfigurirate ima raspored osvježavanja. Tijekom osvježavanja sustav traži nove ili ažurirane podatke koje će uključiti u izvoz. Prema zadanim postavkama izvozi se izvode kao dio svakog [zakazanog osvježavanja sustava](schedule-refresh.md). Raspored osvježavanja možete prilagoditi ili ga isključiti za ručno pokretanje izvoza.

Rasporedi izvoza ovise o stanju vašeg okruženja. Ako su u tijeku ažuriranja na [ovisnostima](system.md#refresh-processes) kada bi trebao započeti planirani izvoz, sustav će prvo dovršiti ažuriranja, a zatim pokrenuti izvoz. Stupac **Osvježeno** prikazuje kada je izvoz posljednji put osvježen.

### <a name="schedule-exports"></a>Zakazivanje izvoza

Definirajte prilagođene rasporede osvježavanja za pojedinačni izvoz ili nekoliko izvoza odjednom. Trenutno definirani raspored naveden je u stupcu **Raspored** na popisu izvoza. Dozvola za promjenu rasporeda jednaka [je uređivanju i definiranju izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite izvoz koji želite zakazati.

1. Odaberite **Raspored**.

1. U oknu **Zakazivanje izvoza** postavite **Pokretanje rasporeda** na **Uključeno** za automatsko pokretanje izvoza. Postavite na **Isključeno** da ga osvježite ručno.

1. Za automatski osvježene izvoze odaberite vrijednost **Ponavljanje** i za nju navedite pojedinosti. Definirano vrijeme odnosi se na sve slučajeve ponavljanja. To je vrijeme kada bi se izvoz trebao početi osvježavati.

1. Odaberite **Spremi**.

Prilikom uređivanja rasporeda za nekoliko izvoza odaberite u odjeljku **Zadrži ili nadjačajte rasporede**:

- **Zadržite pojedinačne rasporede**: zadržite prethodno definiran raspored za odabrani izvoz i samo ih onemogućite ili omogućite.
- **Definiraj novi raspored za sve odabrane izvoze**: Zamijenite postojeće rasporede odabranih izvoza.

### <a name="run-exports-on-demand"></a>Pokretanje izvoza na zahtjev

Da biste izvezli podatke bez čekanja na zakazano osvježavanje, idite na **Podaci** > **Izvozi**.

- Da biste pokrenuli sve izvoze, odaberite **Pokreni sve** na naredbenoj traci. Izvode se samo izvozi koji imaju aktivan raspored. Da biste pokrenuli izvoz koji nije aktivan, pokrenite jedan izvoz.
- Da biste pokrenuli jedan izvoz, odaberite ga na popisu i odaberite **Pokreni** na naredbenoj traci.

## <a name="troubleshooting"></a>Rješavanje problema

### <a name="segment-not-eligible-for-export"></a>Segment ne ispunjava uvjete za izvoz

**Problem** U okruženju poslovnih računa vaš izvoz ne uspijeva s porukom o pogrešci: "Sljedeći segment ne ispunjava uvjete za ovo izvozno odredište: "{naziv segmenta}". Odaberite samo segmente vrste ContactProfile i pokušajte ponovno."

**Rješenja** okruženja customer insights za poslovne račune ažurirana su kako bi podržala segmente kontakata uz segmente računa. Zbog te promjene izvoz koji treba podatke za kontakt radi samo sa segmentima koji se temelje na kontaktima.

1. [Kreirajte segment na temelju kontakata](segment-builder.md) koji odgovaraju prethodno korištenom segmentu.

1. Nakon pokretanja tog segmenta kontakta uredite odgovarajući izvoz i odaberite novi segment.

1. Odaberite **Spremi** da biste spremili konfiguraciju ili **Spremi i pokrenite** da biste odmah testirali taj izvoz.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
