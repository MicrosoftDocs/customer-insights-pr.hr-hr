---
title: Obogatite korisničke profile podacima o identitetu s LiveRampa (pregled)
description: Obogatite profile kupaca LiveRamp podacima.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0aa6dc144602741b87843a5373779855ee3e334c
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237803"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Obogatite korisničke profile podacima o identitetu s LiveRampa (pregled)

LiveRamp pruža determinističko izvanmrežno rješavanje identiteta i konsolidaciju korisničkih podataka. Osobne identifikatore u svojim podacima o kupcima možete mapirati na grafikon identiteta tvrtke AbiliTec i primati AbiliTec ID-ove. Zatim možete koristiti te ID-ove za bolje ujedinjenje podataka o kupcima.

## <a name="supported-countriesregions"></a>Podržane zemlje/regije

Trenutno podržavamo obogaćivanje profila kupaca s LiveRamp podacima samo u Sjedinjenim Državama.

## <a name="prerequisites"></a>Preduvjeti

- Aktivna pretplata na LiveRamp. Da biste dobili pretplatu, obratite se timu za LiveRamp račun ili zatražite [dynamics@liveramp.com](mailto:dynamics@liveramp.com) dodatne informacije.

- Aktivna pretplata na AbiliTec s ID-om klijenta i tajnom pristupa API-ju. Dodatne informacije potražite u odjeljku [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/).

- LiveRamp [vezu](connections.md)[konfigurira](#configure-the-connection-for-liveramp) administrator.

## <a name="configure-the-connection-for-liveramp"></a>Konfiguriranje veze za LiveRamp

Morate biti [administrator](permissions.md#admin) u customer insights i imati aktivni LiveRamp klijentski ID i tajnu.

1. Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćenja ili Idite na **Veze s administratorima** > **·**, a zatim odaberite **Postavi** na pločici LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Okno konfiguracije za postavljanje veze sa servisom LiveRamp AbiliTec.":::

1. Unesite naziv veze i valjani LiveRamp ID klijenta i tajnu.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Provjeri** da biste provjerili valjanost konfiguracije, a zatim **Spremi**.

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

1. Odaberite **Obogati moje podatke** na pločici **Identitet** s liveramp pločice.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Pločica identiteta na stranici s pregledom obogaćivanja.":::

1. Pregledajte pregled, a zatim odaberite **Dalje**.

1. Odaberite vezu. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Odaberite **Dalje**.

1. **Odaberite skup podataka** za korisnike i odaberite profil ili segment koji želite obogatiti podacima o identitetu s LiveRampa. Subjekt *Kupac* obogaćuje sve vaše profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Definirajte koja će se vrsta polja iz vaših jedinstvenih profila koristiti za podudaranje podataka o identitetu s LiveRampa. Potrebno je barem jedno od polja **Naziv i adresa**, **E-pošta** ili **Telefon**. Za veću točnost podudaranja dodajte druga polja. Odaberite **Dalje**.

1. Mapirajte svoja polja na identifikacijske podatke s LiveRampa.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Mogućnosti mapiranja podataka za obogaćivanje LiveRamp-a.":::

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja.

1. Navedite naziv **za obogaćivanje i naziv izlaznog entiteta** **.**

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

1. Odaberite **Pokreni** da biste pokrenuli postupak obogaćivanja ili zatvorili da biste se vratili na **stranicu Obogaćivanje**.

## <a name="view-enrichment-results"></a>Prikaz rezultata obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Broj **kupaca obogaćenih poljem** pruža dubinsku analizu pokrivenosti svakog obogaćenog polja.

## <a name="next-steps"></a>Sljedeći koraci

Nadogradite na svoje obogaćene podatke o klijentu. Koristite AbiliTec ID-ove za konsolidaciju korisničkih profila u prikaz temeljen na osobi.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
