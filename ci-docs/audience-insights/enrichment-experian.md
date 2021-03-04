---
title: Obogaćivanje pomoću obogaćivanja treće strane tvrke Experian
description: Opće informacije o obogaćivanju treće strane tvrtke Experian.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269551"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obogaćivanje profila klijenata demografskim podacima tvrtke Experian (pretpregled)

Experian je svjetski predvodnik u izvješćivanju o potrošačkim i poslovnim kreditima i marketinškim uslugama. Uz Experianove usluge obogaćivanja podataka možete izgraditi bolje temelje za razumijevanje svojih klijenata obogaćujući profile svojih klijenata demografskim podacima kao što su veličina kućanstva, prihod i još mnogo toga.

## <a name="prerequisites"></a>Preduvjeti

Za konfiguraciju Experiana potrebno je ispuniti sljedeće preduvjete:

- Trebate imati aktivnu pretplatu na Experian. Kako biste nabavili pretplatu, izravno se [obratite tvrtki Experian](https://www.experian.com/marketing-services/contact). [Saznajte više o obogaćivanju podataka od strane tvrtke Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Trebate imati ID korisnika, ID stranke i broj modela za svoj SSH-omogućeni račun sigurnog prijenosa (ST, Secure Transport) koji je Experian stvorio za vas.
- Imate dozvole [administratora](permissions.md#administrator) u uvidima u ciljnu skupinu.

## <a name="configuration"></a>Konfiguracija

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

1. Odaberite **Obogati moje podatke** na pločici Experian.

   > [!div class="mx-imgBorder"]
   > ![Pločica Experian](media/experian-tile.png "Pločica Experian")

1. Odaberite **Početak** i unesite ID korisnika, ID stranke i broj modela za svoj Experian račun za siguran prijenos. Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**. Potvrdite sve unose odabirom mogućnosti **Primijeni**.

## <a name="map-your-fields"></a>Mapirajte svoja polja

1.  Odaberite **Dodaj podatke** i odaberite **Skup korisničkih podataka** koji želite obogatiti demografskim podacima iz sustava Experian. Možete odabrati entitet **Klijent** za obogaćivanje svih vaših korisničkih profila ili odaberite segmentni entitet za obogaćivanje samo korisničkih profila sadržanih u tom segmentu.

1. Odaberite svoje identifikatore ključa iz **Naziv i adresa**, **E-poošta** ili **Telefon** da biste ih poslali u Experian radi rješavanja identiteta.

   > [!TIP]
   > Više atributa ključnih identifikatora poslanih Experianu vjerojatno daje veću stopu podudaranja.

1. Odaberite **Dalje** i mapirajte odgovarajuće atribute iz vašeg objedinjenog entiteta klijenta za odabrana polja ključnih identifikatora.

1. Odaberite **Dodaj atribut** kako biste mapirali sve dodatne atribute koje biste željeli poslati Experianu.

1.  Odaberite **Spremi** da biste dovršili mapiranje polja.

    > [!div class="mx-imgBorder"]
    > ![Mapiranja polja Experian](media/experian-field-mapping.png "Mapiranja polja Experian")

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake. Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab). Vrijeme obrade ovisit će o veličini vaših podataka o klijentu i postupcima obogaćivanja koje je za vaš račun postavio Experian.

Nakon završetka postupka obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod stavkom **Moja obogaćivanja**. Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.

## <a name="next-steps"></a>Sljedeći koraci

Nadogradite na svoje obogaćene podatke o klijentu. Stvorite [segmente](segments.md), [mjere](measures.md), pa i [izvezite podatke](export-destinations.md) kako biste svojim klijentima pružili personalizirano iskustvo.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Experian, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Experian ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE[footer-include](../includes/footer-banner.md)]