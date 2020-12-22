---
title: Obogaćivanje pomoću SFTP prilagođenog uvoza
description: Opće informacije o obogaćivanju SFTP prilagođenog uvoza.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568417"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="eb0fe-103">Obogaćivanje profila klijenata pomoću prilagođenih podataka (pretpregled)</span><span class="sxs-lookup"><span data-stu-id="eb0fe-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="eb0fe-104">Prilagođeni uvoz Protokola sigurnog prijenosa datoteka (SFTP) omogućava vam uvoz podataka koji ne moraju proći kroz postupak objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="eb0fe-105">To je fleksibilan, siguran i jednostavan način unosa podataka.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="eb0fe-106">SFTP prilagođeni uvoz može se koristiti u kombinaciji sa [SFTP izvozom](export-sftp.md) koji vam omogućava izvoz podataka profila klijenata potrebnih za obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="eb0fe-107">Podaci se zatim mogu obrađivati i obogaćivati, a SFTP prilagođeni uvoz može se koristiti za vraćanje obogaćenih podataka u mogućnost uvida u ciljnu skupinu usluge Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eb0fe-108">Preduvjeti</span><span class="sxs-lookup"><span data-stu-id="eb0fe-108">Prerequisites</span></span>

<span data-ttu-id="eb0fe-109">Da biste konfigurirali SFTP prilagođeni uvoz, moraju biti ispunjeni sljedeći preduvjeti:</span><span class="sxs-lookup"><span data-stu-id="eb0fe-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="eb0fe-110">Imate korisničke vjerodajnice (korisničko ime i lozinku) za SFTP lokaciju podataka koji će se uvoziti.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="eb0fe-111">Imate URL i broj priključka (obično 22) za STFP glavno računalo.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="eb0fe-112">Imate naziv datoteke i mjesto datoteke koja će se uvesti na SFTP glavnom računalu.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="eb0fe-113">Postoji *model.json* datoteka koja specificira shemu za podatke koje treba uvesti.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="eb0fe-114">Ova datoteka mora biti u istom direktoriju kao i datoteka za uvoz.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="eb0fe-115">Imate dozvolu [administratora](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="eb0fe-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="eb0fe-116">Konfiguracija</span><span class="sxs-lookup"><span data-stu-id="eb0fe-116">Configuration</span></span>

1. <span data-ttu-id="eb0fe-117">Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="eb0fe-118">Na **pločici SFTP prilagođenog uvoza** odaberite **Obogaćivanje mojih podataka**.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="eb0fe-119">![Pločica SFTP prilagođenog uvoza](media/SFTP_Custom_Import_tile.png "Pločica SFTP prilagođenog uvoza")</span><span class="sxs-lookup"><span data-stu-id="eb0fe-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="eb0fe-120">Odaberite **Početak** i navedite vjerodajnice i adresu za SFTP poslužitelj.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="eb0fe-121">Na primjer, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="eb0fe-122">Unesite naziv datoteke koja sadrži podatke i put do datoteke na SFTP poslužitelju ako nije u korijenskoj mapi.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="eb0fe-123">Potvrdite sve unose odabirom stavke **Povezivanje s prilagođenim uvozom**.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="eb0fe-124">![Potpaleta konfiguracije SFTP prilagođenog uvoza](media/SFTP_Custom_Import_Configuration_flyout.png "Potpaleta konfiguracije SFTP prilagođenog uvoza")</span><span class="sxs-lookup"><span data-stu-id="eb0fe-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="eb0fe-125">Definiranje mapiranja polja</span><span class="sxs-lookup"><span data-stu-id="eb0fe-125">Defining field mappings</span></span> 

<span data-ttu-id="eb0fe-126">Direktorij koji sadrži datoteku koju treba uvesti na SFTP poslužitelj mora sadržavati i *model.json* datoteku.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="eb0fe-127">Ova datoteka definira shemu koja će se koristiti za uvoz podataka.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="eb0fe-128">Shema mora koristiti [Common Data Model](https://docs.microsoft.com/common-data-model/) za određivanje mapiranja polja.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="eb0fe-129">Jednostavan primjer model.json datoteke izgleda ovako:</span><span class="sxs-lookup"><span data-stu-id="eb0fe-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="eb0fe-130">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="eb0fe-130">Enrichment results</span></span>

<span data-ttu-id="eb0fe-131">Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="eb0fe-132">Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eb0fe-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="eb0fe-133">Vrijeme obrade ovisit će o veličini podataka koji se uvoze i vezi sa SFTP poslužiteljem.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="eb0fe-134">Nakon završetka postupka obogaćivanja, svoje tek uvezene prilagođene podatke obogaćivanja možete pregledati u odjeljku **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="eb0fe-135">Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="eb0fe-136">Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="eb0fe-137">Sljedeći koraci</span><span class="sxs-lookup"><span data-stu-id="eb0fe-137">Next steps</span></span>

<span data-ttu-id="eb0fe-138">Nadogradite na svoje obogaćene podatke o klijentu.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="eb0fe-139">Stvorite [segmente](segments.md) i [mjere](measures.md) i [izvezite podatke](export-destinations.md) kako biste svojim klijentima ponudili personalizirana iskustva.</span><span class="sxs-lookup"><span data-stu-id="eb0fe-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


