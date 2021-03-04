---
title: Prilagođeni modeli za strojno učenje | Microsoft Docs
description: Radite s prilagođenim modelima iz Strojnog učenja Azure u aplikaciji Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267225"
---
# <a name="custom-machine-learning-models"></a>Prilagođeni modeli za strojno učenje

**Inteligencija** > **Prilagođeni modeli** omogućava upravljanje tijekovima rada na temelju modela strojnog učenja Azure. Tijekovi rada pomažu vam u odabiru podataka iz kojih želite generirati uvide i mapiranju rezultata u vaše objedinjene podatke o klijentima. Dodatne informacije o izradi prilagođenih modela strojnog učenja potražite u odjeljku [Upotreba modela na temelju Strojnog učenja Azure](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Odgovorna umjetna inteligencija

Predviđanja nude mogućnosti stvaranja boljih korisničkih iskustava, poboljšanja poslovnih mogućnosti i izvora prihoda. Preporučujemo vam da uravnotežite vrijednost svog predviđanja u odnosu na učinak koji ima i pristranosti koje bi se mogle uvesti na etičan način. Saznajte više o tome kako Microsoft [obrađuje odgovornu umjetnu inteligenciju](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Također možete saznati o [tehnikama i postupcima za odgovorno strojno učenje](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specifičnim za Strojno učenje Azure.

## <a name="prerequisites"></a>Preduvjeti

- Trenutno ova značajka podržava web-servise objavljene putem [Studija strojnog učenja (klasično)](https://studio.azureml.net) i [skupnih kanala Strojnog učenja Azure](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Za upotrebu ove značajke potreban vam je račun za pohranu Azure Data Lake Gen2 povezan s instancom Azure Studio. Dodatne informacije potražite u odjeljku [Stvaranje računa za pohranu Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Dodavanje novog tijeka rada

1. Idite u odjeljak **Inteligencija** > **Prilagođeni modeli** i odaberite **Novi tijek rada**.

1. Dodijelite prilagođenom modelu neki prepoznatljiv naziv u polju **Naziv**.

   > [!div class="mx-imgBorder"]
   > ![Snimak zaslona okna Novi tijek rada](media/new-workflowv2.png "Snimak zaslona okna Novi tijek rada")

1. Odaberite tvrtku ili ustanovu koja sadrži web-servis u **Klijent koji sadrži vaš web-servis**.

1. Ako je pretplata na Strojno učenje Azure u nekom drugom klijentu, a ne u sustavu Customer Insights, odaberite **Prijava** s vjerodajnicama za odabranu tvrtku ili ustanovu.

1. Odaberite **Radne prostore** povezane s vašim web-servisom. Navedena su dva odjeljka, jedan za Strojno učenje Azure v1 (Studio strojnog učenja (klasični)) i Strojno učenje Azure v2 (Strojno učenje Azure). Ako niste sigurni koji radni prostor odgovara vašem web-servisu Studio strojnog učenja (klasični), odaberite **Bilo koji**.

1. Odaberite web-servis Studio strojnog učenja (klasični) ili kanal Strojno učenje Azure na padajućem popisu **Web-servis koji sadrži vaš model**. Zatim odaberite **Dalje**.
   - Saznajte više o [objavljivanju web-servisa u Studiju strojnog učenja (klasični)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Saznajte više o [objavljivanju kanala u Strojnom učenju Azure pomoću dizajnera](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ili [SDK-a](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Vaš kanal mora biti objavljen pod [krajnjom točkom kanala](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

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
   Morate odabrati atribut iz zaključnih rezultata s vrijednostima sličnim stupcu ID klijenta entiteta Klijent. Ako nemate takav stupac u svom skupu podataka, odaberite atribut koji jedinstveno identificira redak.

## <a name="run-a-workflow"></a>Pokretanje tijeka rada

1. Na stranici **Prilagođeni modeli** odaberite okomite tri točke u stupcu **Radnje** pokraj toka rada koji ste prethodno stvorili.

1. Odaberite **Pokretanje**.

Vaš tijek rada se također pokreće automatski sa svakim zakazanim osvježavanjem. Saznajte više o [postavljanju zakazanog osvježavanja](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Brisanje tijeka rada

1. Na stranici **Prilagođeni modeli** odaberite okomite tri točke u stupcu **Radnje** pokraj toka rada koji ste prethodno stvorili.

1. Odaberite **Izbriši** i potvrdite brisanje.

Vaš će se tijek rada izbrisati. [Entitet](entities.md) koji je stvoren kada ste stvorili tijek rada ostaje i može se pregledati na stranici **Entiteti**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]