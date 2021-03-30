---
title: Izvoz podataka servisa Customer Insights u Adobe Campaign Standard
description: Saznajte kako koristiti segmente uvida u ciljnu skupinu u servisu Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596306"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Korištenje segmenata servisa Customer Insights u servisu Adobe Campaign Standard (pretpregled)

Možda ste kao korisnik uvida u ciljnu skupinu za Dynamics 365 Customer Insights stvorili segmente kako biste svoje marketinške kampanje učinili učinkovitijim ciljanjem relevantnih ciljnih skupina. Da biste koristili segment iz uvida u ciljnu skupinu u servisu Adobe Experience Platform i aplikacijama kao što je Adobe Campaign Standard, morate slijediti nekoliko koraka navedenih u ovom članku.

:::image type="content" source="media/ACS-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a>Preduvjeti

-   Licenca sustava Dynamics 365 Customer Insights
-   Licenca za Adobe Campaign Standard
-   Račun za Azure spremište blobova

## <a name="campaign-overview"></a>Pregled kampanje

Da biste bolje razumjeli kako možete koristiti segmente iz uvida u ciljnu skupinu u servisu Adobe Experience Platform, pogledajmo fiktivni primjer kampanje.

Pretpostavimo da vaša tvrtka nudi mjesečnu uslugu zasnovanu na pretplati vašim klijentima u Sjedinjenim Državama. Želite identificirati klijente čije pretplate trebaju biti obnovljene u sljedećih osam dana, ali koji još nisu obnovili pretplatu. Da biste zadržali te klijente, želite im poslati promotivnu ponudu putem e-pošte koristeći Adobe Campaign Standard.

U ovom primjeru želimo jednom provesti promotivnu kampanju putem e-pošte. Ovaj članak ne pokriva slučaj upotrebe za provođenje kampanje više puta. Međutim, uvidi u ciljnu skupinu i Adobe Campaign Standard mogu se konfigurirati i za rad s ponovljenim scenarijem kampanje.

## <a name="identify-your-target-audience"></a>Identificiranje ciljne skupine

U našem scenariju pretpostavljamo da su adrese e-pošte klijenata dostupne u uvidima u ciljnu skupinu i analizirane su njihove promotivne preferencije kako bi se identificirali članovi segmenta.

[Segment koji ste definirali u uvidima u ciljnu skupinu](segments.md) se zove **ChurnProneCustomers** i tim klijentima planirate poslati promotivnu e-poštu.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimka zaslona sa stranicom segmenata sa stvorenim segmentom ChurnProneCustomers.":::

E-pošta s ponudom koju želite poslati sadržavat će ime, prezime i datum završetka pretplate klijenta. Ona obavještava klijente o popustu koji će dobiti ako obnove pretplatu prije nego što završi.

## <a name="export-your-target-audience"></a>Izvoz ciljne skupine

Nakon što identificiramo našu ciljnu skupinu, možemo konfigurirati izvoz iz uvida u ciljnu skupinu na račun za Azure spremište blobova.

1. U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.

1. Na pločici **Adobe Campaign** odaberite **Postavljanje**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Pločica za konfiguraciju za Adobe Campaign Standard.":::

1. Navedite **zaslonski naziv** za ovo novo odredište izvoza, a zatim unesite **Naziv računa**, **Ključ računa** i **Spremnik** računa za Azure spremište blobova na koji želite izvesti segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimka zaslona konfiguracije računa za pohranu. "::: 

   - Da biste saznali više o pronalaženju imena i ključa računa spremišta blobova platforme Azure, pogledajte [Upravljanje postavkama računa za pohranu na portalu Azure](/azure/storage/common/storage-account-manage).

   - Pogledajte kako stvoriti spremnik [Stvaranje spremnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Odaberite **Dalje**.

1. Odaberite segment koji želite izvesti. U ovom primjeru je to **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimka zaslona korisničkog sučelja za odabir segmenta s odabranim segmentom ChurnProneCustomers.":::

1. Odaberite **Dalje**.

1. Sada mapiramo polja **Izvor** od segmenta uvida u ciljnu skupinu do naziva polja **Cilj** u shemi profila servisa Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapiranje polja za poveznik Adobe Campaign Standard.":::

   Ako želite dodati još atributa, odaberite **Dodaj atribut**. Naziv cilja može se razlikovati od naziva izvornog polja, tako da i dalje možete mapirati izlaz segmenta iz uvida u ciljnu skupinu u Adobe Campaign Standard ako polja nemaju isti naziv u dva sustava.

   > [!NOTE]
   > Adresa e-pošte koristi se kao polje identiteta, ali možete upotrijebiti bilo koji drugi identifikator iz vašeg profila klijenta uvida u ciljnu skupinu za mapiranje podataka u Adobe Campaign Standard.

1. Odaberite **Spremi**.

Nakon spremanja odredišta izvoza, pronaći ćete ga u odjeljku **Administrator** > **Izvozi** > **Moja odredišta izvoza**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Snimka zaslona s istaknutim popisom izvoza i uzorkom segmenta.":::

Sada možete [izvesti segment na zahtjev](export-destinations.md#export-data-on-demand). Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md).

> [!NOTE]
> Provjerite je li broj zapisa u izvezenom segmentu unutar dopuštenog ograničenja vaše licence za Adobe Campaign Standard.

Izvezeni podaci pohranjeni su u spremniku Azure spremište blobova koji ste ranije konfigurirali. Sljedeća putanja mape stvara se automatski u vašem spremniku:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Primjer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfiguracija servisa Adobe Campaign Standard

Kada se segment izveze iz uvida u ciljnu skupinu, on sadrži stupce koje ste odabrali prilikom definiranja odredišta izvoza u prethodnom koraku. Ti se podaci mogu koristiti za [stvaranje profila u servisu Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Da bismo koristili segment u servisu Adobe Campaign Standard, moramo proširiti shemu profila u servisu Adobe Campaign Standard tako da uključuje dva dodatna polja. Saznajte kako [proširiti resurs profila](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) s novim poljima u servisu Adobe Campaign Standard.

U našem primjeru ta su polja *Naziv segmenta i Datum segmenta (neobavezno).*

Pomoću ovih polja identificirat ćemo profile u servisu Adobe Campaign Standard koje želimo ciljati za ovu kampanju.

Ako u servisu Adobe Campaign Standard ne postoje drugi zapisi, osim onoga što ćete uvoziti, možete preskočiti ovaj korak.

## <a name="import-data-into-adobe-campaign-standard"></a>Uvoz podataka u Adobe Campaign Standard

Sad kad je sve na svom mjestu, trebamo uvesti pripremljene podatke o ciljnim skupinama iz uvida u ciljnu skupinu u Adobe Campaign Standard radi stvaranja profila. Saznajte [kako uvesti profile u Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) koristeći tijek rada.

Tijek rada uvoza na slici ispod konfiguriran je za pokretanje svakih 8 sati i traži izvezene segmente uvida u ciljnu skupinu (.csv datoteka u Azure spremištu blobova). Tijek rada izdvaja sadržaj .csv datoteke u navedenom redoslijedu stupaca. Ovaj je tijek rada napravljen za izvođenje osnovne obrade pogreški i osigurava da svaki zapis ima adresu e-pošte prije popunjavanja podacima u servisu Adobe Campaign Standard. Tijek rada također izdvaja naziv segmenta iz naziva datoteke prije dodavanja u podatke ACS profila.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Snimka zaslona tijeka rada uvoza u korisničkom sučelju servisa Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Dohvaćanje ciljne skupine u servisu Adobe Campaign Standard

Nakon što se podaci uvezu u Adobe Campaign Standard, [možete stvoriti tijek rada](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [upitati](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) klijente na temelju polja *Naziv segmenta* i *Datum segmenta* da odaberu profile koji su identificirani za našu oglednu kampanju.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Stvaranje i slanje e-pošte pomoću servisa Adobe Campaign Standard

Stvorite sadržaj e-pošte, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoju poruku e-pošte.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ogledna poruka e-pošte s ponudom za obnovu iz servisa Adobe Campaign Standard.":::