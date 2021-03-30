---
title: Poveznik za Power BI
description: Saznajte kako upotrebljavati poveznik značajke Dynamics 365 Customer Insights u programu Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596030"
---
# <a name="connector-for-power-bi-preview"></a>Poveznik za Power BI (pretpregled)

Stvorite vizualne prikaze za svoje podatke pomoću usluge Power BI Desktop. Generirajte dodatne uvide i izradite izvješća s objedinjenim podacima o klijentima.

## <a name="prerequisites"></a>Preduvjeti

- Imate objedinjene profile klijenata.
- Najnovija verzija servisa [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je instalirana na vašem računalu. [Saznajte više o Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfiguracija poveznika za Power BI

1. U Power BI Desktop odaberite **Datoteka** > **Dohvati podatke**.

1. Odaberite **Vidi više** i potražite **Dynamics 365 Customer Insights**

1. Odaberite **Poveži**.

1. Odaberite **Prijavi se** s istim računom tvrtke ili ustanove koji koristite za aplikaciju Customer Insights i odaberite **Poveži**.
   > [!NOTE]
   > Račun koji navedete u ovom koraku upotrebljava se za dohvaćanje podataka iz aplikacije Customer Insights i ne mora biti isti na koji ste prijavljeni u uslugu Power BI. Da biste ponovno postavili račun koji se koristi za dohvaćanje podataka, otvorite Power BI i idite u odjeljak **Datoteka** > **Mogućnosti** > **Postavke** > **Postavke izvora podataka**. Na popisu izvora podataka odaberite **Prijava u aplikaciju Dynamics 365 Customer Insights** i odaberite **Obriši dozvole**.  

1. U dijaloškom okviru **Navigator**. vidjet ćete popis svih okruženja kojima imate pristup. Proširite okruženje i otvorite bilo koju mapu (entiteti, mjere, segmenti, obogaćenja). Na primjer, otvorite mapu **Entiteti** da prikažete sve entitete koje možete uvesti.

   ![Navigator poveznika programa Power BI](media/power-bi-navigator.png "Navigator poveznika programa Power BI")

1. Odaberite potvrdne okvire pored entiteta koje treba uključiti i **Učitaj**. Možete odabrati više entiteta iz više okruženja.

1. Vidjet ćete dijaloški okvir za učitavanje dok se entiteti učitavaju. Nakon što se učitaju svi odabrani entiteti, možete koristiti mogućnosti usluge Power BI za vizualizaciju podataka.

## <a name="large-data-sets"></a>Veliki skupovi podataka

Priključak za Customer Insights za Power BI dizajniran je da funkcionira za skupove podataka koji sadrže do 1 milijun korisničkih profila. Uvoz većih skupova podataka može funkcionirati, ali to traje dugo. Osim toga, postupak bi mogao biti vremenski ograničen zbog ograničenja za Power BI. Za više informacija pogledajte [Power BI: Preporuke za velike skupove podataka](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Rad s podskupom podataka

Razmislite o radu s podskupom podataka. Na primjer, možete stvarati [segmente](segments.md) umjesto izvoza svih zapisa klijenata u Power BI.

## <a name="troubleshooting"></a>Otklanjanje poteškoća

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Okruženje Customer Insights ne prikazuje se u Power BI

Okruženja koja imaju više od jednog [odnosa](relationships.md) definirana između dva identična entiteta u uvidima u ciljnu skupinu neće biti dostupni u povezniku usluge Power BI.

Možete identificirati i ukloniti duplicirane odnose.

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Odnosi** u okruženju koje vam nedostaje u Power BI.
2. Identificiranje dupliciranih odnosa:
   - Provjerite postoji li više odnosa definiranih između dvaju istih entiteta.
   - Provjerite postoji li odnos stvoren između dvaju entiteta koja su oba uključena u proces objedinjavanja. Definiran je implicitni odnos između svih entiteta uključenih u proces objedinjavanja.
3. Uklonite sve identificirane duplicirane odnose.

Nakon uklanjanja dupliciranih odnosa, pokušajte ponovno konfigurirati poveznik za Power BI. Okruženje bi sada trebalo biti dostupno.

[!INCLUDE[footer-include](../includes/footer-banner.md)]