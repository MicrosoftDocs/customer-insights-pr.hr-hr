---
title: Izvoz podataka customer insights u Facebook upravitelj oglasa (sadrži videozapis)
description: Saznajte kako konfigurirati vezu i izvesti u Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f610ab1af83bfd512ec1861e7dc76ebb2eecfcbb
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642857"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Izvoz popisa segmenata u Facebook Ads Manager (pretpregled)

Izvezite segmente objedinjenih korisničkih profila u Upravitelj Facebook oglasa radi izrade kampanja na Facebooku i Instagramu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Preduvjeti za vezu

- Morate imati [**račun za Facebook oglase**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) koji uključuje [**poslovni račun za Facebook**](https://business.facebook.com/).
- Morate biti administrator na [**računu za Facebook oglase**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Poznata ograničenja

- Do 10 milijuna profila kupaca po izvozu u Facebook Upravitelj oglasa.
- Izvoz u Facebook Ads Manager ograničen je na segmente.
- Stvorite ili ažurirajte prilagođenu ciljnu skupinu na društvenoj mreži Facebook isključivo vrste *popis klijenata*.
- Izvoz segmenata s ukupno 10 milijuna profila klijenata u može potrajati do 90 minuta.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Postavljanje veze s Facebook Ads Manager

Prije nego što korisnici mogu stvoriti izvoz, administrator mora konfigurirati vezu s uslugom i dopustiti suradnicima korištenje veze.

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **Facebook Ads Manager** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Provjera autentičnosti uz Facebook Ads: 

   1. Odaberite **Nastavi uz Facebook** za prijavu na svoj račun za Facebook oglase.

   1. Omogućite dozvolu za **upravljanje oglasima** nakon provjere autentičnosti pomoću usluge Facebook.

   1. Odaberite **Upravitelj Facebook oglasa** s kojim želite raditi.

   1. Odaberite **Postojeća prilagođena publika** s padajućeg popisa ili stvorite opciju **Nova prilagođena publika**. Za više informacija pogledajte [**Publike u Upravitelju Facebook oglasa**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > S ovim izvozom na društvenoj mreži Facebook možete stvarati ili ažurirati isključivo prilagođene ciljne skupine vrste *popis klijenata*. U nekim slučajevima na padajućem popisu vidite prilagođene publike različitih vrsta. Odabir vrste različite od *popis klijenata* rezultirat će neuspjelim izvozom. 

1. Pregledajte **Zaštita privatnosti podataka i usklađenost** i odaberite **Slažem se**.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**. 

1. Pod **Veza za izvoz** odaberite vezu iz odjeljka **Facebook Ads Manager**. Ako ne vidite naziv ovog odjeljka, tada vam nisu dostupne veze ove vrste.

1. U polju **Odaberite ključni identifikator**, odaberite **E-pošta**, **Ime i adresa** ili **Telefon** koji će se poslati u Upravitelj Facebook oglasa. 

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**.

1. Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za odabrani identifikator ključa.
   > [!TIP]
   > Najveći izgledi za podudaranje pojavljuju se ako kao ključni identifikator odaberete **E-pošta**. Dodavanje dodatnih identifikatora može poboljšati podudaranje.

1. Odaberite **Dodaj atribut** za mapiranje više atributa za slanje u Facebook Ads Manager. Atributi iz Facebook Ads Manager mapiraju se na sljedeće nazive prilagođene korisnicima: **FN** = **Ime**, **LN** = **Prezime**, **FI** = **Prvi inicijal**, **PHONE** = **Telefon**, **GEN** = **Spol**, **DOB** = **Datum rođenja**, **ST** = **Država**, **CT** = **Grad**, **ZIP** = **Poštanski broj**, **COUNTRY** = **Zemlja/regija**

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). 

Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Upravitelj Facebook oglasa, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da usluga Facebook oglasi ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE [footer-include](includes/footer-banner.md)]