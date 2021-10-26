---
title: Stvaranje okruženja u aplikaciji Customer Insights
description: Koraci za stvaranje okruženja s licenciranom pretplatom za Dynamics 365 Customer Insights.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 95afd1fedb98a451e4978ee66be2ea98ad7a4a76
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645672"
---
# <a name="create-an-environment-in-audience-insights"></a>Stvaranje okruženja u uvidima u ciljne skupine

Ovaj članak objašnjava kako stvoriti novo okruženje nakon što je vaša tvrtka ili ustanova kupila pretplatu za Dynamics 365 Customer Insights. 

Tvrtke ili ustanove mogu stvoriti *dva* okruženja za svaku licencu za Customer Insights. Ako vaša tvrtka ili ustanova kupi više licenci, [obratite se našem timu za podršku](https://go.microsoft.com/fwlink/?linkid=2079641) da biste povećali broj dostupnih okruženja. Za više informacija o kapacitetu i dodatnom kapacitetu preuzmite [Vodič za licenciranje Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Ako želite isprobati uslugu, pogledajte odjeljak [Postavljanje probnog okruženja](../trial-signup.md).

## <a name="create-a-new-environment"></a>Stvaranje novog okruženja

Nakon što je kupio pretplatničku licencu za Customer Insights, globalni administrator klijenta Microsoft 365 prima poruku e-pošte koja ga poziva da stvori okruženje. Idite na [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) za početak. 

Vođeno iskustvo pomaže vam kroz korake prikupiti sve potrebne informacije za novo okruženje. Za stvaranje ili upravljanje okruženjima potrebne su vam [administratorske dozvole](permissions.md) u uvidima u ciljne skupine.

1. U uvidima u ciljne skupine otvorite birač okruženja i odaberite **+ Novo**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Odaberite birač okruženja.":::

1. Slijedite vođeno iskustvo opisano u sljedećim odjeljcima.

### <a name="step-1-provide-environment-information"></a>1. korak: navedite informacije o okruženju

U koraku **Osnovne informacije** odaberite želite li stvoriti okruženje od nule ili [kopirati podatke iz drugog okruženja](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dijaloški okvir za stvaranje novog okruženja Customer Insights.":::

Navedite sljedeće pojedinosti:
   - **Naziv**: Naziv za ovo okruženje. Ovo je polje već popunjeno ako ste kopirali iz postojećeg okruženja, ali to možete promijeniti.
   - **Odaberite poslovanje**: Odaberite primarnu ciljnu skupinu za novo okruženje. Možete raditi s pojedinačnim klijentima (B2C) ili [poslovnim računima](work-with-business-accounts.md) (B2B).
   - **Vrsta**: Odaberite želite li stvoriti radno okruženje ili okruženje sigurnosne ograde. Okruženja sigurnosne ograde ne dopuštaju zakazano osvježavanje podataka i namijenjena su predimplementaciji i testiranju. Okruženja sigurnosne ograde koriste istu primarnu ciljnu skupinu kao i trenutačno odabrano radno okruženje.
   - **Regija**: Regija u kojoj je usluga uvedena i udomaćena.

### <a name="step-2-configure-data-storage"></a>2. korak: Konfigurirajte pohranu podataka

U koraku **Pohrana podataka** odaberite gdje želite pohraniti podatke iz uvida u ciljne skupine.

Imat ćete dvije mogućnosti: **Pohrana za Customer Insights** (Azure Data Lake kojim upravlja tim za Customer Insights) i **Azure Data Lake Storage** (vlastiti Azure Data Lake Storage). Prema zadanome je odabrana mogućnost pohrane aplikacije Customer Insights.

:::image type="content" source="media/data-storage-environment.png" alt-text="Odaberite Azure Data Lake Storage za pohranu podataka o uvidima u ciljne skupine.":::

Spremanjem podataka u repozitorij Azure Data Lake Storage, slažete se da će se podaci prenijeti i pohraniti na odgovarajuću geografsku lokaciju za taj račun za pohranu Azure. Ta se lokacija može razlikovati od lokacije na kojoj su podaci pohranjeni u sustavu Dynamics 365 Customer Insights. Saznajte više u [Microsoftom centru za pouzdanost](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights trenutačno podržava sljedeće:
> - Uvezeni entiteti iz tokova podataka programa Power BI koji su pohranjeni u Data Lake kojim upravlja Microsoft Dataverse.  
> - Računi za Azure Data Lake Storage iz iste regije za Azure koju ste odabrali prilikom stvaranja okruženja.
> - Računi za Azure Data Lake Storage koji imaju omogućen *prostor za hijerarhijski naziv*.

Za opciju Azure Data Lake Storage možete birati između opcije koja se temelji na resursima i opcije na temelju pretplate za provjeru autentičnosti. Za više informacija pogledajte [Povezivanje uvida ciljne skupine s računom servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure](connect-service-principal.md). Naziv **Spremnika** bit će `customerinsights` i ne može se promijeniti.

Kada su procesi sustava, poput unosa podataka, završeni, sustav stvara odgovarajuće mape na računu za pohranu koji ste naveli. Podatkovne datoteke i datoteke *model.json* stvaraju se i dodaju u mape na temelju naziva procesa.

Ako stvorite više okruženja za Customer Insights i odlučite spremiti izlazne entitete iz tih okruženja na svoj račun za pohranu, Customer Insights stvara zasebne mape za svako okruženje s `ci_environmentID` u spremniku.

### <a name="step-3-connect-to-microsoft-dataverse"></a>3. korak: Povezivanje s platformom Microsoft Dataverse
   
Korak **Microsoft Dataverse** omogućuje vam da povežete Customer Insights s okruženjem Dataverse.

Da biste koristili [gotove modele predviđanja](predictions-overview.md#out-of-box-models), konfigurirajte dijeljenje podataka s platformom Dataverse. Ili možete omogućiti uvoz podataka iz lokalnih izvora podataka, navodeći URL okruženja Microsoft Dataverse kojim upravlja vaša tvrtka ili ustanova. Odaberite **Omogući dijeljenje podataka** za dijeljenje izlaznih podataka usluge Customer Insights pomoću Dataverse Managed Data Lake.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Mogućnosti konfiguracije za omogućavanje dijeljenja podataka uz Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights ne podržava sljedeće scenarije dijeljenja podataka:
> - Ako sve podatke spremite na vlastiti repozitorij Azure Data Lake Storage, nećete moći omogućiti dijeljenje podataka s repozitorijem Data Lake kojim upravlja Microsoft Dataverse.
> - Ako omogućite dijeljenje podataka s repozitorijem Data Lake kojim upravlja Microsoft Dataverse, nećete moći [stvoriti predviđene ili nedostajuće vrijednosti u entitetu](predictions.md).

### <a name="step-4-finalize-the-settings"></a>4. korak: Dovršavanje postavki

U koraku **Pregled** prođite kroz sve navedene postavke. Ako sve izgleda dovršeno, odaberite **Stvori** da postavite okruženje. 

Većinu postavki možete promijeniti i kasnije. Dodatne informacije potražite u odjeljku [Upravljanje okruženjima](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Rad s novim okruženjem

Pregledajte sljedeće članke koji će vam pomoći da započnete s konfiguriranjem Customer Insights. 

- [Dodajte još korisnika i dodijelite dozvole](permissions.md).
- [Unesite svoje izvore podataka](data-sources.md) i provedite ih kroz [proces objedinjavanja podataka](data-unification.md) da biste dobili [objedinjene profile klijenata](customer-profiles.md).
- [Obogatite objedinjene profile klijenata](enrichment-hub.md) ili [pokrenite modele predviđanja](predictions-overview.md).
- [Stvorite segmente](segments.md) da biste grupirali klijente i [mjere](measures.md) pregleda KPI-jeva.
- [Postavite veze](connections.md) i [izvoze](export-destinations.md) za obradu podskupa vaših podataka u ostalim aplikacijama.
