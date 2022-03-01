---
title: Izvoz podataka usluge Customer Insights u Azure Data Lake Storage druge generacije
description: Saznajte kako konfigurirati vezu s uslugom Azure Data Lake Storage druge generacije.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477170"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Poveznik za Azure Data Lake Storage druge generacije (pretpregled)

Pohranite podatke iz usluge Customer Insights na Azure Data Lake Storage druge generacije ili ih koristite za prijenos podataka u ostale aplikacije.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Konfiguriranje poveznika za Azure Data Lake Storage druge generacije

1. U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.

1. Pod **Azure Data Lake Storage druge generacije** odaberite **Postavi**.

1. Dodijelite odredištu prepoznatljivi naziv u polju **Zaslonski naziv**.

1. Unesite **Naziv računa**, **Ključ računa** i **Spremnik** za svoj Azure Data Lake Storage druge generacije.
    - Da biste saznali kako stvoriti račun za pohranu za korištenje uz Azure Data Lake Storage druge generacije, pogledajte [Stvaranje računa za pohranu](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Da biste saznali više o tome kako pronaći naziv računa za pohranu Azure Data Lake druge generacije i ključ računa, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Odaberite **Dalje**.

1. Označite okvir pokraj svakog entiteta koji želite izvesti na ovo odredište.

1. Odaberite **Spremi**.

## <a name="export-the-data"></a>Izvoz podataka

Možete [izvesti podatke na zahtjev](export-destinations.md#export-data-on-demand). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).
