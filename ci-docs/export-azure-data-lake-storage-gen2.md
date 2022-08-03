---
title: Izvoz podataka u Azure Data Lake Storage Gen2 (pretpregled)
description: Saznajte kako konfigurirati vezu s uslugom Azure Data Lake Storage druge generacije.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196431"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Izvoz podataka u Azure Data Lake Storage Gen2 (pretpregled)

Pohranite podatke s usluge Customer Insights na račun za Azure Data Lake Storage Gen2 ili ih upotrijebite za prijenos podataka u druge aplikacije.

## <a name="prerequisites"></a>Preduvjeti

- Račun [za pohranu koji će se koristiti s programom Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Upute za pronalaženje naziva i ključa računa za pohranu potražite u članku [Upravljanje postavkama računa za pohranu na portalu servisa Azure](/azure/storage/common/storage-account-manage).
- An [Azure Blob Storage container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Poznata ograničenja

- Za Azure Data Lake Storage Gen2 odaberite između [standardnih performansi i premium razine performansi](/azure/storage/blobs/create-data-lake-storage-account). Ako odaberete razinu Premium performasi, odaberite [Premium blobove bloka kao vrstu računa](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Postavljanje veze s gen2 Azure Data Lake Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Azure Data Lake Gen 2**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **Naziv računa**, **Ključ računa** i **Spremnik** za svoj Azure Data Lake Storage druge generacije.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. **U polju Veza za izvoz** odaberite vezu iz odjeljka Azure Data Lake. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. Unesite naziv mape za prostor za pohranu u Azure Data Lake Storage gen2.

1. Označite okvir pokraj svakog entiteta koji želite izvesti na ovo odredište.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Izvezeni podaci pohranjuju se u spremnik za pohranu za Azure Data Lake Gen 2 koji ste konfigurirali.

> [!TIP]
> Izvoz entiteta koji sadrže veliku količinu podataka može dovesti do više CSV datoteka u istoj mapi za svaki izvoz. Podjela izvoza događa se iz razloga performansi kako bi se smanjilo vrijeme potrebno za dovršetak izvoza.

[!INCLUDE [footer-include](includes/footer-banner.md)]
