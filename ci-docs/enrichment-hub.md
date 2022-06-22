---
title: Obogaćivanje objedinjenih profila klijenata
description: Koristite mogućnosti za obogaćivanje podataka o klijentima.
ms.date: 06/10/2022
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
ms.openlocfilehash: 3bbe8b829a6698da55d84709dbab6c36aa76792a
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954032"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obogaćivanje za korisničke profile (pretpregled)

Koristite podatke iz izvora poput Microsofta i drugih partnera kako biste obogatili podatke o klijentima.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica središta za obogaćivanje.":::

Idite na **Data** > **Enrichment** da biste radili s mogućnostima obogaćivanja.  

Da biste stvorili ili uredili obogaćivanja, morate imati dozvole Suradnik ili Administrator. Za dodatne informacije pogledajte [Dozvole](permissions.md).

Na kartici **Otkrij** pronaći ćete sve podržane mogućnosti obogaćivanja.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- [AbiliTec identitet](enrichment-liveramp.md) pruža LiveRamp AbiliTec
- [Brendovi](enrichment-microsoft.md) koje je omogućio Microsoft
- [Demografske podatke](enrichment-experian.md) pruža Experian
- [Poboljšane adrese](enrichment-enhanced-addresses.md) koje je omogućio Microsoft
- [Interesi](enrichment-microsoft.md) koje je omogućio Microsoft
- [podaci](enrichment-azure-maps.md) o lokaciji koje Microsoft Azure pružaju Karte
- [Podatke o lokaciji](enrichment-here.md) pruža tvrtka HERE Technologies
- [SFTP prilagođeni podaci](enrichment-SFTP-custom-import.md) putem Protokola za siguran prijenos datoteka (SFTP)

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

- [Podaci o](enrichment-office.md) angažmanu računa koje je dostavio Microsoft
- [Podaci o](enrichment-dnb.md) tvrtki koje je dostavio Dun & Bradstreet
- [Podatke o tvrtki](enrichment-leadspace.md) omogućuje tvrtka Leadspace
- [Poboljšane adrese](enrichment-enhanced-addresses.md) koje je omogućio Microsoft
- [Poboljšani podaci tvrtke](enrichment-enhanced-company-data.md) koje je dostavio Microsoft
- [podaci](enrichment-azure-maps.md) o lokaciji koje Microsoft Azure pružaju Karte
- [Podatke o lokaciji](enrichment-here.md) pruža tvrtka HERE Technologies
- [SFTP prilagođeni podaci](enrichment-SFTP-custom-import.md) putem Protokola za siguran prijenos datoteka (SFTP)

---

Na kartici **Moja obogaćivanja** možete vidjeti obogaćivanja koja ste konfigurirali i urediti njihova svojstva. Također možete stvoriti [segmente](segments.md) ili [mjere](measures.md) iz obogaćivanja.

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

Entitet koji treba obogatiti naveden je tijekom konfiguracije obogaćivanja, što vam omogućuje obogaćivanje samo podskupina vaših profila. Na primjer, obogatite podatke samo za određeni segment. Možete konfigurirati nekoliko obogaćivanja iste vrste i ponovno koristiti istu vezu. Neka obogaćivanja imat će ograničenja u broju obogaćivanja iste vrste koja se mogu stvoriti. Ograničenja i trenutna upotreba mogu se vidjeti na svakoj pločici **na kartici Otkrivanje** na **stranici Obogaćivanje**.

## <a name="enrich-data-sources-before-unification"></a>Obogatite izvore podataka prije ujedinjenja

Podatke o kupcima možete obogatiti prije ujedinjenja podataka kako biste povećali kvalitetu podudaranja podataka. Za više informacija pogledajte [izvor podataka obogaćivanje](data-sources-enrichment.md).

## <a name="run-or-refresh-enrichments"></a>Pokretanje ili osvježavanje obogaćenja

1. Da biste pokrenuli postupak obogaćivanja, odaberite **Pokreni**. Ili neka sustav automatski pokrene obogaćivanje kao dio zakazanog [osvježavanja](system.md#schedule-tab). Vrijeme obrade ovisi o veličini vaših podataka o klijentima.

1. Po želji pogledajte [napredak procesa](#see-the-progress-of-the-enrichment-process) obogaćivanja.

1. Nakon završetka procesa obogaćivanja, idite na **My enrichments** kako biste pregledali novoobogaćene podatke o profilima kupaca, vrijeme posljednjeg ažuriranja i broj obogaćenih profila.

1. Odaberite obogaćivanje da biste vidjeli [rezultate](#enrichment-results) obogaćivanja.

### <a name="see-the-progress-of-the-enrichment-process"></a>Pogledajte napredak procesa obogaćivanja

Možete pronaći pojedinosti o obradi obogaćivanja, uključujući status i potencijalne probleme dok se osvježava ili nakon dovršetka osvježavanja. Razumijte koji su procesi uključeni za osvježavanje obogaćivanja i koliko je vremena potrebno za pokretanje procesa. Status obogaćivanja podržan je za Experian, Leadspace, HERE Technologies, SFTP Import i Azure karte.

1. Idite na **Podaci** > **Obogaćivanje**.
1. Na kartici **Moja obogaćivanja** odaberite status obogaćivanja da biste otvorili bočno okno.
1. U oknu **Pojedinosti o napretku** proširite odjeljak **Obogaćivanja**.
1. Pod obogaćivanjem za koje želite vidjeti napredak odaberite **Pogledaj pojedinosti**.
1. U oknu **Pojedinosti o zadatku** odaberite **Pokaži pojedinosti** da biste vidjeli procese koji su uključeni u ažuriranje obogaćivanja i njihov status.

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon završenog ciklusa obogaćivanja, pregledajte rezultate obogaćivanja.

1. Idite na **Podaci** > **Obogaćivanje**.
1. Na kartici **Moja obogaćivanja** odaberite obogaćivanje o kojem želite informacije.

Sva obogaćivanja prikazuju osnovne informacije poput broja obogaćenih profila i broja obogaćenih profila tijekom vremena. Pločica **Pretpregled** obogaćenih kupaca prikazuje uzorak generiranog entiteta za obogaćivanje. Da biste vidjeli detaljan prikaz, odaberite **Vidi više**, a zatim karticu **Podaci**.

:::image type="content" source="media/enrichments-results.png" alt-text="Stranica s rezultatima obogaćivanja.":::

Ako je **dostupan, broj kupaca obogaćenih poljem** pruža dubinsku analizu pokrivenosti svakog obogaćenog polja.

Neka obogaćenja također pokazuju informacije specifične za vrstu obogaćivanja. Dodatne informacije potražite u povezanoj dokumentaciji.

[!INCLUDE [footer-include](includes/footer-banner.md)]
