---
title: Obogaćivanje pomoću SFTP prilagođenog uvoza
description: Opće informacije o obogaćivanju SFTP prilagođenog uvoza.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595846"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Obogaćivanje profila klijenata pomoću prilagođenih podataka (pretpregled)

Prilagođeni uvoz Protokola sigurnog prijenosa datoteka (SFTP) omogućava vam uvoz podataka koji ne moraju proći kroz postupak objedinjavanja podataka. To je fleksibilan, siguran i jednostavan način unosa podataka. SFTP prilagođeni uvoz može se koristiti u kombinaciji sa [SFTP izvozom](export-sftp.md) koji vam omogućava izvoz podataka profila klijenata potrebnih za obogaćivanje. Podaci se zatim mogu obrađivati i obogaćivati, a SFTP prilagođeni uvoz može se koristiti za vraćanje obogaćenih podataka u mogućnost uvida u ciljnu skupinu usluge Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Preduvjeti

Da biste konfigurirali SFTP prilagođeni uvoz, moraju biti ispunjeni sljedeći preduvjeti:

- Imate korisničke vjerodajnice (korisničko ime i lozinku) za SFTP lokaciju podataka koji će se uvoziti.
- Imate URL i broj priključka (obično 22) za STFP glavno računalo.
- Imate naziv datoteke i mjesto datoteke koja će se uvesti na SFTP glavnom računalu.
- Postoji *model.json* datoteka koja specificira shemu za podatke koje treba uvesti. Ova datoteka mora biti u istom direktoriju kao i datoteka za uvoz.
- Imate dozvolu [administratora](permissions.md#administrator).

## <a name="configuration"></a>Konfiguracija

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

1. Na **pločici SFTP prilagođenog uvoza** odaberite **Obogaćivanje mojih podataka**.

   > [!div class="mx-imgBorder"]
   > ![Pločica SFTP prilagođenog uvoza](media/SFTP_Custom_Import_tile.png "Pločica SFTP prilagođenog uvoza")

1. Odaberite **Početak** i navedite vjerodajnice i adresu za SFTP poslužitelj. Na primjer, sftp://mysftpserver.com:22.

1. Unesite naziv datoteke koja sadrži podatke i put do datoteke na SFTP poslužitelju ako nije u korijenskoj mapi.

1. Potvrdite sve unose odabirom stavke **Povezivanje s prilagođenim uvozom**.

   > [!div class="mx-imgBorder"]
   > ![Potpaleta konfiguracije SFTP prilagođenog uvoza](media/SFTP_Custom_Import_Configuration_flyout.png "Potpaleta konfiguracije SFTP prilagođenog uvoza")

## <a name="defining-field-mappings"></a>Definiranje mapiranja polja 

Direktorij koji sadrži datoteku koju treba uvesti na SFTP poslužitelj mora sadržavati i *model.json* datoteku. Ova datoteka definira shemu koja će se koristiti za uvoz podataka. Shema mora koristiti [Common Data Model](/common-data-model/) za određivanje mapiranja polja. Jednostavan primjer model.json datoteke izgleda ovako:

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

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake. Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab). Vrijeme obrade ovisit će o veličini podataka koji se uvoze i vezi sa SFTP poslužiteljem.

Nakon završetka postupka obogaćivanja, svoje tek uvezene prilagođene podatke obogaćivanja možete pregledati u odjeljku **Moja obogaćivanja**. Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.

## <a name="next-steps"></a>Sljedeći koraci

Nadogradite na svoje obogaćene podatke o klijentu. Stvorite [segmente](segments.md) i [mjere](measures.md) i [izvezite podatke](export-destinations.md) kako biste svojim klijentima ponudili personalizirana iskustva.




[!INCLUDE[footer-include](../includes/footer-banner.md)]