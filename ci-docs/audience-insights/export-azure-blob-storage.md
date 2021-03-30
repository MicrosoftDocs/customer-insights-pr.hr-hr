---
title: Izvoz podataka usluge Customer Insights u Azure spremište blobova
description: Saznajte kako konfigurirati vezu sa spremištem bloba platforme Azure.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596168"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Konektor za spremište bloba platforme Azure (pretpregled)

Pohranite svoje podatke usluge Customer Insights u Azure spremište blobova ili ga upotrijebite za prijenos podataka u druge aplikacije.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Konfigracija konektora za spremište bloba platforme Azure

1. U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.

1. U odjeljku **Skladište bloba platforme Azure** odaberite **Postavljanje**.

1. Unesite **Naziv računa**, **Ključ računa** i **Spremnik** za vaš račun za pohranu bloba platforme Azure.
    - Da biste saznali više o pronalaženju imena i ključa računa spremišta blobova platforme Azure, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](/azure/storage/common/storage-account-manage).
    - Pogledajte kako stvoriti spremnik [Stvaranje spremnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Dodijelite odredištu prepoznatljivi naziv u polju **Zaslonski naziv**.

1. Odaberite **Dalje**.

1. Označite okvir pokraj svakog entiteta koji želite izvesti na ovo odredište.

1. Odaberite **Spremi**.

Izvezeni podaci pohranjuju se u spremnik za pohranu bloba platforme Azure koji ste konfigurirali. Sljedeći se putovi mapa automatski stvaraju u vašem spremniku:

- Za izvorne entitete i entitete koje generira sustav: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Primjer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model.json za izvezene entitete nalazit će se razini %ExportDestinationName%
  - Primjer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Izvoz podataka

Možete [izvesti podatke na zahtjev](export-destinations.md#export-data-on-demand). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]