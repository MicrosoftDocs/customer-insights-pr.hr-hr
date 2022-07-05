---
title: Azure Synapse Povezivanje izvor podataka (pretpregled)
description: Koristite bazu podataka u sustavu Azure Synapse kao izvor podataka u programu Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c4ae65613a02df38a30f907dae72d413bf1a702f
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052690"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Azure Synapse Analytics Povezivanje izvor podataka (pretpregled)

Azure Synapse Analytics je usluga analitike poduzeća koja ubrzava vrijeme do uvida u skladišta podataka i big data sustava. Azure Synapse Analytics objedinjuje najbolje od SQL tehnologija koje se koriste u skladištu poslovnih podataka, Spark tehnologije koje se koriste za velike podatke, Data Explorer za analitiku log i vremenskih serija, Pipelines za integraciju podataka i ETL /ELT te duboku integraciju s drugim Azure uslugama kao Power BI što su, Cosmos DB i AzureML.

Dodatne informacije potražite u pregledu [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Preduvjeti

> [!IMPORTANT]
> Obavezno postavite sve **dodjele uloga** kako je opisano.  

**U odjeljku Uvidi kupaca**:

* Imate administratorsku **ulogu** u korisničkom uvidu. Saznajte više o [korisničkim dozvolama u odjeljku Customer Insights](permissions.md#assign-roles-and-permissions).

**In Azure**:

- Aktivna pretplata na Azure.

- Ako koristite novi Azure Data Lake Storage gen2 račun, *upravitelj usluge za Customer Insights* treba **dozvole za pohranu bloba podataka suradnik**. Saznajte više o [povezivanju Azure Data Lake Storage s programom s upraviteljem usluge za Customer Insights](connect-service-principal.md). Data Lake Storage druge generacije **mora imati** omogućeno [hijerarhijsko polje imena](/azure/storage/blobs/data-lake-storage-namespace).

- U grupi resursa radni Azure Synapse prostor se nalazi, upravitelju *usluge* i korisniku *za uvide u kupce potrebno je dodijeliti* najmanje **Čitatelj** dozvola. Dodatne informacije potražite u odjeljku [Dodjela uloga servisa Azure pomoću portala Azure](/azure/role-based-access-control/role-assignments-portal).

- *Korisnik* treba dozvole **Suradnik za podatke blobova pohrane** na računu Azure Data Lake Storage druge generacije na kojem su podaci smješteni i povezani s radnim prostorom servisa Azure Synapse. Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identitet kojim upravlja radni prostor servisa Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* treba dozvole **Suradnik za podatke blobova pohrane** na računu Azure Data Lake Storage druge generacije na kojem su podaci smješteni i povezani s radnim prostorom servisa Azure Synapse. Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Na radnom prostoru upravitelju *usluge za Customer Insights* potrebna je **uloga administratora** synapsea. Dodatne informacije potražite u odjeljku [Kako postaviti kontrolu pristupa za vaš radni prostor servisa Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Poveži se s bazom podataka na jezeru podataka u programu Azure Synapse Analytics

1. Idite na **Podaci** > **Izvor podataka**.

1. Odaberite **Dodaj izvor podataka**.

1. Odaberite metodu **Azure Synapse Analytics (Pretpregled).**

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dijaloški okvir za povezivanje s podacima synapse Analyticsa":::
  
1. **Unesite naziv** izvor podataka i neobavezni **Opis**.

1. Odaberite dostupnu [vezu s](connections.md)Azure Synapse Analytics novom ili je stvorite.

1. **Odaberite bazu podataka** iz radnog prostora povezanog s odabranom Azure Synapse Analytics vezom i odaberite **Dalje**. Trenutno podržavamo samo bazu podataka *tipa* Lake.

1. Odaberite entitete koje želite progutati iz povezane baze podataka i odaberite **Dalje**.

1. Po želji odaberite podatkovne entitete na kojima želite dopustiti profiliranje podataka.

1. Odaberite **Spremi** da biste primijenili svoj odabir i započeli unos podataka iz novostvorenih izvor podataka povezanih s tablicama baze podataka Lake u sustavu Azure Synapse Analytics. Otvorit **će se stranica Izvori** podataka koja prikazuje novi izvor podataka u **statusu Osvježavanje**.
