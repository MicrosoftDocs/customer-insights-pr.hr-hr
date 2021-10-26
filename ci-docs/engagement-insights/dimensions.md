---
title: Prikaz i stvaranje dimenzija
description: Kako stvarati, uređivati i brisati dimenzije.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 136da1e1265c7087d861712d34d011b09cb60ad5
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623623"
---
# <a name="view-and-create-dimensions"></a>Prikaz i stvaranje dimenzija

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dimenzija je atribut događaja koji može opisati, filtrirati ili grupirati podatke. Ako na svom web-mjestu provodite marketinšku promociju, dimenzije možete koristiti za sortiranje posjetitelja prema novim i povratnim korisnicima.  

Uvidi o angažmanu uključuju gotove dimenzije (OOB) za svojstva događaja. Primjeri:

- Naziv preglednika
- Naziv stranice
- Model uređaja
- Operacijski sustav
- Zemlja

## <a name="view-dimensions"></a>Prikaz dimenzija

Dimenzije se temelje na postojećim svojstvima događaja. Kada kôd za praćenje koristite za uvide u angažman, dimenzije sustava se izrađuju automatski.

1. Idite u odjeljak **Podaci** u lijevom navigacijskom oknu. 
1. Odaberite **Dimenzije** za prikaz popisa svih dimenzija u radnom prostoru. 
   > [!NOTE]
   > Dimenzije generirane sustavom samo su za čitanje. Ne možete ih urediti. Možete stvarati i uređivati samo prilagođene dimenzije.

## <a name="create-a-dimension"></a>Stvorite dimenziju

Uz dimenzije generirane sustavom, administratori okruženja i radnog prostora mogu stvoriti prilagođene dimenzije. Prilagođene dimenzije temelje se na zadanim svojstvima osnovnih događaja ili mogu koristiti [prilagođena svojstva događaja](advanced-SDK-implementation.md).

1. Idite u odjeljak **Podaci** > **Dimenzije**.
1. Odaberite **Nova dimenzija**.

   :::image type="content" source="media/add-dimension.png" alt-text="Dodajte dimenziju događaju.":::

1. U oknu **Stvori dimenziju** odaberite svojstvo na kojem će se dimenzija temeljiti. Popis svojstava prikazat će sva svojstva u radnom prostoru koja nisu dodijeljena dimenziji.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="Stvorite novu dimenziju.":::
      
3. Unesite naziv u okvir **Zaslonski naziv**. Ako želite, možete dodati **Opis**.
4. Odaberite **Stvori** da biste spremili dimenziju. Može proći i do jedne minute prije nego što možete upotrijebiti dimenziju u [prilagođenom izvješću](custom-reports.md) ili [segmentu](segments.md). 

## <a name="edit-a-dimension"></a>Uređivanje dimenzije

Možete promijeniti naziv i opis dimenzije. Možete uređivati samo dimenzije koje su stvorili korisnici, ali ne možete uređivati dimenzije sustava.


1. Idite u odjeljak **Podaci** > **Dimenzije**.
1. Odaberite dimenziju koju želite obrisati.
1. U oknu **Uredi dimenziju** ažurirajte dimenziju.
1. Odaberite **Primijeni** da biste spremili promjene.

## <a name="delete-a-dimension"></a>Brisanje dimenzije

Možete izbrisati samo dimenzije koje su stvorili korisnici, ali ne možete ukloniti dimenzije sustava.

Brisanje dimenzije je trajno. Izvješća i segmenti koji koriste izbrisanu dimenziju više neće raditi. 

1. Idite u odjeljak **Podaci** > **Dimenzije**.
1. Odaberite dimenziju koju želite obrisati.
1. U oknu **Uredi dimenziju** odaberite **Izbriši dimenziju**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Izbrišite dimenziju za događaj.":::

1. Unesite **POTVRDI BRISANJE** (velikim slovima) za potvrdu brisanja. 
1. Odaberite **Obriši**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
