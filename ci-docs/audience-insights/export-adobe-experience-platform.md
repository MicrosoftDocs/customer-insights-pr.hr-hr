---
title: Izvoz podataka servisa Customer Insights u Adobe Experience Platform
description: Saznajte kako koristiti segmente uvida u ciljnu skupinu u servisu Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596260"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Korištenje segmenata servisa Customer Insights u servisu Adobe Experience Platform (pretpregled)

Možda ste kao korisnik uvida u ciljnu skupinu za Dynamics 365 Customer Insights stvorili segmente kako biste svoje marketinške kampanje učinili učinkovitijim ciljanjem relevantnih ciljnih skupina. Da biste koristili segment iz uvida u ciljnu skupinu u servisu Adobe Experience Platform i aplikacijama kao što je Adobe Campaign Standard, morate slijediti nekoliko koraka navedenih u ovom članku.

:::image type="content" source="media/AEP-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a>Preduvjeti

-   Licenca sustava Dynamics 365 Customer Insights
-   Licenca za Adobe Experience Platform
-   Licenca za Adobe Campaign Standard
-   Račun za Azure spremište blobova

## <a name="campaign-overview"></a>Pregled kampanje

Da biste bolje razumjeli kako možete koristiti segmente iz uvida u ciljnu skupinu u servisu Adobe Experience Platform, pogledajmo fiktivni primjer kampanje.

Pretpostavimo da vaša tvrtka nudi mjesečnu uslugu zasnovanu na pretplati vašim klijentima u Sjedinjenim Državama. Želite identificirati klijente čije pretplate trebaju biti obnovljene u sljedećih osam dana, ali koji još nisu obnovili pretplatu. Da biste zadržali te klijente, želite im poslati promotivnu ponudu putem e-pošte koristeći Adobe Experience Platform.

U ovom primjeru želimo jednom provesti promotivnu kampanju putem e-pošte. Ovaj članak ne pokriva slučaj upotrebe za provođenje kampanje više puta.

## <a name="identify-your-target-audience"></a>Identificiranje ciljne skupine

U našem scenariju pretpostavljamo da su adrese e-pošte klijenata dostupne u uvidima u ciljnu skupinu i analizirane su njihove promotivne preferencije kako bi se identificirali članovi segmenta.

[Segment koji ste definirali u uvidima u ciljnu skupinu](segments.md) se zove **ChurnProneCustomers** i tim klijentima planirate poslati promotivnu e-poštu.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimka zaslona sa stranicom segmenata sa stvorenim segmentom ChurnProneCustomers.":::

E-pošta s ponudom koju želite poslati sadržavat će ime, prezime i datum završetka pretplate klijenta. Ona obavještava klijente o popustu koji će dobiti ako obnove pretplatu prije nego što završi.

## <a name="export-your-target-audience"></a>Izvoz ciljne skupine

Nakon što identificiramo našu ciljnu skupinu, možemo konfigurirati izvoz iz uvida u ciljnu skupinu na račun za Azure spremište blobova.

1. U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.

1. Na pločici **Azure spremište blobova** odaberite **Postavljanje**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Pločica za konfiguraciju za Azure spremište blobova.":::

1. Navedite **zaslonski naziv** za ovo novo odredište izvoza, a zatim unesite **Naziv računa**, **Ključ računa** i **Spremnik** računa za Azure spremište blobova na koji želite izvesti segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimka zaslona konfiguracije računa za pohranu. "::: 

   - Da biste saznali više o pronalaženju imena i ključa računa spremišta blobova platforme Azure, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](/azure/storage/common/storage-account-manage).

   - Pogledajte kako stvoriti spremnik [Stvaranje spremnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Odaberite **Dalje**.

1. Odaberite segment koji želite izvesti. U ovom primjeru je to **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimka zaslona korisničkog sučelja za odabir segmenta s odabranim segmentom ChurnProneCustomers.":::

1. Odaberite **Spremi**.

Nakon spremanja odredišta izvoza, pronaći ćete ga u odjeljku **Administrator** > **Izvozi** > **Moja odredišta izvoza**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Snimka zaslona s istaknutim popisom izvoza i uzorkom segmenta.":::

Sada možete [izvesti segment na zahtjev](export-destinations.md#export-data-on-demand). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md).

> [!NOTE]
> Provjerite je li broj zapisa u izvezenom segmentu unutar dopuštenog ograničenja vaše licence za Adobe Campaign Standard.

Izvezeni podaci pohranjeni su u spremniku Azure spremište blobova koji ste ranije konfigurirali. Sljedeća putanja mape stvara se automatski u vašem spremniku:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Primjer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*Model.json* za izvezene entitete nalazi se razini *%ExportDestinationName%*.

Primjer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definiranje Podatkovnog modela iskustva (XDM) u servisu Adobe Experience Platform

Prije nego što se izvezeni podaci iz uvida u ciljnu skupinu mogu upotrijebiti u servisu Adobe Experience Platform, moramo definirati shemu Podatkovnog modela iskustva i [konfigurirati podatke za profil klijenta u stvarnom vremenu](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Saznajte [što je XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) i usvojite [osnove sastavljanja sheme](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Uvoz podataka u Adobe Experience Platform

Sad kad je sve na svom mjestu, trebamo uvesti pripremljene podatke o ciljnim skupinama iz uvida u ciljnu skupinu u Adobe Experience Platform.

Najprije [stvorite izvornu vezu za Azure spremište blobova](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Nakon definiranja izvorne veze, [konfigurirajte tok podataka](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) za skup veza za pohranu u oblaku za uvoz rezultata segmenta iz uvida u ciljnu skupinu u Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Stvaranje ciljne skupine u servisu Adobe Campaign Standard

Za slanje e-pošte za ovu kampanju koristit ćemo Adobe Campaign Standard. Nakon uvoza podataka u Adobe Experience Platform, trebamo [stvoriti ciljnu skupinu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) u servisu Adobe Campaign Standard koristeći podatke u servisu Adobe Experience Platform.

Saznajte kako [koristiti sastavljač segmenata](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) u servisu Adobe Campaign Standard za definiranje ciljne skupine na temelju podataka u servisu Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Stvaranje i slanje e-pošte pomoću servisa Adobe Campaign Standard

Stvorite sadržaj e-pošte, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoju poruku e-pošte.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ogledna poruka e-pošte s ponudom za obnovu iz servisa Adobe Campaign Standard.":::