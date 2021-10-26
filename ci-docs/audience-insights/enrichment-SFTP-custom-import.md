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
ms.openlocfilehash: fa1d4ffd9f77e128b5d804e4562e964561f4684f
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618673"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Obogaćivanje profila klijenata pomoću prilagođenih podataka (pretpregled)

Prilagođeni uvoz Protokola sigurnog prijenosa datoteka (SFTP) omogućava vam uvoz podataka koji ne moraju proći kroz postupak objedinjavanja podataka. To je fleksibilan, siguran i jednostavan način unosa podataka. SFTP prilagođeni uvoz može se koristiti u kombinaciji sa [SFTP izvozom](export-sftp.md) koji vam omogućava izvoz podataka profila klijenata potrebnih za obogaćivanje. Podaci se zatim mogu obraditi i obogatiti, a SFTP prilagođeni uvoz može se koristiti za vraćanje obogaćenih podataka u sposobnost uvida publike značajke Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Preduvjeti

Da biste konfigurirali SFTP prilagođeni uvoz, moraju biti ispunjeni sljedeći preduvjeti:

- Imate naziv datoteke i lokaciju (putanju) do datoteke koju treba uvesti na SFTP host.
- Postoji datoteka *model.json* koja navodi [shemu Common Data Model](/common-data-model/) za podatke koji se trebaju uvesti. Ova datoteka mora biti u istom direktoriju kao i datoteka za uvoz.
- Administrator je već konfigurirao vezu SFTP *ili* imate [administratorske](permissions.md#administrator) dozvole. Trebat će vam vjerodajnice korisnika, URL i broj priključka za lokaciju SFTP odakle želite uvesti podatke.


## <a name="configure-the-import"></a>Konfiguracija uvoza

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

1. Na **Pločici za prilagođeni uvoz SFTP** odaberite **Obogati moje podatke** i zatim odaberite **Započni**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Pločica za prilagođeni uvoz SFTP.":::

1. Odaberite [vezu](connections.md) s padajućeg popisa. Ako nijedna veza nije dostupna, obratite se administratoru. Ako ste administrator, vezu možete stvoriti odabirom **Dodaj vezu** pa odabirom **SFTP prilagođeni uvoz** s padajućeg popisa.

1. Odaberite **Poveži se s prilagođenim uvozom** za potvrdu odabrane veze.

1.  Odaberite **Dalje** pa unesite podatke **Putanja** i **Naziv datoteke** za podatkovnu datoteku koju želite uvesti.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Snimka zaslona prilikom unosa lokacije podataka.":::

1. Odaberite **Dalje** i odaberite skup podataka klijenta. To mogu biti svi profili klijenata ili segment.

1. Odaberite **Sljedeće** i navedite naziv za obogaćivanje i naziv za izlazni entitet. 

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfiguriranje veze za prilagođeni uvoz SFTP 

Morate biti administrator da biste konfigurirali veze. Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćivanja *ili* idite na **Admin** > **Veze** i odaberite **Postavi** na pločici Prilagođeni uvoz.

1. Unesite naziv za vezu u dijaloški okvir **Zaslonski naziv**.

1. Unesite važeće korisničko ime, lozinku i URL hosta za SFTP poslužitelj na kojem se nalaze podaci koji se uvoze.

1. Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**.

1. Odaberi **Potvrdi** za provjeru valjanosti konfiguracije.

1. Nakon završetka provjere vezu možete spremiti odabirom **Spremi**.

   > [!div class="mx-imgBorder"]
   > ![Stranica konfiguracije veze za Experian.](media/enrichment-SFTP-connection.png "Stranica konfiguracije veze na Experian")


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

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
