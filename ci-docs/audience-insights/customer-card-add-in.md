---
title: Dodatak kartice kupca za aplikacije sustava Dynamics 365 (videozapis)
description: Pomoću ovog dodatka prikažite podatke iz uvida u ciljne skupine u aplikacijama Dynamics 365.
ms.date: 12/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: f3d613d7183fd0af2998cd081d08d4316c7a5628
ms.sourcegitcommit: ae3b92926ea1adfcc50e4bfd000b06ea0ccfc0ee
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/15/2021
ms.locfileid: "7921856"
---
# <a name="customer-card-add-in-preview"></a>Dodatak kartice klijenta (pretpregled)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dobijte prikaz svojih klijenata od 360 stupnjeva izravno u Dynamics 365 aplikacijama. S dodatkom kartice klijenta instaliranim u podržanoj aplikaciji Dynamics 365, možete odabrati prikaz polja profila klijenta, uvida i vremenske trake aktivnosti. Dodatak će dohvatiti podatke iz usluge Customer Insights bez utjecaja na podatke u povezanoj aplikaciji Dynamics 365.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Preduvjeti

- Dodatak funkcionira samo s aplikacijama Dynamics 365 stvorenim prema modelu, kao što su Sales ili Customer Service verzije 9.0 i novije.
- Da bi se vaši podaci sustava Dynamics 365 preslikali u profile klijenata uvida u ciljne skupine, moraju se [unijeti iz aplikacije Dynamics 365 s pomoću poveznika Microsoft Dataverse](connect-power-query.md).
- Svi korisnici sustava Dynamics 365 za dodatak kartice klijenta moraju se [dodati kao korisnici](permissions.md) u uvidima u ciljne skupine da bi vidjeli podatke.
- [Konfigurirane mogućnosti pretraživanja i filtriranja](search-filter-index.md) u uvidima u ciljne skupine su potrebne za funkcioniranje pretraživanja podataka.
- Svaka kontrola dodatka oslanja se na određene podatke u uvidima u ciljne skupine. Neki podaci i kontrole dostupni su samo u okruženjima određenih vrsta. Konfiguracija dodatka obavijestit će vas ako kontrola nije dostupna zbog odabrane vrste okruženja. Saznajte više o [slučajevima upotrebe okruženja](work-with-business-accounts.md).
  - **Kontrola mjera**: Zahtijeva [konfigurirane mjere](measures.md) atributa vrste klijenta.
  - **Kontrola inteligencije** : zahtijeva podatke generirane [pomoću predviđanja ili prilagođenih modela](predictions-overview.md).
  - **Kontrola pojedinosti o klijentu**: Sva polja iz profila dostupna su u objedinjenom profilu klijenta.
  - **Kontrola obogaćivanja**: Zahtijeva aktivna [obogaćivanja](enrichment-hub.md) primijenjena na profile klijenata. Dodatak za kartice podržava ova obogaćivanja: [robne marke](enrichment-microsoft.md) koje pruža Microsoft, [interesi](enrichment-microsoft.md) koje pruža Microsoft i podaci o [angažmanu sustava Office koje pruža](enrichment-office.md) Microsoft.
  - **Kontrola kontakata**: Zahtijeva definiciju semantičkog entiteta vrste kontakata.
  - **Kontrola vremenske trake**: Zahtijeva [konfigurirane aktivnosti](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instaliranje dodatka za korisničku karticu

Dodatak za korisničku karticu rješenje je za aplikacije Customer Engagement u programu Dynamics 365. Da biste instalirali rješenje, idite na AppSource i potražite **Kartica klijenta Dynamics**. Odaberite [Dodatak kartice klijenta na AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i odaberite **Nabavi odmah**.

Možda ćete se trebati prijaviti s vjerodajnicama svog administratora za aplikaciju Dynamics 365 da biste postavili rješenje. Možda će biti potrebno neko vrijeme da se rješenje instalira u vaše okruženje.

## <a name="configure-the-customer-card-add-in"></a>Konfiguriranje dodatka kartice klijenta

1. Kao administrator, idite na dio **Postavke** u aplikaciji Dynamics 365 i odaberite **Rješenja**.

1. Odaberite vezu **Naziv zaslona** za rješenje **Dynamics 365 Customer Insights dodatak kartice klijenta (pretpregled)**.

   > [!div class="mx-imgBorder"]
   > ![Odaberite zaslonski naziv.](media/select-display-name.png "Odaberite zaslonski naziv.")

1. Odaberite **Prijavi se** i unesite vjerodajnice za administratorski račun koji koristite za konfiguriranje aplikacije Customer Insights.

   > [!NOTE]
   > Provjerite blokira li blokator skočnih prozora preglednika prozor za provjeru autentičnosti kada odaberete gumb **Prijavi se**.

1. Odaberite okruženje usluge Customer Insights iz kojeg želite dohvatiti podatke.

1. Definirajte preslikavanje polja u zapise u aplikaciji Dynamics 365. Ovisno o vašim podacima u usluzi Customer Insights, možete odabrati preslikavanje sljedećih mogućnosti:
   - Za mapiranje s kontaktom odaberite polje u entitetu Kupac koje se podudara s ID-om entiteta vašeg kontakta.
   - Za mapiranje računom odaberite polje u entitetu Kupac koje se podudara s ID-om entiteta vašeg računa.

   > [!div class="mx-imgBorder"]
   > ![Polje za ID kontakta.](media/contact-id-field.png "Polje za ID kontakta.")

1. Odaberite **Spremi konfiguraciju** da biste spremili postavke.

1. Zatim trebate dodijeliti sigurnosne uloge u sustavu Dynamics 365 da bi korisnici mogli prilagoditi i vidjeti karticu klijenta. U sustavu Dynamics 365 idite na **Postavke** > **Sigurnost** > **Korisnici**. Odaberite korisnike da biste uredili uloge korisnika i odaberite **Upravljaj ulogama**.

1. Dodijelite ulogu **osobe za prilagodbu kartice Customer Insights** korisnicima koji će cijeloj organizaciji prilagoditi sadržaj prikazan na kartici.

## <a name="add-customer-card-controls-to-forms"></a>Dodavanje kontrola kartice klijenta u obrasce

Ovisno o vašem scenariju, možete odabrati dodavanje kontrola bilo u obrazac **Kontakt** ili **Račun**. Ako je vaše okruženje uvida u ciljne skupine za poslovne račune, preporučujemo da dodate kontrole u obrazac Račun. U tom slučaju, u sljedećim koracima zamijenite „kontakt” s „račun”.

1. Da biste dodali kontrole kartice klijenta u obrazac za kontakt, idite na **Postavke** > **Prilagodbe** u sustavu Dynamics 365.

1. Odaberite **Prilagođavanje sustava**.

1. Idite na entitet **Kontakt**, proširite ga i odaberite **Obrasci**.

1. Odaberite obrazac za kontakt kojem želite dodati kontrole kartice klijenta.

    > [!div class="mx-imgBorder"]
    > ![Odaberite obrazac Kontakt.](media/contact-active-forms.png "Odaberite obrazac za kontakt.")

1. Da biste dodali kontrolu, u uređivaču obrazaca povucite bilo koje polje iz **Preglednika polja** tamo gdje želite da se kontrola pojavi.

1. Odaberite polje na obrascu koje ste upravo dodali i odaberite **Promjena svojstava**.

1. Otvorite karticu **Kontrole** i odaberite **Dodaj kontrolu**. Odaberite jednu od dostupnih prilagođenih kontrola i odaberite **Dodaj**.

1. U dijalogu **Svojstva polja** poništite potvrdni okvir **Prikazani natpis na obrascu**.

1. Odaberite mogućnost **Web** za kontrolu. Za kontrolu obogaćivanja, konfiguriranjem polja **enrichmentType** odaberite vrstu obogaćivanja koju želite prikazati. Dodajte zasebnu kontrolu obogaćivanja za svaku vrstu obogaćivanja.

1. Odaberite **Spremi** i **Objavi** da biste objavili ažurirani obrazac za kontakt.

1. Idite na objavljeni obrazac za kontakt. Vidjet ćete novododanu kontrolu. Možda ćete se morati prijaviti prilikom prvog korištenja.

1. Da biste prilagodili ono što želite prikazati na prilagođenoj kontroli, odaberite gumb za uređivanje u gornjem desnom kutu.

## <a name="upgrade-customer-card-add-in"></a>Nadogradnja dodatka za karticu kupca

Dodatak za karticu kupca ne nadograđuje se automatski. Za nadogradnju na najnoviju verziju slijedite ove korake u aplikaciji Dynamics 365 s instaliranim dodatkom.

1. U aplikaciji Dynamics 365 idite na **Postavke** > **Prilagođavanje** i odaberite **Rješenja**.

1. U tablici dodataka potražite **CustomerInsightsCustomerCard** i odaberite redak.

1. Odaberite **Primijeni nadogradnju rješenja** na akcijskoj traci.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Nadogradite rješenje u području Prilagođavanje aplikacija sustava Dynamics 365.":::

1. Nakon pokretanja postupka nadogradnje vidjet ćete indikator učitavanja sve dok nadogradnja ne završi. Ako nema novije verzije, nadogradnja će prikazati poruku o pogrešci.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
