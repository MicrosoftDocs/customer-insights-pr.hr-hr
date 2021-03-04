---
title: LiveRamp poveznik
description: Saznajte kako izvesti podatke u LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270149"
---
# <a name="liverampreg-connector-preview"></a>Poveznik za LiveRamp&reg; (pretpregled)

Aktivirajte svoje podatke na usluzi LiveRamp da biste se povezali s preko 500 platformi u digitalnim, društvenim i TV ekosustavima. Radite sa svojim podacima na usluzi LiveRamp kako biste ciljali, suzbili i personalizirali oglasne kampanje.

## <a name="prerequisites"></a>Preduvjeti

- Za upotrebu ovog poveznika potrebna vam je pretplata na LiveRamp.
- Da biste se pretplatili, izravno [kontaktirajte LiveRamp](https://liveramp.com/contact/). [Saznajte više o usluzi LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Povezivanje na uslugu LiveRamp

1. U uvidima u ciljnu skupinu idite na **Administrator** > **Odredišta izvoza**.

1. Na pločici **LiveRamp** odaberite **Postavljanje**.

1. Dodijelite odredištu prepoznatljivi naziv u polju **Zaslonski naziv**.

1. Unesite **Korisničko ime** i **Lozinku** za račun LiveRamp Secure FTP (SFTP).
Ove vjerodajnice mogu biti različite od vaših vjerodajnica za LiveRamp Onboarding.

1. Odaberite **Provjeri** da biste testirali vezu s uslugom LiveRamp.

1. Nakon uspješne provjere dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**.

1. Odaberite **Dalje** za postavljanje poveznika za LiveRamp.

## <a name="configure-the-connector"></a>Konfiguracija poveznika

1. U polju **Odabir identifikatora ključa** odaberite **E-pošta**, **Ime i adresa** ili **Telefon** da biste ih poslali usluzi LiveRamp radi potvrde identiteta.

1. Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za odabrani identifikator ključa.

1. Odaberite **Dodavanje atributa** za mapiranje dodatnih atributa koje treba poslati u LiveRamp.

   > [!TIP]
   > Ako pošaljete više atributa identifikatora ključa usluzi LiveRamp, vjerojatno ćete dobiti višu stopu podudaranja.

1. Odaberite segmente koje želite eksportirati u LiveRamp.

1. Odaberite **Spremi**.

> [!div class="mx-imgBorder"]
> ![Poveznik za LiveRamp s mapiranjem atributa](media/export-liveramp-segments.png "Poveznik za LiveRamp s mapiranjem atributa")

## <a name="export-the-data"></a>Izvoz podataka

Izvoz će započeti ubrzo ako su ispunjeni svi preduvjeti za izvoz. Podaci će se izvoziti uz svako [zakazano osvježavanje](system.md#schedule-tab).
Nakon uspješnog izvoza možete se prijaviti u LiveRamp Onboarding da biste aktivirali i distribuirali svoje podatke.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Liveramp, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Liveramp ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.

[!INCLUDE[footer-include](../includes/footer-banner.md)]