---
title: Unos podataka iz Azure Synapse Analytics
description: Koristite bazu podataka u sustavu Azure Synapse kao izvor podataka u programu Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642272"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Azure Synapse Povezivanje izvor podataka (pretpregled)

Azure Synapse Analytics je usluga analitike poduzeća koja ubrzava vrijeme do uvida u skladišta podataka i big data sustava. Azure Synapse Analytics objedinjuje najbolje od SQL tehnologija koje se koriste u skladištu poslovnih podataka, Spark tehnologije koje se koriste za velike podatke, Data Explorer za analitiku log i vremenskih serija, Pipelines za integraciju podataka i ETL /ELT te duboku integraciju s drugim Azure uslugama kao Power BI što su, Cosmos DB i AzureML.

Dodatne informacije potražite u pregledu [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Preduvjeti

Moraju biti ispunjeni sljedeći preduvjeti za konfiguriranje veze iz Dynamics 365 Customer Insights sustava u Azure Synapse sustav.

> [!IMPORTANT]
> Obavezno postavite sve **dodjele uloga** kako je opisano.  

## <a name="prerequisites-in-customer-insights"></a>Preduvjeti u usluzi Customer Insights

* Imate administratorsku **ulogu** u korisničkom uvidu. Saznajte više o [korisničkim dozvolama u odjeljku Customer Insights](permissions.md#assign-roles-and-permissions).

U servisu Azure: 

- Aktivna pretplata na Azure.

- Ako koristite novi Azure Data Lake Storage gen2 račun, *upravitelj usluge za Customer Insights* treba **dozvole za pohranu bloba podataka suradnik**. Saznajte više o [povezivanju Azure Data Lake Storage s programom s upraviteljem usluge za Customer Insights](connect-service-principal.md). Data Lake Storage druge generacije **mora imati** omogućeno [hijerarhijsko polje imena](/azure/storage/blobs/data-lake-storage-namespace).

- U grupi resursa radni Azure Synapse prostor se nalazi, upravitelju *usluge* i korisniku *za uvide u kupce potrebno je dodijeliti* najmanje **Čitatelj** dozvola. Dodatne informacije potražite u odjeljku [Dodjela uloga servisa Azure pomoću portala Azure](/azure/role-based-access-control/role-assignments-portal).

- *Korisnik* treba dozvole **Suradnik za podatke blobova pohrane** na računu Azure Data Lake Storage druge generacije na kojem su podaci smješteni i povezani s radnim prostorom servisa Azure Synapse. Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identitet kojim upravlja radni prostor servisa Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* treba dozvole **Suradnik za podatke blobova pohrane** na računu Azure Data Lake Storage druge generacije na kojem su podaci smješteni i povezani s radnim prostorom servisa Azure Synapse. Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Na radnom prostoru upravitelju *usluge za Customer Insights* potrebna je **uloga administratora** synapsea. Dodatne informacije potražite u odjeljku [Kako postaviti kontrolu pristupa za vaš radni prostor servisa Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Poveži se s bazama podataka na jezeru podataka u programu Azure Synapse Analytics

1. Idite na **Podaci** > **Izvor podataka**.

1. Odaberite **Dodaj izvor podataka**.

1. Odaberite metodu **Azure Synapse Analytics (Pretpregled).**

1. Navedite **Naziv** izvora podataka i odaberite **Dalje** kako biste stvorili izvor podataka. 

1. Odaberite dostupnu [vezu s](connections.md)Azure Synapse Analytics novom ili je stvorite.

1. Odaberite jezersku **bazu podataka** iz radnog prostora povezanog s odabranom Azure Synapse Analytics vezom i odaberite **Dalje**.

1. Odaberite entitete koje želite progutati iz povezane baze podataka. 

1. Po želji odaberite podatkovne entitete na kojima želite dopustiti profiliranje podataka. 

1. Odaberite **Spremi** da biste primijenili svoj odabir i započeli unos podataka iz novostvorenih izvor podataka povezanih s tablicama baze podataka Lake u sustavu Azure Synapse Analytics.
