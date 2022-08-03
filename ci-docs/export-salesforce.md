---
title: Izvoz podataka u marketinški oblak salesforcea (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197029"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Izvoz podataka u marketinški oblak salesforcea (pretpregled)

Upotrijebite podatke o klijentima na servisu Salesforce Marketing Cloud tako što ćete ih izvesti preko lokacije protokola za sigurni prijenos datoteka (SFTP).

## <a name="prerequisites"></a>Preduvjeti

- Glavno [računalo SFTP-a za Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) i odgovarajuće administratorske vjerodajnice.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Postavljanje veze s marketinškim oblakom salesforcea

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim Salesforce **Marketing Cloud**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite **Korisničko ime**, **Lozinku**, **Naziv glavnog računala** i **Mapu za izvoz** za vaš SFTP račun.

1. Odaberite **Provjeri** da biste testirali vezu.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka SFTP. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. Odaberite želite li izvesti svoje podatke **Komprimirane** ili **Nekomprimirane** i **graničnik polja** za izvezene datoteke.

1. Odaberite entitete, na primjer segmente, koje želite izvesti.

   > [!NOTE]
   > Svaki odabrani entitet bit će podijeljen u najviše pet izlaznih datoteka prilikom izvoza.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Uvoz podataka značajke Customer Insights sa SFTP lokacije u Salesforce Marketing Cloud

1. Stvorite [proširenja podataka na servisu Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) za uvoz podatkovne datoteke servisa Customer Insights sa SFTP lokacije.

2. [Uvoz podataka sa SFTP lokacije](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) u proširenje podataka servisa Salesforce Marketing Cloud.

3. Postavite automatizaciju za uvoz podataka u proširenja podataka. Naučite više o [automatizacijama ispuštanja datoteka i zakazanim automatizacijama](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definirajte [automatizaciju ispuštanja datoteka](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ili  [zakazanu automatizaciju](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Evo primjera [automatizacije sa SFTP-om](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
