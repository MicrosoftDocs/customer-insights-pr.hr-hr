---
title: Izvoz podataka značajke Customer Insights u ActiveCampaign
description: Saznajte kako konfigurirati vezu i izvesti u ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 089b9b0d76437e695f797f941ed384734d8f772e
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227800"
---
# <a name="export-segments-to-activecampaign-preview"></a>Izvoz segmenata u ActiveCampaign (pretpregled)

Izvezite segmente objedinjenih profila kupaca u ActiveCampaign i upotrijebite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduvjeti

-   Imate [račun za ActiveCampaign](https://www.activecampaign.com/) i odgovarajuće vjerodajnice administratora.
-   Imate [konfigurirane segmente](segments.md) u uvidima u ciljnu skupinu.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje s adresom e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Možete izvesti do 1 milijun profila klijenata po izvozu u ActiveCampaign, a dovršetak može potrajati do 90 minuta.
- Izvoz u ActiveCampaign ograničen je na segmente.
- Broj profila klijenata koje možete izvesti u ActiveCampaign ovisi o ugovoru s uslugom ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Postavljanje veze na ActiveCampaign

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodavanje veze** pa odaberite **ActiveCampaign** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj [ključ API-ja za ActiveCampaign i naziv hosta REST krajnje točke](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). Naziv glavnog računala krajnje točke za REST je samo naziv glavnog računala, bez https://. 

1. Odaberite **Prihvaćam** da biste potvrdili **Privatnost podataka i sukladnost**.

1. Odaberite **Spoji** za pokretanje veze na ActiveCampaign.

1. Odaberite **Dodajte se kao korisnik izvoza** i unesite svoje vjerodajnice za Customer Insights.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka ActiveCampaign. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. Unesite svoj [**ID popisa za ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. U odjeljku **Podudaranje podataka** u polju **E -pošta** odaberite polje koje predstavlja adresu e-pošte klijenta. Obvezno je izvoziti segmente u ActiveCampaign. Po želji možete izvesti Ime, Prezime, i Telefon da biste stvorili personaliziraniju e-poštu. Odaberite Dodavanje atributa za mapiranje ovih polja.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kad omogućite Dynamics 365 Customer Insights za prijenos podataka u ActiveCampaign dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke poput osobnih podataka. Microsoft će prenositi takve podatke prema vašoj uputi, ali vi ste odgovorni za to da ActiveCampaign ispunjava sve obveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.
