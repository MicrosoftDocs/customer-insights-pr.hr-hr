---
title: Unos podataka iz Azure Synapse Analytics
description: Koristite bazu podataka u programu Azure Synapse kao izvor podataka u sustavu Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356042"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Azure Synapse Povezivanje izvor podataka (pretpregled)

Azure Synapse Analytics je usluga analitike poduzeća koja ubrzava vrijeme do uvida u skladišta podataka i sustave velikih podataka. Azure Synapse Analytics objedinjuje najbolje od SQL tehnologija koje se koriste u poslovnom zaštiti podataka, Spark tehnologije koje se koriste za velike podatke, Data Explorer za analitiku dnevnika i vremenskih serija, Cjevovode za integraciju podataka i ETL/ELT te duboku integraciju s drugim servisima platforme Azure kao Power BI Cosmos DB što su, i AzureML.

Dodatne informacije potražite u članku [Azure Synapse Pregled](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Preduvjeti

Za konfiguriranje veze od usluge Customer Insights do Azure Synapse moraju biti ispunjeni sljedeći preduvjeti.

> [!IMPORTANT]
> Obavezno postavite sve **dodjele uloga** kako je opisano.  

## <a name="prerequisites-in-customer-insights"></a>Preduvjeti u usluzi Customer Insights

* Imate administratorsku **ulogu** u uvidima u klijenta. Saznajte više o [korisničkim dozvolama u uvidima u ciljne skupine](permissions.md#assign-roles-and-permissions).

U servisu Azure: 

- Aktivna pretplata na Azure.

- Ako koristite račun za novi Azure Data Lake Storage druge generacije, *upravitelj servisa za uvide u ciljne skupine* treba dozvole **Suradnik za podatke blobova pohrane**. Saznajte više o [povezivanju s ravnateljem Azure Data Lake Storage servisa radi publika uvida](connect-service-principal.md). Data Lake Storage druge generacije **mora imati** omogućeno [hijerarhijsko polje imena](/azure/storage/blobs/data-lake-storage-namespace).

- U grupi resursa u kojoj se nalazi radni prostor servisa Azure Synapse, *upravitelju usluge* i *korisniku za uvide u ciljne skupine* treba dodijeliti barem dozvole **Čitatelj**. Dodatne informacije potražite u odjeljku [Dodjela uloga servisa Azure pomoću portala Azure](/azure/role-based-access-control/role-assignments-portal).

- *Korisnik* treba dozvole **Suradnik za podatke blobova pohrane** na računu Azure Data Lake Storage druge generacije na kojem su podaci smješteni i povezani s radnim prostorom servisa Azure Synapse. Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identitet kojim upravlja radni prostor servisa Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* treba dozvole **Suradnik za podatke blobova pohrane** na računu Azure Data Lake Storage druge generacije na kojem su podaci smješteni i povezani s radnim prostorom servisa Azure Synapse. Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- U radnom prostoru servisa Azure Synapse, *upravitelj usluge za uvide u ciljne skupine* treba dodijeljenu ulogu **Administrator za Synapse**. Dodatne informacije potražite u odjeljku [Kako postaviti kontrolu pristupa za vaš radni prostor servisa Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Povezivanje s bazama podataka podatkovnog jezera u Azure Synapse Analytics

1. Idite na **Podaci** > **Izvor podataka**.

1. Odaberite **Dodaj izvor podataka**.

1. Odaberite metodu **Azure Synapse Analytics (pretpregleda**).

1. Navedite **Naziv** izvora podataka i odaberite **Dalje** kako biste stvorili izvor podataka. 

1. Odaberite dostupnu [vezu s](connections.md)Azure Synapse Analytics novom ili je stvorite.

1. **Odaberite bazu podataka** jezera iz radnog prostora povezanog u odabranoj Azure Synapse Analytics vezi, a zatim **Dalje**.

1. Odaberite entitete koje želite progutati iz povezane baze podataka. 

1. Po želji odaberite podatkovne entitete da biste dopustili profiliranje podataka. 

1. Odaberite **Spremi** da biste primijenili odabir i započeli unos podataka iz novostvorenih izvor podataka povezanih s tablicama baze podataka jezera u sustavu Azure Synapse Analytics.
