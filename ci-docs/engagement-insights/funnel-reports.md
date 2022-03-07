---
title: Izvješća o kanalima
description: Kako upotrijebiti izvješća o kanalima kako biste razumjeli kako ciljna skupina donosi odluke.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/17/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 901e7ec50037d66c7c5ceb635d1c6cda6cfff83b
ms.sourcegitcommit: 3bafa27adae113948636b30c7462e0af060c7131
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/17/2021
ms.locfileid: "7498633"
---
# <a name="create-and-manage-funnel-reports"></a>Stvaranje i upravljanje izvješćima o kanalu

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Izvješće o kanalu prikuplja informacije o koracima koji se događaju tijekom puta klijenta kroz vašu web stranicu ili mobilnu aplikaciju. Pomaže vam razumjeti kako ciljna skupina napreduje kroz postupak i prepoznaje točke isključivanja. Na primjer, možete upotrijebiti izvješće o kanalu kako biste identificirali putove koje vaši klijenti poduzimaju prije nego što izvrše kupnju. Izvješće o kanalu pruža podatke za donošenje odluka i identificiranje područja za optimizaciju i poboljšanje postupka.

## <a name="create-a-funnel-report"></a>Izrada izvješća o kanalu

Da biste stvorili izvješće o kanalu, navedite korake koje želite uključiti i aktivnost za svaki korak. Aktivnost je [događaj](glossary.md) koji predstavlja ponašanje korisnika. Izvješće o kanalu prikazuje broj korisnika koji su dovršili svaki definirani korak. 

1. Idite na **Kanali** i odaberite **+Novi kanal** za pokretanje izvješća o kanalu.

1. U **Uređivaču kanal**, u opciji **Koraci** odaberite **+Dodaj korak.** 

1. Unesite naziv u **Naslov koraka**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Novo izvješće o kanalu.":::

1. Odaberite **Aktivnost**. Aktivnost bilježi kada korisnik pregleda stranicu (aktivnost **Prikaz**) ili kad stupi u interakciju sa sadržajem (aktivnost **Radnja**).

1. S pomoću **Kriterija koraka** navedite dimenziju aktivnosti. [Dimenzije](dimensions.md) su atributi koji mogu opisati, filtrirati ili grupirati podatke.

1. Ako želite, možete konfigurirati korake kanala s više uvjeta. Odaberite **Dodaj uvjet** kako biste odredili više dimenzija u koraku. Dodatni kriteriji moraju koristiti istu vrstu aktivnosti. Možete odabrati hoće li više uvjeta biti povezano s operatorom AND ili OR.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Uređivač kanala koji prikazuje konfiguraciju koraka s više uvjeta.":::

1. Odaberite **Dodaj korak** dok ne dovršite sve korake koje želite u izvješću.

1. Odaberite **Spremi**, imenujte izvješće i ponovno odaberite **Spremi**. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Primjer: izvješće o kanalu tvrtke Fourth Coffee

Sljedeći scenarij prikazuje jedan način upotrebe izvješća o kanalu. Analitičar tvrtke Fourth Coffee želi shvatiti utjecaj nedavne promocije na stope pretplate. Analitičar izrađuje izvješće o kanalu kako bi identificirao aktivnost klijenata. Započinje kad klijenti dospiju na početnu stranicu tvrtke dok ne upotrijebe promotivni kod pretplate. Analitičar izrađuje izvješće o kanalu, sa sljedećim koracima:

1. korak: klijenti koji dospiju na početnu stranicu   
2. korak: klijenti koji izvrše kupnju   
3. korak: klijenti koji koriste promotivni kod za popust na pretplatu   
4. korak: registracija za pretplatu   

:::image type="content" source="media/funnel-report-example.png" alt-text="primjer izvješća o kanalu.":::
  
Ovaj kanal omogućuje vam prikaz broja korisnika koji su koristili promotivni kod nakon jednokratne kupnje za registraciju na program pretplate.

### <a name="configure-advanced-settings"></a>Konfiguriranje naprednih postavki 

Izvješća o kanalima vam omogućuju definiranje ograničenja vremena potrebnog za dovršetak kanala. Na primjer, možete postaviti vrijeme za dovršetak kanala na četiri dana. Ova će postavka računati samo uspješne prijave na pretplatu koje su se dogodile u roku od četiri dana od posjeta korisnika početnoj stranici.

1. Idite na **Kanali** da biste otvorili **Biblioteku kanala**.

1. Odaberite naziv za otvaranje izvješća. 

1. U oknu **Uređivač kanala** odaberite **Napredne postavke**. 

1. Postavite Ograniči vrijeme za dovršetak kanala na **Uključeno**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Uređivač kanala koji prikazuje napredne postavke i mogućnosti za ograničavanje vremena za dovršetak kanala.":::

1. Odaberite vrijeme u kojem se kanal morao dovršiti na padajućem popisu **Postavi ograničenje na**.

1. Odaberite **Spremi** za primjenu izmjena.


## <a name="cross-channel-funnel-reports"></a>Izvješća o kanalima više kanala 

Uvidi o angažmanu također mogu prikupljati podatke o ponašanju kupaca u vašoj mobilnoj aplikaciji. Nakon što ste svoju mobilnu aplikaciju instrumentirali [Android SDK-om](get-started-android.md) ili [iOS SDK-om](get-started-ios.md) za uvide u angažman, možete stvoriti izvješća o kanalima više kanala. 

### <a name="create-a-cross-channel-funnel-report"></a>Stvaranje izvješća o kanalima više kanala 

1. Slijedite korake za [stvaranje izvješća o kanalu](#create-a-funnel-report).    

1. Da biste pratili kako vaši kupci komuniciraju s vašom robnom markom na vašem web-mjestu i u mobilnoj aplikaciji, ili na više web-mjesta, koristite prebacivač radnog prostora za izradu koraka kanala s podacima iz drugih radnih prostora. U **Uređivač kanala** pod **Koraci** odaberite iz kojeg radnog prostora trebaju dolaziti podaci za vaš korak kanala.

## <a name="manage-funnel-reports"></a>Upravljanje izvješćima o kanalima

Možete pregledati izvješća o kanalima da biste analizirali podatke, pratili izvedbu i prikupljali uvide.

> [!NOTE]
> - Izvješća o kanalu uvida u angažman trenutačno podržavaju scenarije u kojima su svi korisnici u kanalu anonimni ili je za sve provjerena auteničnost. 
> - Povijesni podaci u izvješćima o kanalima dostupni su za posljednjih 30 dana.

### <a name="view-funnel-reports"></a>Prikaz izvješća o kanalima

1. Idite na **Kanali** da biste otvorili **Biblioteku kanala**.
1. Odaberite naziv za otvaranje izvješća.    

### <a name="see-the-data-collected-for-a-report"></a>Pogledajte prikupljene podatke za izvješće   

Da biste vidjeli informacije o fazi

- Pokažite na korak u izvješću.

:::image type="content" source="media/funnel-step-data.png" alt-text="podaci o kanalu.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Promijenite datumski raspon za izvješće o kanalu

1. Idite na **Kanali** da biste otvorili **Biblioteku kanala**.

1. Odaberite naziv za otvaranje izvješća.

1. Otvorite **vremenski raspon** i odaberite novo vremensko razdoblje s popisa ili **Fiksni datumski raspon** za određivanje datumskog raspona.

## <a name="edit-or-delete-funnel-reports"></a>Uređivanje ili brisanje izvješća o kanalu

Možete promijeniti naziv izvješća o kanalu, izbrisati ga ili izmijeniti korake u izvješću.

### <a name="rename-or-delete-a-funnel-report"></a>Preimenovanje ili brisanje izvješća o kanalu

1. Idite na **Kanali** da biste otvorili **Biblioteku kanala**. 

1. Odaberite **Više** pored izvješća koje želite promijeniti te odaberite **Uredi naziv** ili **Izbriši**.

### <a name="edit-a-funnel-step"></a>Uređivanje koraka kanala  

1. Idite na **Kanali** da biste otvorili **Biblioteku kanala**. 

1. Odaberite naziv za otvaranje izvješća.

1. Odaberite korak koji želite urediti.

1. Odaberite **Uredi**.

1. U **Uređivaču kanala** ažurirajte podatke koje želite promijeniti.  

1. Odaberite **Spremi**.

### <a name="reorder-a-funnel-step"></a>Promjena rasporeda koraka kanala

1. Idite na **Kanali** da biste otvorili **Biblioteku kanala**. 

1. Odaberite naziv za otvaranje izvješća.

1. Odaberite korak za koji želite promijeniti raspored.

1. Za pomicanje koraka odaberite **Pomakni**, a zatim **Gore**, **Dolje**, **Na vrh** ili **Na dno**.

### <a name="delete-a-funnel-step"></a>Brisanje koraka kanala

1. Idite na **Kanali** da biste otvorili **Biblioteku kanala**. 

1. Odaberite naziv za otvaranje izvješća.

1. Odaberite korak koji želite ukloniti, a zatim odaberite **Izbriši**.

## <a name="funnel-insights"></a>Uvidi u kanal 

Uvidi u angažman sada klijentima nude uvide u kanal. Koristite uvide u kanal kako biste stekli dublji uvid u ponašanje klijenta o koracima u izvješću o kanalu. Kada stvorite i spremite novo izvješće o kanalu, za vaše izvješće automatski se generiraju uvidi u kanal. 

Možete vidjeti uvide u kanal iz sljedećih kategorija, i na glavnoj i na razini koraka: 

 - Stopa konverzije 
 - Vrijeme prijelaza 
 - Vrijeme dovršetka 

Pomoću ovih uvida dublje istražite ponašanje klijenata i bolje razumijte ispusne točke i konverzije za svoje izvješće o kanalu. 

Uvidi u kanal preračunavaju se svaka 24 sata ili kada odaberete **Spremi** izvješće o kanalu. 

> [!NOTE]
> Da biste vidjeli uvide za svoj kanal, morate spremiti izvješće svaki put kada unesete izmjene. 

