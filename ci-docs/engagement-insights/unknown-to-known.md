---
title: Prepoznavanje web-događaja od strane prethodno provjerenih posjetitelja od nepoznatih do poznatih
description: Značajka nepoznato do poznatog omogućuje vam povezivanje događaja na web-stranici s posjetiteljima kojima se prethodno provjerila autentičnost.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036774"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Prepoznavanje web-događaja od strane prethodno provjerenih posjetitelja

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Značajka **nepoznato do poznatog** u mogućnosti uvida u angažman omogućuje povezivanje događaja na web-stranici s posjetiteljima kojima se prethodno provjerila autentičnost. Ako je značajka onemogućena, posjetitelji kojima se provjerila autentičnost tijekom ranijeg posjeta, a zatim su otišli, neće biti identificirani ako im se ponovno ne provjeri autentičnost prilikom povratka. 

Na primjer, osoba je prošli tjedan posjetila web-stranicu, prijavila se u svoj korisnički račun na web-stranici i pregledala katalog proizvoda. Osoba se sljedeći tjedan vraća da pregleda još proizvoda bez prijavljivanja u svoj račun. Vlasnik web-stranice koristi značajku **nepoznato do poznatog** da bi znao da se ista osoba vratila i što je učinila na web-stranici. To omogućuje preciznije izvještavanje i analizu aktivnosti na web-stranici.

## <a name="enable-unknown-to-known"></a>Omogućavanje nepoznatog do poznatog

Trebate biti [administrator radnog prostora](user-roles.md) za omogućavanje ove značajke. 

1. U uvidima u angažman idite na **Admin** > **Radni prostor**. 
2. Odaberite karticu **Postavke**.
3. U odjeljku **Nepoznato do poznatog** postavite preklopni gumb na **Omogućeno**.

![Omogućavanje nepoznatog do poznatog](media/U2Ktoggle.png "Omogućavanje nepoznatog do poznatog")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Dodavanje JavaScript koda u isječak praćenja vaše web-stranice

Web-stranica može snimiti **autorizaciju korisnika** sa sljedećim uzorkom JavaScript koristeći [web SDK za uvide u angažman](advanced-SDK-implementation.md). Kako bi značajka **nepoznato do poznatog** funkcionirala, morate snimiti authId *i* omogućiti userMapping:True u svojem isječku JavaScript kao u donjem primjeru.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]