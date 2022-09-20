---
title: Dodatak korisničke kartice za aplikacije sustava Dynamics 365 (pretpregled) (sadrži videozapis)
description: Pomoću ovog dodatka prikažite podatke o profilu korisnika iz aplikacije Customer Insights iz aplikacija sustava Dynamics 365.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 65fd80cc563b8b3b8c8874b66f179f8b0c7a19f0
ms.sourcegitcommit: fe33cc76d015232ff8737f77193f44f2b884bb6b
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473633"
---
# <a name="customer-card-add-in-for-dynamics-365-apps-preview"></a>Dodatak za karticu kupca za aplikacije sustava Dynamics 365 (pretpregled)

Dobijte prikaz svojih klijenata od 360 stupnjeva izravno u Dynamics 365 aplikacijama. S dodatkom kartice klijenta instaliranim u podržanoj aplikaciji Dynamics 365, možete odabrati prikaz polja profila klijenta, uvida i vremenske trake aktivnosti. Dodatak će dohvatiti podatke iz usluge Customer Insights bez utjecaja na podatke u povezanoj aplikaciji Dynamics 365.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Preduvjeti

- Aplikacije sustava Dynamics 365 stvorene prema modelu, kao što su Prodaja ili služba za korisnike, verzija 9.0 i novija.
- Da bi se podaci sustava Dynamics 365 mapirali na korisničke profile customer insights, preporučujemo da se [unose iz aplikacije Dynamics 365 pomoću Microsoft Dataverse poveznika](connect-power-query.md). Ako koristite drugu metodu za unos kontakata sustava Dynamics 365 (ili poslovnih subjekata), provjerite `contactid` je li polje (ili `accountid`) postavljeno kao [primarni ključ za taj izvor podataka tijekom postupka objedinjavanja podataka](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Svi korisnici sustava Dynamics 365 dodatka Customer Card moraju se [dodati kao korisnici](permissions.md) u Customer Insights da bi vidjeli podatke.
- [Konfigurirane mogućnosti pretraživanja i filtriranja](search-filter-index.md) u aplikaciji Customer Insights.
- Neki podaci i kontrole dostupni su samo u okruženjima određenih vrsta. Konfiguracija dodatka obavijestit će vas ako kontrola nije dostupna zbog odabrane vrste okruženja. Ova će se pogreška prikazati unutar kontrole prilikom prikazivanja. Saznajte više o [slučajevima upotrebe okruženja](work-with-business-accounts.md).
- Svaka kontrola dodatka oslanja se na određene podatke u customer insights.
  - **Kontrola** mjere zahtijeva [konfigurirane mjere](measures.md) atributa klijenta.
  - **Kontrola** inteligencije zahtijeva podatke generirane pomoću [predviđanja ili prilagođenih modela](predictions-overview.md).
  - **Kontrola** detalja o kupcu prikazuje sva polja iz profila dostupna u jedinstvenom profilu kupca.
  - **Kontrola** obogaćivanja zahtijeva aktivno [obogaćivanje](enrichment-hub.md) koje se primjenjuje na profile kupaca. Dodatak kartice podržava ova obogaćivanja: [robne marke](enrichment-microsoft.md) koje pruža Microsoft, [interesi](enrichment-microsoft.md) koje pruža Microsoft i [podaci o](enrichment-office.md) angažmanu sustava Office koje pruža Microsoft.
  - **Kontrola** kontakata zahtijeva vrstu semantičkog entiteta kontakta.
  - **Kontrola** vremenske trake zahtijeva [konfigurirane aktivnosti](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instaliranje dodatka za korisničku karticu

Dodatak za korisničku karticu rješenje je za aplikacije Customer Engagement u programu Dynamics 365. Da biste instalirali rješenje:

1. Idite na AppSource Dynamics Customer Card i u okvir za **pretraživanje unesite Dynamics Customer Card**.

1. Odaberite [Dodatak kartice klijenta na AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i odaberite **Nabavi odmah**.

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

Ovisno o vašem scenariju, možete odabrati dodavanje kontrola bilo u obrazac **Kontakt** ili **Račun**. Ako je vaše okruženje Customer Insights namijenjeno poslovnim računima, preporučujemo dodavanje kontrola u obrazac Račun. U tom slučaju, u sljedećim koracima zamijenite „kontakt” s „račun”.

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

## <a name="troubleshooting"></a>Rješavanje problema

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Kontrole iz dodatka Customer Card ne pronalaze podatke

**Problem:**

Čak i s ispravno konfiguriranim poljima ID-a, kontrole ne mogu pronaći podatke za bilo kojeg kupca.  

**Rješenje:**

1. Provjerite jeste li konfigurirali dodatak kartica prema uputama: [Konfiguriranje dodatka Kartica kupca](#configure-the-customer-card-add-in)

1. Pregledajte konfiguraciju gutanja podataka. Uredite izvor podataka za sustav Dynamics 365 koji sadrži GUID ID kontakta. Ako je GUID ID kontakta prikazan s velikim slovima u uređivaču Power Query, pokušajte sljedeće korake:
    1. Uredite izvor podataka da biste otvorili izvor podataka u uređivaču Power Query.
    1. Odaberite stupac ID kontakta.
    1. Na traci zaglavlja odaberite **Pretvorba** da biste vidjeli dostupne akcije.
    1. Odaberite **malo slovo**. Provjerite jesu li GUID-ovi u tablici sada mala slova.
    1. Spremite izvor podataka.
    1. Pokrenite procese gutanja podataka, objedinjavanja i silaznog lanca da biste prenijeli promjene u GUID.

Nakon što sustav dovrši potpuno osvježavanje, kontrole dodataka kartice kupca trebale bi prikazivati očekivane podatke.

[!INCLUDE [footer-include](includes/footer-banner.md)]
