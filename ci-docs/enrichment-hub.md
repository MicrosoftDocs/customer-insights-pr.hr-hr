---
title: Obogaćivanje objedinjenih profila klijenata
description: Koristite mogućnosti za obogaćivanje podataka o klijentima.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: abc1b6af80e8854ee3bc930453634ef67376c4af
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800596"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obogaćivanje za korisničke profile (pretpregled)

Koristite podatke iz izvora poput Microsofta i drugih partnera kako biste obogatili podatke o klijentima.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica središta za obogaćivanje.":::

Idite na **Data** > **Enrichment** da biste radili s mogućnostima obogaćivanja.  

Da biste stvorili ili uredili obogaćivanja, morate imati dozvole Suradnik ili Administrator. Za dodatne informacije pogledajte [Dozvole](permissions.md).

Na kartici **Otkrij** pronaći ćete sve podržane mogućnosti obogaćivanja.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- [Brendovi](enrichment-microsoft.md) koje je omogućio Microsoft
- [Interesi](enrichment-microsoft.md) koje je omogućio Microsoft
- [Poboljšane adrese](enrichment-enhanced-addresses.md) koje je omogućio Microsoft 
- [Demografske podatke](enrichment-experian.md) pruža Experian
- [Prilagođeni podaci](enrichment-SFTP-custom-import.md) putem Protokola sigurnog prijenosa datoteka (SFTP) 
- [Azure karte](enrichment-azure-maps.md) omogućuje Microsoft
- [Podatke o lokaciji](enrichment-here.md) pruža tvrtka HERE Technologies 
- [Identitet](enrichment-liveramp.md) pruža LiveRamp AbiliTec

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

- [Podatke o tvrtki](enrichment-leadspace.md) omogućuje tvrtka Leadspace
- [Poboljšane adrese](enrichment-enhanced-addresses.md) koje je omogućio Microsoft 
- [Poboljšani podaci tvrtke](enrichment-enhanced-company-data.md) koje je dostavio Microsoft
- [Podatke o lokaciji](enrichment-here.md) pruža tvrtka HERE Technologies 
- [Prilagođeni podaci](enrichment-SFTP-custom-import.md) putem Protokola sigurnog prijenosa datoteka (SFTP) 
- [Azure karte](enrichment-azure-maps.md) omogućuje Microsoft
- [Podaci o](enrichment-dnb.md) tvrtki koje je dostavio Dun & Bradstreet
- [Podaci o](enrichment-office.md) angažmanu računa koje je dostavio Microsoft

---

Na kartici **Moja obogaćivanja** možete vidjeti obogaćivanja koja ste konfigurirali i urediti njihova svojstva.

## <a name="manage-existing-enrichments"></a>Upravljanje postojećim obogaćivanjima

Idite na karticu **Moja obogaćivanja** da biste vidjeli sva konfigurirana obogaćivanja. Svako obogaćivanje predstavljeno je kao redak koji uključuje dodatne informacije o obogaćivanju.

Odaberite obogaćivanje da biste vidjeli dostupne mogućnosti. Također možete odabrati okomitu trotočje (&vellip;) na stavci popisa da biste vidjeli mogućnosti. Ako ste konfigurirali nekoliko obogaćivanja, možete ih brzo pronaći pomoću okvira za pretraživanje.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Mogućnosti upravljanja obogaćivanjima na popisu obogaćivanja.":::

- **Prikaži** pojedinosti o obogaćivanju brojem obogaćenih profila klijenata.
- **Uredi** konfiguraciju obogaćivanja.
- **Pokreni** obogaćivanje za ažuriranje profila kupaca najnovijim podacima.
- **Deaktiviraj** postojeće obogaćivanje za zaustavljanje automatskog osvježavanja prilikom svakog zakazanog osvježavanja. Podaci iz posljednjeg uspješnog osvježavanja i dalje će biti dostupni. **Aktiviraj** neaktivno obogaćivanje za ponovno pokretanje automatskog osvježavanja sa svakim zakazanim osvježavanjem.
- Odaberite **Izbriši** obogaćivanje.

Pokrenite ili deaktivirajte više obogaćivanja odjednom tako da ih odaberete na popisu. Mogućnosti prikaza i uređivanja nisu dostupne kao skupna radnja. Funkcioniraju samo za jedno obogaćivanje odjednom.

## <a name="enrichments-and-connections"></a>Obogaćivanja i veze

Obogaćivanja treće strane konfigurirana su pomoću [veza](connections.md) koje administrator postavlja s vjerodajnicama i daje pristanak za prijenos podataka. Veze mogu upotrebljavati administratori i suradnici za konfiguriranje obogaćivanja.  

## <a name="multiple-enrichments-of-the-same-type"></a>Višestruka obogaćivanja iste vrste

Entitet koji treba obogatiti naveden je tijekom konfiguracije obogaćivanja, što vam omogućuje obogaćivanje samo podskupina vaših profila. Na primjer, obogatite podatke samo za određeni segment. Možete konfigurirati nekoliko obogaćivanja iste vrste i ponovno koristiti istu vezu. Neka obogaćivanja imat će ograničenja u broju obogaćivanja iste vrste koja se mogu stvoriti. Ograničenja i trenutna upotreba mogu se vidjeti na stranici **Obogaćivanje**.

## <a name="enrich-data-sources-before-unification"></a>Obogatite izvore podataka prije ujedinjenja

Podatke o kupcima možete obogatiti prije ujedinjenja podataka kako biste povećali kvalitetu podudaranja podataka. Za više informacija pogledajte [izvor podataka obogaćivanje](data-sources-enrichment.md).

## <a name="see-the-progress-of-the-enrichment-process"></a>Pogledajte napredak procesa obogaćivanja

Možete pronaći pojedinosti o obradi obogaćivanja, uključujući status i potencijalne probleme dok se osvježava ili nakon dovršetka osvježavanja. Razumijte koji su procesi uključeni za osvježavanje obogaćivanja i koliko je vremena potrebno za pokretanje procesa. Status obogaćivanja podržan je za Experian, Leadspace, HERE Technologies, SFTP Import i Azure karte.

Da biste vidjeli status obogaćivanja

1. Idite na **Podaci** > **Obogaćivanje**. 
1. Na kartici **Moja obogaćivanja** odaberite status obogaćivanja da biste otvorili bočno okno. 
1. U oknu **Pojedinosti o napretku** proširite odjeljak **Obogaćivanja**. 
1. Pod obogaćivanjem za koje želite vidjeti napredak odaberite **Pogledaj pojedinosti**. 
1. U oknu **Pojedinosti o zadatku** odaberite **Pokaži pojedinosti** da biste vidjeli procese koji su uključeni u ažuriranje obogaćivanja i njihov status. 

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon završenog ciklusa obogaćivanja, možete pregledati rezultate obogaćivanja.

1. Idite na **Podaci** > **Obogaćivanje**. 
1. Odaberite obogaćivanje o kojem želite informacije.

Sva obogaćivanja prikazuju osnovne informacije kao što su broj obogaćenih profila, pregled generiranog subjekta za obogaćivanje i broj obogaćenih profila tijekom vremena. Ako je **dostupan, broj kupaca obogaćenih poljem** pruža dubinsku analizu pokrivenosti svakog obogaćenog polja.

:::image type="content" source="media/enrichments-results.png" alt-text="Stranica s rezultatima obogaćivanja.":::

Neka obogaćenja također pokazuju informacije specifične za vrstu obogaćivanja. Više informacija potražite u dokumentaciji za relevantno obogaćivanje.


[!INCLUDE [footer-include](includes/footer-banner.md)]
