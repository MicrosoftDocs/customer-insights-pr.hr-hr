---
title: Obogaćivanje profila klijenata podacima o lokaciji iz Azure karata
description: Općenite informacije o obogaćivanju prve strane Azure kartama.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 6a1c3791076a7dda4531664ca88632f7f1b914e3
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642199"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Obogaćivanje profila klijenata pomoću Azure karata (pretpregled)

Azure karte pružaju podatke i usluge usmjerene na lokaciju za pružanje iskustava koja se temelje na geoprostornim podacima s ugrađenom inteligencijom lokacije. Usluge obogaćivanja podataka usluge Azure karte poboljšavaju preciznost informacija o lokaciji vaših klijenata. Donose mogućnosti poput normalizacije adrese i izdvajanja zemljopisne širine i dužine u Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Preduvjeti

Da biste konfigurirali obogaćivanje podataka Azure karata, moraju biti ispunjeni sljedeći preduvjeti:

- Imate aktivnu pretplatu na Azure karte. Da biste dobili pretplatu, možete se [prijaviti ili nabaviti besplatno probno razdoblje](https://azure.microsoft.com/services/azure-maps/).

- [Veza](connections.md) za Azure karte je dostupna *ili* imate [administratorske](permissions.md#admin) dozvole i aktivni ključ za API za Azure karte.

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje**. 

1. Na pločici **Lokacija** odaberite **Obogati moje podatke**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Pločica Azure karte.":::

1. Odaberite [vezu](connections.md) s padajućeg popisa. Obratite se administratoru ako nije dostupna veza za Azure karte. Ako ste administrator, možete [konfigurirati vezu za Azure karte](#configure-the-connection-for-azure-maps). 

1. Odaberi **Sljedeće** za potvrdu odabira.

1. Odaberite **Skup podataka o klijentima** koji želite obogatiti podacima o lokaciji iz Azure karata. Možete odabrati entitet **Klijent** za obogaćivanje svih vaših objedinjenih profila klijenata ili odaberite entitet segmenta za obogaćivanje samo profila klijenata koji se nalaze u tom segmentu.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Snimka zaslona prilikom odabira skupa podataka o klijentu.":::

1. Odaberite želite li mapirati polja na primarnu i/ili sekundarnu adresu. Možete navesti mapiranje polja za obje adrese i zasebno obogatiti profile za obje adrese&mdash;na primjer, za kućnu adresu i poslovnu adresu. Odaberite **Dalje**.

1. Definirajte koja polja iz vaših objedinjenih profila treba koristiti za traženje podudarnih podataka o lokaciji iz Azure karata. Polja **Ulica 1** i **Poštanski broj** obavezna su za odabranu primarnu ili sekundarnu adresu. Za veću točnost podudaranja možete dodati još polja.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Stranica za konfiguraciju obogaćivanja Azure karata.":::

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja.

1. Procijenite želite li izmijeniti **Napredne postavke**. One su pružene kako bi dale maksimalnu fleksibilnost u rješavanju naprednih slučajeva korištenja, ali zadane će vrijednosti u većini slučajeva biti primjerene:
   - **Vrsta adresa**: Zadano je ponašanje da će obogaćivanje vratiti najbolje podudaranje adrese čak i ako je nepotpuno. Da biste dobili samo potpune adrese&mdash;na primjer, adrese koje uključuju kućni broj&mdash;poništite sve potvrdne okvire osim **Adrese točaka**. 
   - **Jezik**: Prema zadanim postavkama adrese se vraćaju na jeziku regije za koju je utvrđeno da joj adresa pripada. Da biste primijenili standardizirani jezik adrese, odaberite jezik s padajućeg izbornika. Na primjer, odabir **Hrvatski** vratit će **Kopenhagen, Danska** umjesto **København, Danmark**.

1. Navedite naziv za obogaćivanje.

1. Pregledajte svoje odabire, a zatim odaberite **Spremi obogaćivanje**.

## <a name="configure-the-connection-for-azure-maps"></a>Konfiguriranje veze za Azure karte

Da biste konfigurirali veze, morate biti administrator u korisničkom uvidu. Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćivanja ili idite na **Administrator** > **Veze** i odaberite **Postavljanje** na pločici Azure karte.

1. U okviru **Zaslonski naziv** unesite naziv veze.

1. Navedite valjani ključ za API za Azure karte.

1. Pregledajte i dajte svoj pristanak za **Zaštita privatnosti podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**

1. Odaberi **Potvrdi** za provjeru valjanosti konfiguracije.

1. Nakon dovršetka provjere valjanosti odaberite **Spremi**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Stranica za konfiguraciju veze za Azure karte.":::

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake. Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab). Vrijeme obrade ovisit će o veličini vaših podataka o klijentu i vremenima odgovora API-ja.

Nakon dovršetka procesa obogaćivanja možete pregledati podatke o novoobogaćenim profilima klijenata pod **Moja obogaćivanja**. Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Azure karte, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke poput osobnih podataka. Microsoft će prenijeti takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Azure karte ispunjavaju sve obveze zaštite privatnosti ili sigurnosti koje imate. Za više informacija idite na [Microsoftovu izjavu o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.

[!INCLUDE [footer-include](includes/footer-banner.md)]