---
title: Izvoz podataka usluge Customer Insights u Azure Data Lake Storage druge generacije
description: Saznajte kako konfigurirati vezu s uslugom Azure Data Lake Storage druge generacije.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 8b14992f8312d333d8a12501e8a28496c8434779
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642251"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Izvoz popisa segmenata i drugih podataka u Azure Data Lake Storage Gen2 (pretpregled)

Pohranite podatke s usluge Customer Insights na račun za Azure Data Lake Storage Gen2 ili ih upotrijebite za prijenos podataka u druge aplikacije.

## <a name="known-limitations"></a>Poznata ograničenja

1. Za Azure Data Lake Storage Gen2 možete birati između [Razina standardnih performansi i Premium performansi](/azure/storage/blobs/create-data-lake-storage-account) kada stvarate račun za pohranu za Data Lake. Ako odaberete razinu Premium performasi, odaberite Premium blobove bloka kao vrstu računa. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Uspostavljanje veze s uslugom Azure Data Lake Storage Gen2 


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

[!INCLUDE [footer-include](includes/footer-banner.md)]
