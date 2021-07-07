---
title: Integracija web-podataka iz uvida u angažman s uvidima u ciljnu skupinu
description: Dobijte web-informacije o klijentima od uvida u angažman do uvida u ciljnu skupinu.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 76a53a897e90152707a7c1255ed5ed93a5f3b5a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305009"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integracija web-podataka iz uvida u angažman s uvidima u ciljnu skupinu

Klijenti često obavljaju svakodnevne transakcije na mreži koristeći web-stranice. Mogućnost uvida u angažman (pregled) u značajci Dynamics 365 Customer Insights praktično je rješenje za integriranje web podataka kao izvora. Osim podataka o transakcijama, demografskim podacima ili podataka o ponašanju, aktivnosti na webu možemo vidjeti i u objedinjenim profilima klijenata. Te profile možemo koristiti za dobivanje dodatnih uvida poput segmenata, mjera ili predviđanja za aktivaciju publike.

Ovaj članak opisuje korake za unošenje podataka o web-aktivnostima vaših klijenata iz uvida u angažman u vaše postojeće okruženje uvida u ciljnu skupinu.

U ovom primjeru pretpostavljamo okruženje koje sadrži objedinjene profile klijenata. Profili su objedinjeni s izvorima iz upitnika, maloprodaje i sustava prodaje karata. Prikazuje i povezane aktivnosti klijenata. 

Sada želimo znati posjećuje li klijent naša web-svojstva i razumije li njihove aktivnosti. Aktivnosti uključuju, na primjer, posjećene web-stranice ili pregledane stranice proizvoda putem veze primljene u e-pošti.

## <a name="prerequisites"></a>Preduvjeti

Da bi se integrirali podaci iz uvida u angažman, mora biti ispunjeno nekoliko preduvjeta: 

- Integrirajte SDK uvida u angažman sa svojim web-mjestom. Za dodatne informacije pogledajte [Pregled resursa za razvojne inženjere](../engagement-insights/developer-resources.md).
- Izvoz web-događaja iz uvida u angažman zahtijeva pristup računu servisa Azure Data Lake Storage koji će se koristiti za unošenje podataka o web-događajima u uvide publike. Za dodatne informacije pogledajte [Izvoz događaja](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Konfiguracija redefiniranih događaja u uvidima u angažman

Nakon što administrator instrumentira web-stranicu SDK-om za uvid u angažman, *osnovni događaji* prikupljaju se kada korisnik pregleda web-stranicu ili negdje klikne. Osnovni događaji obično sadrže brojne pojedinosti. Ovisno o vašem slučaju korištenja, potreban vam je samo podskup podataka u osnovnom događaju. Uvidi u angažman omogućuju vam stvaranje *redefiniranih događaja* koji sadrže samo svojstva osnovnog događaja koji ste odabrali.     

Za dodatne informacije pogledajte [Stvaranje i izmjena redefiniranih događaja](../engagement-insights/refined-events.md).

Razmatranja prilikom stvaranja redefiniranih događaja: 

- Navedite suvisli naziv za redefinirani događaj. Upotrijebit će se kao naziv aktivnosti u uvidima publike.
- Odaberite barem sljedeća svojstva da biste stvorili aktivnost u uvidima u ciljnu skupinu: 
    - Signal.Action.Name – označava pojedinosti o aktivnosti.
    - Signal.User.Id – koristi se za mapiranje pomoću ID-a klijenta.
    - Signal.View.Uri – koristi se kao web-adresa kao osnova za segmente ili mjere.
    - Signal.Export.Id – koristi se kao primarni ključ za događaje.
    - Signal.Timestamp – određuje datum i vrijeme aktivnosti.

Odaberite filtre da biste se usredotočili na događaje i stranice koji su bitni za vaš slučaj korištenja. U ovom ćemo primjeru koristiti naziv radnje „Promocija putem e-pošte”.

## <a name="export-the-refined-web-events"></a>Izvoz web-događaja sužene pretrage 

Nakon definiranja događaja sužene pretrage, morate konfigurirati izvoz podataka o događaju u Azure Data Lake Storage, koji se može postaviti kao izvor podataka za unošenje u uvidima publike. Izvozi se neprestano događaju dok događaji proizlaze iz web-svojstva.

Za dodatne informacije pogledajte [Izvoz događaja](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Unošenje podataka o događajima u uvide u ciljnu skupinu

Sada kada ste definirali redefinirani događaj i konfigurirali njegov izvoz, prelazimo na unošenje podataka u uvide u ciljnu skupinu. Trebate stvoriti novi izvor podataka na temelju mape Common Data Model. Unesite pojedinosti za račun pohrane na koji izvozite događaje. U datoteci *default.cdm.json* odaberite redefinirani događaj koji ćete unijeti i stvoriti entitet u uvidima u ciljnu skupinu.

Za dodatne informacije pogledajte [Povezivanje s mapom modela Common Data Model pomoću računa za Azure Data Lake](connect-common-data-model.md).


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Redefinirane podatke o događajima povežite kao aktivnost profila klijenta

Nakon dovršetka unosa entiteta, možete konfigurirati aktivnost za profil klijenta.

Za dodatne informacije pogledajte [Aktivnosti klijenata](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Stranica s aktivnostima s proširenim oknom uređivanja aktivnosti i popunjenim poljima.":::

Konfigurirajte novu aktivnost pomoću sljedećeg mapiranja: 

- **Primarni ključ**: Signal.Export.Id, jedinstveni ID koji je dostupan za svaki zapis o događaju u uvidima u ciljnu skupinu. Ovo se svojstvo automatski generira.

- **Vremenska oznaka**: Signal.Timestamp u svojstvu događaja.

- **Događaj**: Signal.Name, naziv događaja koji želite pratiti.

- **Web-adresa**: Signal.View.Uri koji se odnosi na URI stranice koja je stvorila događaj.

- **Pojedinosti**: Signal.Action.Name za predstavljanje podataka koji će se povezati s događajem. Odabrano svojstvo u ovom slučaju označava da je događaj za promociju putem e-pošte.

- **Vrsta aktivnosti**: U ovom primjeru odabiremo postojeću vrstu aktivnosti WebLog. Ovaj je odabir korisna mogućnost filtriranja za pokretanje modela predviđanja ili stvaranje segmenata na temelju ove vrste aktivnosti.

- **Postavi odnos**: Ova važna postavka veže aktivnost uz postojeće profile klijenata. **Signal.User.Id** je identifikator konfiguriran u SDK-u koji se prikuplja i koji se odnosi na korisnički ID u ostalim izvorima podataka koji su konfigurirani u uvidima u ciljnu skupinu. U ovom primjeru konfiguriramo odnos između Signal.User.Id i RetailCustomers: CustomerRetailId, što je primarni ključ koji je identificiran u koraku mapiranja u procesu objedinjavanja podataka.

Nakon obrade aktivnosti možete pregledati zapise o klijentima i otvoriti karticu klijenta da biste na vremenskoj traci vidjeli aktivnosti iz uvida u angažman. 

> [!TIP]
> Da biste pronašli ID klijenta koji ima aktivnost uvida u angažman, idite na **Entiteti** i pregledajte podatke za entitet UnifiedActivity. ActivityTypeDisplay = WebLog sadrži aktivnost uvida u angažman konfiguriranu u gornjem primjeru. Kopirajte ID klijenta za jedan od tih zapisa i za taj ID na stranici **Klijenti**.

## <a name="next-steps"></a>Sljedeći koraci

Sada možete stvoriti [segmente](segments.md), [mjere](measures.md) i [predviđanja](predictions.md) da biste uspostavili smislenu vezu sa svojim klijentima.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
