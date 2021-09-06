---
title: Stvaranje i konfiguriranje probne verzije za Customer Insights
description: Koraci za dobivanje probne pretplate za Dynamics 365 Customer Insights i konfiguraciju.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f038dedd369ac9e623146b66528efa87c47a8c23769037d8709fa9b804a0b723
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035406"
---
# <a name="set-up-a-trial-environment"></a>Postavljanje probnog okruženja 

Probna verzija za Dynamics 365 Customer Insights omogućuje vam pregled ključnih mogućnosti i upoznavanje s različitim značajkama. Probna pretplata briše se nakon isteka. Probna okruženja stvaraju pojedinačni korisnici koji postaju administratori probnog okruženja. Oni mogu pozvati više korisnika na probnu verziju i konfigurirati različite značajke.

## <a name="create-a-trial-environment"></a>Stvaranje novog okruženja

Možete se prijaviti za probno razdoblje na [stranici za prijavu za probnu razdoblje](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Odaberite mogućnost **Prijavi se za besplatno probno razdoblje** i odaberite **Prijavi se odmah**.

1. Navedite svoju poslovnu ili školsku adresu e-pošte, recite nam nešto više o sebi i odaberite **Početak**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dijaloški okvir za prijavu za probnu verziju instance":::

1. Pregledajte uvjete i odredbe i odaberite **Nastavi** da biste potvrdili.

1. Navedite **Naziv** za svoje novo okruženje. 

1. Postavite **Vrstu** okruženja kao **Probno**.

1. U polju **Odaberite pokaznu verziju industrije**, neobavezno možete odabrati skup podataka za određenu industriju. Možete i kasnije [promijeniti u pokaznu verziju industrije](#use-industry-specific-demo-data-sets-in-audience-insights) i započeti sa zadanim skupom podataka.

1. Odaberite **Regiju** za svoje okruženje.

1. Neobavezno, ako ste administrator tvrtke ili ustanove Dynamics 365: Odaberite **Napredne postavke** i navedite URL svoje tvrtke ili ustanove za korištenje značajki predviđanja, kao što je predviđanje gubitka klijenata. 

1. Kliknite **Stvori**. 

Dovršetak postavljanja okruženja traje nekoliko trenutaka. Nakon dovršetka bit ćete preusmjereni na demo okruženje ili pokaznu verziju industrije koju ste odabrali u gornjem koraku. Sada možete istraživati aplikaciju s demo podacima samo za čitanje. Za dodavanje vlastitih podataka u okruženje pogledajte [Stvaranje demo podataka specifičnih za scenarij u vlastitom okruženju](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Snimka zaslona novostvorenog probnog okruženja.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Korištenje skupova demo podataka specifičnih za industriju u uvidima u ciljnu skupinu

Povezivanje stvarnih izvora podataka jedan je od kritičnih koraka u korištenju snage koju posjeduje Customer Insights. Za isprobavanje značajki bez sukoba s vlastitim podacima, neobavezno možete koristiti demo podatke specifične za industriju. Dostupno je nekoliko skupova demo podataka za sljedeće industrije: 

-   Automobilska industrija
-   Bankarstvo
-   Potrošačka roba
-   Državne ustanove
-   Zdravstvena skrb
-   Uslužna djelatnost
-   Osiguranje
-   Proizvodnja
-   Profesionalne usluge
-   Maloprodaja

### <a name="see-industry-specific-demo-data-in-trials"></a>Pogledajte demo podatke specifične za industriju u probnim verzijama

Za verziju Customer Insights samo za čitanje, prilagođenu određenoj industriji ili scenariju, započnite u demo okruženju. 
 
1.  U uvidima u ciljnu skupinu odaberite **Demo** okruženje u biraču okruženja.

2.  Na zaslonu **Početno** odaberite mogućnost s padajućeg izbornika Odabir demonstracije industrije.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Odaberite industriju za probno okruženje.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Stvaranje demo podataka specifičnih za scenarij u vlastitom okruženju

Kao administrator odaberite birač okruženja u zaglavlju aplikacije da biste stvorili novo okruženje. U novom okruženju možete konfigurirati vlastite izvore podataka i postaviti aplikaciju prema svojim zahtjevima. 

1.  U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2.  Za uvoz vlastitih izvora podataka idite na [vodič za unos podataka](data-sources.md).     
   Ako više volite raditi s uzorcima podataka koji vam omogućuju isprobavanje unosa podataka, možete unijeti demo podatke industrije u svoje okruženje. Odaberite mogućnost **Uvezi iz Središta za podatke** i slijedite korake u nastavku.

3.  Odaberite karticu industrije koja odgovara vašem scenariju. 

4.  Pregledajte i neobavezno ažurirajte predloženi naziv izvora podataka. 

5.  Odaberite **Dalje** za unos uzorka podataka. 

Sada možete koristiti unesene podatke za prilagođavanje Customer Insights svome scenariju. Da biste vidjeli okruženje specifično za unesene demo podatke, odaberite mogućnost **<Industry> Demo** u biraču okruženja.

## <a name="limitations-in-trials"></a>Ograničenja u probnim verzijama

- Probne su verzije prema zadanim postavkama aktivne 30 dana. Međutim, možete ih produžiti nakon 23. dana od kada se prijavite za probno razdoblje.
- Ne možete koristiti vlastiti račun za Azure Data Lake Storage za pohranu izlaznih podataka tijekom probnog razdoblja. Međutim, možete unijeti podatke s računa za pohranu Data Lake.
- Možete pohraniti do 3 GB podataka u okruženje Dataverse koje se automatski dodjeljuje kada započnete probnu verziju Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Kopiranje podataka iz probne verzije na plaćenu pretplatu

Općenito preporučujemo da počnete iznova s vlastitim podacima prilikom nadogradnje na plaćenu verziju Customer Insights. 

Neobavezno možete kopirati svoje podatke iz probnog okruženja ako kupite Customer Insights. Morate biti administrator probne verzije Customer Insights i globalni administrator vašeg klijenta za Microsoft 365 ili administrator sustava Dynamics 365 u vašoj tvrtki ili ustanovi za premještanje postavki iz probnog okruženja u plaćeno okruženje. 

Nakon što se prvi put prijavite u svoju plaćenu instancu Customer Insights, od vas će se tražiti da stvorite novo okruženje. U ovom procesu možete odabrati kopiranje konfiguracije iz postojećeg okruženja i premještanje većine postavki. Ako imate gore navedene dozvole, probno okruženje prikazat će se na ovom popisu. Za više informacija pogledajte [Kopiranje konfiguracije okruženja](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Sljedeći koraci

Pregledajte sljedeće članke koji će vam pomoći da započnete s konfiguriranjem Customer Insights. 

- [Dodajte još korisnika i dodijelite dozvole](permissions.md).
- [Unesite svoje izvore podataka](data-sources.md) i provedite ih kroz [proces objedinjavanja podataka](data-unification.md) da biste dobili [objedinjene profile klijenata](customer-profiles.md).
- [Obogatite objedinjene profile klijenata](enrichment-hub.md) ili [pokrenite modele predviđanja](predictions-overview.md).
- Stvorite [segmente](segments.md) da biste grupirali klijente i [mjere](measures.md) pregleda KPI-jeva.
- Postavite [veze](connections.md) i [izvoze](export-destinations.md) za obradu podskupa vaših podataka u ostalim aplikacijama.