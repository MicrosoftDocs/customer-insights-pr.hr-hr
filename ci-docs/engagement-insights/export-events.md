---
title: Izvoz pročišćenih događaja
description: Kako izvesti pročišćene događaje i osnovne događaje.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032376"
---
# <a name="export-events"></a>Izvoz događaja

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Događaj predstavlja ponašanje korisnika. Bilježi kada korisnik pregleda stranicu (prikaz događaja) ili kad stupi u interakciju sa sadržajem (događaj radnje). Kada možete odlučiti koja svojstva podataka želite prikazati u izvješću, ovaj virtualni prikaz podataka naziva se *pročišćeni događaj*. 

- Događaje i pročišćene događaje možete izvesti u vanjsku pohranu. 
- Izvoz je napredni tok podataka. Nije moguć ponovni unos u tok. 
- Izvozi imaju fiksne sheme. Ako događaju dodate prilagođena svojstva, ona neće biti uključena. Morat ćete stvoriti novi izvoz.

## <a name="prerequisites"></a>Preduvjeti

Prije postavljanja izvoza morate imati pristup i aktivnu pretplatu na portal Azure. Tijekom postupka izvoza trebat će vam podaci o računu za pohranu. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Stvaranje računa Azure Data Lake Storage Gen 2

1. Prijavite se na portal Azure i [stvorite novi račun za pohranu](/azure/storage/common/storage-account-create). 

1. Obavezno omogućite **Prostor za hijerarhijski naziv** na kartici **Napredno**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Omogućite prostor za hijerarhijski naziv na kartici Napredno.":::

1. Nakon što je postavljen, idite na novi račun za pohranu. U navigacijskom oknu odaberite **Postavke** > **Pristupni ključevi**. 

1. Kopirajte **Naziv računa** i **Ključ** za upotrebu pri stvaranju novog izvoza.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Pristupni ključevi na računu za pohranu.":::

## <a name="export-events"></a>Izvezi događaje

Postoje dva načina za izvoz događaja: 
- Idite na **Podaci** > **Izvozi** i odaberite **Novi izvoz**.
- Idite na **Podaci** > **Događaji**, odaberite **Više [...]** pored događaja koji želite izvesti pa odaberite **Izvezi** na padajućem izborniku. 

Prikazat će se vodič kroz korake za stvaranje izvoza:

1. Navedite **Naziv izvoza**.

1. Na padajućem popisu **Izbor događaja** odaberite osnovne događaje i događaje sužene pretraga koje ćete uključiti u izvoz. 

1. U opciji **Struktura datoteke** odaberite kadencu za stvaranje novih datoteka u odredišnoj pohrani. Događaji se izvoze kontinuirano kako pristižu.

1. Odaberite format za izvoz. Možete birati između formata **Common Data Model**, **CSV** i **JSON**. Da biste koristili izvoz s drugim aplikacijama Dynamics 365, preporučujemo upotrebu formata Common Data Model.

1. U koraku **Odaberite odredište** navedite lokaciju za Azure Data Lake Storage Gen 2.
    1. **Naziv računa ADLS Gen 2** je naziv računa za pohranu na koji želite spremiti izvoz. 
    1. **Putanja mape** definira gdje se izvoz treba pohraniti u datotečni sustav i strukturu direktorija računa za pohranu.
    1. **Dijeljeni ključ** dostupan je na portalu Azure za račun pohrane.

1. Pregledajte i potvrdite svoje odabire.

## <a name="view-and-manage-exports"></a>Pregled i upravljanje izvozima

Nakon što postavite izvoz, idite na **Podaci** > **Izvozi** da biste ga pregledali. Odaberite **Više [...]** za bilo koji postojeći izvoz da biste ga uredili ili izbrisali.


[!INCLUDE[footer-include](../includes/footer-banner.md)]