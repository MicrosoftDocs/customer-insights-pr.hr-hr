---
title: Izvoz segmenata uvida kupaca u Adobe standard kampanje (pretpregled)
description: Saznajte kako koristiti segmente Customer Insights u aplikaciji Adobe Standard kampanje.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195511"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Izvoz segmenata uvida kupaca u Adobe standard kampanje (pretpregled)

Izvezite segmente koji ciljaju relevantnu publiku u Adobe Standard kampanje.

:::image type="content" source="media/ACS-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a>Preduvjeti

- Standardna Adobe licenca kampanje.
- Naziv [računa i ključ računa](/azure/storage/blobs/create-data-lake-storage-account) servisa Azure Blob Storage. Upute za pronalaženje naziva i ključa potražite u članku [Upravljanje postavkama računa za pohranu na portalu servisa Azure](/azure/storage/common/storage-account-manage).
- An [Azure Blob Storage container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Pregled kampanje

Da biste bolje razumjeli kako možete koristiti segmente iz customer insights u Adobe Experience Platform sustavu, pogledajmo izmišljenu oglednu kampanju.

Pretpostavimo da vaša tvrtka nudi mjesečnu uslugu zasnovanu na pretplati vašim klijentima u Sjedinjenim Državama. Želite identificirati klijente čije pretplate trebaju biti obnovljene u sljedećih osam dana, ali koji još nisu obnovili pretplatu. Da biste zadržali te klijente, želite im putem e-pošte poslati promotivnu ponudu koristeći se alatom Adobe Campaign Standard.

U ovom primjeru želimo jednom provesti promotivnu kampanju putem e-pošte. Ovaj članak ne pokriva slučaj upotrebe za provođenje kampanje više puta. Međutim, uvidi u kupce i Adobe standard kampanje mogu se konfigurirati tako da rade i za scenarij ponavljajuće kampanje.

## <a name="identify-your-target-audience"></a>Identificiranje ciljne skupine

U našem scenariju pretpostavljamo da su adrese e-pošte kupaca dostupne u Customer Insights i da su njihove promotivne preferencije analizirane kako bi se identificirali članovi segmenta.

Segment koji [ste definirali u Customer Insights](segments.md) zove se **ChurnProneCustomers i planirate** tim kupcima poslati promociju e-pošte.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimka zaslona sa stranicom segmenata sa stvorenim segmentom ChurnProneCustomers.":::

E-pošta s ponudom koju želite poslati sadržavat će ime, prezime i datum završetka pretplate klijenta. Ona obavještava klijente o popustu koji će dobiti ako obnove pretplatu prije nego što završi.

## <a name="export-your-target-audience"></a>Izvoz ciljne skupine

### <a name="set-up-connection-to-adobe-campaign"></a>Postavljanje veze s kampanjom Adobe

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **Adobe Kampanja**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Unesite naziv** računa, **ključ** računa i **spremnik** za svoj račun za pohranu bloba.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimka zaslona konfiguracije računa za pohranu. ":::

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Spremi** da biste završili vezu.

### <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Adobe Campaign. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. Odaberite segment koji želite izvesti. U ovom primjeru je to **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimka zaslona korisničkog sučelja za odabir segmenta s odabranim segmentom ChurnProneCustomers.":::

1. Odaberite **Dalje**.

1. Mapirajte **polja Izvor** iz segmenta Uvidi kupaca do naziva ciljnih **polja** u shemi Adobe profila Standard kampanje.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Preslikavanje polja za poveznik alata Adobe Campaign Standard.":::

   Ako želite dodati još atributa, odaberite **Dodaj atribut**. Ciljni naziv može se razlikovati od naziva izvorišnog polja tako da i dalje možete mapirati izlaz segmenta iz Customer Insights u Adobe Standard kampanje ako polja nemaju isti naziv u ta dva sustava.

   > [!NOTE]
   > Adresa e-pošte koristi se kao polje identiteta, ali možete koristiti bilo koji drugi identifikator iz korisničkog profila za mapiranje podataka u Adobe Standard kampanje.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Provjerite je li količina zapisa u izvezenom segmentu unutar dopuštenog ograničenja vaše licence za Adobe Campaign Standard.

Izvezeni podaci pohranjeni su u spremniku Azure spremište blobova koji ste ranije konfigurirali. U spremniku se automatski stvara sljedeći put mape: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Primjer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfiguriranje alata Adobe Campaign Standard

Izvezeni segmenti sadrže stupce koje ste odabrali tijekom konfiguriranja izvoza. Ti se podaci mogu koristiti za [izradu profila u alatu Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Da biste koristili segment u Adobe standardu kampanje, [proširite shemu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) profila u Adobe standardu kampanje tako da uključuje dva dodatna polja.

U našem primjeru ta su polja Naziv segmenta i Datum segmenta. Tim ćemo se poljima koristiti za identifikaciju profila u alatu Adobe Campaign Standard koje želimo ciljati za ovu kampanju.

Ako u standardu Adobe kampanje nema drugih zapisa, osim onoga što ćete uvesti, preskočite ovaj korak.

## <a name="import-data-into-adobe-campaign-standard"></a>Uvoz podataka u alat Adobe Campaign Standard

Uvezite pripremljene podatke publika iz customer insights u Adobe Standard kampanje da biste [stvorili profile pomoću tijeka rada](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Tijek rada za uvoz na donjoj slici konfiguriran je za izvođenje svakih osam sati i traženje izvezenih segmenata Customer Insights (.csv datoteke u servisu Azure Blob Storage). Tijek rada izdvaja sadržaj .csv datoteke u navedenom redoslijedu stupaca. Ovaj tijek rada izgrađen je za obavljanje osnovnih postupaka rješavanja pogrešaka te kako biste bili sigurni da svaki zapis ima adresu e-pošte prije dodavanja podatka u alat Adobe Campaign Standard. Tijek rada također izdvaja naziv segmenta iz naziva datoteke prije dodavanja u podatke profila alata Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Snimka zaslona tijeka rada uvoza korisničkog sučelja alata Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Dohvaćanje ciljne skupine u alatu Adobe Campaign Standard

Nakon što se podaci uvezu u Adobe Standard kampanje, [stvorite tijek rada](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [pošaljite upit](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) kupcima na temelju naziva segmenta i datuma segmenta da biste odabrali profile koji su identificirani za našu oglednu kampanju.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Izrada i slanje e-pošte pomoću alata Adobe Campaign Standard

Stvorite sadržaj e-pošte, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoju poruku e-pošte.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ogledna poruka e-pošte s ponudom za obnovu iz alata Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
