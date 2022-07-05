---
title: Izvoz segmenata u Adobe Experience Platform (pretpregled)
description: Saznajte kako koristiti segmente Customer Insights u sustavu Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: c29b8264019669ffd954a298ce3a633c852477fa
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052502"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Izvoz segmenata u Adobe Experience Platform (pretpregled)

Kao korisnik Dynamics 365 Customer Insights sustava možda ste stvorili segmente kako biste svoje marketinške kampanje učinili učinkovitijima ciljajući relevantnu publiku. Da biste koristili segment iz Customer Insights Adobe Experience Platform u aplikacijama i aplikacijama kao što je Adobe Standard kampanje, morate slijediti nekoliko koraka navedenih u ovom članku.

:::image type="content" source="media/AEP-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a>Preduvjeti

-   Licenca sustava Dynamics 365 Customer Insights
-   Licenca sustava Adobe Experience Platform
-   Licenca za Adobe Campaign Standard
-   Račun za Azure spremište blobova

## <a name="campaign-overview"></a>Pregled kampanje

Da biste bolje razumjeli kako možete koristiti segmente iz customer insights u Adobe Experience Platform sustavu, pogledajmo izmišljenu oglednu kampanju.

Pretpostavimo da vaša tvrtka nudi mjesečnu uslugu zasnovanu na pretplati vašim klijentima u Sjedinjenim Državama. Želite identificirati klijente čije pretplate trebaju biti obnovljene u sljedećih osam dana, ali koji još nisu obnovili pretplatu. Da biste zadržali te klijente, želite im putem e-pošte poslati promotivnu ponudu koristeći se alatom Adobe Experience Platform.

U ovom primjeru želimo jednom provesti promotivnu kampanju putem e-pošte. Ovaj članak ne pokriva slučaj upotrebe za provođenje kampanje više puta.

## <a name="identify-your-target-audience"></a>Identificiranje ciljne skupine

U našem scenariju pretpostavljamo da su adrese e-pošte kupaca dostupne u Customer Insights i da su njihove promotivne preferencije analizirane kako bi se identificirali članovi segmenta.

Segment koji [ste definirali u Customer Insights](segments.md) zove se **ChurnProneCustomers i planirate** tim kupcima poslati promociju e-pošte.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimka zaslona sa stranicom segmenata sa stvorenim segmentom ChurnProneCustomers.":::

E-pošta s ponudom koju želite poslati sadržavat će ime, prezime i datum završetka pretplate klijenta. Ona obavještava klijente o popustu koji će dobiti ako obnove pretplatu prije nego što završi.

## <a name="export-your-target-audience"></a>Izvoz ciljne skupine

S identificiranim ciljnim publika možemo konfigurirati izvoz iz Customer Insights na račun za pohranu servisa Azure Blob.

### <a name="configure-a-connection"></a>Konfiguracija veze

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** pa odaberite **Azure Blob Storage** ili odaberite **Postavljanje** na pločici **Azure Blob Storage** radi konfiguriranja veze.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Pločica za konfiguraciju za Azure spremište blobova."::: 

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **Naziv računa**, **Ključ računa** i **Spremnik** za svoj račun spremnika za pohranu bloba na koji želite izvesti segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimka zaslona konfiguracije računa za pohranu. "::: 
   
    - Da biste saznali više o tome kako pronaći naziv računa apremnika za pohranu bloba i ključ računa, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](/azure/storage/common/storage-account-manage).
    - Pogledajte kako stvoriti spremnik [Stvaranje spremnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Odaberite **Spremi** da biste završili vezu. 

### <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, ddaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Spremnik za pohranu bloba za Azure. Ako ne vidite naziv ovog odjeljka, tada vam nisu dostupne veze ove vrste.

1. Odaberite segment koji želite izvesti. U ovom primjeru je to **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimka zaslona korisničkog sučelja za odabir segmenta s odabranim segmentom ChurnProneCustomers.":::

1. Odaberite **Spremi**.

Nakon spremanja izvoznog odredišta pronaći ćete ga na **Podaci** > **Izvozi**.

Sada možete [izvesti segment na zahtjev](export-destinations.md#run-exports-on-demand). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md).

> [!NOTE]
> Provjerite je li količina zapisa u izvezenom segmentu unutar dopuštenog ograničenja vaše licence za Adobe Campaign Standard.

Izvezeni podaci pohranjeni su u spremniku Azure spremište blobova koji ste ranije konfigurirali. Sljedeća putanja mape stvara se automatski u vašem spremniku:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Primjer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*Model.json* za izvezene entitete nalazi se razini *%ExportDestinationName%*.

Primjer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definiranje specifikacije Experience Data Model (XDM) u alatu Adobe Experience Platform

Prije nego što se izvezeni podaci iz Customer Insightsa mogu koristiti unutar Adobe Experience Platform, moramo definirati shemu Experience Data Model i [konfigurirati podatke za profil](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) kupaca u stvarnom vremenu.

Saznajte [što je XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) i usvojite [osnove sastavljanja sheme](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Uvoz podataka u Adobe Experience Platform

Sada kada je sve na svom mjestu, moramo uvesti pripremljene podatke publika iz Customer Insights u Adobe Experience Platform.

Najprije [stvorite izvornu vezu za Azure spremište blobova](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Nakon definiranja izvorišne veze [konfigurirajte tok](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) podataka za vezu serije pohrane u oblaku da biste uvezli izlaz segmenta iz Customer Insights u Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Izrada ciljne skupine u alatu Adobe Campaign Standard

Za slanje e-pošte za ovu kampanju upotrijebit ćemo Adobe Campaign Standard. Nakon uvoza podataka u alat Adobe Experience Platform moramo [izraditi ciljnu skupinu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) u alatu Adobe Campaign Standard koristeći se podacima iz alata Adobe Experience Platform.


Naučite kako [se koristiti sastavljačem segmenata](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) u alatu Adobe Campaign Standard za definiranje ciljne skupine na temelju podataka u alatu Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Izrada i slanje e-pošte pomoću alata Adobe Campaign Standard

Stvorite sadržaj e-pošte, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoju poruku e-pošte.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ogledna poruka e-pošte s ponudom za obnovu iz alata Adobe Campaign Standard.":::
