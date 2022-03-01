---
title: Unos podataka i ograničenja u stvarnom vremenu
description: Opće informacije o mogućnostima u stvarnom vremenu u uvidima u ciljnu skupinu.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00a72e6a67e33c8e70ccc6139c5e62020f9d3e1
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689166"
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

- [posredno](#connect-via-the-dynamics-365-customer-insights-connector), korištenjem [Dynamics 365 Customer Insights poveznika](https://docs.microsoft.com/connectors/customerinsights/)
- [izravno](#connect-directly-to-the-real-time-api), s kodom

Oba načina dijele iste sljedeće preduvjete:

- A Okruženje Customer Insights
- Objedinjeni profili klijenata
- Aktivnosti konfigurirane i pokrenute
- Dozvole suradnika ili administratora za provjeru autentičnosti vašeg računa

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Povezivanje putem Dynamics 365 Customer Insights poveznika

API u stvarnom vremenu može unositi podatke s namjenskog Power Platform poveznika, [Dynamics 365 Customer Insights poveznika](https://docs.microsoft.com/connectors/customerinsights/), bez potrebe za pisanjem i implementiranjem bilo kojeg koda.    
Poveznik može raditi iste radnje u stvarnom vremenu kao API. Za vrhunske poveznike potrebna je valjana licenca. Za dodatne informacije pogledajte [Najčešća pitanja o licenciranju za Power Apps i Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps i/ili Power Automate](https://docs.microsoft.com/connectors/)
- Azure [Logičke aplikacije](https://docs.microsoft.com/azure/connectors/apis-list)

Za pojedinosti o stvaranju tokova pogledajte [Dokumentaciju za Power Automate](https://docs.microsoft.com/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Izravno povezivanje s API-jem u stvarnom vremenu

Mogućnosti u stvarnom vremenu možete se koristiti izgradnjom vlastitog kanala i izravnim povezivanjem s API-jem u stvarnom vremenu.    
Aktivnost možete objaviti u formatu svog izvornog sustava ili u formatu UnifiedActivity. Nabavite format upućivanjem API poziva u /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Pojedinosti ovog API-ja, uključujući parametre i odgovore, možete pronaći u odjeljku **EntityData** o [Referenci API-ja Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Dodatne informacije potražite u odjeljku [Rad s API-jima Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Objašnjenje uporabe u stvarnom vremenu uz telemetriju

Dohvatite pregled količine zahtjeva API-ju u stvarnom vremenu i informacije o problemima na koje sustav može naići. Možete [pristupiti telemetriji u stvarnom vremenu](system.md#api-usage-tab) odlaskom u **Admin** > **Sustav** > **Upotreba API-ja**. U tablici **Operacije** retci za API operacije koje primjenjuju metode u stvarnom vremenu sadrže gumb za prikaz upotrebe API-ja u stvarnom vremenu. Gumb je prikazan sa simbolom dvogleda. Odaberite gumb da biste otvorili bočno okno s detaljima o upotrebi API-ja u stvarnom vremenu u trenutačnom okruženju.

Koristite birača **Grupiraj prema** da biste odabrali kako najbolje predstaviti svoje interakcije u stvarnom vremenu na vremenskoj traci u rasponu od posljednja 24 sata do posljednjih 30 dana. Možete grupirati podatke prema načinu rada API-ja, nazivu kvalificiranog entiteta (uvučeni entitet), kreatoru (izvor događaja), rezultatu (uspjeh ili neuspjeh) ili kodovima pogrešaka. Podaci su dostupni u vidu povijesnog grafikona i tablice.
