---
title: Pregled obogaćivanja podataka (pretpregleda)
description: Da biste obogatili korisničke podatke, koristite mogućnosti microsofta i drugih servisa drugih proizvođača.
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
ms.openlocfilehash: 0c2a900190b4ab6e93098d05a2fd66bcd2b847fd
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245870"
---
# <a name="data-enrichment-preview-overview"></a>Pregled obogaćivanja podataka (pretpregleda)

Koristite podatke iz izvora poput Microsofta i drugih partnera kako biste obogatili podatke o klijentima. Obogaćivanja treće strane konfigurirana su pomoću [veza](connections.md) koje administrator postavlja s vjerodajnicama i daje pristanak za prijenos podataka. Veze mogu upotrebljavati administratori i suradnici za konfiguriranje obogaćivanja.  

## <a name="multiple-enrichments-of-the-same-type"></a>Višestruka obogaćivanja iste vrste

Entitet koji treba obogatiti naveden je tijekom konfiguracije obogaćivanja, što vam omogućuje obogaćivanje samo podskupina vaših profila. Na primjer, obogatite podatke samo za određeni segment. Možete konfigurirati nekoliko obogaćivanja iste vrste i ponovno koristiti istu vezu. Neka obogaćivanja imat će ograničenja u broju obogaćivanja iste vrste koja se mogu stvoriti. Ograničenja i trenutna upotreba mogu se vidjeti na svakoj pločici **na kartici Otkrivanje** na **stranici Obogaćivanje**.

## <a name="enrich-data-sources-before-unification"></a>Obogatite izvore podataka prije ujedinjenja

Podatke o kupcima možete obogatiti prije ujedinjenja podataka kako biste povećali kvalitetu podudaranja podataka. Za više informacija pogledajte [izvor podataka obogaćivanje](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Stvaranje obogaćivanja

Za stvaranje ili uređivanje obogaćenja morate imati suradnik ili administratorske [dozvole](permissions.md).

Idite na **Podaci** > **Obogaćivanje**. Kartica **Discover** prikazuje sve podržane mogućnosti obogaćivanja.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica središta za obogaćivanje.":::

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

## <a name="manage-existing-enrichments"></a>Upravljanje postojećim obogaćivanjima

Idite na **Podaci** > **Obogaćivanje**. **Na kartici Moja obogaćivanja** pogledajte konfigurirana obogaćivanja, njihov status, broj obogaćenih kupaca i posljednji put kada su podaci osvježeni. Popis obogaćenja možete sortirati po bilo kojem stupcu ili pomoću okvira za pretraživanje pronaći obogaćivanje kojim želite upravljati.

Odaberite obogaćivanje da biste vidjeli dostupne akcije.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Mogućnosti upravljanja obogaćivanjima na popisu obogaćivanja.":::

- **Prikaži** pojedinosti o obogaćivanju brojem obogaćenih profila klijenata.
- **Uredi** konfiguraciju obogaćivanja.
- [**Pokrenite**](#run-or-refresh-enrichments) obogaćivanje da biste ažurirali profile kupaca najnovijim podacima. Pokrenite više obogaćivanja odjednom tako da ih odaberete na popisu.
- **Aktiviranje** ili **deaktiviranje** obogaćivanja. Neaktivna obogaćivanja neće se osvježiti tijekom zakazanog [osvježavanja](schedule-refresh.md).
- Odaberite **Izbriši** obogaćivanje.

Također možete stvoriti [segmente](segments.md) ili [mjere](measures.md) iz obogaćivanja.

## <a name="run-or-refresh-enrichments"></a>Pokretanje ili osvježavanje obogaćenja

Nakon pokretanja, obogaćivanja se mogu osvježiti prema automatskom rasporedu ili ručno osvježiti na zahtjev.

1. Da biste ručno osvježili jednu ili više obogaćenja, odaberite ih i odaberite **Pokreni**. Da biste [zakazali automatsko osvježavanje](schedule-refresh.md), idite na **Raspored** > **administratorskih** > **sustava**. Vrijeme obrade ovisi o veličini vaših podataka o klijentima.

1. Po želji pogledajte [napredak procesa](#see-the-progress-of-the-enrichment-process) obogaćivanja.

1. Nakon završetka procesa obogaćivanja, idite na **My enrichments** kako biste pregledali novoobogaćene podatke o profilima kupaca, vrijeme posljednjeg ažuriranja i broj obogaćenih profila.

1. Odaberite obogaćivanje da biste vidjeli [rezultate](#view-enrichment-results) obogaćivanja.

### <a name="see-the-progress-of-the-enrichment-process"></a>Pogledajte napredak procesa obogaćivanja

Možete pronaći pojedinosti o obradi obogaćivanja, uključujući status i potencijalne probleme dok se osvježava ili nakon dovršetka osvježavanja. Razumijte koji su procesi uključeni za osvježavanje obogaćivanja i koliko je vremena potrebno za pokretanje procesa. Status obogaćivanja podržan je za Experian, Leadspace, HERE Technologies, SFTP Import i Azure karte.

1. Idite na **Podaci** > **Obogaćivanje**.
1. Na kartici **Moja obogaćivanja** odaberite status obogaćivanja da biste otvorili bočno okno.
1. U oknu **Pojedinosti o napretku** proširite odjeljak **Obogaćivanja**.
1. Pod obogaćivanjem za koje želite vidjeti napredak odaberite **Pogledaj pojedinosti**.
1. U oknu **Pojedinosti o zadatku** odaberite **Pokaži pojedinosti** da biste vidjeli procese koji su uključeni u ažuriranje obogaćivanja i njihov status.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Prikaz rezultata obogaćivanja

Nakon završenog ciklusa obogaćivanja, pregledajte rezultate obogaćivanja.

1. Idite na **Podaci** > **Obogaćivanje**.
1. Na kartici **Moje bogaćenje** odaberite obogaćivanje koje želite pregledati.

Sva obogaćivanja prikazuju osnovne informacije poput broja obogaćenih profila i broja obogaćenih profila tijekom vremena. Pločica **Pretpregled** obogaćenih kupaca prikazuje uzorak generiranog entiteta za obogaćivanje. Da biste vidjeli detaljan prikaz, odaberite **Vidi više**, a zatim karticu **Podaci**.

:::image type="content" source="media/enrichments-results.png" alt-text="Stranica s rezultatima obogaćivanja.":::

Ako je **dostupan, broj kupaca obogaćenih poljem** pruža dubinsku analizu pokrivenosti svakog obogaćenog polja.

Neka obogaćenja također pokazuju informacije specifične za vrstu obogaćivanja. Dodatne informacije potražite u povezanoj dokumentaciji.

[!INCLUDE [footer-include](includes/footer-banner.md)]
