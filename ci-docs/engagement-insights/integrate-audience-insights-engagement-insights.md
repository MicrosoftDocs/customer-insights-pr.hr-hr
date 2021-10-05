---
title: Izrada veze između uvida u ciljnu skupinu i uvida u angažman
description: Izradite aktivnu vezu između uvida u ciljnu skupinu i uvida u angažman da biste omogućili dvosmjerno dijeljenje podataka.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d93a49a29c29103e189a6d4a42294c18dc28abd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/27/2021
ms.locfileid: "7559009"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Izrada veze između uvida u ciljnu skupinu i uvida u angažman

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Integracija između uvida u angažman i uvida u ciljnu skupinu povezuje okruženja iz obje mogućnosti te omogućuje dvosmjernu razmjenu podataka između njih.

Upotrijebite objedinjene profile i segmente iz uvida u ciljnu skupinu za više mogućnosti analize u uvidima u angažman. Iz uvida u angažman izvezite događaje koji imaju visoku poslovnu vrijednost. Pomoću ovih događaja dodajte podatke u objedinjene profile u uvidima u ciljnu skupinu.

## <a name="prerequisites"></a>Preduvjeti

- Profili uvida u ciljnu skupinu moraju se pohraniti na Azure Data Lake Storage račun koji posjedujete ili u [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash; upravljano jezero podataka. 
- Vaše okruženje uvida u ciljnu skupinu treba imati pridruženo okruženje Dataverse. I ako to okruženje koristi Dataverse i za pohranu podataka provjerite mogućnost **Omogući dijeljenje podataka** u uvidima u ciljnu skupinu. Više informacija pogledajte u [Stvaranje i konfiguriranje plaćenog okruženja u uvidima u ciljnu skupinu](../audience-insights/get-started-paid.md).
- Za okruženja uvida u angažman i uvida u ciljnu skupinu potrebne su vam administratorske dozvole.
- Povezana okruženja moraju se nalaziti u istoj zemljopisnoj regiji.

> [!NOTE]
> - Ako imate probnu verziju pretplate na uvide u ciljnu skupinu koja koristi interno upravljano data lake uvida u ciljnu skupinu, za pomoć se obratite na [pirequest@microsoft.com](mailto:pirequest@microsoft.com). 
> - Ako vaše okruženje uvida u ciljnu skupinu upotrebljava vaš vlastiti Azure Data Lake Storage za pohranu podataka, svom računu za pohranu morate dodati upravitelja usluge Azure za uvide u angažman. Pojedinosti potražite u članku [Spajanje na Azure Data Lake Storage račun upotrebom upravitelja usluge Azure za uvide u ciljnu skupinu](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Izrada veze okruženja

Vezu okruženja možete izraditi ažuriranjem postavki **Administrator** > **Okruženje** u uvidima u angažman.

**Izrada aktivne veze između uvida u ciljnu skupinu i uvida u angažman**

1. Na stranici **Administrator okruženja** odaberite karticu **Povezivanje okruženja**.

    :::image type="content" source="media/integrate1.png" alt-text="Postavite okruženje.":::

1. Odaberite **Postavljanje okruženja** u gornjem lijevom kutu ili pri dnu zaslona.

     :::image type="content" source="media/integrate2.png" alt-text="Odaberite okruženje uvida u ciljnu skupinu.":::

1. Odaberite okruženje uvida u ciljnu skupinu, a zatim odaberite **Dalje** da biste dovršili postupak. Sada možete odabrati neobavezne značajke za povezana okruženja.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Omogućavanje atributa i segmenata objedinjenih profila uvida u ciljnu skupinu

Nakon povezivanja okruženja možete odabrati neobavezne značajke za povezana okruženja. Te značajke omogućavaju atribute i segmente objedinjenih profila iz uvida u ciljnu skupinu za interaktivnu analizu podataka klijenta.

> [!IMPORTANT]
> Da bi se segmenti uvida u ciljnu skupinu prikazivali u uvidima u angažman, prvo morate [pokrenuti spajanje i nizvodne procese](../audience-insights/merge-entities.md). Nizvodni procesi važni su jer generiraju jedinstvenu tablicu koja priprema segmente uvida u ciljnu skupinu za dijeljenje s uvidima u angažman. (Ako je zakazano osvježavanje sustava, ono će automatski uključiti nizvodne procese.)

**Analiza web-podataka u uvidima u angažman**

1. Na stranici **Administrator okruženja** uključite opciju **Dijeljenje podataka iz uvida u ciljnu skupinu s uvidima u angažman**, a zatim odaberite **Dalje**.

    :::image type="content" source="media/integrate4.png" alt-text="Odaberite značajke.":::

1. Odaberite atribute objedinjenih profila koji će postati dimenzije u uvidima u angažman. (Nisu svi atributi korisne dimenzije. Na primjer, **Ime** ili **Prezime** vjerojatno vam neće biti potrebni kao atributi za analizu događaja na vašoj web-stranici.)

    :::image type="content" source="media/integrate5.png" alt-text="Priredite dimenzije.":::

   >[!NOTE]
   > Svi atributi profila uvida u ciljnu skupinu koji predstavljaju identifikatore (kao što su **ID** i **zamjenski ID**) filtriraju se iz dostupnih atributa i postaju dimenzije u uvidima u angažman.

1. Kad završite s odabirom atributa, odaberite **Dalje**.
1. Dodajte korisnike koji mogu vidjeti dimenzije i segmente profila uvida u ciljnu skupinu u uvidima u angažman.

    :::image type="content" source="media/integrate6.png" alt-text="Upravljajte pristupom podacima klijenta.":::

   > [!IMPORTANT]
   > Ako u ovom koraku izričito ne dodate korisnike, podaci će biti skriveni od korisnika u uvidima u angažman.
   > Da bi se segmenti uvida u ciljnu skupinu prikazivali u uvidima u angažman, prvo morate [pokrenuti spajanje i nizvodne procese](../audience-insights/merge-entities.md). Nizvodni procesi važni su jer generiraju jedinstvenu tablicu koja priprema segmente uvida u ciljnu skupinu za dijeljenje s uvidima u angažman. (Ako je zakazano osvježavanje sustava, ono će automatski uključiti nizvodne procese.)

1. Pregledajte svoj odabir, a zatim odaberite **Završi**.

    :::image type="content" source="media/integrate7.png" alt-text="Pregledajte postavke podataka klijenta.":::

## <a name="export-refined-events-to-audience-insights"></a>Izvoz događaja sužene pretrage u uvide o ciljnoj skupini

Nakon što izradite vezu između okruženja možete izvesti događaje sužene pretrage iz uvida o angažmanu u uvide o ciljnoj skupini i unijeti ih kao novi izvor podataka. 

Više informacije potražite u članku [Integracija web-podataka iz uvida o angažmanu s uvidima o ciljnoj publici](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
