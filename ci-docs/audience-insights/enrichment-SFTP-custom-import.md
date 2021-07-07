---
title: Obogaćivanje pomoću SFTP prilagođenog uvoza
description: Opće informacije o obogaćivanju SFTP prilagođenog uvoza.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304641"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="47bc4-103">Obogaćivanje profila klijenata pomoću prilagođenih podataka (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="47bc4-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="47bc4-104">Prilagođeni uvoz Protokola sigurnog prijenosa datoteka (SFTP) omogućava vam uvoz podataka koji ne moraju proći kroz postupak objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="47bc4-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="47bc4-105">To je fleksibilan, siguran i jednostavan način unosa podataka.</span><span class="sxs-lookup"><span data-stu-id="47bc4-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="47bc4-106">SFTP prilagođeni uvoz može se koristiti u kombinaciji sa [SFTP izvozom](export-sftp.md) koji vam omogućava izvoz podataka profila klijenata potrebnih za obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="47bc4-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="47bc4-107">Podaci se zatim mogu obraditi i obogatiti, a SFTP prilagođeni uvoz može se koristiti za vraćanje obogaćenih podataka u sposobnost uvida publike značajke Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="47bc4-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="47bc4-108">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="47bc4-108">Prerequisites</span></span>

<span data-ttu-id="47bc4-109">Da biste konfigurirali SFTP prilagođeni uvoz, moraju biti ispunjeni sljedeći preduvjeti:</span><span class="sxs-lookup"><span data-stu-id="47bc4-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="47bc4-110">Imate naziv datoteke i lokaciju (putanju) do datoteke koju treba uvesti na SFTP host.</span><span class="sxs-lookup"><span data-stu-id="47bc4-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="47bc4-111">Postoji datoteka *model.json* koja navodi [shemu Common Data Model](/common-data-model/) za podatke koji se trebaju uvesti.</span><span class="sxs-lookup"><span data-stu-id="47bc4-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="47bc4-112">Ova datoteka mora biti u istom direktoriju kao i datoteka za uvoz.</span><span class="sxs-lookup"><span data-stu-id="47bc4-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="47bc4-113">Administrator je već konfigurirao vezu SFTP *ili* imate [administratorske](permissions.md#administrator) dozvole.</span><span class="sxs-lookup"><span data-stu-id="47bc4-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="47bc4-114">Trebat će vam vjerodajnice korisnika, URL i broj priključka za lokaciju SFTP odakle želite uvesti podatke.</span><span class="sxs-lookup"><span data-stu-id="47bc4-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="47bc4-115">Konfiguracija uvoza</span><span class="sxs-lookup"><span data-stu-id="47bc4-115">Configure the import</span></span>

1. <span data-ttu-id="47bc4-116">Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.</span><span class="sxs-lookup"><span data-stu-id="47bc4-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="47bc4-117">Na **Pločici za prilagođeni uvoz SFTP** odaberite **Obogati moje podatke** i zatim odaberite **Započni**.</span><span class="sxs-lookup"><span data-stu-id="47bc4-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Pločica za prilagođeni uvoz SFTP.":::

1. <span data-ttu-id="47bc4-119">Odaberite [vezu](connections.md) s padajućeg popisa.</span><span class="sxs-lookup"><span data-stu-id="47bc4-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="47bc4-120">Ako nijedna veza nije dostupna, obratite se administratoru.</span><span class="sxs-lookup"><span data-stu-id="47bc4-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="47bc4-121">Ako ste administrator, vezu možete stvoriti odabirom **Dodaj vezu** pa odabirom **SFTP prilagođeni uvoz** s padajućeg popisa.</span><span class="sxs-lookup"><span data-stu-id="47bc4-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="47bc4-122">Odaberite **Poveži se s prilagođenim uvozom** za potvrdu odabrane veze.</span><span class="sxs-lookup"><span data-stu-id="47bc4-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="47bc4-123">Odaberite **Dalje** pa unesite podatke **Putanja** i **Naziv datoteke** za podatkovnu datoteku koju želite uvesti.</span><span class="sxs-lookup"><span data-stu-id="47bc4-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Snimka zaslona prilikom unosa lokacije podataka.":::

1. <span data-ttu-id="47bc4-125">Odaberite **Sljedeće** i navedite naziv za obogaćivanje i naziv za izlazni entitet.</span><span class="sxs-lookup"><span data-stu-id="47bc4-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="47bc4-126">Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.</span><span class="sxs-lookup"><span data-stu-id="47bc4-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="47bc4-127">Konfiguriranje veze za prilagođeni uvoz SFTP</span><span class="sxs-lookup"><span data-stu-id="47bc4-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="47bc4-128">Morate biti administrator da biste konfigurirali veze.</span><span class="sxs-lookup"><span data-stu-id="47bc4-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="47bc4-129">Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćivanja *ili* idite na **Admin** > **Veze** i odaberite **Postavi** na pločici Prilagođeni uvoz.</span><span class="sxs-lookup"><span data-stu-id="47bc4-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="47bc4-130">Unesite naziv za vezu u dijaloški okvir **Zaslonski naziv**.</span><span class="sxs-lookup"><span data-stu-id="47bc4-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="47bc4-131">Unesite važeće korisničko ime, lozinku i URL hosta za SFTP poslužitelj na kojem se nalaze podaci koji se uvoze.</span><span class="sxs-lookup"><span data-stu-id="47bc4-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="47bc4-132">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="47bc4-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="47bc4-133">Odaberi **Potvrdi** za provjeru valjanosti konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="47bc4-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="47bc4-134">Nakon završetka provjere vezu možete spremiti odabirom **Spremi**.</span><span class="sxs-lookup"><span data-stu-id="47bc4-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="47bc4-135">![Stranica konfiguracije veze na Experian](media/enrichment-SFTP-connection.png "Stranica konfiguracije veze na Experian")</span><span class="sxs-lookup"><span data-stu-id="47bc4-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="47bc4-136">Definiranje mapiranja polja</span><span class="sxs-lookup"><span data-stu-id="47bc4-136">Defining field mappings</span></span> 

<span data-ttu-id="47bc4-137">Direktorij koji sadrži datoteku koju treba uvesti na SFTP poslužitelj mora sadržavati i *model.json* datoteku.</span><span class="sxs-lookup"><span data-stu-id="47bc4-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="47bc4-138">Ova datoteka definira shemu koja će se koristiti za uvoz podataka.</span><span class="sxs-lookup"><span data-stu-id="47bc4-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="47bc4-139">Shema mora koristiti [Common Data Model](/common-data-model/) za određivanje mapiranja polja.</span><span class="sxs-lookup"><span data-stu-id="47bc4-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="47bc4-140">Jednostavan primjer model.json datoteke izgleda ovako:</span><span class="sxs-lookup"><span data-stu-id="47bc4-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="47bc4-141">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="47bc4-141">Enrichment results</span></span>

<span data-ttu-id="47bc4-142">Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake.</span><span class="sxs-lookup"><span data-stu-id="47bc4-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="47bc4-143">Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="47bc4-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="47bc4-144">Vrijeme obrade ovisit će o veličini podataka koji se uvoze i vezi sa SFTP poslužiteljem.</span><span class="sxs-lookup"><span data-stu-id="47bc4-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="47bc4-145">Nakon završetka postupka obogaćivanja, svoje tek uvezene prilagođene podatke obogaćivanja možete pregledati u odjeljku **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="47bc4-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="47bc4-146">Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="47bc4-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="47bc4-147">Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.</span><span class="sxs-lookup"><span data-stu-id="47bc4-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="47bc4-148">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="47bc4-148">Next steps</span></span>

<span data-ttu-id="47bc4-149">Nadogradite na svoje obogaćene podatke o klijentu.</span><span class="sxs-lookup"><span data-stu-id="47bc4-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="47bc4-150">Stvorite [segmente](segments.md) i [mjere](measures.md) pa [izvezite podatke](export-destinations.md) radi pružanja personaliziranih iskustava svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="47bc4-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
