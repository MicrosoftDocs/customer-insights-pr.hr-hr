---
title: Izvoz segmenata uvida kupaca u Adobe standard kampanje (pretpregled)
description: Saznajte kako koristiti segmente Customer Insights u aplikaciji Adobe Standard kampanje.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 9915591cd969bf825f5d1669de43ed4f9953f898
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082340"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Izvoz segmenata uvida kupaca u Adobe standard kampanje (pretpregled)

Kao korisnik Dynamics 365 Customer Insights sustava možda ste stvorili segmente kako biste svoje marketinške kampanje učinili učinkovitijima ciljajući relevantnu publiku. Da biste koristili segment iz Customer Insights Adobe Experience Platform u aplikacijama i aplikacijama kao što je Adobe Standard kampanje, morate slijediti nekoliko koraka navedenih u ovom članku.

:::image type="content" source="media/ACS-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a>Preduvjeti

- Licenca sustava Dynamics 365 Customer Insights
- Licenca za Adobe Campaign Standard
- Račun za Azure spremište blobova

## <a name="campaign-overview"></a>Pregled kampanje

Da biste bolje razumjeli kako možete koristiti segmente iz customer insights u Adobe Experience Platform sustavu, pogledajmo izmišljenu oglednu kampanju.

Pretpostavimo da vaša tvrtka nudi mjesečnu uslugu zasnovanu na pretplati vašim klijentima u Sjedinjenim Državama. Želite identificirati klijente čije pretplate trebaju biti obnovljene u sljedećih osam dana, ali koji još nisu obnovili pretplatu. Da biste zadržali te klijente, želite im putem e-pošte poslati promotivnu ponudu koristeći se alatom Adobe Campaign Standard.

U ovom primjeru želimo jednom provesti promotivnu kampanju putem e-pošte. Ovaj članak ne pokriva slučaj upotrebe za provođenje kampanje više puta. Međutim, uvidi u kupce i Adobe standard kampanje mogu se konfigurirati tako da rade i za scenarij ponavljajuće kampanje.

## <a name="identify-your-target-audience"></a>Identificiranje ciljne skupine

U našem scenariju pretpostavljamo da su adrese e-pošte kupaca dostupne u sustavu i da su analizirane njihove promotivne preferencije kako bi se identificirali članovi segmenta.

Segment koji [ste definirali u Customer Insights](segments.md) zove se **ChurnProneCustomers i planirate** tim kupcima poslati promociju e-pošte.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimka zaslona sa stranicom segmenata sa stvorenim segmentom ChurnProneCustomers.":::

E-pošta s ponudom koju želite poslati sadržavat će ime, prezime i datum završetka pretplate klijenta. Ona obavještava klijente o popustu koji će dobiti ako obnove pretplatu prije nego što završi.

## <a name="export-your-target-audience"></a>Izvoz ciljne skupine

### <a name="configure-a-connection"></a>Konfiguracija veze

S utvrđenim ciljnim publika možemo konfigurirati izvoz na račun servisa Azure Blob Storage.

1. U odjeljku Customer Insights otvorite **Administratorske** > **veze**.

1. Odaberite **Dodaj vezu**, a zatim **Adobe Campaign** da biste konfigurirali vezu ili odaberite **Postavi** na pločici **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfiguracijska pločica za Adobe Campaign Standard.":::

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Unesite **Naziv računa**, **Ključ računa** i **Spremnik** računa spremnika za pohranu bloba za Azure na koji želite izvesti segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimka zaslona konfiguracije računa za pohranu. "::: 

   - Da biste saznali više o pronalaženju imena i ključa računa spremišta blobova platforme Azure, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](/azure/storage/common/storage-account-manage).

   - Pogledajte kako stvoriti spremnik [Stvaranje spremnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Odaberite **Spremi** da biste završili vezu.

### <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, ddaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Adobe Campaign. Ako ne vidite naziv ovog odjeljka, tada vam nisu dostupne veze ove vrste.

1. Odaberite segment koji želite izvesti. U ovom primjeru je to **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimka zaslona korisničkog sučelja za odabir segmenta s odabranim segmentom ChurnProneCustomers.":::

1. Odaberite **Dalje**.

1. Sada mapiramo **polja Izvor** iz segmenta Uvidi kupaca do **naziva ciljnih** polja u shemi Adobe profila Standard kampanje.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Preslikavanje polja za poveznik alata Adobe Campaign Standard.":::

   Ako želite dodati još atributa, odaberite **Dodaj atribut**. Ciljni naziv može se razlikovati od naziva izvorišnog polja tako da i dalje možete mapirati izlaz segmenta iz Customer Insights u Adobe Standard kampanje ako polja nemaju isti naziv u ta dva sustava.

   > [!NOTE]
   > Adresa e-pošte koristi se kao polje identiteta, ali možete koristiti bilo koji drugi identifikator iz korisničkog profila za mapiranje podataka u Adobe Standard kampanje.

1. Odaberite **Spremi**.

Nakon spremanja izvoznog odredišta pronaći ćete ga na **Podaci** > **Izvozi**.

Sada možete [izvesti segment na zahtjev](export-destinations.md#run-exports-on-demand). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md).

> [!NOTE]
> Provjerite je li količina zapisa u izvezenom segmentu unutar dopuštenog ograničenja vaše licence za Adobe Campaign Standard.

Izvezeni podaci pohranjeni su u spremniku Azure spremište blobova koji ste ranije konfigurirali. Sljedeća putanja mape stvara se automatski u vašem spremniku:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Primjer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfiguriranje alata Adobe Campaign Standard

Izvezeni segmenti sadrže stupce koje ste odabrali prilikom definiranja odredišta izvoza u prethodnom koraku. Ti se podaci mogu koristiti za [izradu profila u alatu Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Za korištenje segmenta u alatu Adobe Campaign Standard moramo proširiti shemu profila u alatu Adobe Campaign Standard tako da uključuje dva dodatna polja. Naučite kako [proširite resurs profila](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) novim poljima u alatu Adobe Campaign Standard.

U našem primjeru ta su polja *Naziv segmenta i Datum segmenta (neobavezno)*.

Tim ćemo se poljima koristiti za identifikaciju profila u alatu Adobe Campaign Standard koje želimo ciljati za ovu kampanju.

Ako u alatu Adobe Campaign Standard nema drugih zapisa osim onih koje ćete uvesti, možete preskočiti ovaj korak.

## <a name="import-data-into-adobe-campaign-standard"></a>Uvoz podataka u alat Adobe Campaign Standard

Sada kada je sve na svom mjestu, moramo uvesti pripremljene publika podatke iz Customer Insightsa u Adobe Standard kampanje kako bismo stvorili profile. Naučite [kako uvesti profile u alat Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) pomoću tijeka rada.

Tijek rada za uvoz na donjoj slici konfiguriran je za izvođenje svakih osam sati i traženje izvezenih segmenata Customer Insights (.csv datoteke u servisu Azure Blob Storage). Tijek rada izdvaja sadržaj .csv datoteke u navedenom redoslijedu stupaca. Ovaj tijek rada izgrađen je za obavljanje osnovnih postupaka rješavanja pogrešaka te kako biste bili sigurni da svaki zapis ima adresu e-pošte prije dodavanja podatka u alat Adobe Campaign Standard. Tijek rada također izdvaja naziv segmenta iz naziva datoteke prije dodavanja u podatke profila alata Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Snimka zaslona tijeka rada uvoza korisničkog sučelja alata Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Dohvaćanje ciljne skupine u alatu Adobe Campaign Standard

Nakon što se podaci uvezu u alat Adobe Campaign Standard, [možete izraditi tijek rada](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [raditi upite](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) za kupce na temelju *Naziva segmenta* i *Datuma segmenta* da biste odabrali profile identificirane za našu oglednu kampanju.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Izrada i slanje e-pošte pomoću alata Adobe Campaign Standard

Stvorite sadržaj e-pošte, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoju poruku e-pošte.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ogledna poruka e-pošte s ponudom za obnovu iz alata Adobe Campaign Standard.":::
