---
title: Izvoz podataka usluge Customer Insights u Azure Data Lake Storage druge generacije
description: Saznajte kako konfigurirati vezu s uslugom Azure Data Lake Storage druge generacije.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760042"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a>Postavljanje veze s Azure Data Lake Storage Gen2 (pretpregled)

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **Azure Data Lake Gen 2** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **Naziv računa**, **Ključ računa** i **Spremnik** za svoj Azure Data Lake Storage druge generacije.
    - Da biste saznali kako stvoriti račun za pohranu za korištenje uz Azure Data Lake Storage druge generacije, pogledajte [Stvaranje računa za pohranu](/azure/storage/blobs/create-data-lake-storage-account). 
    - Da biste saznali više o nazivu računa za pohranu i ključu računa za Azure Data Lake Gen2, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](/azure/storage/common/storage-account-manage).

1. Odaberite **Spremi** da biste završili vezu. 

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, ddaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka **Azure Data Lake**. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Označite okvir pokraj svakog entiteta koji želite izvesti na ovo odredište.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 

Izvezeni podaci pohranjuju se u spremnik za pohranu za Azure Data Lake Gen 2 koji ste konfigurirali. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
