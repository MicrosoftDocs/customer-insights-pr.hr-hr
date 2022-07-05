---
title: Dopunite djelomične podatke predviđanjima
description: Koristite predviđanja za popunjavanje nepotpunih podataka o kupcima.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-predictions
- ci-custom-models
- customerInsights
ms.openlocfilehash: 7e93670007db27d13b84d7516f56830988da083e
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082508"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Ispunite svoje djelomične podatke s predviđanjima (zastarjelim)

> [!IMPORTANT]
> Ova će značajka biti **zastarjela** od **5. studenog 2021**. Trenutne implementacije nastavit će raditi dok se značajka ne ukloni, ali nećete moći stvoriti nove integracije pomoću uputa u nastavku.

Predviđanja omogućuju lako stvaranje predviđenih vrijednosti koje mogu poboljšati razumijevanje klijenta. Na stranici **Inteligencija** > **Predviđanja** možete odabrati **Moja predviđanja** da biste vidjeli predviđanja koja ste konfigurirali u ostalim dijelovima aplikacije Customer Insights i omogućili njihovo daljnje prilagođavanje.

> [!NOTE]
> Ne možete upotrebljavati tu značajku ako vaše okruženje koristi pohranu Azure Data Lake Gen 2 Storage.
>
> Značajka predviđanja upotrebljava automatizirana sredstva za procjenu podataka i predviđanja na temelju tih podataka, pa se stoga može upotrijebiti kao metoda profiliranja jer je taj pojam definiran Općom uredbom o zaštiti podataka (GDPR odn. OUZP). Klijentova upotreba ove značajke za obradu podataka može biti podložna OUZP-u ili drugim zakonima ili propisima. Odgovorni ste osigurati da je da vaše korištenje Dynamics 365 Customer Insights, uključujući predviđanja, u skladu sa svim primjenjivim zakonima i uredbama, uključujući zakone koji se odnose na privatnost, osobne podatke, biometrijske podatke, zaštitu podataka i povjerljivost komunikacija.

## <a name="prerequisites"></a>Preduvjeti

Da bi vaša tvrtka ili ustanova mogla upotrebljavati značajku predviđanja, mora ispuniti sljedeće preduvjete:

1. Vaša tvrtka ili ustanova ima instancu [postavljenu u Microsoft Dataverse](/ai-builder/build-model#prerequisites) i u istoj je tvrtki ili ustanovi kao i Customer Insights.

2. Okruženje aplikacije Customer Insights priloženo je usluzi Dataverse.

Dodatne informacije potražite u odjeljku [Stvaranje novog okruženja](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Stvaranje predviđanja u entitetu klijenta

1. Otvorite **Podatkovni** > **entiteti**.

2. Odaberite entitet **Klijent**.

3. U entitetu **Klijent: CustomerInsights** odaberite karticu **Polja**.

4. Pronađite naziv atributa za koje želite predvidjeti vrijednosti, a zatim odaberite ikonu **Pregled** u stupcu **Sažetak**.
   > [!div class="mx-imgBorder"]
   > ![Ikona pregleda.](media/intelligence-overviewicon.png "Ikona pregleda")

5. Ako za atribut postoji visoka stopa vrijednosti koje nedostaju, odaberite **Predviđanje vrijednosti koje nedostaju** da biste nastavili s predviđanjima.
   > [!div class="mx-imgBorder"]
   > ![Status pregleda s prikazanim gumbom za predviđanje vrijednosti koje nedostaju.](media/intelligence-overviewpredictmissingvalues.png "Status pregleda s prikazanim gumbom za predviđanje vrijednosti koje nedostaju")

6. Unesite **Zaslonski naziv** i **Naziv izlaznog entiteta** za rezultate predviđanja.

7. Unaprijed popunjen popis opcija prikazat će mjesto gdje možete preslikati vrijednosti u predviđenu kategoriju. U tom slučaju, jedine mogućnosti kategorije bit će 0 ili 1 jer se preslikavaju na točnu/netočnu ili binarnu prirodu predviđanja. U stupcu Kategorija preslikajte vrijednosti polja koje želite klasificirati kao „0” u konačnom predviđanju na „0”, a stavke koje želite klasificirati kao „1” u konačnom predviđanju na „1”.
   > [!div class="mx-imgBorder"]
   > ![Primjer koji pokazuje mapirane vrijednosti polja u kategorije.](media/intelligence-categorymapping.png "Primjer koji prikazuje preslikane vrijednosti polja u kategorije")

8. Odaberite **Gotovo** i predviđanje će se obraditi. Obrada traje neko vrijeme, ovisno o veličini i složenosti podataka. Rezultati će biti dostupni u novom entitetu temeljenom na **Nazivu izlaznog entiteta** predviđanja koje ste stvorili.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Stvaranje predviđanja tijekom stvaranja segmenta

Predviđanje vrijednosti koje nedostaju za određeni atribut moguće je i prilikom stvaranja segmenta. Preciznije, kada brzo stvorite segment na temelju objedinjenog entiteta klijenta ili entiteta Customer_Measure.

Kao dio tog tijeka, odabirete određeni atribut na kojem ćete temeljiti svoj segment, kao što su zadovoljstvo klijenta ili iznos kupnje. Nakon stvaranja segmenta sustav će predložiti metodu za predviđanje vrijednosti koje nedostaju za ovaj atribut.

1. Otvorite **Segmenti** i odaberite pločicu **Profili**.

2. Odaberite **Polje** da biste stvorili segment i odaberite **Operator**, a zatim odaberite **Pregled**.

3. Unesite **Naziv** i **Zaslonski naziv** za segment.

4. Odaberite **Spremi**.

5. Ako segment koji ste upravo stvorili ima nepotpune podatke u polju izvora, možete odlučiti predvidjeti vrijednosti koje nedostaju.
   > [!div class="mx-imgBorder"]
   > ![Gumb predviđanja.](media/segments-predictoption.png "Gumb predviđanja")

6. Unesite **Zaslonski naziv** i **Naziv izlaznog entiteta** za rezultate predviđanja.

7. Odaberite **Gotovo**. Predviđanja će se uskoro generirati u novom entitetu s nazivom koji ste naveli za **Naziv izlaznog entiteta**.

## <a name="view-a-prediction"></a>Prikaz predviđanja

1. Idi na **Obavještajna** > **predviđanja** > **Moja predviđanja**.

2. Odaberite predviđanje koje želite pregledati.

3. Odaberite okomitu trotočje (&vellip;) u stupcu **Akcije** i odaberite **Prikaz**.

4. U prikazu predviđanja vidjet ćete brojne podatkovne točke.
   > [!div class="mx-imgBorder"]
   > ![Stranica predviđanja.](media/intelligence-predictionsviewpage.png "Stranica predviđanja")

   - **Predviđene vrijednosti** prikazuje preslikavanje koje ste stvorili tijekom faze vrijednosti polja u fazi preslikavanja kategorije. To su vrijednosti u vašem skupu podataka koje su preslikane u određenu kategoriju.
   -**Glavni utjecaji** su faktori unutar skupa podataka koji bi najvjerojatnije mogli utjecati na povjerenje predviđanja vrijednosti polja koje se preslikava u određenu kategoriju.
   - **Performanse** označava kako rade predviđanja. Odaberite vezu da biste saznali više.
   - **Pregled** prikazuje uzorke izlaznog skupa podataka iz vašeg predviđanja i vjerojatnost ili naše pouzdanje za predviđene vrijednosti, gdje je 0 neizvjestan, a 1 je sigurno.

## <a name="update-a-prediction"></a>Ažuriranje predviđanja

1. Idi na **Obavještajna** > **predviđanja** > **Moja predviđanja**.

2. Odaberite predviđanje koje želite ažurirati i odaberite ikonu **Ažuriraj**.

3. Predviđanje će biti zakazano za obradu. Vrijeme posljednjeg ažuriranja možete vidjeti u stupcu **Ažurirano** na stranici **Predviđanja**.

## <a name="edit-a-prediction"></a>Uređivanje predviđanja

Nakon što izradite predviđanje, možete prilagoditi model u odjeljku AI Builder kako biste povećali učinkovitost svog modela.  

1. Idi na **Obavještajna** > **predviđanja** > **Moja predviđanja**.

2. Odaberite predviđanje koje želite urediti.

3. Odaberite okomitu trotočje (&vellip;) u stupcu **Akcije** i odaberite **Prikaz**.

4. U programu izaberite stavku **AI Builder** Prilagodi.

5. Ažurirajte svoj model u .AI Builder [Saznajte više o upravljanju modelima u alatu AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models),

Sljedeće pokretanje predviđanja upotrebljavat će ažurirani model koji ste stvorili.

> [!NOTE]
> Novi modeli stvoreni u sustavu AI Builder neće se prikazivati u Customer Insights osim ako model nije stvoren iz gore navedenih iskustava.

## <a name="remove-a-prediction"></a>Uklanjanje predviđanja

1. Idi na **Obavještajna** > **predviđanja** > **Moja predviđanja**.

2. Odaberite predviđanje koje želite izbrisati.

3. Odaberite okomitu trotočje (&vellip;) u stupcu **Akcije** i odaberite **Izbriši**.

4. Potvrdite brisanje.

## <a name="troubleshooting"></a>Rješavanje problema

Ako ne možete dovršiti proces prilaganja usluge Dataverse zbog pogreške, možete pokušati ručno dovršiti proces. Postoje dva poznata problema koji se mogu pojaviti u procesu prilaganja:

- Rješenje dodatka za korisničku karticu nije instalirano.
    1. Dopunite upute za [instaliranje i konfiguriranje rješenja](customer-card-add-in.md).

- Dopuštenja za aplikacije nisu dodijeljena.
    1. Idite na [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Odaberite **Okruženja**.
    1. Odaberite okomitu trotočje (&vellip;) pokraj okruženja u koje želite dodati dozvolu i odaberite **Postavke**.
    1. Proširite **Korisnici + dozvole** i odaberite **Korisnici**.
    1. Odaberite **+ Novo** i odaberite **Korisnik**.
    1. Odaberite **Korisnik aplikacije** ako već nije odabran i unesite sljedeće informacije:
        - **Korisničko ime:** cihelp@microsoft.com
        - **ID aplikacije:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Ime:** Customer
        - **Prezime:** Insights
        - **Primarna e-pošta:** cihelp@microsoft.com
    1. Odaberite **Spremi i zatvori**.
    1. Odaberite korisnika kojeg ste stvorili.
    1. Odaberite **Upravljanje ulogama** na traci izbornika na vrhu.
    1. Odaberite **Administrator sustava**, zatim odaberite **U redu**.


[!INCLUDE [footer-include](includes/footer-banner.md)]
