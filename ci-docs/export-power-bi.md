---
title: Poveznik za Power BI (pretpregled)
description: Saznajte kako upotrebljavati poveznik značajke Dynamics 365 Customer Insights u programu Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196661"
---
# <a name="power-bi-connector-preview"></a>Poveznik za Power BI (pretpregled)

Stvorite vizualizacije za svoje podatke pomoću Microsoft Power BI radne površine. Generirajte dodatne uvide i izradite izvješća s objedinjenim podacima o klijentima.

## <a name="prerequisites"></a>Preduvjeti

- Jedinstveni profili kupaca.
- Najnovija verzija servisa [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je instalirana na vašem računalu. [Saznajte više o Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfiguracija poveznika za Power BI

1. U Power BI Desktop odaberite **Datoteka** > **Dohvati podatke**.

1. Odaberite **Vidi više** i potražite **Dynamics 365 Customer Insights**

1. Odaberite **Poveži**.

1. Odaberite **Prijavi se** s istim računom tvrtke ili ustanove koji koristite za aplikaciju Customer Insights i odaberite **Poveži**.
   > [!NOTE]
   > Račun koji navedete u ovom koraku upotrebljava se za dohvaćanje podataka iz aplikacije Customer Insights i ne mora biti isti na koji ste prijavljeni u uslugu Power BI. Da biste ponovno postavili račun koji se koristi za dohvaćanje podataka, otvorite Power BI i idite u odjeljak **Datoteka** > **Mogućnosti** > **Postavke** > **Postavke izvora podataka**. Na popisu izvora podataka odaberite **Prijava u aplikaciju Dynamics 365 Customer Insights** i odaberite **Obriši dozvole**.  

1. **U dijaloškom okviru Navigator** pogledajte popis svih okruženja kojima imate pristup. Proširite okruženje i otvorite bilo koju mapu (entiteti, mjere, segmenti, obogaćenja). Na primjer, otvorite mapu **Entiteti** da prikažete sve entitete koje možete uvesti.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Navigator poveznika programa Power BI.":::

1. Odaberite potvrdne okvire pored entiteta koje treba uključiti i **Učitaj**. Možete odabrati više entiteta iz više okruženja.

   Dijaloški okvir učitavanja prikazuje se tijekom učitavanja entiteta. Nakon što se učitaju svi odabrani entiteti, koristite mogućnosti Power BI vizualizacije podataka.

## <a name="large-data-sets"></a>Veliki skupovi podataka

Priključak za Customer Insights za Power BI dizajniran je da funkcionira za skupove podataka koji sadrže do 1 milijun korisničkih profila. Uvoz većih skupova podataka može funkcionirati, ali traje dugo i mogao bi isteći zbog Power BI ograničenja. Za više informacija pogledajte [Power BI: Preporuke za velike skupove podataka](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Rad s podskupom podataka

Razmislite o radu s podskupom podataka. Na primer, kreiraj [segmente](segments.md) umjesto da izvezeš sve zapise o klijentima u Power BI.

## <a name="troubleshooting"></a>Otklanjanje poteškoća

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Okruženje Customer Insights ne prikazuje se u Power BI

Okruženja koja imaju više od jednog [odnosa definiranog](relationships.md) između dva identična entiteta u Customer Insights neće biti dostupna u povezniku Power BI.

Identificirajte i uklonite duplicirane Odnosi.

1. Otvorite **Podaci** > **Odnosi** o okruženju koje vam nedostaje .Power BI
1. Identificiranje dupliciranih odnosa:
   - Provjerite postoji li više odnosa definiranih između dvaju istih entiteta.
   - Provjerite postoji li odnos stvoren između dvaju entiteta koja su oba uključena u proces objedinjavanja. Definiran je implicitni odnos između svih entiteta uključenih u proces objedinjavanja.
1. Uklonite sve identificirane duplicirane odnose.

Nakon uklanjanja dupliciranih odnosa, pokušajte ponovno konfigurirati poveznik za Power BI.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Pogreške u poljima datuma prilikom učitavanja entiteta u Power BI Desktop

Prilikom učitavanja entiteta koji sadrže polja s oblikom datuma kao što je MM/DD/GGGG, možda ćete naići na pogreške zbog neusklađenih oblika regionalne sheme. Ta se nepodudarnost događa kada je datoteka Power BI Desktop postavljena na drugu regionalnu shemu nego na engleski (Sad), jer se polja datuma u korisničkim uvidima spremaju u američkom obliku.

Datoteka Power BI Desktop ima jednu postavku jezika koja se primjenjuje prilikom preuzimanja podataka. Da biste ispravili pogreške datuma, [postavite regionalnu shemu . BPI datoteka](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) na engleski (Sjedinjene Američke Države).

[!INCLUDE [footer-include](includes/footer-banner.md)]
