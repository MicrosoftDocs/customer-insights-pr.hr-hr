---
title: 'Kako: stvoriti novo okruženje'
description: Koraci za stvaranje okruženja u sustavu Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 875cbbd095dfd239ab83c1c80db28ea7c0a04ed0
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245548"
---
# <a name="how-to-create-a-new-environment"></a>Kako: stvoriti novo okruženje

Nakon [kupnje licence za pretplatu za Dynamics 365 Customer Insights](paid-license.md), globalni administrator Microsoft 365 klijenta prima e-poruku koja ih poziva na stvaranje okruženja. Idite na [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) za početak. U ovom scenariju možete ići izravno na [prvi korak: Navedite osnovne informacije](#step-1-provide-basic-information).

Nakon stvaranja prvog okruženja globalni administrator klijenta može Microsoft 365 dodati korisnike koji [formiraju svoju organizaciju kao administratore](permissions.md). Napredujući, ti administratori mogu upravljati korisnicima i okruženjima. Ako vaša tvrtka ili ustanova kupi više od jedne licence za Customer Insights, [obratite se našem timu](https://go.microsoft.com/fwlink/?linkid=2079641) za podršku da biste povećali broj dostupnih okruženja. Dodatne informacije o kapacitetu i kapacitetu dodatka potražite u vodiču [za](https://go.microsoft.com/fwlink/?LinkId=866544) licenciranje sustava Dynamics 365.

> [!TIP]
> Ako želite isprobati uslugu, pogledajte odjeljak [Postavljanje probnog okruženja](trial-signup.md).

## <a name="prerequisites"></a>Preduvjeti

Za stvaranje okruženja ili upravljanje njima potrebne su vam [administratorske](permissions.md) dozvole u customer insights.

## <a name="start-the-environment-creation-process"></a>Pokretanje postupka stvaranja okruženja

1. Otvorite birač okruženja i odaberite **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Odaberite birač okruženja.":::

1. Slijedite vođeno iskustvo navedeno u sljedećim odjeljcima da biste pružili sve potrebne informacije za novo okruženje. Ako ste ranije konfigurirali okruženje, možete kopirati i [konfiguraciju](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Prvi korak: pružanje osnovnih informacija

U koraku **Osnovne informacije** odaberite želite li stvoriti okruženje od nule ili [kopirati podatke iz drugog okruženja](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dijaloški okvir za stvaranje novog okruženja Customer Insights.":::

Navedite sljedeće pojedinosti:

- **Naziv**: Naziv za ovo okruženje. Ovo je polje već popunjeno ako ste kopirali iz postojećeg okruženja, ali to možete promijeniti. Ako imate više radnih okruženja, svakome dajte lako prepoznatljivo ime.
- **Odaberi poslovanje**: Odaberite primarnu ciljnu skupinu za novo okruženje. Možete raditi s pojedinačnim potrošačima (B2C) ili [poslovnim računima](work-with-business-accounts.md) (B2B). Ako vaša organizacija uglavnom posluje s pojedincima, kao što su trgovac na malo ili kafić, odaberite pojedinačne potrošače. U slučaju da su vaše glavne publika druge tvrtke, poput proizvođača automobila ili papirne tvrtke, odaberite poslovne račune.
- **Vrsta**: Odaberite želite li stvoriti radno okruženje ili okruženje sigurnosne ograde. Okruženja sigurnosne ograde ne dopuštaju zakazano osvježavanje podataka i namijenjena su predimplementaciji i testiranju. Okruženja sigurnosne ograde koriste istu primarnu ciljnu skupinu kao i trenutačno odabrano radno okruženje.
- **Regija**: Regija u kojoj je usluga uvedena i udomaćena. Da biste [koristili vlastiti Azure Data Lake Storage račun](own-data-lake-storage.md) ili [se povezali s postojećom Microsoft Dataverse organizacijom](customer-insights-dataverse.md), okruženje Customer Insights mora biti u istoj regiji.

## <a name="step-2-configure-data-storage"></a>2. korak: Konfigurirajte pohranu podataka

U koraku **za pohranu** podataka odaberite gdje želite pohraniti podatke Customer Insights.

Možete birati između dvije mogućnosti:

- **Pohrana** customer insights: Pohranom podataka upravlja tim Customer Insights. To je zadana opcija i ako ne postoje posebni zahtjevi za pohranu podataka na vlastitom računu za pohranu, preporučujemo upotrebu ove opcije.
- **Azure Data Lake Storage**: Navedite vlastiti Azure Data Lake Storage račun za pohranu podataka kako biste imali potpunu kontrolu nad mjestom pohrane podataka. Dodatne informacije potražite u članku [Korištenje vlastitog Azure Data Lake Storage računa](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Odaberite željenu opciju za pohranu podataka.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>3. korak: Povezivanje s platformom Microsoft Dataverse

Korak **Microsoft Dataverse** omogućuje vam da povežete Customer Insights s okruženjem Dataverse. Podijelite podatke s programom Dataverse da biste ih koristili s poslovnim aplikacijama na temelju, kao što su Dynamics 365 Marketing ili aplikacije temeljene na Dataverse modelu u Power Apps sustavu.

Ostavite ovo polje prazno ako nemate vlastito Dataverse okruženje, a mi ćemo ga stvoriti za vas.

Dodatne informacije potražite u odjeljku [Rad s podacima o uvidima u klijente u sustavu Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="zajedničko korištenje podataka s omogućenim Microsoft Dataverse automatskim omogućivanjem za nova mrežna okruženja.":::

### <a name="step-4-finalize-the-settings"></a>4. korak: Dovršavanje postavki

U koraku **Pregled** prođite kroz sve navedene postavke. Ako sve izgleda dovršeno, odaberite **Stvori** da postavite okruženje.

Neke postavke možete promijeniti kasnije. Dodatne informacije potražite u odjeljku [Upravljanje okruženjima](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Rad s novim okruženjem

Pregledajte sljedeće članke koji će vam pomoći da započnete s konfiguriranjem Customer Insights:

- [Dodajte još korisnika i dodijelite dozvole](permissions.md).
- [Unesite svoje izvore podataka](data-sources.md) i provedite ih kroz [proces objedinjavanja podataka](data-unification.md) da biste dobili [objedinjene profile klijenata](customer-profiles.md).
- [Obogatite objedinjene profile klijenata](enrichment-hub.md) ili [pokrenite modele predviđanja](predictions-overview.md).
- [Stvori segmente](segments.md) da biste grupirali klijente i [mjere](measures.md) za pregled KPI-jeva.
- [Postavite veze](connections.md) i [izvoze](export-destinations.md) za obradu podskupa vaših podataka u ostalim aplikacijama.

## <a name="copy-the-environment-configuration"></a>Kopiranje konfiguracije okruženja

Kao administrator možete odabrati kopiranje konfiguracije iz postojećeg okruženja kada stvorite novu.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Snimka zaslona mogućnosti postavki u postavkama okruženja.":::

Vidjet ćete popis svih dostupnih okruženja u svojoj tvrtki ili ustanovi iz kojih možete kopirati podatke.

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

## <a name="set-up-a-copied-environment"></a>Postavljanje kopiranog okruženja

Kada kopirate konfiguraciju okruženja, morate proći kroz neke dodatne korake da biste potvrdili vjerodajnice:

- Profili klijenata. Prvo provjerite autentičnost i unos izvora podataka i pokrenite ujedinjenje podataka da biste ponovno stvorili korisničke profile.
- Vjerodajnice izvora podataka. Morate navesti vjerodajnice za svaki izvor podataka za ručnu provjeru autentičnosti i osvježavanje izvora podataka.
- Izvori podataka iz mape Zajednički podatkovni model i Dataverse. Te izvore podataka morate stvoriti ručno s istim nazivom kao u izvorišnom okruženju.
- Tajne povezivanja koje se koriste za izvoz i obogaćivanje. Morate ponovno uspostaviti veze, a zatim ponovno aktivirati obogaćivanja i izvoz.

Prilikom stvaranja kopiranog okruženja prikazat će se potvrdna poruka. Odaberite **Idi na izvore podataka** da biste vidjeli popis izvora podataka.

Svi će izvori podataka prikazati status **Potrebne su vjerodajnice**. Uredite izvore podataka i unesite vjerodajnice kako biste ih osvježili.

:::image type="content" source="media/data-sources-copied.png" alt-text="Popis izvora podataka koji su kopirani i potrebna im je provjera autentičnosti.":::

Nakon osvježenja izvora podataka, idite na **Podaci** > **Objedini**. Ovdje ćete pronaći postavke iz izvornog okruženja. Uredite ih po potrebi ili odaberite **Pokreni** za pokretanje postupka objedinjavanja podataka i stvaranje jedinstvenog entiteta klijenta.

Nakon završetka objedinjavanja podataka idite na **Mjere** i **Segmenti** da ih osvježite.

Prije nego što ponovno aktivirate izvoz i obogaćivanja, idite na **Administratorske** > **veze** da biste ponovno uspostavili veze u novom okruženju.

[!INCLUDE [footer-include](includes/footer-banner.md)]
