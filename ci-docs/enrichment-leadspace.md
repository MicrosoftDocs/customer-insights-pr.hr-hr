---
title: Obogaćivanje profila tvrtki pomoću obogaćivanja treće strane tvrtke Leadspace
description: Opće informacije o obogaćivanju treće strane tvrtke Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 08a4c56eb1c387015fd9e985a0c9484a13236fcf
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642314"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Obogaćivanje profila tvrtke uz Leadspace (pretpregled)

Leadspace je tvrtka za znanost o podacima koja nudi B-to-B platformu za podatke o klijentima. Omogućuje okruženjima s objedinjenim profilima klijenata koji se temelje na računima da obogate svoje podatke. Obogatite *Profile klijenata* atributima kao što su veličina tvrtke, lokacija ili industrija. Obogatite *Profile kontakta* atributima poput naslova, osobe ili potvrde e-pošte.

## <a name="prerequisites"></a>Preduvjeti

Za konfiguriranje Leadspacea, potrebno je ispuniti sljedeće preduvjete:

- Imate aktivnu licencu Leadspace.
- Imate [objedinjene profile klijenata](customer-profiles.md) na temelju računa.
- Vezu Leadspace administrator je već konfigurirao ili imate [administratorske](permissions.md#admin) dozvole i „trajni ključ” (u daljnjem tekstu **Token za Leadspace**). Obratite se izravno tvrtki [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) za pojedinosti o njihovu proizvodu.

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje**.

1. Odaberite **Obogati moje podatke** na pločici Leadspace i odaberite **Započni**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snimka zaslona pločice Leadspace.":::

1. Odaberite [vezu](connections.md) s padajućeg popisa. Ako nijedna veza nije dostupna, obratite se administratoru. Ako ste administrator, vezu možete stvoriti odabirom **Dodaj vezu** i **Leadspace**. 

1. Odaberite **Poveži se s Leadspace** za potvrdu veze.

1. Odaberite **Sljedeće** i odaberite **Skup podataka klijenta** koji želite obogatiti podacima o tvrtki iz Leadspace. Možete odabrati entitet **Klijent** za obogaćivanje svih vaših korisničkih profila ili odaberite segmentni entitet za obogaćivanje samo korisničkih profila sadržanih u tom segmentu.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Snimka zaslona prilikom odabira skupa podataka o klijentu.":::

1. Odaberite **Sljedeće** i definirajte koja se polja iz vaših objedinjenih profila koriste za traženje odgovarajućih podataka o tvrtki iz Leadspace. Polje **Naziv tvrtke** je obavezno. Za veću preciznost podudaranja, mogu se dodati do dva druga polja, **Web-stranica tvrtke** i **Lokacija tvrtke**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okno za mapiranje polja usluge Leadspace.":::

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja.

1. Potvrdite potvrdni okvir ako imate *Profile kontakta* koje biste htjeli obogatiti. Customer Insights automatski će mapirati potrebna polja.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Obogaćivanje zapisa o kontaktima na usluzi Leadspace.":::
 
1. Navedite naziv za obogaćivanje i odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.


## <a name="configure-the-connection-for-leadspace"></a>Konfiguriranje veze za Leadspace 

Morate biti administrator da biste konfigurirali veze. Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćivanja *ili* idite na **Admin** > **Veze** i odaberite **Postavi** na pločici Leadspace.

1. Odaberite **Početak rada**. 

1. Unesite naziv za vezu u dijaloški okvir **Zaslonski naziv**.

1. Navedite valjani token za Leadspace.

1. Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom opcije **Slažem se**.

1. Odaberi **Potvrdi** za provjeru valjanosti konfiguracije.

1. Nakon dovršetka provjere valjanosti odaberite **Spremi**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Stranica za konfiguraciju veze za Leadspace.":::

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon osvježavanja obogaćivanja, možete pregledati novoobogaćene podatke tvrtke pod [Moja obogaćivanja](enrichment-hub.md). Možete pronaći vrijeme posljednjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.

Za dodatne informacije pogledajte [API-ji za Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Sljedeći koraci


[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Leadspace, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Leadspace ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE [footer-include](includes/footer-banner.md)]
