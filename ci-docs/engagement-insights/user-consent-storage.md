---
title: Upravljanje kolačićima i pristankom korisnika za pohranu korisničkih podataka na usluzi Dynamics 365 Customer Insights
description: Razumijte kako se kolačići i pristanak korisnika koriste za identificiranje posjetitelja web-mjesta.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228976"
---
# <a name="manage-cookies-and-user-consent"></a>Upravljanje kolačićima i pristankom korisnika

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights mogućnost uvida u angažman koristi se kolačićima i ključevima (`localStorage`) za identifikaciju posjetitelja web-stranice.

Kolačići su male datoteke koje pohranjuju komadiće informacija o korisnikovoj interakciji s web-mjestom. Pohranjeni su u web-preglednicima. Kada korisnici posjete web-mjesto za koje su vaši korisnici pohranili kolačiće, preglednik šalje te podatke poslužitelju koji vraća podatke koji su jedinstveni za korisnika. To je tehnologija koja omogućuje da, na primjer, mrežna kolica za kupovinu zadrže odabrane stavke čak i ako korisnik ode s web-mjesta.

## <a name="user-consent"></a>Pristanak korisnika

[Opća uredba o zaštiti podataka (GDPR)](/dynamics365/get-started/gdpr/) uredba je Europske unije (EU) koja nalaže kako tvrtke ili ustanove trebaju postupati s privatnošću i sigurnošću svojih korisnika. Kolačići često pohranjuju ili sakupljaju „osobne podatke”, kao što su mrežni identifikatora koji je obuhvaćen GDPR-om. Ako vaša tvrtka koristi i/ili prodaje subjektima podataka iz EU-a, GDPR utječe na vas. [Saznajte više o tome kako vam Microsoft može pomoći u usklađivanju s GDPR-om](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Da biste SDK-u za uvide u angažman omogućili pohranu kolačića ili ostalih osjetljivih podataka, morate navesti jesu li vaši korisnici pristali. To se događa prilikom inicijalizacije SDK -a postavljanjem polja `userConsent` u konfiguraciji.

Ako naznačite da ne postoji pristanak korisnika, SDK neće pohranjivati nikakve podatke i neće slati događaje koji se mogu koristiti za praćenje ponašanja korisnika. Svi prethodno pohranjeni podaci izbrisat će se iz preglednika.

Ako nije navedena vrijednost pristanka korisnika, SDK će pretpostaviti da je korisnik pristao. To znači da će se, ako vi (kao naš klijent) ne navedete vrijednost za pristanak korisnika u SDK-u, podaci sakupiti. Međutim, ako navedete da vrijednost za pristanak korisnika mora biti „true”, podaci se neće prikupljati ako korisnik odbije ili ne pruži izričit pristanak.

U nastavku je isječak koda za inicijalizaciju web-SDK -a uz pristanak korisnika:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Pohrana podataka o posjetiteljima u mogućnosti uvida u angažman

### <a name="cookies"></a>Kolačići

- _msei
    - Pohranjuje ID anonimnog korisnika. Ovaj je kolačić postavljen u domenu klijenta i istječe za 365 dana.

### <a name="local-storage"></a>Lokalna pohrana

Mogućnost uvida u angažman također se koristi (`localStorage`) ključevima za praćenje neosjetljivih podataka. Ti su podaci u potpunosti pohranjeni u samom pregledniku, bez prometa koji se šalje na vaše poslužitelje ili s njih.

- *EISession.Id*
    - Pohranjuje informacije o korisničkoj sesiji u tijeku, kao što je ID sesije, kada je započela i kada istječe.
- *EISession.Previous*
    - Pohranjuje URL prethodno posjećene stranice u trenutnoj sesiji.

Ključevi u lokalnoj pohrani ne istječu automatski i vratit će se na zadano tijekom sljedeće sesije SDK -a.

## <a name="deleting-cookies"></a>Brisanje kolačića

Vaši klijenti mogu ručno izbrisati kolačiće i ključeve lokalne pohrane u bilo kojem trenutku putem postavki svojih preglednika.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
