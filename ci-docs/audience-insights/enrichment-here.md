---
title: Obogaćivanje pomoću obogaćivanja treće strane tvrke HERE Technologies
description: Opće informacije o obogaćivanju treće strane tvrtke HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597732"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Obogaćivanje profila klijenata pomoću usluge HERE Technologies (pretpregled)

HERE Technologies je tvrtka za lokacijsku platformu koja pruža podatke i usluge usmjerene na lokaciju. Pomoću usluga obogaćivanja podataka tvrtke HERE Technologies možete stvoriti preciznije razumijevanje lokacije svojih klijenata uz normalizaciju adrese, izvlačenje zemljopisne širine i dužine i još mnogo toga.

## <a name="prerequisites"></a>Preduvjeti

Da biste konfigurirali obogaćivanje usluge HERE Technologies, moraju biti ispunjeni sljedeći preduvjeti:

- Imate aktivnu pretplatu za HERE Technologies. Da biste dobili pretplatu, možete se [prijaviti ovdje](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ili izravno [kontaktirati tvrtku HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Saznajte više o obogaćivanju lokacije tvrtke HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Imate API ključ za HERE Technologies.

- Imate dozvole [administratora](permissions.md#administrator).

## <a name="configuration"></a>Konfiguracija

1. Idite na **Podaci** > **Obogaćivanje**.

1. Odaberite **Obogaćivanje mojih podataka** na pločici za HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![Pločica za HERE Technologies](media/HERE-tile.png "Pločica za HERE Technologies")

1. Unesite aktivni **API ključ za HERE Technologies**. Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**. 

1. Potvrdite oba unosa odabirom mogućnosti **Povezivanje s uslugom HERE**.

1.  Odaberite **Dodaj podatke** i odaberite **Skup korisničkih podataka** koji želite obogatiti podacima o mjestu iz sustava HERE Technologies. Možete odabrati entitet **Klijent** za obogaćivanje svih vaših korisničkih profila ili odaberite segmentni entitet za obogaćivanje samo korisničkih profila sadržanih u tom segmentu.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Snimka zaslona prilikom odabira skupa podataka o klijentu.":::

1. Odaberite želite li mapirati polja na primarnu i/ili sekundarnu adresu. Možete odrediti mapiranje polja za obje adrese (na primjer, kućnu i poslovnu adresu) i obogatiti profile za obje adrese zasebno. Odaberite **Dalje**.

1. Definirajte koja se polja iz vaših objedinjenih profila trebaju koristiti za traženje odgovarajućih podataka o lokaciji iz usluge HERE Technologies. Polja **Ulica 1** i **Poštanski broj** su obavezna za odabranu primarnu i/ili sekundarnu adresu. Za veću točnost podudaranja može se dodati više polja.

   > [!div class="mx-imgBorder"]
   > ![Stranica za konfiguraciju obogaćivanja usluge HERE Technologies](media/enrichment-HERE-configuration.png "Stranica za konfiguraciju obogaćivanja usluge HERE Technologies")

1. Odaberite **Primijeni** za dovršetak mapiranja polja.

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake. Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab). Vrijeme obrade ovisit će o veličini vaših podataka o klijentu i vremenu odziva API-ja u usluzi HERE Technologies.

Nakon završetka postupka obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod stavkom **Moja obogaćivanja**. Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.

## <a name="next-steps"></a>Sljedeći koraci

Nadogradite na svoje obogaćene podatke o klijentu. Stvorite [segmente](segments.md), [mjere](measures.md), pa i [izvezite podatke](export-destinations.md) kako biste svojim klijentima pružili personalizirano iskustvo.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u HERE Technologies, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da HERE Technologies ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE[footer-include](../includes/footer-banner.md)]