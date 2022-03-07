---
title: Izvoz podataka usluge Customer Insights u Spremnik za pohranu bloba za Azure
description: Saznajte kako konfigurirati vezu i izvesti u Spremnik za pohranu bloba.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5ea8e58822e1bb901552ff1de960d5340d340003
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231242"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Izvoz popisa segmenata i ostalih podataka u Spremnik za pohranu bloba za Azure (pretpregled)

Pohranite podatke usluge Customer Insights na Spremnik za pohranu bloba ili ih koristite za prijenos svojih podataka u ostale aplikacije.

## <a name="known-limitations"></a>Poznata ograničenja

1. Za Azure Blob Storage možete birati između [Razine standardnih performansi i razine Premium performansi](/azure/storage/blobs/storage-blob-performance-tiers). Ako odaberete razinu Premium performasi, odaberite [Premium blobove bloka kao vrstu računa](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Postavljanje veze za pohranu bloba

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **Spremnik za pohranu bloba za Azure** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **Naziv računa**, **Ključ računa** i **Spremnik** za svoj račun za pohranu bloba.
    - Da biste saznali više o tome kako pronaći naziv računa apremnika za pohranu bloba i ključ računa, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](/azure/storage/common/storage-account-manage).
    - Pogledajte kako stvoriti spremnik [Stvaranje spremnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Odaberite **Spremi** da biste završili vezu. 

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Ako ste uključili postavku mekanog brisanja za račun za pohranu bloba servisa Azure, izvozi neće uspjeti. Isključite mekano brisanje za izvoz podataka u blobove. Za više informacija pogledajte [Omogućavanje mekanog brisanja bloba](/azure/storage/blobs/soft-delete-blob-enable.md)

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Spremnik za pohranu bloba za Azure. Ako ne vidite naziv ovog odjeljka, tada vam nisu dostupne veze ove vrste.

1. Označite okvir pokraj svakog entiteta koji želite izvesti na ovo odredište.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab).     

Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 

Izvezeni podaci pohranjuju se u spremnik za pohranu bloba koji ste konfigurirali. Sljedeći se putovi mapa automatski stvaraju u vašem spremniku:

- Za izvorne entitete i entitete koje generira sustav:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Primjer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- Model.json za izvezene entitete bit će na razini %ExportDestinationName%.  
  - Primjer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
