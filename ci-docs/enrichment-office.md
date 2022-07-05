---
title: Obogatite profile kupaca podacima iz Microsoft Office 365 (pretpregleda)
description: Koristite vlasničke podatke iz Microsoft Office kako biste obogatili svoje profile kupaca podacima o angažmanu.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 75762afb70814c8a81c1574ee7ea1553a2048737
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055665"
---
# <a name="enrich-customer-profiles-with-data-from-microsoft-office-365-preview"></a>Obogatite profile kupaca podacima iz Microsoft Office 365 (pretpregleda)

Koristite podatke iz Microsoft Office 365 da biste obogatili profile svojih korisničkih računa uvidima u angažmane putem Office 365 aplikacija. Podaci o angažmanu sastoje se od aktivnosti e-pošte i sastanka, koja se agregira na razini računa. Na primjer, broj e-poruka s poslovnog računa ili broj sastanaka s računom. Podaci o pojedinačnim korisnicima nisu dostupni.

## <a name="supported-countries-or-regions"></a>Podržane države ili regije

Trenutačno podržavamo sljedeće regije: Ujedinjenu Kraljevinu, Europu, Sjevernu Ameriku.

## <a name="prerequisites"></a>Preduvjeti

- Aktivna Office 365 licenca u oblaku.
- [Objedinjeni profili](customer-profiles.md) kupaca na [temelju poslovnih računa](work-with-business-accounts.md).
- Organizacija [Microsoft Dataverse pridružena](create-environment.md#step-3-connect-to-microsoft-dataverse) vašem okruženju Customer Insights.
- [Administratorske](permissions.md#admin) dozvole.
- Privolite Office 365 administratora klijenta da koristite podatke za pružanje Office 365 **uvida za organizaciju** u aplikacijama sustava Dynamics 365.

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

1. Odaberite **Obogati moje podatke** na pločici **Angažman** računa.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Pločica za zaruke računa.":::

1. Pregledajte pregled, a zatim odaberite **Dalje**.

1. Unesite adrese e-pošte tvrtke ili ustanove za koje će se prikupljati podaci sustava Office. Za relevantnu komunikaciju obrađuju se samo podaci s navedenih adresa e-pošte. Najbolji način je da koristite grupe e-pošte, na primjer, *američki prodajni tim*, kojim možete upravljati u sustavu Office 365. Broj adresa e-pošte u grupama je riješen i prikazan. Ukupan broj adresa e-pošte mora biti najmanje 2 i ne smije biti veći od 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Adrese e-pošte za angažiranje računa.":::

1. Pregledajte i dajte svoj pristanak za [Office 365 pristanak](#office-365-tenant-administrator-consent) administratora klijenta odabirom **slažem se**.

1. Odaberite **Dalje**.

1. **Odaberite skup podataka** za kontakt i odaberite profil koji želite obogatiti. Odaberite **Dalje**.

1. Mapirajte polje adrese e-pošte kontakta i odaberite **Dalje**.

1. Navedite naziv **za** obogaćivanje i izlazni **entitet**.

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

1. Odaberite **Zatvori** da biste se vratili na **stranicu Obogaćivanje**.

### <a name="office-365-tenant-administrator-consent"></a>Office 365 pristanak administratora klijenta

Office 365 Za aktiviranje obogaćivanja potreban je pristanak administratora klijenta. Prilikom spremanja obogaćivanja administratorima klijenta šalje Office 365 se poruka e-pošte u kojoj se od njih traži da pregledaju i pristanu na to da aplikacijama sustava Dynamics 365 omoguće korištenje podataka vaših poduzeća za pružanje Office 365 uvida **za organizaciju**. Administrator Office 365 klijenta također može pristati izravno na svojoj administratorskoj Office 365 konzoli odabirom **mogućnosti Uvidi za organizaciju**.

## <a name="running-the-enrichment-for-the-first-time"></a>Prvi put pokretanje obogaćivanja

Kada se obogaćivanje započne prvi put, nakon što Office 365 administrator klijenta da pristanak, počinje preuzimanje podataka.Office 365 Ovaj proces traje neko vrijeme. Prva utrka obogaćivanja trebala bi se dogoditi s kašnjenjem od šest sati. Broj dana koje podaci pokrivaju možete vidjeti na stranici pregleda angažmana računa nakon završetka obogaćivanja. S velikim volumenom podataka ponovno pokrenite obogaćivanje nakon nekoliko dana. Osigurava da su podaci potpuni za cijelo vremensko razdoblje, što je jedna godina.

Ovisno o veličini podataka iz sustava Office, može proći nekoliko sati dok se ne dovrši postupak obogaćivanja.

Kada pokrenete obogaćivanje, Microsoft će obrađivati podatke unutar Office 365 granice usklađenosti kako bi stvorio agregirane uvide koji se zatim dodaju u vaše okruženje Customer Insights. Korisnicima korisničkih uvida ne postaju dostupni podaci na pojedinačnoj razini (na primjer, tijelo bilo koje pozivnice za e-poštu ili kalendar).

Odaberite **Pokreni** da biste pokrenuli postupak obogaćivanja.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Prikaz rezultata obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Ovo je *entitet Office*. *Office_UserEntity* sadrži ID-ove servisa Active Directory za adrese e-pošte odabrane tijekom konfiguracije obogaćivanja.

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Pretpregled rezultata nakon pokretanja postupka obogaćivanja.":::

Svi se podaci agregiraju do razine računa. Sustav izračunava ocjenu angažmana, koja se kreće od 0 do 100, za svaki račun. Ocjena angažmana pruža kompozitnu mjeru angažmana računa na e-porukama i sastancima u odnosu na vaše druge račune. Sljedeći popis sadrži agregirane podatke koje pruža obogaćivanje angažmana računa:

| Podaci                                                                              | Naziv stupca                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Rezultat angažmana                                                                  |  EngagementScore                         |
| Broj poruka e-pošte na račun                                                       |  NoOfEmails_ToAccount                    |
| Broj poruka e-pošte s računa                                                     |  NoOfEmails_FromAccount                  |
| Broj sastanaka koje je pokrenuo račun                                           |  NoOfMeetings_FromAccount                |
| Broj sastanaka koje je pokrenula vaša tvrtka ili ustanova                                 |  NoOfMeetings_ToAccount                  |
| Broj osoba iz vaše tvrtke ili ustanove na sastancima s računom                  |  NoOfContactsInvolved_Meetings           |
| Broj osoba iz tvrtke ili ustanove u razgovorima e-poštom s računom       |  NoOfContactsInvolved_Emails             |
| Broj osoba s računa na sastancima s tvrtkom ili ustanovom                  |  NoOfAccountContactsInvolved_Meetings    |
| Broj osoba s računa u razgovorima e-poštom s tvrtkom ili ustanovom       |  NoOfAccountContactsInvolved_Emails      |
| Datum početka angažmana (prva e-pošta ili sastanak u podacima)                        |  EngagementStartDate                     |
| Dani od zadnje e-pošte                                                             |  DaysSinceLastEmail                      |
| Dani od zadnjeg sastanka                                                           |  DaysSinceLastMeeting                    |
| Prosječno trajanje sastanaka                                                      |  AverageDuration_Of_Meetings             |
| Prosječno trajanje odgovora e-poštom s računa                                    |  AverageDuration_Of_AccountEmailReplies  |
| Datum početka agregacije                                                            |  AggregationStartDate                    |
| Razina agregacije (godina, mjesec ili tjedan)                                          |  AggregationLevel                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>Prikaz podataka o obogaćivanju na kartici klijenta

Angažman računa također se može pogledati na pojedinačnim karticama kupaca. Idite na **Klijenti** i odaberite profil klijenta. Na kartici kupca pronaći ćete ocjenu angažmana računa, ukupan broj e-poruka i ukupan broj sastanaka objedinjenih tijekom prošle godine. Također možete pronaći grafikone koji prikazuju povijest e-pošte i sastanaka.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kartica klijenta s obogaćenim podacima.":::

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Na primjer, segment koji sadrži sve kupce koji imaju vrijednost veću od 60 za *dane od posljednje e-pošte* i *dane od posljednjeg sastanka*. Taj segment sadrži ustajale račune koje možete pokušati ponovno aktivirati.

[!INCLUDE [footer-include](includes/footer-banner.md)]
