---
title: Povežite se s entitetima u upravljanom jezeru servisa Common Data Service
description: Uvoz podataka iz rješenja Data Lake kojim upravlja platforma Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643389"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Povezivanje s podacima iz rješenja Data Lake kojim upravlja platforma Common Data Service.

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

U ovom članku nalaze se informacije o načinu na koji se postojeći korisnici sustava Dynamics 365 mogu brzo povezati sa svojim analitičkim entitetima u jezeru kojim upravlja Common Data Service. Morate biti administrator u tvrtki ili ustanovi platforme Common Data Service kako biste nastavili i vidjeli popis entiteta dostupnih u upravljanom jezeru.

## <a name="important-considerations"></a>Važne stavke

Podaci pohranjeni u internetskom servisu kao što je Azure Data Lake Storage mogu biti pohranjeni na mjestu drugačijem od onoga na kojemu se podaci obrađuju ili pohranjuju u sustavu Dynamics 365 Customer Insights. Uvozom ili povezivanjem s podacima pohranjenima u internetskim servisima slažete se da se podaci mogu prenijeti i pohraniti sa sustavom Dynamics 365 Customer Insights. [Saznajte više u programu Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Povezivanje s jezerom za upravljanje Common Data Service

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Odaberite **Dodaj izvor podataka**.

3. Odaberite **Poveži se s opcijom Common Data Service** i odaberite **Sljedeće**.

4. Unesite **Naziv** za izvor podataka i odaberite **Dalje**.

5. Navedite **Adresu poslužitelja** za svoju tvrtku ili ustanovu Common Data Service i odaberite **Prijava**.

   > [!div class="mx-imgBorder"]
   > ![Dijaloški okvir za unos adrese poslužitelja značajke Common Data Service](media/enter-CDS-org-details.png)

6. Odaberite entitete koje želite unijeti s dostupnog popisa.    

   > [!NOTE]
   > Ako su neki entiteti već odabrani, mogle bi ih koristiti druge aplikacije Dynamics 365 (poput Dynamics 365 Sales Insights ili Customer Service Insights). Taj odabir ne možete promijeniti. Ti će entiteti biti dostupni kada se stvori izvor podataka.

   > [!div class="mx-imgBorder"]
   > ![Dijaloški okvir s popisom entiteta u tvrtki ili ustanovi Common Data Service](media/select-analytical-entities.png)

7. Spremite svoj odabir da biste pokrenuli sinkronizaciju odabranih entiteta s jezerom za upravljanje Common Data Service. Novu dodanu vezu pronaći ćete na stranici **Izvori podataka**. Stavit će se u red za osvježavanje i prikazati broj entiteta kao 0 dok se svi entiteti ne sinkroniziraju.

Samo jedan izvor podataka okruženja može istovremeno koristiti isto upravljano jezero servisa Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Uređivanje izvora podataka jezera za upravljanje Common Data Service

Odabir entiteta uređujete tek nakon što stvorite izvor podataka. Na primjer, ako su platformi Common Data Service dodani dodatni entiteti, a i njih također želite uvesti.    
Da biste povezali drugi Common Data Service, [stvorite novi izvor podataka](#connect-to-a-common-data-service-managed-lake).

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Pored izvora podataka koji želite ažurirati odaberite elipsu.

3. S popisa odaberite mogućnost **Uredi**.

4. Odaberite dodatne entitete s dostupnog popisa entiteta i odaberite **Spremi**.
