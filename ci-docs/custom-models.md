---
title: Prilagođeni modeli za strojno učenje | Microsoft Docs
description: Radite s prilagođenim modelima iz Strojnog učenja Azure u aplikaciji Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609734"
---
# <a name="custom-machine-learning-models"></a>Prilagođeni modeli za strojno učenje

> [!NOTE]
> Podrška za Strojno učenje Studio (klasik) završit će 31. kolovoza 2024. Preporučujemo da do tog datuma prijeđete na [Strojno učenje](/azure/machine-learning/overview-what-is-azure-machine-learning) servisa Azure.
>
> Od 1. prosinca 2021. nećete moći stvarati nove Strojno učenje Studio (klasične) resurse. Do 31. kolovoza 2024. možete nastaviti koristiti postojeće resurse Strojno učenje Studija (klasičnih). Dodatne informacije potražite u članku [Migracija na Strojno učenje servisa Azure](/azure/machine-learning/migrate-overview).

Prilagođeni modeli omogućuju upravljanje tijekovima rada na temelju modela servisa Azure Strojno učenje. Tijekovi rada pomažu vam u odabiru podataka iz kojih želite generirati uvide i mapiranju rezultata u vaše objedinjene podatke o klijentima. Dodatne informacije o izradi prilagođenih modela strojnog učenja potražite u odjeljku [Upotreba modela na temelju Strojnog učenja Azure](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Preduvjeti

- Web-usluge objavljene putem [skupnih cjevovoda servisa Azure Strojno učenje](/azure/machine-learning/concept-ml-pipelines).
- Plinovod mora biti objavljen u okviru cjevovoda [krajnja točka](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Račun [za](/azure/storage/blobs/data-lake-storage-quickstart-create-account) pohranu servisa Azure Data Lake Gen2 povezan s instancom servisa Azure Studio.
- Za radne prostore servisa Azure Strojno učenje s dozvolama za klijente, vlasnika ili administratora korisničkog pristupa u radni prostor azure Strojno učenje.

  > [!NOTE]
  > Podaci se prenose između instanci servisa Customer Insights i odabranih web-servisa Azure ili kanala u tijeku rada. Kada prenosite podatke na uslugu Azure, provjerite je li usluga konfigurirana za obradu podataka na način i na lokaciji koja je potrebna da ti podaci ispune sve pravne ili regulatorne zahtjeve vaše tvrtke ili ustanove.

## <a name="add-a-new-workflow"></a>Dodavanje novog tijeka rada

1. Idite u odjeljak **Inteligencija** > **Prilagođeni modeli** i odaberite **Novi tijek rada**.

1. Navedite prepoznatljiv **naziv**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Snimka zaslona okna Novi tijek rada.":::

1. Odaberite tvrtku ili ustanovu koja sadrži web-servis u **Klijent koji sadrži vaš web-servis**.

1. Ako je pretplata na Strojno učenje Azure u nekom drugom klijentu, a ne u sustavu Customer Insights, odaberite **Prijava** s vjerodajnicama za odabranu tvrtku ili ustanovu.

1. Odaberite **Radne prostore** povezane s vašim web-servisom.

1. Odaberite kanal Azure Strojno učenje u web-usluzi **koja sadrži padajući izbornik modela**. Zatim odaberite **Dalje**.
   Saznajte više o [objavljivanju kanala u Strojnom učenju Azure pomoću dizajnera](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ili [SDK-a](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Za svaki **Ulazni podatak web-servisa** odaberite odgovarajući **Entitet** iz aplikacije Customer Insights. Zatim odaberite **Dalje**.
   > [!NOTE]
   > Tijek rada prilagođenog modela primijenit će heuristiku za mapiranje polja za unos web-usluga u atribute entiteta na temelju naziva i vrste podataka polja. Vidjet ćete pogrešku ako se polje web-usluge ne može mapirati na entitet.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Konfigurirajte tijek rada.":::

1. Za **izlazne parametre** modela postavite sljedeća svojstva:
   - **Naziv** entiteta za izlazne rezultate kanala
   - **Naziv** parametra izlazne pohrana podataka skupnog cjevovoda
   - **Naziv** parametra izlaznog puta skupnog kanala

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Okno izlaznog parametra modela.":::

1. Odaberite odgovarajući atribut iz **korisničkog ID-a u rezultatima** koji identificiraju klijente i odaberite **Spremi**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Okno povezivanja rezultata s podacima klijenta.":::

   Zaslon spremljenog **tijeka** rada prikazuje detalje o tijeku rada. Ako ste konfigurirali tijek rada za kanal Azure Strojno učenje, Customer Insights prilaže se radnom prostoru koji sadrži kanal. Customer Insights dobit **će suradnik** ulogu u radnom prostoru servisa Azure.

1. Odaberite **Gotovo**. Prikazuje se stranica Prilagođeni **modeli**.

1. Odaberite okomitu trotočje (&vellip;) za tijek rada i odaberite **Pokreni**. Tijek rada također se automatski pokreće sa svakim [zakazanim osvježavanjem](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Upravljanje postojećim tijekom rada

Idite na **Prilagođene modele inteligencije** > **da** biste vidjeli tijekove rada koje ste stvorili.

Odaberite tijek rada za prikaz dostupnih akcija.

- **Uređivanje** tijeka rada
- **Pokretanje** tijeka rada
- [**Brisanje**](#delete-a-workflow) tijeka rada

### <a name="edit-a-workflow"></a>Uređivanje tijeka rada

1. Idite na **Prilagođene modele inteligencije** > **·**.

1. Uz tijek rada koji želite ažurirati odaberite okomitu trotočje (&vellip;) i odaberite **Uredi**.

1. Po potrebi promijenite **zaslonsko ime**, a zatim odaberite **Dalje**.

1. Za svaki **unos** web-usluge po potrebi ažurirajte odgovarajući **entitet** iz Customer Insights. Zatim odaberite **Dalje**.

1. Za **izlazne parametre** modela promijenite nešto od sljedećeg:
   - **Naziv** entiteta za izlazne rezultate kanala
   - **Naziv** parametra izlazne pohrana podataka skupnog cjevovoda
   - **Naziv** parametra izlaznog puta skupnog kanala

1. Promijenite atribut podudaranja iz **korisničkog ID-a u rezultatima** da biste identificirali kupce. Odaberite atribut iz zaključnih rezultata s vrijednostima sličnim stupcu ID klijenta entiteta Klijent. Ako nemate takav stupac u skup podataka, odaberite atribut koji jedinstveno identificira redak.

1. Odaberite **Spremi**

### <a name="delete-a-workflow"></a>Brisanje tijeka rada

1. Idite na **Prilagođene modele inteligencije** > **·**.

1. Uz tijek rada koji želite izbrisati odaberite okomitu trotočje (&vellip;) i odaberite **Izbriši**.

1. Potvrdite brisanje.

Vaš će se tijek rada izbrisati. Entitet [koji](entities.md) je stvoren prilikom stvaranja tijeka rada se nastavlja i može se prikazati sa **stranice Entiteti** > **podataka**.

## <a name="view-the-results"></a>Prikaz rezultata

Rezultati tijeka rada pohranjuju se u naziv entiteta definiran za **izlazne parametre** modela. Pristupite tim podacima sa [**stranice Podatkovni** > **entiteti** ili s pristupom](entities.md) API-ju [...](apis.md).

### <a name="api-access"></a>API pristup

Za određeni upit OData za dobivanje podataka iz entiteta prilagođenog modela koristite sljedeći format:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Zamijenite `<your instance id>` ga ID-om okruženja Customer Insights koje se prikazuje u adresnoj traci vašeg preglednika prilikom pristupa Customer Insights.

1. Zamijenite `<custom model output entity>` nazivom entiteta koji ste naveli za izlazne parametre **modela**.

1. Zamijenite `<guid value>` ga ID-om kupca kupca kojem želite pristupiti. Ovaj se ID prikazuje na [stranici](customer-profiles.md) profili kupaca u polju ID kupca.

## <a name="frequently-asked-questions"></a>Najčešća pitanja

- Zašto ne mogu vidjeti svoj kanal prilikom postavljanja tijeka rada prilagođenog modela?
  Uzrok ovog problema je često u konfiguraciji u kanalu. Osigurajte da je [konfiguriran ulazni parametar](azure-machine-learning-experiments.md#dataset-configuration) i da su konfigurirani [izlazni parametri spremišta podataka i putanje](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).

- Što znači pogreška "Nije bilo moguće spremiti tijek rada inteligencije"? 
  Korisnici obično vide ovu poruku o pogrešci ako u radnom prostoru nemaju privilegije administratora pristupa vlasnika ili korisnika. Korisnik treba višu razinu dozvola kako bi omogućio servisu Customer Insights da obradi tijek rada kao uslugu umjesto korištenja korisničkih vjerodajnica za sljedeća izvođenja tijeka rada.

- Je li podržana privatna krajnja točka / privatna veza za tijek rada prilagođenog modela?
  Customer Insights trenutno ne podržava privatne krajnja točka za prilagođene modele izvan okvira, ali dostupno je ručno zaobilazno rješenje. Za detalje se obratite podršci.

## <a name="responsible-ai"></a>Odgovorna umjetna inteligencija

Predviđanja nude mogućnosti stvaranja boljih korisničkih iskustava, poboljšanja poslovnih mogućnosti i izvora prihoda. Preporučujemo vam da uravnotežite vrijednost svog predviđanja u odnosu na učinak koji ima i pristranosti koje bi se mogle uvesti na etičan način. Saznajte više o tome kako Microsoft [obrađuje odgovornu umjetnu inteligenciju](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Također možete saznati o [tehnikama i postupcima za odgovorno strojno učenje](/azure/machine-learning/concept-responsible-ml) specifičnim za Strojno učenje Azure.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
