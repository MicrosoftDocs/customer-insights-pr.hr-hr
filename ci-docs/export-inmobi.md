---
title: Izvoz podataka customer insights u InMobi
description: Saznajte kako konfigurirati vezu i izvesti u InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059606"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Izvoz popisa segmenata i drugih podataka u InMobi (pretpregled)

Izvezite popise segmenata ili druge podatke iz instance Customer Insights u [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Preduvjeti

1. Imate [InMobi račun](https://www.inmobi.com/) i administratorske vjerodajnice.
1. Imate naziv računa za pohranu servisa Azure Blob i odgovarajući ključ računa. Dodatne informacije potražite u članku [Upravljanje postavkama računa za pohranu na portalu servisa Azure](/azure/storage/common/storage-account-manage). Na računu za pohranu nalazi se spremnik u koji se mogu izvoziti inMobi podaci. Dodatne informacije potražite u članku [Stvaranje spremnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi će stvoriti izravnu vezu s vašom pohranom bloba i konfigurirati automatski uvoz vaših podataka u InMobi. Da biste pokrenuli postupak, obratite se predstavniku tvrtke InMobi.

## <a name="known-limitations"></a>Poznata ograničenja

1. Za Azure Blob Storage možete birati između [standardnih performansi i premium razine performansi](/azure/storage/blobs/storage-blob-performance-tiers). Ako odaberete razinu Premium performasi, odaberite [Premium blobove bloka kao vrstu računa](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Postavljanje veze s pohranom blobova servisa Azure i konfiguriranje izvoza

1. Slijedite upute za [postavljanje veze s pohranom blobova servisa](export-azure-blob-storage.md) Azure.
2. Slijedite upute za konfiguriranje [izvoza](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
