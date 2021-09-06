---
title: Dodatak kartice klijenta za aplikacije Dynamics 365
description: Pomoću ovog dodatka prikažite podatke iz uvida u ciljne skupine u aplikacijama Dynamics 365.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0f6c922104df229980b308136a4d764938121b35d6d744f41b1530bdb5515e7f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032979"
---
# <a name="customer-card-add-in-preview"></a>Dodatak kartice klijenta (pretpregled)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dobijte prikaz svojih klijenata od 360 stupnjeva izravno u Dynamics 365 aplikacijama. Pomoću dodatka kartice klijenta instaliranog u podržanoj aplikaciji Dynamics 365 možete odabrati prikaz demografskih podataka, uvida i vremenskih traka aktivnosti. Dodatak će dohvatiti podatke iz usluge Customer Insights bez utjecaja na podatke u povezanoj aplikaciji Dynamics 365. 

## <a name="prerequisites"></a>Preduvjeti

- Dodatak funkcionira samo s aplikacijama Dynamics 365 stvorenim prema modelu, kao što su Sales ili Customer Service verzije 9.0 i novije.
- Da bi se vaši podaci sustava Dynamics 365 preslikali u profile klijenata uvida u ciljne skupine, moraju se [unijeti iz aplikacije Dynamics 365 pomoću poveznika Microsoft Dataverse](connect-power-query.md).
- Svi korisnici sustava Dynamics 365 za dodatak kartice klijenta moraju se [dodati kao korisnici](permissions.md) u uvidima u ciljne skupine da bi vidjeli podatke.
- [Konfigurirane mogućnosti pretraživanja i filtriranja](search-filter-index.md) u uvidima u ciljne skupine su potrebne za funkcioniranje pretraživanja podataka.
- Svaka kontrola dodatka oslanja se na određene podatke u uvidima u ciljne skupine:
  - Kontrola mjerenja: Zahtijeva [konfigurirana mjerenja](measures.md).
  - Kontrola inteligencije: zahtijeva podatke stvorene pomoću [predviđanja](predictions.md) ili [prilagođenih modela](custom-models.md).
  - Kontrola demografije: demografska polja (kao što su dob ili spola) dostupna su u objedinjenom profilu klijenta.
  - Kontrola obogaćivanja: Zahtijeva aktivna [obogaćivanja](enrichment-hub.md) primijenjena na profile klijenata.
  - Kontrola vremenske trake: Zahtijeva [konfigurirane aktivnosti](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instaliranje dodatka za korisničku karticu

Dodatak za korisničku karticu rješenje je za aplikacije Customer Engagement u programu Dynamics 365. Da biste instalirali rješenje, idite na AppSource i potražite **Kartica klijenta Dynamics**. Odaberite [Dodatak kartice klijenta na AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i odaberite **Nabavi odmah**.

Možda ćete se trebati prijaviti s vjerodajnicama svog administratora za aplikaciju Dynamics 365 da biste postavili rješenje.

Možda će biti potrebno neko vrijeme da se rješenje instalira u vaše okruženje.

## <a name="configure-the-customer-card-add-in"></a>Konfiguriranje dodatka kartice klijenta

1. Kao administrator, idite na dio **Postavke** u aplikaciji Dynamics 365 i odaberite **Rješenja**.

1. Odaberite vezu **Naziv zaslona** za rješenje **Dynamics 365 Customer Insights dodatak kartice klijenta (pretpregled)**.

   > [!div class="mx-imgBorder"]
   > ![Odaberite zaslonski naziv.](media/select-display-name.png "Odabir zaslonskog naziva")

1. Odaberite **Prijavi se** i unesite vjerodajnice za administratorski račun koji koristite za konfiguriranje aplikacije Customer Insights.

   > [!NOTE]
   > Provjerite blokira li blokator skočnih prozora preglednika prozor za provjeru autentičnosti kada odaberete gumb **Prijavi se**.

1. Odaberite okruženje usluge Customer Insights iz kojeg želite dohvatiti podatke.

1. Definirajte preslikavanje polja u zapise u aplikaciji Dynamics 365. Ovisno o vašim podacima u usluzi Customer Insights, možete odabrati preslikavanje sljedećih mogućnosti:
   - Za mapiranje s kontaktom odaberite polje u entitetu Kupac koje se podudara s ID-om entiteta vašeg kontakta.
   - Za mapiranje računom odaberite polje u entitetu Kupac koje se podudara s ID-om entiteta vašeg računa.

   > [!div class="mx-imgBorder"]
   > ![Polje za ID kontakta.](media/contact-id-field.png "Polje za ID kontakta")

1. Odaberite **Spremi konfiguraciju** da biste spremili postavke.

1. Zatim trebate dodijeliti sigurnosne uloge u sustavu Dynamics 365 da bi korisnici mogli prilagoditi i vidjeti karticu klijenta. U sustavu Dynamics 365 idite na **Postavke** > **Sigurnost** > **Korisnici**. Odaberite korisnike da biste uredili uloge korisnika i odaberite **Upravljaj ulogama**.

1. Dodijelite ulogu **osobe za prilagodbu kartice Customer Insights** korisnicima koji će cijeloj organizaciji prilagoditi sadržaj prikazan na kartici.

## <a name="add-customer-card-controls-to-forms"></a>Dodavanje kontrola kartice klijenta u obrasce
  
1. Da biste dodali kontrole kartice klijenta u obrazac za kontakt, idite na **Postavke** > **Prilagodbe** u sustavu Dynamics 365.

1. Odaberite **Prilagođavanje sustava**.

1. Idite na entitet **Kontakt**, proširite ga i odaberite **Obrasci**.

1. Odaberite obrazac za kontakt kojemu želite dodati kontrole kartice klijenta.

    > [!div class="mx-imgBorder"]
    > ![Odaberite obrazac Kontakt.](media/contact-active-forms.png "Odabir obrasca za kontakt")

1. Da biste dodali kontrolu, u uređivaču obrazaca povucite bilo koje polje iz **Preglednika polja** tamo gdje želite da se kontrola pojavi.

1. Odaberite polje na obrascu koje ste upravo dodali i odaberite **Promjena svojstava**.

1. Otvorite karticu **Kontrole** i odaberite **Dodaj kontrolu**. Odaberite jednu od dostupnih prilagođenih kontrola i odaberite **Dodaj**.

1. U dijalogu **Svojstva polja** poništite potvrdni okvir **Prikazani natpis na obrascu**.

1. Odaberite mogućnost **Web** za kontrolu. Za kontrolu obogaćivanja, konfiguriranjem polja **enrichmentType** odaberite vrstu obogaćivanja koju želite prikazati. Dodajte zasebnu kontrolu obogaćivanja za svaku vrstu obogaćivanja.

1. Odaberite **Spremi** i **Objavi** da biste objavili ažurirani obrazac za kontakt.

1. Idite na objavljeni obrazac za kontakt. Vidjet ćete novododanu kontrolu. Možda ćete se morati prijaviti prilikom prvog korištenja.

1. Da biste prilagodili ono što želite prikazati na prilagođenoj kontroli, odaberite gumb za uređivanje u gornjem desnom kutu.

## <a name="upgrade-customer-card-add-in"></a>Nadogradnja dodatka za karticu kupca
Dodatak za karticu kupca ne nadograđuje se automatski. Da biste nadogradili na najnoviju verziju, slijedite ovaj postupak u aplikaciji Dynamics 365 u kojoj je instaliran dodatak.

1. U aplikaciji Dynamics 365 idite na **Postavke** > **Prilagođavanje** i odaberite **Rješenja**.

1. U tablici dodataka potražite **CustomerInsightsCustomerCard** i odaberite redak.

1. Odaberite **Primijeni nadogradnju rješenja** na akcijskoj traci.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Nadogradite rješenje u području Prilagođavanje aplikacija sustava Dynamics 365.":::

1. Nakon pokretanja postupka nadogradnje vidjet ćete indikator učitavanja sve dok nadogradnja ne završi. Ako nema novije verzije, nadogradnja će prikazati poruku o pogrešci.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
