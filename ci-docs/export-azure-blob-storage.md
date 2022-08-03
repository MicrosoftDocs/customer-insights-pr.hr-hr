---
title: Izvoz podataka u spremište blobova servisa Azure (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Spremnik za pohranu bloba.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195695"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Izvoz podataka u spremište blobova servisa Azure (pretpregled)

Pohranite podatke usluge Customer Insights na Spremnik za pohranu bloba ili ih koristite za prijenos svojih podataka u ostale aplikacije.

## <a name="prerequisites"></a>Preduvjeti

- Naziv [računa i ključ računa](/azure/storage/blobs/create-data-lake-storage-account) servisa Azure Blob Storage. Upute za pronalaženje naziva i ključa potražite u članku [Upravljanje postavkama računa za pohranu na portalu servisa Azure](/azure/storage/common/storage-account-manage).
- An [Azure Blob Storage container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Poznata ograničenja

- Za Azure Blob Storage odaberite između [standardnih performansi i premium razine performansi](/azure/storage/blobs/storage-blob-performance-tiers). Ako odaberete razinu Premium performasi, odaberite [Premium blobove bloka kao vrstu računa](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Postavljanje veze s spremištem bloba

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Azure Blob Storage**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **Naziv računa**, **Ključ računa** i **Spremnik** za svoj račun za pohranu bloba.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Da biste konfigurirali taj izvoz, morate imati [dozvolu](export-destinations.md#set-up-a-new-export) za ovu vrstu veze.

> [!IMPORTANT]
> Ako ste uključili postavku [mekog](/azure/storage/blobs/soft-delete-blob-enable) brisanja za račun servisa Azure Blob Storage, izvoz neće uspjeti. Isključite mekano brisanje za izvoz podataka u blobove.

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Spremnik za pohranu bloba za Azure. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. Unesite naziv mape za spremište bloba.

1. Označite okvir pokraj svakog entiteta koji želite izvesti na ovo odredište.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Izvezeni podaci pohranjuju se u spremnik za pohranu bloba koji ste konfigurirali. Sljedeći se putovi mapa automatski stvaraju u vašem spremniku:

- Za izvorne entitete i entitete koje generira sustav:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Primjer: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Izvoz entiteta koji sadrže veliku količinu podataka može dovesti do više CSV datoteka u istoj mapi za svaki izvoz. Podjela izvoza događa se iz razloga performansi kako bi se smanjilo vrijeme potrebno za dovršetak izvoza.

- Model.json za izvezene entitete nalazi se na *%ExportDestinationName%* razini.  
  
  Primjer: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
