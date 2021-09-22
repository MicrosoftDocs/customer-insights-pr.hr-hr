---
title: Upravljanje kolačićima i pristankom korisnika za pohranu korisničkih podataka
description: Razumijte kako se kolačići i pristanak korisnika koriste za identificiranje posjetitelja web-mjesta.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036729"
---
# <a name="manage-cookies-and-user-consent"></a>Upravljanje kolačićima i pristankom korisnika

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Mogućnost uvida u angažman sustava Dynamics 365 Customer Insights koristi kolačiće i lokalnu pohranu (`localStorage`) za identificiranje posjetitelja web-mjesta.

Kolačići su male datoteke koje pohranjuju komadiće informacija o korisnikovoj interakciji s web-mjestom. Pohranjeni su u web-preglednicima. Kada korisnici posjete web-mjesto za koje su vaši korisnici pohranili kolačiće, preglednik šalje te podatke poslužitelju koji vraća podatke koji su jedinstveni za korisnika. To je tehnologija koja omogućuje da, na primjer, mrežna kolica za kupovinu zadrže odabrane stavke čak i ako korisnik ode s web-mjesta.

## <a name="user-consent"></a>Pristanak korisnika

[Opća uredba o zaštiti podataka (GDPR)](/dynamics365/get-started/gdpr/) uredba je Europske unije (EU) koja nalaže kako tvrtke ili ustanove trebaju postupati s privatnošću i sigurnošću svojih korisnika. Kolačići često pohranjuju ili sakupljaju „osobne podatke”, kao što su mrežni identifikatora koji je obuhvaćen GDPR-om. Ako vaša tvrtka koristi i/ili prodaje subjektima podataka iz EU-a, GDPR utječe na vas. [Saznajte više o tome kako vam Microsoft može pomoći u usklađivanju s GDPR-om](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Da biste SDK-u za uvide u angažman omogućili pohranu kolačića ili ostalih osjetljivih podataka, morate navesti jesu li vaši korisnici pristali. To se događa prilikom inicijalizacije SDK-a.

Ako naznačite da ne postoji pristanak korisnika, SDK neće pohranjivati nikakve podatke i neće slati događaje koji se mogu koristiti za praćenje ponašanja korisnika. Svi prethodno pohranjeni podaci izbrisat će se iz preglednika.

Ako nije navedena vrijednost pristanka korisnika, SDK će pretpostaviti da je korisnik pristao. To znači da će se, ako vi (kao naš klijent) ne navedete vrijednost za pristanak korisnika u SDK-u, podaci sakupiti. Međutim, ako navedete da vrijednost za pristanak korisnika mora biti „true”, podaci se neće prikupljati ako korisnik odbije ili ne pruži izričit pristanak.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Pohrana podataka o posjetiteljima u mogućnosti uvida u angažman

### <a name="cookies"></a>Kolačići

- _msei
    - Pohranjuje ID anonimnog korisnika. Ovaj je kolačić postavljen u domenu klijenta i istječe za 365 dana.

### <a name="local-storage"></a>Lokalna pohrana

Mogućnost uvida u angažman također koristi lokalnu pohranu (`localStorage`) za praćenje neosjetljivih podataka. Ti su podaci u potpunosti pohranjeni u samom pregledniku, bez prometa koji se šalje na vaše poslužitelje ili s njih.

- *EISession.Id* 
    - Pohranjuje informacije o korisničkoj sesiji u tijeku, kao što je ID sesije, kada je započela i kada istječe.
- *EISession.Previous*
    - Pohranjuje URL prethodno posjećene stranice u trenutnoj sesiji.
    
Ključevi u lokalnoj pohrani ne istječu automatski. SDK će ih ponovno postaviti tijekom sljedeće sesije.

## <a name="deleting-cookies"></a>Brisanje kolačića

Vaši klijenti mogu ručno izbrisati kolačiće i ključeve lokalne pohrane u bilo kojem trenutku putem postavki svojih preglednika.


[!INCLUDE[footer-include](../includes/footer-banner.md)]