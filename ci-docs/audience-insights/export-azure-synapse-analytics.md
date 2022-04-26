---
title: Izvoz podataka usluge Customer Insights u Azure Synapse Analytics
description: Saznajte kako konfigurirati vezu na Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 8ace9fbee4fbd8822629a39d5902e176f8511cb5
ms.sourcegitcommit: 9f6733b2f2c273748c1e7b77f871e9b4e5a8666e
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/11/2022
ms.locfileid: "8560378"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Izvoz podataka u Azure Synapse Analytics (pretpregled)

Azure Synapse je analitička usluga koja ubrzava vrijeme za uvid u skladišta podataka i sustave velikih podataka. Svoje Customer Insights podatke možete unijeti i upotrijebiti u servisu [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Preduvjeti

Za konfiguriranje veze od usluge Customer Insights do Azure Synapse moraju biti ispunjeni sljedeći preduvjeti.

> [!NOTE]
> Obavezno postavite sve **dodjele uloga** kako je opisano.  

## <a name="prerequisites-in-customer-insights"></a>Preduvjeti u usluzi Customer Insights

* Vaš Azure Active Directory (AD) korisnički račun ima administratorsku **ulogu** u customer insights. Dodatne informacije o [postavljanju korisničkih dozvola u uvidima u ciljne skupine](permissions.md#assign-roles-and-permissions)

U servisu Azure: 

- Aktivna pretplata na Azure.

- Ako koristite novi Azure Data Lake Storage gen2 račun, *upravitelj usluge za Customer Insights* treba **dozvole za pohranu bloba podataka suradnik**. Saznajte više o [povezivanju na račun Azure Data Lake Storage druge generacije s upraviteljem usluge Azure za uvide u ciljne skupine](connect-service-principal.md). Data Lake Storage druge generacije **mora imati** omogućeno [hijerarhijsko polje imena](/azure/storage/blobs/data-lake-storage-namespace).

- U grupi resursa u kojoj Azure Synapse se nalazi radni prostor, upravitelju *usluge i korisniku* *Azure AD s administratorskim dozvolama u Customer Insights potrebno je dodijeliti* najmanje **Čitatelj** dozvola. Dodatne informacije potražite u odjeljku [Dodjela uloga servisa Azure pomoću portala Azure](/azure/role-based-access-control/role-assignments-portal).

- Korisniku *Azure AD s administratorskim dozvolama u customer insightsu potrebne* **su dozvole za pohranu blob podataka suradnik** na gen2 računu na Azure Data Lake Storage kojem se podaci nalaze i povezani su s radnim prostorom Azure Synapse. Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identitet kojim upravlja radni prostor servisa Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* treba dozvole **Suradnik za podatke blobova pohrane** na računu Azure Data Lake Storage druge generacije na kojem su podaci smješteni i povezani s radnim prostorom servisa Azure Synapse. Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Na radnom prostoru upravitelju *usluge za Customer Insights* potrebna je **uloga administratora** synapsea. Dodatne informacije potražite u odjeljku [Kako postaviti kontrolu pristupa za vaš radni prostor servisa Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Postavljanje veze i izvoz u Azure Synapse

### <a name="configure-a-connection"></a>Konfiguracija veze

Da biste stvorili vezu, upravitelj usluge i korisnički račun u customer insightsu trebaju **Čitatelj** dozvole za grupu *resursa u kojoj* se nalazi radni prostor Synapse Analytics. Uz to, upravitelju usluge i korisniku u radnom prostoru Synapse Analytics potrebna **su dopuštenja administratora** synapsea. 

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim Odaberite **Azure Synapse Analytics** ili odaberite **Postavljanje** na pločici **Azure Synapse Analytics** da biste konfigurirali vezu.

1. Dodijelite vezi prepoznatljivi naziv u polju Zaslonski naziv. Naziv i vrsta veze opisuju ovu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Odaberite ili potražite pretplatu u kojoj želite koristiti podatke Customer Insights. Čim se odabere pretplata, možete odabrati i **Radni prostor**, **Račun za pohranu** i **Spremnik**.

1. Odaberite **Spremi** da biste spremili vezu.

### <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Da biste konfigurirali izvoz sa zajedničkom vezom, potrebno vam je najmanje **suradnik** dozvola u customer insights. Dodatne informacije potražite u odjeljku [dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, ddaberite **Dodaj izvoz**.

1. **U polju Veza za izvoz** odaberite vezu iz odjeljka **Azure Synapse Analytics**. Ako ne vidite naziv ovog odjeljka, nema dostupnih [veza](connections.md) ove vrste.

1. Navedite prepoznatljiv **zaslonski naziv** za vaš izvoz i **naziv baze podataka**.

1. Izaberite entitete u koje želite da izvezete Azure Synapse Analytics.
   > [!NOTE]
   > Izvori podataka temeljeni na [Mapi Common Data Model](connect-common-data-model.md) nisu podržani.

2. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).

Da biste upitali podatke koji su izvezeni u Synapse Analytics, potrebni **su vam podaci o blobama za pohranu Čitatelj** pristup odredišnoj pohrani u radnom prostoru izvoza. 

### <a name="update-an-export"></a>Ažuriranje izvoza

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Uredi** na izvozu koji želite ažurirati.

   - **Dodajte** ili **uklonite** entitete iz odabira. Ako se entiteti uklone iz odabira, neće se izbrisati iz baze podataka analitike servisa Synapse. Međutim, buduća osvježavanja podataka neće ažurirati uklonjene entitete u toj bazi podataka.

   - **Promjena naziva baze podataka** stvara novu bazu podataka analitike servisa Synapse. Baza podataka s nazivom koji je ranije konfiguriran neće primati ažuriranja u budućim osvježavanjima.
