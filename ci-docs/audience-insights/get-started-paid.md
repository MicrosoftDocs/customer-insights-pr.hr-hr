---
title: Stvaranje i konfiguriranje plaćene licence za Customer Insights
description: Koraci za dobivanje licencirane pretplate za Dynamics 365 Customer Insights i konfiguraciju.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034443"
---
# <a name="get-started-with-a-paid-subscription"></a>Uvod u plaćenu pretplatu

Ovaj članak objašnjava kako stvoriti novo okruženje nakon što je vaša tvrtka ili ustanova kupila pretplatu za Dynamics 365 Customer Insights. Ako želite kupiti Customer Insights, naše su mogućnosti kontakta navedene na [web-stranici Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Ako želite isprobati uslugu i značajke, pogledajte [Postavljanje probnog okruženja](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Stvaranje okruženja u postojećoj tvrtki ili ustanovi

Nakon što je kupio pretplatničku licencu za Customer Insights, globalni administrator klijenta Microsoft 365 prima poruku e-pošte koja ga poziva da stvori okruženje. Idite na [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) za početak. 

Customer Insights nije licenciran po korisniku pa se neće prikazivati u području Licence. Ako tražite licencu u centru za administratore Microsoft 365, idite na **Vaši proizvodi**. 

> [!NOTE]
> Tvrtke ili ustanove mogu stvoriti *dva* okruženja za svaku licencu za Customer Insights. Ako vaša tvrtka ili ustanova kupi više od jedne licence, [obratite se našem timu za podršku](https://go.microsoft.com/fwlink/?linkid=2079641) kako bi se povećao broj dostupnih okruženja. Za više informacija o kapacitetu i dodatnom kapacitetu preuzmite [Vodič za licenciranje Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Da biste stvorili okruženje:

1. U dijaloškom okviru **Stvaranje okruženja** odaberite **Novo okruženje**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dijaloški okvir za stvaranje novog okruženja Customer Insights.":::

   Preporučujemo da počnete postavljati okruženje od početka. Međutim, ako ste administrator ili član probnog okruženja, mogli biste [kopirati podatke iz drugog okruženja](manage-environments.md#copy-the-environment-configuration) odabirom **Kopiraj iz postojećeg okruženja**. Vidjet ćete popis svih dostupnih okruženja u svojoj tvrtki ili ustanovi iz kojih možete kopirati podatke.

1. Navedite sljedeće pojedinosti:
   - **Naziv**: Naziv za ovo okruženje. Ovo je polje već popunjeno ako ste kopirali iz postojećeg okruženja, ali to možete promijeniti.
   - **Regija**: Regija u kojoj je usluga uvedena i udomaćena.
   - **Vrsta**: Odaberite želite li stvoriti radno okruženje ili okruženje sigurnosne ograde. Okruženja sigurnosne ograde ne dopuštaju zakazano osvježavanje podataka i namijenjena su predimplementaciji i testiranju.
   
1. Po želji, možete odabrati **Napredne postavke**:

   - **Spremi sve podatke u**: Određuje gdje želite pohraniti izlazne podatke generirane iz aplikacije Customer Insights. Imat ćete dvije mogućnosti: **Pohrana za Customer Insights** (Azure Data Lake kojim upravlja tim za Customer Insights) i **Azure Data Lake Storage** (vlastiti Azure Data Lake Storage). Prema zadanome je odabrana mogućnost pohrane aplikacije Customer Insights.

     > [!NOTE]
     > Pohranjivanjem podataka u Azure Data Lake Storage slažete se s prijenosom podataka na odgovarajuću geografsku lokaciju za taj račun za pohranu za Azure te s njihovom pohranom na toj lokaciji. Ta lokacija može se razlikovati od lokacije za pohranu podataka u aplikaciji Dynamics 365 Customer Insights. [Saznajte više u Microsoftom centru za pouzdanost.](https://www.microsoft.com/trust-center)
     >
     > Trenutno se uneseni entiteti iz tijekova podataka Power BI pohranjuju u Data Lake kojim upravlja Microsoft Dataverse. 
     > 
     > Podržavamo samo Azure Data Lake Storage račune iz iste Azure regije koju ste odabrali prilikom stvaranja okruženja. 
     > 
     > Podržavamo samo Azure Data Lake Storage račune koji imaju omogućen hijerarhijski imenski prostor.


   - Za opciju Azure Data Lake Storage možete birati između opcije koja se temelji na resursima i opcije na temelju pretplate za provjeru autentičnosti. Za više informacija pogledajte [Povezivanje uvida ciljne skupine s računom servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure](connect-service-principal.md). Naziv **Spremnika** se ne može promijeniti i bit će `customerinsights`.
   
   - Ako želite koristiti [gotove modele](predictions-overview.md#out-of-box-models), konfigurirajte dijeljenje podataka pomoću Microsoft Dataverse ili omogućite unos podataka iz lokalnih izvora podataka, dostavite URL okruženja Microsoft Dataverse pod **Konfiguriraj dijeljenje podataka pomoću Microsoft Dataverse i omogući dodatne mogućnosti**. Odaberite **Omogući dijeljenje podataka** za dijeljenje izlaznih podataka usluge Customer Insights pomoću Microsoft Dataverse Managed Data Lake.

     > [!NOTE]
     > - Dijeljenje podataka pomoću Microsoft Dataverse Managed Data Lake trenutno nije podržano kada sve podatke spremite u vlastiti Azure Data Lake Storage.
     > - [Predviđanje vrijednosti koje nedostaju u entitetu](predictions.md) trenutno nije podržano kada omogućite dijeljenje podataka uz Microsoft Dataverse Managed Data Lake.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Mogućnosti konfiguracije za omogućavanje dijeljenja podataka uz Microsoft Dataverse.":::

   Kada se procesi sustava, kao što je unos podataka, dovrše, sustav stvara odgovarajuće mape na računu za pohranu koji ste naveli. Podatkovne datoteke i datoteke model.json stvaraju se i dodaju u mape na temelju naziva procesa.

   Ako stvorite više okruženja značajke Customer Insights i odaberete spremiti izlazne entitete iz tih okruženja na svoj račun za pohranu, za svako će se okruženje stvoriti zasebne mape s ci_<environmentid> u spremniku.

1. Odaberite **Stvori** da biste postavili okruženje. 

## <a name="configure-an-environment"></a>Konfiguracija okruženja

Pregledajte sljedeće članke koji će vam pomoći da započnete s konfiguriranjem Customer Insights. 

- [Dodajte još korisnika i dodijelite dozvole](permissions.md).
- [Unesite svoje izvore podataka](data-sources.md) i provedite ih kroz [proces objedinjavanja podataka](data-unification.md) da biste dobili [objedinjene profile klijenata](customer-profiles.md).
- [Obogatite objedinjene profile klijenata](enrichment-hub.md) ili [pokrenite modele predviđanja](predictions-overview.md).
- Stvorite [segmente](segments.md) da biste grupirali klijente i [mjere](measures.md) pregleda KPI-jeva.
- Postavite [veze](connections.md) i [izvoze](export-destinations.md) za obradu podskupa vaših podataka u ostalim aplikacijama.
