---
title: Obogatite profile tvrtke Dun & Bradstreet (pregled)
description: Opće informacije o obogaćivanju treće strane Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 71b35e4295e19c13edadc6548ac79715555e8183
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196017"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Obogatite profile tvrtke Dun & Bradstreet (pregled)

Dun & Bradstreet pruža komercijalne podatke, analitiku i uvide za tvrtke. Klijentima pruža objedinjene korisničke profile kako bi tvrtke obogatile svoje podatke. Obogaćivanja uključuju atribute kao što su DUNS broj, veličina tvrtke, lokacija, industrija i još mnogo toga.

## <a name="prerequisites"></a>Preduvjeti

- Aktivna [licenca Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Jedinstveni profili](customer-profiles.md) kupaca za tvrtke.
- Postavljen je projekt [Dun & Bradstreet](#set-up-your-dun--bradstreet-project).
- Vezu Dun & Bradstreet [...](connections.md)[konfigurira](#configure-a-connection-for-dun--bradstreet) administrator.

## <a name="set-up-your-dun--bradstreet-project"></a>Postavite svoj projekt Dun & Bradstreet

Kao licencirani korisnik Dun & Bradstreeta, možete postaviti projekt u [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Prijavite se na [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Da biste dohvatili vjerodajnice, [vratite lozinku](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Preuzmite [našu datoteku](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) csv predloška koja će se koristiti za mapiranje polja Customer Insights u odgovarajuća polja Dun & Bradstreet.

1. Prenesite datoteku u koraku **prijenosa podataka** iskustva stvaranja projekta Dun & Bradstreet.

1. Odaberite vodoravne točke ispod relevantnog **izvora** u novostvorenom projektu Dun & Bradstreet da biste vidjeli dostupne opcije.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Snimka zaslona točaka u projektu Dun & Bradstreet.":::

1. Odaberite **Dohvati detalje o** S3. Te podatke pohranite na sigurno mjesto. Trebat će vam za [postavljanje veze za obogaćivanje](#configure-a-connection-for-dun--bradstreet) u Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Snimka zaslona odabira s3 informacija u projektu Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfiguriranje veze za Dun & Bradstreet

Morate biti [administrator](permissions.md#admin) u Customer Insights i imati vjerodajnice tvrtke Dun & Bradstreet Connect.

1. Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćenja ili Idite na **Administratorske** > **veze**, a zatim odaberite **Postavi** na pločici Dun & Bradstreet.

1. Unesite naziv veze.

1. Navedite valjane vjerodajnice Dun & Bradstreet i detalje projekta *Dun & Bradstreet Regija, Put mape Drop i Naziv* mape Drop. Ove [informacije](#set-up-your-dun--bradstreet-project) dobivate iz projekta Dun & Bradstreet.

1. Pregledajte i dajte svoj pristanak za [Privatnost podataka i usklađenost](#data-privacy-and-compliance) odabirom opcije **Slažem se**.

1. Odaberite **Provjeri** da biste provjerili valjanost konfiguracije, a zatim **Spremi**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Stranica konfiguracije veze Dun & Bradstreet.":::

### <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights prijenos podataka u Dun & Bradstreet, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenijeti takve podatke prema vašim uputama, ali vi ste odgovorni za to da Dun & Bradstreet ispunjava sve obveze privatnosti ili sigurnosti koje možda imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.

## <a name="supported-countries-or-regions"></a>Podržane države ili regije

Trenutno podržavamo sljedeće opcije zemlje / regije: Kanada (engleski) ili Sjedinjene Američke Države (engleski).

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

1. Odaberite **Obogatite moje podatke** **o podacima** tvrtke za pločicu Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Snimka zaslona pločice Dun & Bradstreet.":::

1. Pregledajte pregled, a zatim odaberite **Dalje**.

1. Odaberite vezu i potvrdite. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Odaberite **Dalje**.

1. **Odaberite skup podataka** kupca i odaberite profil ili segment koji želite obogatiti podacima tvrtke Dun & Bradstreet. Subjekt *Kupac* obogaćuje sve vaše profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Definirajte koju vrstu polja iz vaših jedinstvenih profila ćete koristiti za podudaranje podataka tvrtke tvrtke Dun & Bradstreet. Potrebno je barem jedno od polja **Ime i adresa**, **Telefon** ili **E-pošta**.

1. Odaberite **Sljedeće**

1. Mapirajte svoja polja na podatke tvrtke Dun & Bradstreet. Potrebna **su POLJA DUNS broj** ili **Naziv tvrtke** i **Država**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Okno za mapiranje polja Dun & Bradstreet.":::

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja.

1. Navedite naziv **za obogaćivanje i naziv izlaznog entiteta** **.**

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

1. Odaberite **Pokreni** da biste pokrenuli postupak obogaćivanja ili zatvorili da biste se vratili na **stranicu Obogaćivanje**.

## <a name="view-enrichment-results"></a>Prikaz rezultata obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
