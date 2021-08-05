---
title: Izvoz podataka iz Customer Insights u Analitiku servisa Azure Synapse
description: Saznajte kako konfigurirati vezu s Analitikom servisa Azure Synapse.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7ee57aa9e86ebf9bd1989d88750642f0b01bd4bf
ms.sourcegitcommit: f18635c29bb25d9e424a3f5825dc2696278450cf
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/30/2021
ms.locfileid: "6327355"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Izvoz podataka u Analitiku servisa Azure Synapse (Pretpregled)

Azure Synapse je analitička usluga koja ubrzava vrijeme za uvid u skladišta podataka i sustave velikih podataka. Svoje Customer Insights podatke možete unijeti i upotrijebiti u servisu [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Preduvjeti

Za konfiguriranje veze od usluge Customer Insights do Azure Synapse moraju biti ispunjeni sljedeći preduvjeti.

> [!NOTE]
> Obavezno postavite sve **dodjele uloga** kako je opisano.  

## <a name="prerequisites-in-customer-insights"></a>Preduvjeti u usluzi Customer Insights

* Imate ulogu **Administrator** u uvidima u ciljne skupine. Dodatne informacije o [postavljanju korisničkih dozvola u uvidima u ciljne skupine](permissions.md#assign-roles-and-permissions)

U servisu Azure: 

- Aktivna pretplata na Azure.

- Ako koristite račun za novi Azure Data Lake Storage druge generacije, *upravitelj servisa za uvide u ciljne skupine* treba dozvole **Suradnik za podatke blobova pohrane**. Saznajte više o [povezivanju na račun Azure Data Lake Storage druge generacije s upraviteljem usluge Azure za uvide u ciljne skupine](connect-service-principal.md). Data Lake Storage druge generacije **mora imati** omogućeno [hijerarhijsko polje imena](/azure/storage/blobs/data-lake-storage-namespace).

- U grupi resursa u kojoj se nalazi radni prostor servisa Azure Synapse, *upravitelju usluge* i *korisniku za uvide u ciljne skupine* treba dodijeliti barem dozvole **Čitatelj**. Dodatne informacije potražite u odjeljku [Dodjela uloga servisa Azure pomoću portala Azure](/azure/role-based-access-control/role-assignments-portal).

- *Korisnik* treba dozvole **Suradnik za podatke blobova pohrane** na računu Azure Data Lake Storage druge generacije na kojem su podaci smješteni i povezani s radnim prostorom servisa Azure Synapse. Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identitet kojim upravlja radni prostor servisa Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* treba dozvole **Suradnik za podatke blobova pohrane** na računu Azure Data Lake Storage druge generacije na kojem su podaci smješteni i povezani s radnim prostorom servisa Azure Synapse. Saznajte više o [korištenju portala Azure za dodjelu uloge servisa Azure za pristup blobu i podacima u redu čekanja](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama Suradnik za podatke blobova pohrane](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- U radnom prostoru servisa Azure Synapse, *upravitelj usluge za uvide u ciljne skupine* treba dodijeljenu ulogu **Administrator za Synapse**. Dodatne informacije potražite u odjeljku [Kako postaviti kontrolu pristupa za vaš radni prostor servisa Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Postavljanje veze i izvoz u Azure Synapse

### <a name="configure-a-connection"></a>Konfiguracija veze

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **Analitika servisa Azure Synapse** ili odaberite **Postavi** na pločici **Analitika servisa Azure Synapse** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju Zaslonski naziv. Naziv i vrsta veze opisuju ovu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Odaberite ili potražite pretplatu u kojoj želite koristiti podatke Customer Insights. Čim se odabere pretplata, možete odabrati i **Radni prostor**, **Račun za pohranu** i **Spremnik**.

1. Odaberite **Spremi** da biste spremili vezu.

### <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Dodatne informacije potražite u odjeljku [dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, ddaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka **Analitika servisa Azure Synapse**. Ako ne vidite naziv ovog odjeljka, nema dostupnih [veza](connections.md) ove vrste.

1. Navedite prepoznatljiv **zaslonski naziv** za vaš izvoz i **naziv baze podataka**.

1. Odaberite koje entitete želite izvesti u Analitiku servisa Azure Synapse.
   > [!NOTE]
   > Izvori podataka temeljeni na [Mapi Common Data Model](connect-common-data-model.md) nisu podržani.

2. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Ažuriranje izvoza

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Uredi** na izvozu koji želite ažurirati.

   - **Dodajte** ili **uklonite** entitete iz odabira. Ako se entiteti uklone iz odabira, neće se izbrisati iz baze podataka analitike servisa Synapse. Međutim, buduća osvježavanja podataka neće ažurirati uklonjene entitete u toj bazi podataka.

   - **Promjena naziva baze podataka** stvara novu bazu podataka analitike servisa Synapse. Baza podataka s nazivom koji je ranije konfiguriran neće primati ažuriranja u budućim osvježavanjima.
