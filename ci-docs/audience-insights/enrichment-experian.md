---
title: Obogaćivanje pomoću obogaćivanja treće strane tvrke Experian
description: Opće informacije o obogaćivanju treće strane tvrtke Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896364"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obogaćivanje profila klijenata demografskim podacima tvrtke Experian (pretpregled)

Experian je svjetski predvodnik u izvješćivanju o potrošačkim i poslovnim kreditima i marketinškim uslugama. Uz Experianove usluge obogaćivanja podataka možete izgraditi bolje temelje za razumijevanje svojih klijenata obogaćujući profile svojih klijenata demografskim podacima kao što su veličina kućanstva, prihod i još mnogo toga.

## <a name="prerequisites"></a>Preduvjeti

Za konfiguraciju Experiana potrebno je ispuniti sljedeće preduvjete:

- Trebate imati aktivnu pretplatu na Experian. Kako biste nabavili pretplatu, izravno se [obratite tvrtki Experian](https://www.experian.com/marketing-services/contact). [Saznajte više o obogaćivanju podataka od strane tvrtke Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Administrator je već konfigurirao vezu s Experianom *ili* imate [administratorske](permissions.md#administrator) dozvole. Potrebni su vam i ID korisnika, ID strane i broj modela za vaš račun sigurnog prijevoza (ST) za koji je omogućen SSH koji je Experian stvorio za vas.

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

1. Odaberite **Obogati moje podatke** na pločici Experian.

   > [!div class="mx-imgBorder"]
   > ![Pločica Experian](media/experian-tile.png "Pločica Experian")
   > 

1. Odaberite [vezu](connections.md) s padajućeg popisa. Ako nijedna veza nije dostupna, obratite se administratoru. Ako ste administrator, vezu možete stvoriti odabirom **Dodaj vezu** i odabirom Experian s padajućeg izbornika. 

1. Odaberite **Poveži se s Experianom** za potvrdu odabira veze.

1.  Odaberite **Sljedeće** i odaberite **Skup podataka klijenta** koji želite obogatiti demografskim podacima iz Experiana. Možete odabrati entitet **Klijent** za obogaćivanje svih vaših korisničkih profila ili odaberite segmentni entitet za obogaćivanje samo korisničkih profila sadržanih u tom segmentu.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Snimka zaslona prilikom odabira skupa podataka o klijentu.":::

1. Odaberite **Sljedeće** i definirajte koja se vrsta polja iz vaših objedinjenih profila treba koristiti za traženje odgovarajućih demografskih podataka iz Experiana. Potrebno je barem jedno od polja **Ime i adresa**, **Telefon** ili **E-pošta**. Za veću točnost podudaranja mogu se dodati do dva druga polja. Ovaj će odabir utjecati na polja za mapiranje kojima imate pristup u sljedećem koraku.

    > [!TIP]
    > Više atributa ključnih identifikatora poslanih Experianu vjerojatno daje veću stopu podudaranja.

1. Odaberite **Sljedeće** da biste započeli mapiranje polja.

1. Definirajte koja se polja iz vaših objedinjenih profila trebaju koristiti za traženje odgovarajućih demografskih podataka iz Experiana. Obavezna su polja označena.

1. Navedite naziv za obogaćivanje i naziv za izlazni entitet.

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

## <a name="configure-the-connection-for-experian"></a>Konfiguriranje veze za Experian 

Morate biti administrator da biste konfigurirali veze. Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćivanja *ili* idite na **Admin** > **Veze** i odaberite **Postavi** na pločici Experian.

1. Odaberite **Početak rada**.

1. Unesite naziv za vezu u dijaloški okvir **Zaslonski naziv**.

1. Unesite valjani ID korisnika, ID strane i broj modela za svoj račun za Experian Secure Transport.

1. Pregledajte i dajte svoj pristanak za **Zaštita privatnosti podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**

1. Odaberi **Potvrdi** za provjeru valjanosti konfiguracije.

1. Nakon dovršetka provjere valjanosti odaberite **Spremi**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Okno za konfiguraciju veze za Experian.":::

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
