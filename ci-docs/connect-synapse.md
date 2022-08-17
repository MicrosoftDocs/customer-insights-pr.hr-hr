---
title: Azure Synapse Povezivanje izvor podataka (pretpregled)
description: Koristite bazu podataka u sustavu Azure Synapse kao izvor podataka u programu Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7bc0c3614e6dd39fbd65ae098ed679d95d09de9d
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259789"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Azure Synapse Analytics Povezivanje izvor podataka (pretpregled)

Azure Synapse Analytics je usluga analitike poduzeća koja ubrzava vrijeme do uvida u skladišta podataka i big data sustava. Azure Synapse Analytics objedinjuje najbolje od SQL tehnologija koje se koriste u skladištu poslovnih podataka, Spark tehnologije koje se koriste za velike podatke, Data Explorer za analitiku log i vremenskih serija, Pipelines za integraciju podataka i ETL /ELT te duboku integraciju s drugim Azure uslugama kao Power BI što su, Cosmos DB i AzureML.

Dodatne informacije potražite u pregledu [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Preduvjeti

> [!NOTE]
> Radni prostori sinapse s omogućenim [vatrozidom](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) trenutno nisu podržani.
> [!IMPORTANT]
> Obavezno postavite sve **dodjele uloga** kako je opisano.  

**U odjeljku Uvidi kupaca**:

* Imate administratorsku **ulogu** u korisničkom uvidu. Saznajte više o [korisničkim dozvolama u odjeljku Customer Insights](permissions.md#add-users).

**In Azure**:

- Aktivna pretplata na Azure.

- Ako koristite novi Azure Data Lake Storage Gen2 račun, *direktor usluge za Customer Insights* koji je "Dynamics 365 AI for Customer Insights" treba **dozvole za pohranu blob podataka suradnik**. Saznajte više o [povezivanju Azure Data Lake Storage s programom s upraviteljem usluge za Customer Insights](connect-service-principal.md). Data Lake Storage druge generacije **mora imati** omogućeno [hijerarhijsko polje imena](/azure/storage/blobs/data-lake-storage-namespace).

- U grupi Azure Synapse resursa nalazi se radni prostor, *glavnom programu* usluge koji je "Dynamics 365 AI for Customer Insights" i korisniku *za uvide u kupce potrebno je dodijeliti* najmanje **Čitatelj** dozvola. Dodatne informacije potražite u odjeljku [Dodjela uloga servisa Azure pomoću portala Azure](/azure/role-based-access-control/role-assignments-portal).

- *Korisnik* treba dozvole **Suradnik za podatke blobova pohrane** na računu Azure Data Lake Storage druge generacije na kojem su podaci smješteni i povezani s radnim prostorom servisa Azure Synapse. Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identitet kojim upravlja radni prostor servisa Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* treba dozvole **Suradnik za podatke blobova pohrane** na računu Azure Data Lake Storage druge generacije na kojem su podaci smješteni i povezani s radnim prostorom servisa Azure Synapse. Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Na radnom prostoru, *direktor usluge za Customer Insights* koji je "Dynamics 365 AI for Customer Insights" treba **dodijeliti ulogu administratora** Synapse. Dodatne informacije potražite u odjeljku [Kako postaviti kontrolu pristupa za vaš radni prostor servisa Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Ako vaše okruženje Customer Insights pohranjuje podatke u vlastitom [Azure Data Lake Storage](own-data-lake-storage.md), korisnik koji vezu postavlja Azure Synapse Analytics na potrebe barem ugrađenog **Čitatelj** ulogu na računu data lake pohrane. Dodatne informacije potražite u odjeljku [Dodjela uloga servisa Azure pomoću portala Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Poveži se s bazom podataka na jezeru podataka u programu Azure Synapse Analytics

1. Idite na **Podaci** > **Izvor podataka**.

1. Odaberite **Dodaj izvor podataka**.

1. Odaberite metodu **Azure Synapse Analytics (Pretpregled).**

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dijaloški okvir za povezivanje s podacima synapse Analyticsa":::
  
1. **Unesite naziv** izvor podataka i neobavezni **Opis**.

1. Odaberite dostupnu [vezu s](connections.md)Azure Synapse Analytics novom [ili](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse) je stvorite.

1. **Odaberite bazu podataka** iz radnog prostora povezanog s odabranom Azure Synapse Analytics vezom i odaberite **Dalje**. Trenutno podržavamo samo bazu podataka *tipa* Lake.

1. Odaberite entitete koje želite progutati iz povezane baze podataka i odaberite **Dalje**.

1. Po želji odaberite podatkovne entitete na kojima želite dopustiti profiliranje podataka.

1. Odaberite **Spremi** da biste primijenili svoj odabir i započeli unos podataka iz novostvorenih izvor podataka povezanih s tablicama baze podataka Lake u sustavu Azure Synapse Analytics. Otvorit **će se stranica Izvori** podataka koja prikazuje novi izvor podataka u **statusu Osvježavanje**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Učitavanje podataka može potrajati. Nakon uspješnog osvježavanja uneseni podaci mogu se pregledati sa [**stranice Entiteti**](entities.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
