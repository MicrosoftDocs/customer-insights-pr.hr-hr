---
title: Izvoz podataka značajke Customer Insights u Salesforce Marketing Cloud
description: Saznajte kako konfigurirati vezu i izvesti u Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 17a608a64433cdc395e0b503a42b6290db5c39ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230195"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Izvoz segmenata i ostalih podataka u Salesforce Marketing Cloud (pretpregled)

Upotrijebite podatke o klijentima na servisu Salesforce Marketing Cloud tako što ćete ih izvesti preko lokacije protokola za sigurni prijenos datoteka (SFTP).

## <a name="prerequisites-for-connection"></a>Preduvjeti za vezu

- Dostupnost SFTP hosta i odgovarajućih vjerodajnica administratora. [Kako postaviti SFTP lokacije za Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Postavljanje veze na Salesforce Marketing Cloud

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodavanje veze** pa odaberite **Salesforce Marketing Cloud** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite **Korisničko ime**, **Lozinku**, **Naziv glavnog računala** i **Mapu za izvoz** za vaš SFTP račun.

1. Odaberite **Provjeri** da biste testirali vezu.

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka SFTP. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Odaberite želite li izvesti svoje podatke **Komprimirane** ili **Nekomprimirane** i **graničnik polja** za izvezene datoteke.

1. Odaberite entitete, na primjer, segmente koje želite izvesti.

   > [!NOTE]
   > Svaki odabrani entitet podijelit će se u do pet izlaznih datoteka prilikom izvoza. 

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Uvoz podataka značajke Customer Insights sa SFTP lokacije u Salesforce Marketing Cloud

1. Stvorite [proširenja podataka na servisu Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) za uvoz podatkovne datoteke servisa Customer Insights sa SFTP lokacije.

2. [Uvoz podataka sa SFTP lokacije](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) u proširenje podataka servisa Salesforce Marketing Cloud. 

3. Postavite automatizaciju za uvoz podataka u proširenja podataka. Naučite više o [automatizacijama ispuštanja datoteka i zakazanim automatizacijama](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definirajte [automatizaciju ispuštanja datoteka](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ili  [zakazanu automatizaciju](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Evo primjera [automatizacije sa SFTP-om](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka putem SFTP-a, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da odredište za izvoz ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
