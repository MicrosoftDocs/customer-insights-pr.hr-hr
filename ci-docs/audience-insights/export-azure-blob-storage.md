---
title: Izvoz podataka usluge Customer Insights u Azure spremište blobova
description: Saznajte kako konfigurirati vezu sa spremištem bloba platforme Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667130"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Konektor za spremište bloba platforme Azure (pretpregled)

Pohranite svoje podatke usluge Customer Insights u Azure spremište blobova ili ga upotrijebite za prijenos podataka u druge aplikacije.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Konfigracija konektora za spremište bloba platforme Azure

1. U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.

1. U odjeljku **Skladište bloba platforme Azure** odaberite **Postavljanje**.

1. Unesite **Naziv računa**, **Ključ računa** i **Spremnik** za vaš račun za pohranu bloba platforme Azure.
    - Da biste saznali više o pronalaženju imena i ključa računa spremišta blobova platforme Azure, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Pogledajte kako stvoriti spremnik [Stvaranje spremnika](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Dodijelite odredištu prepoznatljivi naziv u polju **Zaslonski naziv**.

1. Odaberite **Dalje**.

1. Označite okvir pokraj svakog entiteta koji želite izvesti na ovo odredište.

1. Odaberite **Spremi**.

Izvezeni podaci pohranjuju se u spremnik za pohranu bloba platforme Azure koji ste konfigurirali. Sljedeći se putovi mapa automatski stvaraju u vašem spremniku:

- Za izvorne entitete i entitete koje generira sustav: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Primjer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model.json za izvezene entitete nalazit će se na razini %ExportDestinationName%
  - Primjer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Izvoz podataka

Možete [izvesti podatke na zahtjev](/export-destinations.md#export-data-on-demand). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).
