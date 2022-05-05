---
title: LiveRamp obogaćivanje podataka o identitetu
description: Obogatite profile kupaca LiveRamp podacima.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0727818f6df565d9a031966a68d521ae7167e484
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642238"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Obogatite profile korisnika podacima o identitetu s LiveRampa (Preview) 

LiveRamp pruža determinističko izvanmrežno rješavanje identiteta i konsolidaciju korisničkih podataka. Osobne identifikatore u svojim podacima o kupcima možete mapirati na grafikon identiteta tvrtke AbiliTec i primati AbiliTec ID-ove. Zatim možete koristiti te ID-ove za bolje ujedinjenje podataka o kupcima. 

## <a name="prerequisites"></a>Preduvjeti 

Da biste konfigurirali obogaćivanje, moraju biti ispunjeni sljedeći preduvjeti: 

- Imate aktivnu pretplatu na LiveRamp. Da biste dobili pretplatu, obratite se timu za LiveRamp račun ili zatražite [dynamics@liveramp.com](mailto:dynamics@liveramp.com) dodatne informacije.   

- Aktivna pretplata na AbiliTec s ID-om klijenta i tajnom pristupa API-ju. Dodatne informacije potražite u odjeljku [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Podržane zemlje/regije 

Trenutno podržavamo obogaćivanje profila kupaca s LiveRamp podacima samo u Sjedinjenim Državama. 

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje 

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**. 

1. Na **pločici Identitet** odaberite Obogati moje **podatke**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Pločica identiteta na stranici s pregledom obogaćivanja.":::

1. Odaberite [vezu](connections.md) s padajućeg popisa. Ako nijedna veza nije dostupna, obratite se administratoru. Ako ste administrator, vezu možete stvoriti tako **da odaberete Dodaj vezu**. Na padajućem popisu odaberite **LiveRamp**. 

1. Odaberite **Dalje** i odaberite **skup podataka** korisnika koje želite obogatiti podacima o identitetu s LiveRampa. Možete odabrati *entitet Kupac* da biste obogatili sve svoje profile kupaca ili odabrali entitet segmenta *da* biste obogatili samo profile kupaca sadržane u tom segmentu. 

1. Odaberite **Dalje** i definirajte koja će se vrsta polja iz vaših jedinstvenih profila koristiti za traženje odgovarajućih podataka o identitetu s LiveRampa. Potrebno je barem jedno od polja **Naziv i adresa**, **Telefon** ili **E-pošta**. 

   > [!TIP]
   > Što više identifikatora ključeva i polja mapirate, veća je vjerojatnost veće stope podudaranja 

1. Mapirajte polja iz jedinstvenog *entiteta klijenta* koja će se koristiti za podudaranje s LiveRampovim grafikonom AbiliTec ID-a. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Mogućnosti mapiranja podataka za obogaćivanje LiveRamp-a.":::

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja. 

1. Navedite naziv **za** obogaćivanje i izlazni **entitet**. 

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira. 

## <a name="configure-the-connection-for-liveramp"></a>Konfiguriranje veze za LiveRamp 

Da biste konfigurirali [veze](connections.md), morate biti administrator. Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćenja ili Idite na **AdminConnections** > **·**, a zatim odaberite **Postavi** na pločici **LiveRamp**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Okno konfiguracije za postavljanje veze sa servisom LiveRamp AbiliTec.":::

1. Za **zaslonsko ime** unesite naziv veze. 

1. Navedite valjani LiveRamp ID klijenta i tajnu. 

1. Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**. 

1. Odaberi **Potvrdi** za provjeru valjanosti konfiguracije. 

1. Da biste dovršili vezu, odaberite **Spremi**. 

## <a name="enrichment-results"></a>Rezultati obogaćivanja 

Da biste pokrenuli postupak obogaćivanja, na naredbenoj traci odaberite Pokreni. Također možete dopustiti sustavu da automatski pokrene obogaćivanje u sklopu odgođenog [osvježavanja](system.md#schedule-tab). Vrijeme obrade ovisi o veličini vaših podataka o klijentima. 

Nakon završetka postupka obogaćivanja, možete pregledati novoobogaćene podatke o profilima kupaca pod **Moja obogaćivanja**. Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila. 

Detaljnom prikazu svakog obogaćenog profila možete pristupiti tako da odaberetePrikaz **obogaćenih** podataka. 

## <a name="next-steps"></a>Sljedeći koraci

Nadogradite na svoje obogaćene podatke o klijentu. Koristite AbiliTec ID-ove za konsolidaciju korisničkih profila u prikaz temeljen na osobi. 
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost 

Kada omogućite Dynamics 365 Customer Insights prijenos podataka na LiveRamp, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenijeti takve podatke prema vašim uputima, ali vi ste odgovorni za to da LiveRamp ispunjava sve obveze zaštite privatnosti ili sigurnosti koje možda imate. Dodatne informacije potražite u Microsoftovoj [izjavi](https://go.microsoft.com/fwlink/?linkid=396732) o zaštiti privatnosti. Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati. 


[!INCLUDE [footer-include](includes/footer-banner.md)]
