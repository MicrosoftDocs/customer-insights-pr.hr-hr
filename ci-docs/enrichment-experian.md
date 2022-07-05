---
title: Obogaćivanje klijentskih profila demografskim podacima tvrtke Experian (pretpregled)
description: Opće informacije o obogaćivanju treće strane Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: a30e98b06ed07590ab95cae1d8db8023e49ff7f9
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053012"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obogaćivanje klijentskih profila demografskim podacima tvrtke Experian (pretpregled)

Experian je svjetski predvodnik u izvještavanju o potrošačkim i poslovnim kreditima i marketinškim uslugama. Uz usluge obogaćivanja podataka tvrtke Experian možete steći dublje razumijevanje svojih klijenata obogaćujući klijentske profile demografskim podacima kao što su veličina kućanstva, prihod i još mnogo toga.

## <a name="supported-countriesregions"></a>Podržane zemlje/regije

Trenutno podržavamo obogaćivanje profila kupaca samo u Sjedinjenim Državama.

## <a name="prerequisites"></a>Preduvjeti

- Aktivna Experian pretplata. Da biste dobili pretplatu, izravno se [obratite Experianu](https://www.experian.com/marketing-services/contact). [Saznajte više o obogaćivanju podataka Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Vezu Experian [je](connections.md) [konfigurirao](#configure-the-connection-for-experian) administrator.

- Experian Korisnički ID, ID stranke i broj modela za vaš račun za siguran prijevoz (ST) koji podržava SSH koji je Experian stvoren za vas.

## <a name="configure-the-connection-for-experian"></a>Konfiguriranje veze za Experian

Morate biti [administrator](permissions.md#admin) u customer insights i imati Experian korisnički ID, ID stranke i broj modela.

1. Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćivanja ili Idite na **Veze s administratorima** > **·**, a zatim odaberite **Postavi** na pločici Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Okno konfiguracije veze na Experian.":::

1. Unesite naziv veze i valjani korisnički ID, ID stranke i broj modela za svoj Experian račun za siguran prijevoz.

1. Pregledajte i dajte svoj pristanak za [Privatnost podataka i usklađenost](#data-privacy-and-compliance) odabirom opcije **Slažem se**.

1. Odaberite **Provjeri** da biste provjerili valjanost konfiguracije, a zatim **Spremi**.

### <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kad omogućite Dynamics 365 Customer Insights za prijenos podataka u Experian, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke poput osobnih podataka. Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Experian ispunjava sve obveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732). Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

1. S pločice odaberite **Obogati moje podatke o** demografiji **·**.Experian

   :::image type="content" source="media/experian-tile.png" alt-text="Experian pločica na stranici s pregledom obogaćivanja.":::

1. Pregledajte pregled, a zatim odaberite **Dalje**.

1. Odaberite vezu. Ako jedan nije dostupan, obratite se administratoru.

1. Odaberite **Dalje**.

1. **Odaberite skup podataka** za korisnike i odaberite profil ili segment koji želite obogatiti demografskim podacima iz Experian sustava. Subjekt *Kupac* obogaćuje sve vaše profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Snimka zaslona prilikom odabira skupa podataka o klijentu.":::

1. Definiši koju vrstu polja iz objedinjenih profila želite koristiti za podudaranje demografskih podataka iz Experian sustava. Potrebno je barem jedno od polja **Ime i adresa**, **Telefon** ili **E-pošta**. Za veću točnost podudaranja dodajte druga polja. Odaberite **Dalje**.

1. Mapirajte polja na demografske podatke iz Experian sustava.

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja.

1. Navedite naziv **za obogaćivanje i naziv izlaznog entiteta** **.**

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

1. Odaberite **Pokreni** da biste pokrenuli postupak obogaćivanja ili zatvorili da biste se vratili na **stranicu Obogaćivanje**.

## <a name="view-enrichment-results"></a>Prikaz rezultata obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Broj **kupaca obogaćenih poljem** pruža dubinsku analizu pokrivenosti svakog obogaćenog polja.

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
