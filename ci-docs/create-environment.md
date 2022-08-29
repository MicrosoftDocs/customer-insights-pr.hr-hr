---
title: Stvaranje novog okruženja
description: Koraci za stvaranje okruženja u sustavu Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304234"
---
# <a name="create-a-new-environment"></a>Stvaranje novog okruženja

Nakon [kupnje licence za pretplatu za Dynamics 365 Customer Insights](paid-license.md), globalni administrator Microsoft 365 klijenta prima e-poruku koja ih poziva na stvaranje okruženja. Idite na [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) za početak. U ovom scenariju započnite s prvim korakom [: navedite osnovne informacije](#step-1-provide-basic-information).

Nakon stvaranja prvog okruženja Microsoft 365 globalni administrator klijenta može [dodati korisnike iz svoje organizacije kao administratore](permissions.md). Ti administratori tada mogu upravljati korisnicima i okruženjima. Ako vaša tvrtka ili ustanova kupi više od jedne licence za Customer Insights, [obratite se našem timu](https://go.microsoft.com/fwlink/?linkid=2079641) za podršku da biste povećali broj dostupnih okruženja. Dodatne informacije o kapacitetu i kapacitetu dodatka potražite u vodiču [za](https://go.microsoft.com/fwlink/?LinkId=866544) licenciranje sustava Dynamics 365. Nakon što imate mogućnost stvaranja dodatnih okruženja, idite na [Započnite postupak stvaranja okruženja](#start-the-environment-creation-process).

> [!TIP]
> Ako želite isprobati uslugu, pogledajte odjeljak [Postavljanje probnog okruženja](trial-signup.md).

## <a name="prerequisites"></a>Preduvjeti

[Administratorske](permissions.md) dozvole u uvidima kupaca

## <a name="start-the-environment-creation-process"></a>Pokretanje postupka stvaranja okruženja

1. Otvorite birač okruženja i odaberite **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Odaberite birač okruženja.":::

1. Slijedite vođeno iskustvo navedeno u sljedećim odjeljcima da biste pružili sve potrebne informacije za novo okruženje.

## <a name="step-1-provide-basic-information"></a>Prvi korak: pružanje osnovnih informacija

1. Odaberite želite li stvoriti okruženje ispočetka ili kopirati podatke iz drugog okruženja. [Kopiranje podataka iz drugog okruženja](#copy-the-environment-configuration) zahtijeva dodatne korake.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dijaloški okvir za stvaranje novog okruženja Customer Insights.":::

1. Navedite sljedeće pojedinosti:

   - **Naziv**: Naziv za ovo okruženje. Ovo je polje već popunjeno ako ste kopirali iz postojećeg okruženja, ali to možete promijeniti.
   - **Odaberite svoju tvrtku**: Primarni publika za novo okruženje: pojedinačni potrošači (B-do-C) ili [poslovni računi](work-with-business-accounts.md) (B-do-B). Ako vaša organizacija uglavnom posluje s pojedincima, kao što su trgovac na malo ili kafić, odaberite pojedinačne potrošače. Ako su vaš glavni publika druge tvrtke, poput proizvođača automobila ili papirne tvrtke, odaberite poslovne račune.
   - **Vrsta**: Vrsta okruženja: proizvodnja ili memorija za testiranje. Okruženja sigurnosne ograde ne dopuštaju zakazano osvježavanje podataka i namijenjena su predimplementaciji i testiranju. Okruženja sigurnosne ograde koriste istu primarnu ciljnu skupinu kao i trenutačno odabrano radno okruženje.
   - **Regija**: regija u koju je usluga uvedena i hostirana. Da biste [koristili vlastiti Azure Data Lake Storage račun](own-data-lake-storage.md) ili [se povezali s postojećom Microsoft Dataverse organizacijom](customer-insights-dataverse.md), okruženje Customer Insights mora biti u istoj regiji.

1. Odaberite **Dalje**.

## <a name="step-2-configure-data-storage"></a>2. korak: Konfigurirajte pohranu podataka

1. Odaberite mjesto na koje želite pohraniti podatke customer insights:

   - **Pohrana** korisničkih uvida: pohranom podataka upravlja se automatski. To je zadana opcija i ako ne postoje posebni zahtjevi za pohranu podataka na vlastitom računu za pohranu, preporučujemo upotrebu ove opcije.
   - **Azure Data Lake Storage**: Vaš vlastiti Azure Data Lake Storage račun za pohranu podataka tako da imate potpunu kontrolu gdje su podaci pohranjeni. Slijedite korake u odjeljku [Korištenje vlastitog Azure Data Lake Storage računa](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Odaberite željenu opciju za pohranu podataka.":::

1. Odaberite **Dalje**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>3. korak: Povezivanje s platformom Microsoft Dataverse

Ako imate okruženje, povežite Dataverse customer insights. Podijelite podatke s programom Dataverse da biste ih koristili s poslovnim aplikacijama na temelju, kao što su Dynamics 365 Marketing ili aplikacije temeljene na Dataverse modelu u Power Apps sustavu.

1. Slijedite korake u odjeljku [Rad s podacima o uvidima u klijente u sustavu Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="zajedničko korištenje podataka s omogućenim Microsoft Dataverse automatskim omogućivanjem za nova mrežna okruženja.":::

1. Odaberite **Dalje**.

## <a name="step-4-finalize-the-settings"></a>4. korak: Dovršavanje postavki

Pregledajte navedene postavke. Ako sve izgleda dovršeno, odaberite **Stvori** da postavite okruženje.

Upute za kasniju promjenu nekih postavki potražite u članku [Upravljanje okruženjima](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Rad s novim okruženjem

Pregledajte sljedeće članke koji će vam pomoći da započnete s konfiguriranjem Customer Insights:

- [Dodajte još korisnika i dodijelite dozvole](permissions.md).
- [Unesite svoje izvore podataka](data-sources.md) i provedite ih kroz [proces objedinjavanja podataka](data-unification.md) da biste dobili [objedinjene profile klijenata](customer-profiles.md).
- [Obogatite objedinjene profile klijenata](enrichment-hub.md) ili [pokrenite modele predviđanja](predictions-overview.md).
- [Stvori segmente](segments.md) da biste grupirali klijente i [mjere](measures.md) za pregled KPI-jeva.
- [Postavite veze](connections.md) i [izvoze](export-destinations.md) za obradu podskupa vaših podataka u ostalim aplikacijama.

## <a name="copy-the-environment-configuration"></a>Kopiranje konfiguracije okruženja

Ako kao administrator odaberete kopiranje konfiguracije iz postojećeg okruženja, odaberite s popisa svih dostupnih okruženja u tvrtki ili ustanovi.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Snimka zaslona mogućnosti postavki u postavkama okruženja.":::

Kopirane su sljedeće postavke konfiguracije:

- Izvori podataka uvezeni putem Power Query
- Konfiguracija objedinjavanja podataka
- Segmenti
- Mjerila
- Odnosi
- Aktivnosti
- Pretraživanje i filtriranje indeksa
- Izvozi
- Raspored osvježavanja
- Obogaćivanja
- Modeli predviđanje
- Dodjele uloga

### <a name="set-up-a-copied-environment"></a>Postavljanje kopiranog okruženja

Kada kopirate konfiguraciju okruženja, prilikom stvaranja kopiranog okruženja prikazuje se potvrdna poruka. Da biste potvrdili vjerodajnice, poduzmite sljedeće korake.

1. Odaberite **Idi na izvore podataka** da biste vidjeli popis izvora podataka. Svi izvori podataka prikazuju **status Potrebne** vjerodajnice.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Popis izvora podataka koji su kopirani i potrebna im je provjera autentičnosti.":::

1. Uredite izvore podataka i unesite vjerodajnice kako biste ih osvježili. Izvori podataka iz mape Zajednički podatkovni model i Dataverse moraju se stvoriti ručno s istim nazivom kao u izvorišnom okruženju.

1. Nakon osvježenja izvora podataka, idite na **Podaci** > **Objedini**. Ovdje ćete pronaći postavke iz izvornog okruženja. Uredite ih po potrebi ili odaberite **Objedini objedinjavanje** > **profila i ovisnosti** korisnika da biste pokrenuli postupak objedinjavanja podataka i stvorili jedinstveni entitet klijenta.

   > [!TIP]
   > Za poslovne subjekte i kontakte odaberite **Objedinjavanje računa** > **Objedinjavanje profila i ovisnosti**.

1. Kada je ujedinjenje podataka dovršeno, idite na **Mjere** i **segmenti** da biste ih osvježili.

1. Idite na **Veze s administratorima** > **da** biste ponovno uspostavili veze u novom okruženju.

1. Idite na **Obogaćivanje** > **podataka** i **izvoz** > **podataka** da biste ih ponovno aktivirali.

[!INCLUDE [footer-include](includes/footer-banner.md)]
