---
title: Obogaćivanje podataka o identitetu LiveRamp
description: Obogatite korisničke profile LiveRamp podacima.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373062"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Obogaćivanje korisničkih profila podacima o identitetu tvrtke LiveRamp (Pretpregled) 

LiveRamp pruža determinističku izvanmrežnu razlučivost identiteta i konsolidaciju korisničkih podataka. Osobne identifikatore u korisničkim podacima možete mapirati na grafikon identiteta AbiliTec i primiti AbiliTec ID-ove. Zatim možete koristiti te ID-ove za bolje ujedinjenje podataka o klijentima. 

## <a name="prerequisites"></a>Preduvjeti 

Da biste konfigurirali obogaćivanje, moraju biti ispunjeni sljedeći preduvjeti: 

- Imate aktivnu pretplatu na LiveRamp. Da biste dobili pretplatu, obratite se timu za LiveRamp račun ili dodatne [dynamics@liveramp.com](mailto:dynamics@liveramp.com) informacije.   

- Aktivna AbiliTec pretplata s ID-om klijenta i tajna pristupa API-u. Dodatne informacije potražite u članku [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Podržane zemlje/regije 

Trenutno podržavamo obogaćivanje korisničkih profila samo LiveRamp podacima u Sjedinjenim Američkim Državama. 

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje 

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**. 

1. Na pločici Identitet odaberite **Obogati moje podatke** **.** 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Pločica identiteta na stranici pregleda obogaćivanja.":::

1. Odaberite [vezu](connections.md) s padajućeg popisa. Ako nijedna veza nije dostupna, obratite se administratoru. Ako ste administrator, vezu možete stvoriti tako da odaberete **Dodaj vezu**. Na padajućem popisu odaberite **LiveRamp**. 

1. Odaberite **Dalje** i odaberite **skup podataka klijenta** koji želite obogatiti podacima o identitetu iz liveRampa. Možete odabrati *entitet Kupac* da biste obogatili sve profile klijenata ili odabrati entitet segmenta *da* biste obogatili samo profile kupaca sadržane u tom segmentu. 

1. Odaberite **Dalje** i definirajte koja bi se vrsta polja iz vaših objedinjenih profila trebala koristiti za traženje odgovarajućih podataka o identitetu iz LiveRamp-a. Potrebno je barem jedno od polja **Ime i adresa**, **Telefon** ili **E-pošta**. 

   > [!TIP]
   > Što više identifikatora ključeva i polja mapirate, veća je vjerojatnost veće stope podudaranja 

1. Mapirajte polja iz objedinjenog *entiteta klijenta* koja će se koristiti za podudaranje s LiveRampovim grafikonom AbiliTec ID. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Mogućnosti mapiranja podataka za obogaćivanje LiveRamp-a.":::

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja. 

1. **Navedite naziv** za obogaćivanje i **entitet Izlaz**. 

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira. 

## <a name="configure-the-connection-for-liveramp"></a>Konfiguriranje veze za LiveRamp 

Da biste konfigurirali veze [, morate](connections.md) biti administrator. Odaberite Dodaj vezu **prilikom konfiguriranja obogaćivanja ili idite na** AdministratorConnections **·** > **, a zatim odaberite** Postavi **na** pločici LiveRamp **.** 

:::image type="content" source="media/liveramp-connection.png" alt-text="Konfiguracijsko okno za postavljanje veze sa servisom LiveRamp AbiliTec.":::

1. Za **zaslonsko ime** unesite naziv veze. 

1. Navedite valjani ID LiveRamp klijenta i tajnu. 

1. Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**. 

1. Odaberi **Potvrdi** za provjeru valjanosti konfiguracije. 

1. Da biste dovršili vezu, odaberite **Spremi**. 

## <a name="enrichment-results"></a>Rezultati obogaćivanja 

Da biste pokrenuli postupak obogaćivanja, s naredbene trake odaberite Pokreni. Također možete dopustiti sustavu automatsko pokretanje obogaćivanja kao dio odgođenog [osvježavanja](system.md#schedule-tab). Vrijeme obrade ovisi o veličini vaših podataka o klijentima. 

Nakon završetka postupka obogaćivanja možete pregledati podatke o novoobogaćenim profilima kupaca podMy **obogaćivanje**. Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila. 

Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabiromPrijava **obogaćenih** podataka. 

## <a name="next-steps"></a>Sljedeći koraci

Nadogradite na svoje obogaćene podatke o klijentu. Koristite AbiliTec ID-ove da biste konsolidirali profile kupaca u prikaz koji se temelji na osobi. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost 

Kada omogućite Dynamics 365 Customer Insights prijenos podataka u LiveRamp, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenijeti takve podatke prema vašim uputama, ali vi ste odgovorni za to da LiveRamp ispunjava sve obveze u pogledu privatnosti ili sigurnosti koje možda imate. Dodatne informacije potražite u Microsoftovoj [izjavi](https://go.microsoft.com/fwlink/?linkid=396732) o zaštiti privatnosti. Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
