---
title: Izvoz podataka customer insights u InMobi
description: Saznajte kako konfigurirati vezu i izvesti u InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195879"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Izvoz podataka customer insights u InMobi (pretpregled)

Izvezite popise segmenata ili druge podatke iz instance Customer Insights u [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Preduvjeti

- [InMobi račun](https://www.inmobi.com/) i administratorske vjerodajnice.
- Naziv [računa i ključ računa](/azure/storage/blobs/create-data-lake-storage-account) servisa Azure Blob Storage. Upute za pronalaženje naziva i ključa potražite u članku [Upravljanje postavkama računa za pohranu na portalu servisa Azure](/azure/storage/common/storage-account-manage).
- Spremnik [servisa Azure Blob Storage u koji](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) ćete izvoziti inMobi podatke.
- InMobi će stvoriti izravnu vezu s vašom pohranom bloba i konfigurirati automatski uvoz vaših podataka u InMobi. Da biste pokrenuli postupak, obratite se predstavniku tvrtke InMobi.

## <a name="known-limitations"></a>Poznata ograničenja

- Za Azure Blob Storage odaberite između [standardnih performansi i premium razine performansi](/azure/storage/blobs/storage-blob-performance-tiers). Ako odaberete razinu Premium performasi, odaberite [Premium blobove bloka kao vrstu računa](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Postavljanje veze s spremištem blobova servisa Azure Blob Storage

[Postavite vezu s pohranom blobova servisa Azure](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Konfiguracija izvoza

[Konfiguriranje izvoza](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
