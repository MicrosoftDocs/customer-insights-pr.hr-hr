---
title: Aktivnosti klijenta
description: Definirajte aktivnosti klijenta i prikažite ih na vremenskoj traci na profilima klijenata.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c99ec2e7d5e4bf32a509bbe4c0c53999129b2305
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732434"
---
# <a name="customer-activities"></a>Aktivnosti klijenta

Kombinirajte aktivnosti klijenta iz [različitih izvora podataka](data-sources.md) u Dynamics 365 Customer Insights da biste stvorili vremensku crtu koja kronološki prikazuje aktivnosti. Uključite vremensku crtu u aplikacije sustava Dynamics 365 pomoću [rješenja dodatka Kartica](customer-card-add-in.md) kupca ili na nadzornu ploču Power BI.

## <a name="define-an-activity"></a>Definiranje aktivnosti

Vaši izvori podataka mogu uključivati entitete s podacima o transakcijama i aktivnostima iz više izvora podataka. Identificirajte te entitete i odaberite aktivnosti koje želite prikazati na vremenskoj traci klijenta. Odaberite entitet koji uključuje vašu ciljanu aktivnost ili aktivnosti.

Entitet mora imati najmanje jedan atribut vrste **Datum** da bi se uključio u vremensku traku klijenta i ne možete dodavati entitete bez polja **Datum**. Kontrola **Dodaj aktivnost** onemogućena je ako nije pronađen takav entitet.

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Aktivnosti**.

1. Odaberite **Dodaj aktivnost** za pokretanje vođenog iskustva za postupak postavljanja aktivnosti.

1. U koraku **Podaci o aktivnostima** postavite vrijednosti za sljedeća polja:

   - **Naziv aktivnosti**: Odaberite naziv za svoju aktivnost.
   - **Entitet**: odaberite entitet koji uključuje podatke o transakcijama ili aktivnostima.
   - **Primarni ključ**: odaberite polje koje jedinstveno identificira zapis. Ne smije sadržavati duplicirane vrijednosti, prazne vrijednosti ili vrijednosti koje nedostaju.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Postavite podatke o aktivnosti s nazivom, entitetom i primarnim ključem.":::

1. Odaberite **Sljedeće** da biste prešli na sljedeći korak.

1. U kkoraku **Odnos** konfigurirajte pojedinosti za povezivanje podataka o aktivnosti s odgovarajućim zapisom klijenta. Ovaj korak vizualizira vezu među entitetima.  

   - **Prvi**: Strano polje u vašem entitetu aktivnosti koje će se koristiti za uspostavljanje odnosa s drugim entitetom.
   - **Drugi**: Odgovarajući izvorni entitet klijenta s kojim će vaš entitet aktivnosti biti u odnosu. Možete se odnositi samo na izvorne entitete klijenata koji se koriste u procesu objedinjavanja podataka.
   - **Treći**: Ako odnos između ovog entiteta aktivnosti i odabranog izvornog entiteta klijenta već postoji, naziv odnosa bit će u načinu samo za čitanje. Ako takav odnos ne postoji, stvorit će se novi odnos s nazivom koji navedete u ovom okviru.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definirajte odnos entiteta.":::

   > [!TIP]
   > U B2B okruženjima možete birati između entiteta računa i ostalih entiteta. Ako odaberete entitet računa, automatski se postavlja putanja odnosa. Za druge entitete morate definirati putanju odnosa preko jednog ili više posrednih entiteta dok ne dođete do entiteta računa.

1. Odaberite **Sljedeće** da biste prešli na sljedeći korak. 

1. U koraku **Objedinjavanje aktivnosti** odaberite događaj aktivnosti i vrijeme početka svoje aktivnosti. 
   - **Obvezna polja**
      - **Aktivnost događaja**: Polje koje je događaj za ovu aktivnost.
      - **Vremenska oznaka**: Polje koje predstavlja vrijeme početka vaše aktivnosti.

   - **Neobvezna polja**
      - **Dodatna pojedinost**: Polje s relevantnim informacijama za ovu aktivnost.
      - **Ikona**: Ikona koja najbolje predstavlja ovu vrstu aktivnosti.
      - **Web-adresa**: Polje koje sadrži URL s informacijama o ovoj aktivnosti. Na primjer, transakcijski sustav iz kojega je potekla ova aktivnost. Ovaj URL može biti bilo koje polje iz izvora podataka ili se može konstruirati kao novo polje s pomoću transformacije Power Query. Podaci o URL-u bit će pohranjeni u entitetu *Objedinjena aktivnost* koji se može konzumirati prema dolje pomoću [API-ja](apis.md).

   - **Prikaži na vremenskoj traci**
      - Odaberite želite li prikazati tu aktivnost na prikazu vremenske trake profila klijenta. Odaberite **Da** za prikaz aktivnosti na vremenskoj traci ili **Ne** za sakrivanje.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Navedite podatke o aktivnostima klijenta u entitetu Objedinjene aktivnosti.":::

1. Odaberite **Sljedeće** da biste se pomaknuli na sljedeći korak. Možete odabrati **Završi i pregledaj** da biste sada spremili aktivnost s vrstom aktivnosti postavljenom na **Ostalo**. 

1. U koraku **Vrsta aktivnosti** odaberite vrstu aktivnosti i neobavezno odaberite želite li semantički mapirati neke od vrsta aktivnosti za korištenje u ostalim područjima Customer Insights. Trenutno vrste aktivnosti *Povratna informacija*, *Vjernost*, *Nalog za prodaju*, *Redak naloga za prodaju* i *Pretplata* mogu se semantički mapirati nakon pristanka na mapiranje polja. Ako vrsta aktivnosti nije relevantna za novu aktivnost, možete odabrati *Ostalo* ili *Stvori novo* za prilagođenu vrstu aktivnosti.

1. Odaberite **Sljedeće** da biste se pomaknuli na sljedeći korak. 

1. U koraku **Pregled** provjerite svoje odabire. Vratite se na bilo koji od prethodnih koraka i ažurirajte podatke ako je potrebno.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Pregledajte navedena polja za aktivnost.":::
   
1. Odaberite **Spremi aktivnost** da biste primijenili promjene i odaberite **Gotovo** da biste se vratili na **Podaci** > **Aktivnosti**. Ovdje možete vidjeti koje su aktivnosti postavljene za prikaz na vremenskoj traci. 

1. Na stranici **Aktivnosti** odaberite **Pokreni** za obradu aktivnosti. 

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Upravljanje postojećim aktivnostima

Na **Podaci** > **Aktivnosti** možete pregledati sve spremljene aktivnosti i upravljati njima. Svaka je aktivnost predstavljena retkom koji također uključuje pojedinosti o izvoru, entitetu i vrsti aktivnosti.

Sljedeće su radnje dostupne kada odaberete aktivnost. 

- **Uredi**: Otvara postavljanje aktivnosti u koraku pregleda. U ovom koraku možete promijeniti bilo koju ili sve trenutne konfiguracije. Nakon promjene konfiguracije odaberite **Spremi aktivnost**, a zatim odaberite **Pokreni** za obradu promjena.

- **Preimenuj** : Otvara dijaloški okvir u koji možete unijeti drugi naziv za odabranu aktivnost. Odaberite **Spremi** za primjenu izmjena.

- **Izbriši**: Otvara dijaloški okvir za potvrdu brisanja odabrane aktivnosti. Možete i izbrisati više aktivnosti odjednom odabirom aktivnosti, a zatim odabirom ikone za brisanje. Odaberite **Izbriši** da biste potvrdili brisanje.

## <a name="view-activity-timelines-on-customer-profiles"></a>Prikaz vremenskih traka aktivnosti na profilima klijenata

Nakon što konfigurirate aktivnosti klijenta, odaberite **Prikaži na vremenskoj traci aktivnosti** u konfiguraciji aktivnosti kako biste pronašli sve aktivnosti klijenta na profilu klijenta.

Da biste otvorili vremensku traku za klijenta, idite na **Klijenti** i odaberite profil klijenta koji želite vidjeti.

Ako je klijent sudjelovao u aktivnosti koju ste konfigurirali, pronaći ćete je u odjeljku **Vremenska traka aktivnosti**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Pregledajte konfigurirane aktivnosti u profilima klijenata.":::

Postoji nekoliko načina za filtriranje aktivnosti na vremenskoj traci aktivnosti:

- Možete odabrati jednu ili više ikona aktivnosti da biste poboljšali rezultate tako da uključuju samo odabrane vrste.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrirajte aktivnosti prema vrsti s pomoću ikona.":::

- Možete odabrati **Filtar** za otvaranje panela s filtrima za konfiguriranje filtara vremenske trake.

   1. Možete filtrirati prema *Vrsti aktivnosti* i *Datumu*
   1. Odaberite **Primijeni** za biste upotrijebili filtre na vremenskoj traci aktivnosti.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="S pomoću panela filtra konfigurirajte uvjete filtra.":::

Da biste uklonili filtre, odaberite **x** pored svakog filtra primijenjenog na vremensku traku ili odaberite **Očisti filtre**.


> [!NOTE]
> Filtri aktivnosti uklanjaju se kada napustite profil klijenta. Morate ih primijeniti svaki put kada otvorite profil klijenta.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
