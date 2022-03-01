---
title: Poveznik za Power BI
description: Saznajte kako upotrebljavati poveznik značajke Dynamics 365 Customer Insights u programu Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405299"
---
# <a name="connector-for-power-bi-preview"></a>Poveznik za Power BI (pretpregled)

Stvorite vizualne prikaze za svoje podatke pomoću usluge Power BI Desktop. Generirajte dodatne uvide i izradite izvješća s objedinjenim podacima o klijentima.

## <a name="prerequisites"></a>Preduvjeti

- Imate objedinjene profile klijenata.
- Najnovija verzija usluge [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) instalirana je na vašem računalu. [Saznajte više o Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfiguracija poveznika za Power BI

1. U Power BI Desktop odaberite **Datoteka** > **Dohvati podatke**.

1. Odaberite **Vidi više** i potražite **Dynamics 365 Customer Insights**

1. Odaberite rezultat i odaberite **Poveži**.

1. Odaberite **Prijavi se** s istim računom tvrtke ili ustanove koji koristite za aplikaciju Customer Insights i odaberite **Poveži**.
   > [!NOTE]
   > Račun koji navedete u ovom koraku upotrebljava se za dohvaćanje podataka iz aplikacije Customer Insights i ne mora biti isti na koji ste prijavljeni u uslugu Power BI. Da biste ponovno postavili račun koji se koristi za dohvaćanje podataka, otvorite Power BI i idite u odjeljak **Datoteka** > **Mogućnosti** > **Postavke** > **Postavke izvora podataka**. Na popisu izvora podataka odaberite **Prijava u aplikaciju Dynamics 365 Customer Insights** i odaberite **Obriši dozvole**.  

1. U dijaloškom okviru **Navigator**. vidjet ćete popis svih okruženja kojima imate pristup. Proširite okruženje i otvorite bilo koju mapu (entiteti, mjere, segmenti, obogaćenja). Na primjer, otvorite mapu **Entiteti** da prikažete sve entitete koje možete uvesti.

   ![Navigator poveznika programa Power BI](media/power-bi-navigator.png "Navigator poveznika programa Power BI")

1. Odaberite potvrdne okvire pored entiteta koje treba uključiti i **Učitaj**. Možete odabrati više entiteta iz više okruženja.

1. Vidjet ćete dijaloški okvir za učitavanje dok se entiteti učitavaju. Nakon što se učitaju svi odabrani entiteti, možete koristiti mogućnosti usluge Power BI za vizualizaciju podataka.

## <a name="large-data-sets"></a>Veliki skupovi podataka

Priključak za Customer Insights za Power BI dizajniran je da funkcionira za skupove podataka koji sadrže do 1 milijun korisničkih profila. Uvoz većih skupova podataka može funkcionirati, ali to traje dugo. Osim toga, postupak bi mogao biti vremenski ograničen zbog ograničenja za Power BI. Za više informacija pogledajte [Power BI: Preporuke za velike skupove podataka](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Rad s podskupom podataka

Razmislite o radu s podskupom podataka. Na primjer, možete stvarati [segmente](segments.md) umjesto izvoza svih zapisa klijenata u Power BI.
