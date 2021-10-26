---
title: Obogaćivanje uz obogaćivanje treće strane Experian
description: Opće informacije o obogaćivanju treće strane Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fabc3cc9faf4e11f46c396782b561ef61cd0f6d5
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618512"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obogaćivanje klijentskih profila demografskim podacima tvrtke Experian (pretpregled)

Experian je svjetski predvodnik u izvještavanju o potrošačkim i poslovnim kreditima i marketinškim uslugama. Uz usluge obogaćivanja podataka tvrtke Experian možete steći dublje razumijevanje svojih klijenata obogaćujući klijentske profile demografskim podacima kao što su veličina kućanstva, prihod i još mnogo toga.

## <a name="prerequisites"></a>Preduvjeti

Za konfiguriranja servisa Experian potrebno je ispuniti sljedeće preduvjete:

- Imate aktivnu pretplatu na Experian. Da biste dobili pretplatu, izravno se [obratite Experianu](https://www.experian.com/marketing-services/contact). [Saznajte više o obogaćivanju podataka Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Administrator je već konfigurirao vezu Experian *ili* imate [administratorske](permissions.md#administrator) dozvole. Također su vam potrebni Korisnički ID, ID stranke i Broj modela za vaš račun sigurnog prijenosa (ST) s omogućenim SSH koji je Experian stvorio za vas.

## <a name="supported-countriesregions"></a>Podržane zemlje/regije

Trenutno podržavamo obogaćivanje profila kupaca samo u Sjedinjenim Državama.

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

1. Odaberite **Obogati moje podatke** na pločici Experian.

   > [!div class="mx-imgBorder"]
   > ![Pločica Experian.](media/experian-tile.png "Experian tile")
   > 

1. Odaberite [vezu](connections.md) s padajućeg popisa. Ako nijedna veza nije dostupna, obratite se administratoru. Ako ste administrator, vezu možete stvoriti odabirom **Dodaj vezu** pa odabirom Experian s padajućeg popisa. 

1. Odaberite **Spoji na Experian** za potvrdu odabira veze.

1.  Odaberite **Dalje** pa odaberite **Skup podataka klijenta** koji želite obogatiti demografskim podacima servisa Experian. Možete odabrati entitet **Klijent** za obogaćivanje svih vaših korisničkih profila ili odaberite segmentni entitet za obogaćivanje samo korisničkih profila sadržanih u tom segmentu.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Snimka zaslona prilikom odabira skupa podataka o klijentu.":::

1. Odaberite **Dalje** pa definirajte koja se vrsta polja iz vaših objedinjenih profila treba koristiti za traženje odgovarajućih demografskih podataka servisa Experian. Potrebno je barem jedno od polja **Ime i adresa**, **Telefon** ili **E-pošta**. Za veću točnost podudaranja mogu se dodati do dva druga polja. Ovaj će odabir utjecati na polja za mapiranje kojima imate pristup u sljedećem koraku.

    > [!TIP]
    > Više atributa identifikatora ključa poslanih servisu Experian vjerojatno donosi višu stopu podudaranja.

1. Odaberite **Sljedeće** da biste započeli mapiranje polja.

1. Definirajte koja polja iz vaših objedinjenih profila treba koristiti za traženje odgovarajućih demografskih podataka servisa Experian. Obavezna su polja označena.

1. Navedite naziv za obogaćivanje i naziv za izlazni entitet.

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

## <a name="configure-the-connection-for-experian"></a>Konfiguriranje veze za Experian 

Morate biti administrator da biste konfigurirali veze. Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćivanja *ili* idite na **Administrator** > **Veze** pa odaberite **Postavljanje** na pločici Experian.

1. Odaberite **Početak rada**.

1. Unesite naziv za vezu u dijaloški okvir **Zaslonski naziv**.

1. Unesite važeći Korisnički ID, ID stranke i Broj modela za svoj račun sigurnog prijenosa za Experian.

1. Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom opcije **Slažem se**.

1. Odaberi **Potvrdi** za provjeru valjanosti konfiguracije.

1. Nakon dovršetka provjere valjanosti odaberite **Spremi**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Okno konfiguracije veze na Experian.":::

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Kako biste započeli postupak obogaćivanja, odaberite **Pokreni** iz naredbene trake. Također možete pustiti sustav da automatski izvrši obogaćivanje kao dio [ planiranog osvježavanja](system.md#schedule-tab). Vrijeme obrade ovisit će o veličini vaših podataka o klijentima i postupcima obogaćivanja koje je za vaš račun postavio Experian.

Nakon završetka postupka obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod stavkom **Moja obogaćivanja**. Uz to ćete pronaći vrijeme zadnjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kad omogućite Dynamics 365 Customer Insights za prijenos podataka u Experian, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke poput osobnih podataka. Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Experian ispunjava sve obveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
