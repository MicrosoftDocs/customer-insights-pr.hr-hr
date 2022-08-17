---
title: Izvoz podataka u Azure Synapse Analytics (pretpregled)
description: Saznajte kako konfigurirati vezu na Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259835"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Izvoz podataka u Azure Synapse Analytics (pretpregled)

Azure Synapse je analitička usluga koja ubrzava vrijeme za uvid u skladišta podataka i sustave velikih podataka. Svoje Customer Insights podatke možete unijeti i upotrijebiti u servisu [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Preduvjeti

> [!NOTE]
> Obavezno postavite sve **dodjele uloga** kako je opisano.

- U odjeljku Customer Insights vaš Azure Active Directory (AD) korisnički račun mora imati administratorsku [ulogu](permissions.md#add-users).

U servisu Azure:

- Aktivna pretplata na Azure.

- Ako koristi novi Azure Data Lake Storage gen2 račun, [upravitelj usluge za Customer Insights](connect-service-principal.md) ima **dozvole za pohranu blob podataka suradnik**. Data Lake Storage druge generacije **mora imati** omogućeno [hijerarhijsko polje imena](/azure/storage/blobs/data-lake-storage-namespace).

- U grupi resursa u kojoj Azure Synapse se nalazi radni prostor, upravitelju *usluge* i korisniku *Azure AD s administratorskim dozvolama u customer insights moraju se dodijeliti* **najmanje** Čitatelj [dozvole](/azure/role-based-access-control/role-assignments-portal).

- Korisnik *Azure AD s administratorskim dozvolama u customer insights* ima **dozvole za pohranu blob podataka suradnik** na gen2 računu na Azure Data Lake Storage kojem se podaci nalaze i povezani su s radnim prostorom Azure Synapse. Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Upravljani identitet radnog prostora ima *[Azure Synapse dozvole za pohranu Blob Data suradnik](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* na gen2 računu na **kojem se podaci nalaze i povezani su s radnim prostorom**.Azure Data Lake Storage Azure Synapse Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Na radnom prostoru upravitelju *usluge za Customer Insights* dodijeljena **je** uloga administratora [synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Ako vaše okruženje Customer Insights pohranjuje podatke u vlastitom [Azure Data Lake Storage](own-data-lake-storage.md), korisnik koji vezu postavlja Azure Synapse Analytics na potrebe barem ugrađenog **Čitatelj** ulogu na računu data lake pohrane. Dodatne informacije potražite u odjeljku [Dodjela uloga servisa Azure pomoću portala Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="set-up-connection-to-azure-synapse"></a>Postavljanje veze na Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite .**Azure Synapse Analytics**

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju ovu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Odaberite ili potražite pretplatu u kojoj želite koristiti podatke Customer Insights. Čim se odabere pretplata, možete odabrati i **Radni prostor**, **Račun za pohranu** i **Spremnik**.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)] Da biste konfigurirali izvoz sa zajedničkom vezom, potrebno vam je najmanje **suradnik** dozvola u customer insights.

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. **U polju Veza za izvoz** odaberite vezu iz odjeljka Azure Synapse Analytics. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Navedite prepoznatljiv **zaslonski naziv** za vaš izvoz i **naziv baze podataka**. Izvoz će stvoriti novu [Azure Synapse bazu podataka](/azure/synapse-analytics/database-designer/concepts-lake-database) jezera u radnom prostoru definiranom u vezi.

1. Izaberite entitete u koje želite da izvezete Azure Synapse Analytics.
   > [!NOTE]
   > Izvori podataka temeljeni na [Mapi Common Data Model](connect-common-data-model.md) nisu podržani.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Da biste upitali podatke koji su izvezeni u Synapse Analytics, potrebni **su vam podaci o blobama za pohranu Čitatelj** pristup odredišnoj pohrani u radnom prostoru izvoza.

## <a name="update-an-export"></a>Ažuriranje izvoza

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Uredi** na izvozu koji želite ažurirati.

   - **Dodajte** ili **uklonite** entitete iz odabira. Ako se entiteti uklone iz odabira, neće se izbrisati iz baze podataka analitike servisa Synapse. Međutim, buduća osvježavanja podataka neće ažurirati uklonjene entitete u toj bazi podataka.

   - **Promjena naziva baze podataka** stvara novu bazu podataka analitike servisa Synapse. Baza podataka s nazivom koji je ranije konfiguriran neće primati ažuriranja u budućim osvježavanjima.

[!INCLUDE [footer-include](includes/footer-banner.md)]
