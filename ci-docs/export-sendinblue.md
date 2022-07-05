---
title: Izvoz segmenata u Sendinblue (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u Sendinblue.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f6550b5c57866702631b4c294bb059279461bd6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083075"
---
# <a name="export-segments-to-sendinblue-preview"></a>Izvoz segmenata u Sendinblue (pretpregled)

Segmente objedinjenih klijenskih profila izvezite za generiranje kampanja, pružanje marketinga putem e-pošte i iskorištavanje određenih grupa klijenata uz Sendinblue.

## <a name="prerequisites-for-connection"></a>Preduvjeti za vezu

-   Imate [račun za Sendinblue](https://www.sendinblue.com/) i odgovarajuće vjerodajnice administratora.
-   Ima postojećih popisa na servisu Sendinblue i odgovarajućih ID-ova.
-   Imate [konfigurirane segmente](segments.md).
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 1 milijun profila klijenata po izvozu u Sendinblue.
- Izvoz u Sendinblue ograničen je na segmente.
- Izvoz segmenata s ukupno 1 milijun profila klijenata može potrajati do 90 minuta. 
- Broj profila klijenata koje možete izvesti u Sendinblue ovisi i ograničen je ugovorom s uslugom Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Postavljanje veze na Sendinblue

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodavanje veze** pa odaberite **Sendinblue** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj **[ključ API-ja za SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Odaberite **Slažem se** da biste potvrdili **Privatnost podataka i usklađenost** pa odaberite **Spoji** za pokretanje veze sa servisom Sendinblue.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka Sendinblue. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Unesite svoj **ID popisa za Sendinblue** 

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. 

1. Po želji možete izvesti **Ime**, **Prezime** i **Telefon**  da biste stvorili personaliziraniju e-poštu. Odaberite **Dodavanje atributa** za mapiranje ovih polja.

1. Odaberite segmente koje želite izvesti. 

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kad omogućite Dynamics 365 Customer Insights za prijenos podataka u Sendinblue dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke poput osobnih podataka. Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da Sendinblue ispunjava sve obveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE [footer-include](includes/footer-banner.md)]
