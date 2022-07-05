---
title: Obogatite profile kupaca here tehnologijama (pregled)
description: Opće informacije o obogaćivanju treće strane tvrtke HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d88085b6be156dd1c895e9e5b38cc9d77acbdb95
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052042"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Obogatite profile kupaca here tehnologijama (pregled)

HERE Technologies je tvrtka za lokacijsku platformu koja pruža podatke i usluge usmjerene na lokaciju. Usluge obogaćivanja podataka HERE Technologies poboljšavaju preciznost informacija o lokaciji vaših kupaca. Pruža normalizaciju adrese, ekstrakciju zemljopisne širine i dužine i još mnogo toga.

## <a name="prerequisites"></a>Preduvjeti

- Aktivna pretplata na HERE Technologies. Da biste dobili pretplatu, [prijavite se ovdje](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ili [se izravno obratite tvrtki HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Saznajte više o obogaćivanju lokacije tvrtke HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Vezu [HERE](connections.md)[konfigurira](#configure-the-connection-for-here-technologies) administrator.

## <a name="configure-the-connection-for-here-technologies"></a>Konfiguriranje veze za HERE Technologies

Morate biti [administrator](permissions.md#admin) u customer insights i imati aktivan ključ API-ja HERE Technologies.

1. Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćivanja ili Idite na **Veze s administratorima** > **·**, a zatim odaberite **Postavi** na pločici HERE Technologies.

1. Unesite naziv veze i valjani API ključ HERE Technologies.

1. Pregledajte i dajte svoj pristanak za [Privatnost podataka i usklađenost](#data-privacy-and-compliance) odabirom opcije **Slažem se**.

1. Odaberite **Provjeri** da biste provjerili valjanost konfiguracije, a zatim **Spremi**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Stranica za konfiguraciju veze za HERE technologies.":::

### <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u HERE Technologies, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da HERE Technologies ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

1. Odaberite **Obogati moje podatke** na pločici **Lokacija** s pločice HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Pločica za HERE Technologies.":::

1. Pregledajte pregled, a zatim odaberite **Dalje**.

1. Odaberite vezu. Ako jedan nije dostupan, obratite se administratoru.

1. Odaberite **Dalje**.

1. **Odaberite customer skup podataka** i odaberite profil ili segment koji želite obogatiti podacima tvrtke HERE Technologies. Subjekt *Kupac* obogaćuje sve vaše profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Definirajte koju vrstu polja iz jedinstvenih profila želite koristiti za podudaranje: primarnu i/ili sekundarnu adresu. Možete odrediti mapiranje polja za obje adrese i obogatiti profile za obje adrese zasebno. Na primjer, za kućnu adresu i poslovnu adresu. Odaberite **Dalje**.

1. Mapirajte svoja polja na podatke iz here technologies. Polja **Ulica 1** i **Poštanski broj** su obavezna za odabranu primarnu i/ili sekundarnu adresu. Za veću točnost podudaranja dodajte još polja.

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja.

1. Navedite naziv **za obogaćivanje i naziv izlaznog entiteta** **.**

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

1. Odaberite **Pokreni** da biste pokrenuli postupak obogaćivanja ili zatvorili da biste se vratili na **stranicu Obogaćivanje**.

## <a name="view-enrichment-results"></a>Prikaz rezultata obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Broj **kupaca obogaćenih poljem** pruža dubinsku analizu pokrivenosti svakog obogaćenog polja.

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
