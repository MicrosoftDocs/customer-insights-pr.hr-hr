---
title: Izvoz segmenata u LiveRamp (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 3e30a16dcb276fa6c951ad0b42ed0a4792f87ce3
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050754"
---
# <a name="export-segments-to-liverampreg-preview"></a>Izvoz segmenata u LiveRamp&reg; (pretpregled)

Aktivirajte svoje podatke u LiveRamp da biste se povezali s više od 500 platformi putem digitalnih i društvenih mreža te televizora. Radite sa svojim podacima na usluzi LiveRamp kako biste ciljali, suzbili i personalizirali oglasne kampanje.

## <a name="prerequisites-for-a-connection"></a>Preduvjeti za vezu

- Za upotrebu ovog poveznika potrebna vam je pretplata na LiveRamp.
- Da biste se pretplatili, izravno [kontaktirajte LiveRamp](https://liveramp.com/contact/). [Saznajte više o usluzi LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Postavljanje veze s LiveRamp

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite **LiveRamp** za konfiguriranje veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Ako ništa ne poduzmete, prema zadanim će postavkama biti Administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **Korisničko ime** i **Lozinku** za račun LiveRamp Secure FTP (SFTP).
Ove vjerodajnice mogu biti različite od vaših vjerodajnica za LiveRamp Onboarding.

1. Odaberite **Provjeri** da biste testirali vezu s uslugom LiveRamp.

1. Nakon uspješne provjere dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom potvrdnog okvira **Slažem se**.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

Ovaj izvoz možete konfigurirati ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste stvorili novi izvoz, odaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka LiveRamp. Ako ne vidite naziv ovog odjeljka, nema dostupnih veza ove vrste.

1. U polju **Odabir identifikatora ključa** odaberite **E-pošta**, **Ime i adresa** ili **Telefon** da biste ih poslali usluzi LiveRamp radi potvrde identiteta.
   > [!div class="mx-imgBorder"]
   > ![Poveznik LiveRamp s mapiranjem atributa.](media/export-liveramp-segments.png "Poveznik za LiveRamp s mapiranjem atributa")

1. Preslikajte odgovarajuće atribute iz entiteta *Klijent* za odabrani identifikator ključa.

1. Odaberite **Dodaj atribut** za mapiranje više atributa za slanje u LiveRamp.

   > [!TIP]
   > Ako pošaljete više atributa identifikatora ključa usluzi LiveRamp, vjerojatno ćete dobiti višu stopu podudaranja.

1. Odaberite segmente koje želite eksportirati u LiveRamp.

1. Odaberite **Spremi**.

Spremanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvježavanjem](system.md#schedule-tab). Također možete [izvesti podatke na zahtjev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights za prijenos podataka u Liveramp, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prema vašoj uputi prenijeti takve podatke, ali vi ste odgovorni za to da Liveramp ispunjava sve obaveze privatnosti ili sigurnosti koje imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo odredište izvoza ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.

[!INCLUDE [footer-include](includes/footer-banner.md)]
