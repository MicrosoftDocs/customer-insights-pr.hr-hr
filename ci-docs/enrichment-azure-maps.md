---
title: Obogatite korisničke profile podaci o lokaciji s servisa Azure Maps (pretpregled)
description: Općenite informacije o obogaćivanju prve strane Azure kartama.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: dfadc08f67beac3fded1a97e557ee9e1880664e0
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052598"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Obogatite korisničke profile podaci o lokaciji s servisa Azure Maps (pretpregled)

Azure Maps pruža podatke i usluge usmjerene na lokaciju za pružanje iskustava temeljenih na geoprostornim podacima s ugrađenom inteligencijom lokacije. Usluge obogaćivanja podataka usluge Azure karte poboljšavaju preciznost informacija o lokaciji vaših klijenata. Donose mogućnosti poput normalizacije adrese i izdvajanja zemljopisne širine i dužine u Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Preduvjeti

- Aktivna pretplata na Azure Maps. Da biste dobili pretplatu, [prijavite se ili ostvarite besplatnu probnu verziju](https://azure.microsoft.com/services/azure-maps/).

- Vezu servisa [Azure](connections.md) Maps [konfigurira](#configure-the-connection-for-azure-maps) administrator.

## <a name="configure-the-connection-for-azure-maps"></a>Konfiguriranje veze za Azure karte

Morate biti [administrator](permissions.md#admin) u customer insights i imati aktivan API ključ servisa Azure Maps.

1. Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćivanja ili idite na **Administrator** > **Veze** i odaberite **Postavljanje** na pločici Azure karte.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Stranica za konfiguraciju veze za Azure karte.":::

1. Unesite naziv veze i valjani API ključ servisa Azure Maps.

1. Pregledajte i dajte svoj pristanak za [Privatnost podataka i usklađenost](#data-privacy-and-compliance) odabirom opcije **Slažem se**.

1. Odaberite **Provjeri** da biste provjerili valjanost konfiguracije, a zatim **Spremi**.

### <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Azure karte, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke poput osobnih podataka. Microsoft će takve podatke prenijeti prema vašim uputima, ali vi ste odgovorni za to da Azure Karte ispunjavaju sve obveze zaštite privatnosti ili sigurnosti koje možda imate. Za više informacija idite na [Microsoftovu izjavu o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

1. Na **pločici** Karte odaberite Obogati moje podatke **na pločici** Lokacija Microsoft Azure.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Pločica Azure karte.":::

1. Pregledajte pregled, a zatim odaberite **Dalje**.

1. Odaberite vezu. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Odaberite **Dalje**.

1. **Odaberite customer skup podataka** i odaberite profil ili segment koji želite obogatiti podacima tvrtke Microsoft. Subjekt *Kupac* obogaćuje sve vaše profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Definirajte koju vrstu polja iz jedinstvenih profila želite koristiti za podudaranje: primarnu i/ili sekundarnu adresu. Možete odrediti mapiranje polja za obje adrese i obogatiti profile za obje adrese zasebno. Na primjer, za kućnu adresu i poslovnu adresu. Odaberite **Dalje**.

1. Mapirajte polja na podaci o lokaciji s servisa Azure Maps. Polja **Ulica 1** i **Poštanski broj** su obavezna za odabranu primarnu i/ili sekundarnu adresu. Za veću točnost podudaranja dodajte još polja.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Maps attribute mapping.":::

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja.

1. Pregledajte **dodatne postavke** koje nude maksimalnu fleksibilnost za rukovanje naprednim slučajevima upotrebe. Međutim, sljedeće zadane vrijednosti obično nije potrebno mijenjati.

   - **Vrsta adresa**: najbolje adrese podudaraju se s povratima čak i ako su nepotpune. Da biste dobili samo potpune adrese&mdash;na primjer, adrese koje uključuju kućni broj&mdash;poništite sve potvrdne okvire osim **Adrese točaka**.
   - **Jezik**: adrese se vraćaju na jeziku na temelju područja adrese. Da biste primijenili standardizirani jezik adrese, odaberite jezik s padajućeg izbornika. Na primjer, odabirom **engleskog** vraća se **Kopenhagen, Danska** umjesto **København, Danmark**.
   - **Maksimalan broj rezultata**: broj rezultata po adresi.

1. Odaberite **Dalje**.

1. Navedite naziv **za obogaćivanje i naziv izlaznog entiteta** **.**

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

1. Odaberite **Pokreni** da biste pokrenuli postupak obogaćivanja ili zatvorili da biste se vratili na **stranicu Obogaćivanje**.

## <a name="view-enrichment-results"></a>Prikaz rezultata obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Broj **kupaca obogaćenih poljem** pruža dubinsku analizu pokrivenosti svakog obogaćenog polja.

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
