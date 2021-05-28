---
title: Izvoz podataka usluge Customer Insights u Marketo
description: Saznajte kako konfigurirati vezu i izvesti u Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059307"
---
# <a name="export-segments-to-marketo-preview"></a>Izvoz segmenata u Marketo (pretpregled)

Izvezite segmente objedinjenih profila klijenata da biste generirali kampanje, pružili marketing putem e-pošte i koristili određene grupe klijenata pomoću usluge Marketo.

## <a name="prerequisites-for-connection"></a>Preduvjeti za vezu

-   Imate [račun za Marketo](https://login.marketo.com/) i odgovarajuće vjerodajnice administratora.
-   Marketo sadrži postojeće popise i odgovarajuće ID-ove. Dodatne informacije potražite u [popisima usluge Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Imate [konfigurirane segmente](segments.md).
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 1 milijun profila po izvozu u Marketo.
- Izvoz u Marketo ograničen je na segmente.
- Izvoz segmenata s ukupno milijun profila može trajati do 3 sata. 
- Broj profila koje možete izvesti u Marketo ovisi i ograničen je vašim ugovorom s tvrtkom Marketo.

## <a name="set-up-connection-to-marketo"></a>Postavljanje veze s Marketo

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **Marketo** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj **[ID klijenta za Marketo, klijentski tajni ključ i naziv glavnog računala krajnje točke za REST](https://developers.marketo.com/rest-api/authentication/)**. Naziv glavnog računala krajnje točke za REST je samo naziv glavnog računala, bez `https://`. Primjer: `xyz-abc-123.mktorest.com`. 

1. Odaberite **Slažem se** da biste potvrdili **Privatnost i usklađenost podataka** i odaberite **Povezivanje** za inicijalizaciju veze s uslugom Marketo.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Marketo. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Unesite svoj **[ID popisa usluge Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. ID popisa je čisto numerička vrijednost. Na primjer, ako je vaš ID popisa usluge Marketo ST12345A7, uklonite znak prije i iza brojeva i unesite `12345`. 

1. U odjeljku **Podudaranje podataka**, u polju **E-pošta**, odaberite polje u vašem objedinjenom profilu klijenta koje predstavlja adresu e-pošte klijenta. 

1. Neobavezno možete izvesti **Ime**, **Prezime**, **Grad**, **Država** **Zemlja/Regija**  za stvaranje personaliziranije e-pošte. Odaberite **Dodavanje atributa** za mapiranje ovih polja.

1. Odaberite segmente koje želite izvesti. U Marketo možete ukupno izvesti do 1 milijun profila klijenata.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). U usluzi Marketo svoje segmente sada možete pronaći u odjeljku [popisi usluge Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Marketo, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Marketo ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
