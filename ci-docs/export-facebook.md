---
title: Izvoz segmenata u Facebook Upravitelj oglasa (pretpregled) (sadrži videozapise)
description: Saznajte kako konfigurirati vezu i izvesti u Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724576"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Izvoz segmenata u Facebook upravitelj oglasa (pretpregled)

Izvezite segmente objedinjenih korisničkih profila u Upravitelj Facebook oglasa radi izrade kampanja na Facebooku i Instagramu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Preduvjeti

- Oglasni [Facebook račun](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) koji uključuje [Facebook poslovni račun](https://business.facebook.com/).
- Administratorske ovlasti na [Facebook računu oglasa](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- Korisnik koji postavlja vezu u korisničkom uvidu mora prihvatiti prilagođene uvjete publika.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 10 milijuna korisničkih profila po izvozu u Facebook Ads Manager, što može potrajati i do 90 minuta.
- Samo segmenti.
- Facebook Integracija oglasa ne podržava korisnike s više od 25 oglasnih računa.
- Facebook *vrsta popisa* klijenata samo u [prilagođenoj publici](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > U nekim slučajevima na padajućem popisu možda ćete vidjeti prilagođenu publiku različitih vrsta. Ako odaberete drugu vrstu koja nije *popis* kupaca, izvoz neće uspjeti.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Postavljanje veze s Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Facebook Upravitelj** oglasa.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. [Dopustite suradnicima korištenje veze za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Provjera autentičnosti uz Facebook Ads:

   1. Odaberite **Nastavi uz Facebook** za prijavu na svoj račun za Facebook oglase.

   1. Omogućite dozvolu za **upravljanje oglasima** nakon provjere autentičnosti pomoću usluge Facebook.

   1. Odaberite **Upravitelj Facebook oglasa** s kojim želite raditi.

   1. Odaberite **Postojeća prilagođena publika** s padajućeg popisa ili stvorite opciju **Nova prilagođena publika**.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. **U polju Veza za izvoz** odaberite vezu iz odjeljka Upravitelj oglasa Facebook. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. **U polju Povezivanje podataka** odaberite **E-pošta**, **ime i adresa** ili **Telefon** koji želite poslati upravitelju Facebook oglasa.

1. Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za odabrani identifikator ključa.
   > [!TIP]
   > Najveći izgledi za podudaranje pojavljuju se ako kao ključni identifikator odaberete **E-pošta**. Dodavanje dodatnih identifikatora može poboljšati podudaranje.

1. Odaberite **Dodaj atribut** za mapiranje više atributa za slanje u Facebook Ads Manager. Atributi iz Facebook Ads Manager mapiraju se na sljedeće nazive prilagođene korisnicima: **FN** = **Ime**, **LN** = **Prezime**, **FI** = **Prvi inicijal**, **PHONE** = **Telefon**, **GEN** = **Spol**, **DOB** = **Datum rođenja**, **ST** = **Država**, **CT** = **Grad**, **ZIP** = **Poštanski broj**, **COUNTRY** = **Zemlja/regija**

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
