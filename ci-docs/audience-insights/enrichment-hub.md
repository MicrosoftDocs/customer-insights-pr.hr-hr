---
title: Obogaćivanje objedinjenih profila klijenata
description: Koristite mogućnosti za obogaćivanje podataka o klijentima.
ms.date: 11/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: de27da92118b83dafa0742b6a1e10ee315750c61
ms.sourcegitcommit: 6efcba688d1db1a5d6343c229f292a26c48fc007
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/05/2021
ms.locfileid: "7770108"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obogaćivanje za korisničke profile (pretpregled)

Koristite podatke iz izvora poput Microsofta i drugih partnera kako biste obogatili podatke o klijentima.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica središta za obogaćivanje.":::

U uvidima u ciljnu skupinu idite na **Podaci** > **Obogaćivanje** za rad s mogućnostima obogaćivanja.  

Da biste stvorili ili uredili obogaćivanja, morate imati dozvole Suradnik ili Administrator. Za dodatne informacije pogledajte [Dozvole](permissions.md).

Na kartici **Otkrij** pronaći ćete sve podržane mogućnosti obogaćivanja.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- [Brendovi](enrichment-microsoft.md) koje je omogućio Microsoft
- [Interesi](enrichment-microsoft.md) koje je omogućio Microsoft
- [Poboljšane adrese](enrichment-enhanced-addresses.md) koje je omogućio Microsoft 
- [Demografske podatke](enrichment-experian.md) omogućuje tvrtka Experian
- [Prilagođeni podaci](enrichment-SFTP-custom-import.md) putem Protokola sigurnog prijenosa datoteka (SFTP) 
- [Azure karte](enrichment-azure-maps.md) omogućuje Microsoft

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (B-to-B)](#tab/b2b)

- [Podatke o tvrtki](enrichment-leadspace.md) omogućuje tvrtka Leadspace
- [Poboljšane adrese](enrichment-enhanced-addresses.md) koje je omogućio Microsoft 
- [Poboljšani podaci tvrtke](enrichment-enhanced-company-data.md) koje pruža Microsoft
- [Podatke o lokaciji](enrichment-here.md) pruža tvrtka HERE Technologies 
- [Prilagođeni podaci](enrichment-SFTP-custom-import.md) putem Protokola sigurnog prijenosa datoteka (SFTP) 
- [Azure karte](enrichment-azure-maps.md) omogućuje Microsoft

---

Na kartici **Moja obogaćivanja** možete vidjeti obogaćivanja koja ste konfigurirali i urediti njihova svojstva.

## <a name="manage-existing-enrichments"></a>Upravljanje postojećim obogaćivanjima

Idite na karticu **Moja obogaćivanja** da biste vidjeli sva konfigurirana obogaćivanja. Svako obogaćivanje predstavljeno je kao redak koji uključuje dodatne informacije o obogaćivanju.

Odaberite obogaćivanje da biste vidjeli dostupne mogućnosti. Možete odabrati i elipsu (...) na stavci popisa da biste vidjeli mogućnosti. Ako ste konfigurirali nekoliko obogaćivanja, možete ih brzo pronaći pomoću okvira za pretraživanje.

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

## <a name="see-the-progress-of-the-enrichment-process"></a>Pogledajte napredak procesa obogaćivanja

Možete pronaći pojedinosti o obradi obogaćivanja, uključujući status i potencijalne probleme dok se osvježava ili nakon dovršetka osvježavanja. Razumijte koji su procesi uključeni za osvježavanje obogaćivanja i koliko je vremena potrebno za pokretanje procesa. Status obogaćivanja podržan je za Experian, Leadspace, HERE Technologies, SFTP Import i Azure Maps.

Da biste vidjeli status obogaćivanja

1. Idite na **Podaci** > **Obogaćivanje**. 
1. Na kartici **Moja obogaćivanja** odaberite status obogaćivanja da biste otvorili bočno okno. 
1. U oknu **Pojedinosti o napretku** proširite odjeljak **Obogaćivanja**. 
1. Pod obogaćivanjem za koje želite vidjeti napredak odaberite **Pogledaj pojedinosti**. 
1. U oknu **Pojedinosti o zadatku** odaberite **Pokaži pojedinosti** da biste vidjeli procese koji su uključeni u ažuriranje obogaćivanja i njihov status. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
