---
title: Prilagođeni modeli za strojno učenje | Microsoft Docs
description: Radite s prilagođenim modelima iz Strojnog učenja Azure u aplikaciji Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 87fb517e9f0b380f9721f77470dceb3bcb7e5616
ms.sourcegitcommit: 55c00ea61c78db7b3b54894c01afb3246dff31c8
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/22/2021
ms.locfileid: "5700659"
---
# <a name="custom-machine-learning-models"></a>Prilagođeni modeli za strojno učenje

**Inteligencija** > **Prilagođeni modeli** omogućava upravljanje tijekovima rada na temelju modela strojnog učenja Azure. Tijekovi rada pomažu vam u odabiru podataka iz kojih želite generirati uvide i mapiranju rezultata u vaše objedinjene podatke o klijentima. Dodatne informacije o izradi prilagođenih modela strojnog učenja potražite u odjeljku [Upotreba modela na temelju Strojnog učenja Azure](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Odgovorna umjetna inteligencija

Predviđanja nude mogućnosti stvaranja boljih korisničkih iskustava, poboljšanja poslovnih mogućnosti i izvora prihoda. Preporučujemo vam da uravnotežite vrijednost svog predviđanja u odnosu na učinak koji ima i pristranosti koje bi se mogle uvesti na etičan način. Saznajte više o tome kako Microsoft [obrađuje odgovornu umjetnu inteligenciju](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Također možete saznati o [tehnikama i postupcima za odgovorno strojno učenje](/azure/machine-learning/concept-responsible-ml) specifičnim za Strojno učenje Azure.

## <a name="prerequisites"></a>Preduvjeti

- Trenutno ova značajka podržava web-servise objavljene putem [Studija strojnog učenja (klasično)](https://studio.azureml.net) i [skupnih kanala Strojnog učenja Azure](/azure/machine-learning/concept-ml-pipelines).

- Za upotrebu ove značajke potreban vam je račun za pohranu Azure Data Lake Gen2 povezan s instancom Azure Studio. Dodatne informacije potražite u odjeljku [Stvaranje računa za pohranu Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Za radne prostore Strojnog učenja Azure s kanalima trebaju vam dozvole administratora pristupa vlasnika ili korisnika za Radni prostor Strojnog učenja Azure.

   > [!NOTE]
   > Podaci se prenose između instanci servisa Customer Insights i odabranih web-servisa Azure ili kanala u tijeku rada. Kada prenosite podatke na uslugu Azure, provjerite je li usluga konfigurirana za obradu podataka na način i na lokaciji koja je potrebna da ti podaci ispune sve pravne ili regulatorne zahtjeve vaše tvrtke ili ustanove.

## <a name="add-a-new-workflow"></a>Dodavanje novog tijeka rada

1. Idite u odjeljak **Inteligencija** > **Prilagođeni modeli** i odaberite **Novi tijek rada**.

1. Dodijelite prilagođenom modelu neki prepoznatljiv naziv u polju **Naziv**.

   > [!div class="mx-imgBorder"]
   > ![Snimak zaslona okna Novi tijek rada](media/new-workflowv2.png "Snimak zaslona okna Novi tijek rada")

1. Odaberite tvrtku ili ustanovu koja sadrži web-servis u **Klijent koji sadrži vaš web-servis**.

1. Ako je pretplata na Strojno učenje Azure u nekom drugom klijentu, a ne u sustavu Customer Insights, odaberite **Prijava** s vjerodajnicama za odabranu tvrtku ili ustanovu.

1. Odaberite **Radne prostore** povezane s vašim web-servisom. Navedena su dva odjeljka, jedan za Strojno učenje Azure v1 (Studio strojnog učenja (klasični)) i Strojno učenje Azure v2 (Strojno učenje Azure). Ako niste sigurni koji radni prostor odgovara vašem web-servisu Studio strojnog učenja (klasični), odaberite **Bilo koji**.

1. Odaberite web-servis Studio strojnog učenja (klasični) ili kanal Strojno učenje Azure na padajućem popisu **Web-servis koji sadrži vaš model**. Zatim odaberite **Dalje**.
   - Saznajte više o [objavljivanju web-servisa u Studiju strojnog učenja (klasični)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Saznajte više o [objavljivanju kanala u Strojnom učenju Azure pomoću dizajnera](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ili [SDK-a](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Vaš kanal mora biti objavljen pod [krajnjom točkom kanala](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Za svaki **Ulazni podatak web-servisa** odaberite odgovarajući **Entitet** iz uvida u ciljnu skupinu pa odaberite **Dalje**.
   > [!NOTE]
   > Tijek rada prilagođenog modela primijenit će heuristiku za mapiranje polja za unos web-usluga u atribute entiteta na temelju naziva i vrste podataka polja. Vidjet ćete pogrešku ako se polje web-usluge ne može mapirati na entitet.

   > [!div class="mx-imgBorder"]
   > ![Konfiguracija tijeka rada](media/intelligence-screen2-updated.png "Konfiguracija tijeka rada")

1. U koraku **Izlazni parametri modela**, postavite sljedeća svojstva:
   - Studio strojnog učenja (klasični)
      1. Unesite izlazni **Naziv entiteta** u koji želite da idu izlazni rezultati web-servisa.
   - Strojno učenje Azure
      1. Unesite izlazni **Naziv entiteta** u koji želite da idu izlazni rezultati kanala.
      1. S padajućeg popisa odaberite **Izlazni naziv parametra pohrane podataka** skupnog kanala.
      1. S padajućeg popisa odaberite **Izlazni naziv parametra puta** skupnog kanala.

      > [!div class="mx-imgBorder"]
      > ![Okno izlaznog parametra modela](media/intelligence-screen3-outputparameters.png "Okno izlaznog parametra modela")

1. Odaberite odgovarajući atribut s padajućeg popisa **ID klijenta u rezultatima** koji identificira klijente pa odaberite **Spremanje**.

   > [!div class="mx-imgBorder"]
   > ![Okno usklađivanja rezultata s podacima klijenta](media/intelligence-screen4-relatetocustomer.png "Okno usklađivanja rezultata s podacima klijenta")

1. Vidjet ćete zaslon **Tijek rada spremljen** s pojedinostima o tijeku rada.    
   Ako ste konfigurirali tijek rada za kanal Strojno učenje Azure, uvidi u ciljnu skupinu će se pridružiti radnom prostoru koji sadrži kanal. Uvidi u ciljnu skupinu dobit će ulogu **Suradnik** u radnom prostoru usluge Azure.

1. Odaberite **Gotovo**.

1. Sada možete pokrenuti tijek rada na stranici **Prilagođeni modeli**.

## <a name="edit-a-workflow"></a>Uređivanje tijeka rada

1. Na stranici **Prilagođeni modeli** odaberite okomite tri točke u stupcu **Radnje** pokraj toka rada koji ste prethodno stvorili te odaberite **Uredi**.

1. Prepoznatljivo ime vašeg tijeka rada možete ažurirati u polju **Zaslonski naziv**, ali ne možete promijeniti konfigurirani web-servis ili kanal. Odaberite **Dalje**.

1. Za svaki **Ulazni podatak web-servisa** možete ažurirati odgovarajući **Entitet** iz uvida u ciljnu skupinu. Zatim odaberite **Dalje**.

1. U koraku **Izlazni parametri modela**, postavite sljedeća svojstva:
   - Studio strojnog učenja (klasični)
      1. Unesite izlazni **Naziv entiteta** u koji želite da idu izlazni rezultati web-servisa.
   - Strojno učenje Azure
      1. Unesite izlazni **Naziv entiteta** u koji želite da idu izlazni rezultati kanala.
      1. Odaberite **Izlazni naziv parametra pohrane podataka** za testni kanal.
      1. Odaberite **Izlazni naziv parametra puta** za testni kanal.

1. Odaberite odgovarajući atribut s padajućeg popisa **ID klijenta u rezultatima** koji identificira klijente pa odaberite **Spremanje**.
   Odaberite atribut iz zaključnih rezultata s vrijednostima sličnim stupcu ID klijenta entiteta Klijent. Ako nemate takav stupac u svom skupu podataka, odaberite atribut koji jedinstveno identificira redak.

## <a name="run-a-workflow"></a>Pokretanje tijeka rada

1. Na stranici **Prilagođeni modeli** odaberite okomite tri točke u stupcu **Radnje** pokraj toka rada koji ste prethodno stvorili.

1. Odaberite **Pokretanje**.

Vaš tijek rada se također pokreće automatski sa svakim zakazanim osvježavanjem. Saznajte više o [postavljanju zakazanog osvježavanja](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Brisanje tijeka rada

1. Na stranici **Prilagođeni modeli** odaberite okomite tri točke u stupcu **Radnje** pokraj toka rada koji ste prethodno stvorili.

1. Odaberite **Izbriši** i potvrdite brisanje.

Vaš će se tijek rada izbrisati. [Entitet](entities.md) koji je stvoren kada ste stvorili tijek rada ostaje i može se pregledati na stranici **Entiteti**.

## <a name="results"></a>Rezultati

Rezultati tijeka rada pohranjuju se u entitetu konfiguriranom tijekom faze Izlazni parametar modela. Ovim podacima možete pristupiti sa [stranice entiteta](entities.md) ili pomoću [API pristupa](apis.md).

### <a name="api-access"></a>API pristup

Za određeni upit OData za dobivanje podataka iz entiteta prilagođenog modela koristite sljedeći format:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Zamijenite `<your instance id>` s ID-om vašeg okruženja Customer Insights, koji ćete pronaći u adresnoj traci svog preglednika prilikom pristupa servisu Customer Insights.

1. Zamijenite `<custom model output entity>` s nazivom entiteta koji ste naveli tijekom koraka Izlazni parametri modela konfiguracije prilagođenog modela.

1. Zamijenite `<guid value>` s ID-om klijenta čijem zapisu želite pristupiti. Ovaj ID obično možete pronaći na [stranici s profilima klijenata](customer-profiles.md) u polju ID klijenta.

## <a name="frequently-asked-questions"></a>Najčešća pitanja

- Zašto ne mogu vidjeti svoj kanal prilikom postavljanja tijeka rada prilagođenog modela?    
  Uzrok ovog problema je često u konfiguraciji u kanalu. Osigurajte da je [konfiguriran ulazni parametar](azure-machine-learning-experiments.md#dataset-configuration) i da su konfigurirani [izlazni parametri spremišta podataka i putanje](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).

- Što znači pogreška "Nije bilo moguće spremiti tijek rada inteligencije"?    
  Korisnici obično vide ovu poruku o pogrešci ako u radnom prostoru nemaju privilegije administratora pristupa vlasnika ili korisnika. Korisnik treba višu razinu dozvola kako bi omogućio servisu Customer Insights da obradi tijek rada kao uslugu umjesto korištenja korisničkih vjerodajnica za sljedeća izvođenja tijeka rada.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
