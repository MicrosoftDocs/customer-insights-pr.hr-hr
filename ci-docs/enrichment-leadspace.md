---
title: Obogatite profile tvrtke Leadspaceom (pretpregled)
description: Opće informacije o obogaćivanju treće strane tvrtke Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 3f23fe7177f931db3e3179970915d0cd3c736f87
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196201"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Obogatite profile tvrtke Leadspaceom (pretpregled)

Leadspace je tvrtka za znanost o podacima koja nudi B-to-B platformu za podatke o klijentima. Omogućuje okruženjima s objedinjenim profilima klijenata koji se temelje na računima da obogate svoje podatke. Obogatite *Profile klijenata* atributima kao što su veličina tvrtke, lokacija ili industrija. Obogatite *Profile kontakta* atributima poput naslova, osobe ili potvrde e-pošte.

## <a name="prerequisites"></a>Preduvjeti

- Aktivna licenca za Leadspace.
- [Objedinjeni profili](customer-profiles.md) kupaca na temelju računa.
- Leadspace [vezu](connections.md)[konfigurira](#configure-the-connection-for-leadspace) administrator. Obratite se izravno tvrtki [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) za pojedinosti o njihovu proizvodu.

## <a name="configure-the-connection-for-leadspace"></a>Konfiguriranje veze za Leadspace

Morate biti [administrator](permissions.md#admin) u Customer Insights i imati "trajni ključ" (koji se naziva **Leadspace token**).

1. Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćivanja ili Idite na **Veze s administratorima** > **·**, a zatim odaberite **Postavi** na pločici Prostor za potencijalne klijente.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Stranica za konfiguraciju veze za Leadspace.":::

1. Unesite naziv veze i valjani leadspace token.

1. Pregledajte i dajte svoj pristanak za [Privatnost podataka i usklađenost](#data-privacy-and-compliance) odabirom opcije **Slažem se**.

1. Odaberite **Provjeri** da biste provjerili valjanost konfiguracije, a zatim **Spremi**.

### <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Leadspace, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Leadspace ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

1. Odaberite **Obogati moje podatke** o **podacima** tvrtke s pločice Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snimka zaslona pločice Leadspace.":::

1. Pregledajte pregled, a zatim odaberite **Dalje**.

1. Odaberite vezu. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Odaberite **Dalje**.

1. **Odaberite skup podataka** kupca i odaberite profil ili segment koji želite obogatiti podacima tvrtke iz prostora za potencijalne klijente. Subjekt *Kupac* obogaćuje sve vaše profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Snimka zaslona prilikom odabira skupa podataka o klijentu.":::

1. Definirajte koju vrstu polja iz jedinstvenih profila želite koristiti za podudaranje: primarnu i/ili sekundarnu adresu. Možete odrediti mapiranje polja za obje adrese i obogatiti profile za obje adrese zasebno. Na primjer, za kućnu adresu i poslovnu adresu. Odaberite **Dalje**.

1. Preslikajte polja na podatke tvrtke iz prostora za potencijalne klijente. Polje **Naziv tvrtke** je obavezno. Za veću preciznost podudaranja, mogu se dodati do dva druga polja, **Web-stranica tvrtke** i **Lokacija tvrtke**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okno za mapiranje polja usluge Leadspace.":::

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja.

1. Potvrdite potvrdni okvir ako imate *Profile kontakta* koje biste htjeli obogatiti. Customer Insights automatski će mapirati potrebna polja.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Obogaćivanje zapisa o kontaktima na usluzi Leadspace.":::

1. Odaberite **Dalje**.

1. Navedite naziv **za obogaćivanje i naziv izlaznog entiteta** **.**

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

1. Odaberite **Pokreni** da biste pokrenuli postupak obogaćivanja ili zatvorili da biste se vratili na **stranicu Obogaćivanje**.

## <a name="view-enrichment-results"></a>Prikaz rezultata obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Za dodatne informacije pogledajte [API-ji za Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
