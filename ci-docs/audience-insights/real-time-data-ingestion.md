---
title: Gutanje podataka u stvarnom vremenu (pretpregled)
description: Opće informacije o mogućnostima u stvarnom vremenu u uvidima u ciljnu skupinu.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 138704445d52df3336af6af60420f0bd0ee0c639
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464017"
---
# <a name="real-time-data-ingestion-preview"></a>Unos podataka u stvarnom vremenu (pretpregled)

Rad praktično u stvarnom vremenu omogućuje vam da za nekoliko sekundi vidite najnovije interakcije klijenata s vašim proizvodima ili uslugama.

[Zakazana osvježenja](system.md#schedule-tab) uključuju velik broj zapisa i nekoliko složenih operacija. Prvo se podaci izvlače iz izvora podataka. Zatim se podaci objedinjuju, a onda obogaćuju dodatnim informacijama. Svako pokretanje ovog procesa može trajati nekoliko minuta ili sati.

Funkcija u stvarnom vremenu odmah pruža podatke za potrošnju, sve dok ih naknadno zakazano osvježenje ne izvuče iz izvora podataka.

Ažuriranja u stvarnom vremenu imaju vrijeme isteka nakon kojeg više ne zamjenjuju vrijednost iz izvora podataka:

- Ažuriranja profila čuvat će se 4 sata
- Aktivnosti će se čuvati 30 dana

Te su vrijednosti parametri pozivanja API-ja koje možete promijeniti. Cilj im je osigurati da vaši izvorni podaci ostanu vaš izvor istine. Ako želite da ažuriranja u stvarnom vremenu dulje budu uključena, morate ih dodati u izvor podataka tako da se povuku tijekom sljedećeg zakazanog osvježavanja.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Ažuriranje polja unificiranog profila klijenta u stvarnom vremenu

Ažurirani profili prikazat će se u prikazu kartice klijenta li bilo kojoj drugoj vizualizaciji u roku od nekoliko sekundi.

Budući da se operacije u stvarnom vremenu odvijaju nakon objedinjavanja podataka, one se primjenjuju samo na objedinjene profile korisnika. Prema tome, promjene profila u stvarnom vremenu neće ažurirati mjere, članstvo segmenta ili obogaćivanja.

### <a name="limitations"></a>Ograničenja

- Korisnički profili mogu se ažurirati, ali ne i stvarati ili brisati.
- Izvoz ažuriranja u stvarnom vremenu u vanjske sustave, poput Power BI, trenutno nije moguće.

## <a name="real-time-creation-of-activities"></a>Stvaranje aktivnosti u stvarnom vremenu

API u stvarnom vremenu omogućuje vam objavljivanje nove aktivnosti iz vašeg izvornog sustava (pojedinačni izvorni zapis) na jedinstveni profil klijenta. Nova će aktivnost biti u roku od nekoliko sekundi dostupna kao objedinjena aktivnost na vremenskoj traci tog objedinjenog korisničkog profila. Vremensku traku možete vidjeti u prikazu kartice klijenta ili bilo kojoj drugoj integraciji vremenske trake koju ste konfigurirali.

> [!NOTE]
>
> - Aktivnosti su nepromjenjive. Nakon stvaranja se ne mijenjaju.
> - Trenutno se segmenti i mjere neće ažurirati na temelju nove aktivnosti.
> - Aktivnosti dodane samo putem API-ja u stvarnom vremenu nisu dio izvoza i neće se pojaviti na nadzornoj ploči PowerBI.

Dva su načina povezivanja s API-jem u stvarnom vremenu:

- [posredno](#connect-via-the-dynamics-365-customer-insights-connector), korištenjem [Dynamics 365 Customer Insights poveznika](/connectors/customerinsights/)
- [izravno](#connect-directly-to-the-real-time-api), s kodom

Oba načina dijele iste sljedeće preduvjete:

- A Okruženje Customer Insights
- Objedinjeni profili klijenata
- Aktivnosti konfigurirane i pokrenute
- Dozvole suradnika ili administratora za provjeru autentičnosti vašeg računa

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Povezivanje putem Dynamics 365 Customer Insights poveznika

API u stvarnom vremenu može unositi podatke s namjenskog Power Platform poveznika, [Dynamics 365 Customer Insights poveznika](/connectors/customerinsights/), bez potrebe za pisanjem i implementiranjem bilo kojeg koda.    
Poveznik može raditi iste radnje u stvarnom vremenu kao API. Za vrhunske poveznike potrebna je valjana licenca. Za dodatne informacije pogledajte [Najčešća pitanja o licenciranju za Power Apps i Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps i/ili Power Automate](/connectors/)
- Azure [Logičke aplikacije](/azure/connectors/apis-list)

Za pojedinosti o stvaranju tokova pogledajte [Dokumentaciju za Power Automate](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Izravno povezivanje s API-jem u stvarnom vremenu

Mogućnosti u stvarnom vremenu možete se koristiti izgradnjom vlastitog kanala i izravnim povezivanjem s API-jem u stvarnom vremenu.    
Aktivnost možete objaviti u formatu svog izvornog sustava ili u formatu UnifiedActivity. Nabavite format upućivanjem API poziva u /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Pojedinosti ovog API-ja, uključujući parametre i odgovore, možete pronaći u odjeljku **EntityData** o [Referenci API-ja Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Dodatne informacije potražite u odjeljku [Rad s API-jima Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Objašnjenje uporabe u stvarnom vremenu uz telemetriju

Dohvatite pregled količine zahtjeva API-ju u stvarnom vremenu i informacije o problemima na koje sustav može naići. Možete [pristupiti telemetriji u stvarnom vremenu](system.md#api-usage-tab). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
