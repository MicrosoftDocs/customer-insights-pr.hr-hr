---
title: Obogatite profile kupaca prilagođenim uvozom SFTP-a (pretpregled)
description: Opće informacije o obogaćivanju SFTP prilagođenog uvoza.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 81ef6c62240e26cb5c9475e6306e08edc7e5eb31
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195787"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Obogatite profile kupaca prilagođenim uvozom SFTP-a (pretpregled)

Prilagođeni uvoz Protokola sigurnog prijenosa datoteka (SFTP) omogućava vam uvoz podataka koji ne moraju proći kroz postupak objedinjavanja podataka. To je fleksibilan, siguran i jednostavan način unosa podataka. SFTP prilagođeni uvoz može se koristiti u kombinaciji sa [SFTP izvozom](export-sftp.md) koji vam omogućava izvoz podataka profila klijenata potrebnih za obogaćivanje. Podaci se zatim mogu obrađivati i obogaćivati, a SFTP prilagođeni uvoz može se koristiti za vraćanje obogaćenih podataka u Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Preduvjeti

- Poznati su naziv datoteke i mjesto (put) datoteke koja će se uvesti na glavno računalo SFTP-a.

- Dostupna *je datoteka model.json* koja određuje shemu uobičajenog podatkovnog modela za podatke koji se uvoze. Ova datoteka mora biti u istom direktoriju kao i datoteka za uvoz.

- Konfigurirana je [SFTP](connections.md) veza [...](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Primjer sheme datoteke

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfiguriranje veze za prilagođeni uvoz SFTP

Morate biti [administrator](permissions.md#admin) u customer insights i imati korisničke vjerodajnice, URL i broj priključka za lokaciju SFTP-a s koje želite uvesti podatke.

1. Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćenja ili Idite na **Veze s administratorima** > **·**, a zatim odaberite **Postavi** na pločici Prilagođeni uvoz.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Stranica konfiguracije prilagođene veze za uvoz.":::

1. Unesite naziv veze.

1. Unesite važeće korisničko ime, lozinku i URL hosta za SFTP poslužitelj na kojem se nalaze podaci koji se uvoze.

1. Pregledajte i dajte svoj pristanak za [Privatnost podataka i usklađenost](#data-privacy-and-compliance) odabirom opcije **Slažem se**.

1. Odaberite **Provjeri** da biste provjerili valjanost konfiguracije, a zatim **Spremi**.

### <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights prijenos podataka pomoću prilagođenog uvoza, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će takve podatke prenijeti prema vašim uputima, ali vi ste odgovorni za to da podaci ispunjavaju sve obveze privatnosti ili sigurnosti koje možda imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.

## <a name="configure-the-import"></a>Konfiguracija uvoza

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

1. Na prilagođenoj pločici za uvoz **SFTP-a** odaberite **Obogati moje podatke**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Pločica za prilagođeni uvoz SFTP.":::

1. Pregledajte pregled, a zatim odaberite **Dalje**.

1. Odaberite vezu. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Odaberite skup podataka **kupca** i odaberite profil ili segment koji želite obogatiti. Subjekt *Kupac* obogaćuje sve vaše profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Odaberite **Dalje**.

1. **Unesite put** i **naziv** datoteke podatkovne datoteke koju želite uvesti.

1. Odaberite **Dalje**.

1. Navedite naziv **za obogaćivanje i naziv izlaznog entiteta** **.**

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

1. Odaberite **Pokreni** da biste pokrenuli postupak obogaćivanja ili zatvorili da biste se vratili na **stranicu Obogaćivanje**.

## <a name="view-enrichment-results"></a>Prikaz rezultata obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
