---
title: Obogaćivanje korisničkih profila podacima iz Microsoft Office 365
description: Koristite vlasničke podatke kako Microsoft Office biste obogatili svoje profile klijenata podacima o angažmanu.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 938a9de83fd8f5ff0c9ae815d626cdfa35228aba
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228465"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Obogaćivanje korisničkih profila podacima o angažmanu (pretpregled)

Koristite podatke iz Microsoft Office 365 da biste obogatili profile korisničkog računa uvidima u angažmane putem Office 365 aplikacija. Podaci o angažmanu sastoje se od aktivnosti e-pošte i sastanka, koje se objedinjuju na razini računa. Na primjer, broj poruka e-pošte s poslovnog računa ili broj sastanaka s računom. Podaci o pojedinačnim korisnicima nisu dostupni. 

Ovo obogaćivanje dostupno je u sljedećim regijama: Velikoj Britaniji, Europi, Sjevernoj Americi.

## <a name="prerequisites"></a>Preduvjeti

Da biste konfigurirali obogaćivanje, moraju biti ispunjeni sljedeći preduvjeti:

- Imate aktivnu Office 365 licencu u oblaku.
- Imate objedinjene [profile](customer-profiles.md) klijenata na temelju [poslovnih računa](work-with-business-accounts.md).
- Okruženje Customer Insights mora imati pridruženu organizaciju [Microsoft Dataverse](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Imate [administratorske](permissions.md#administrator) dozvole.
- Imate ili možete dobiti pristanak administratora klijenta Office 365 za korištenje Office 365 podataka za pružanje **uvida za organizaciju** u aplikacijama sustava Dynamics 365.

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. U uvidima u ciljnu skupinu idite u odjeljak **Podaci** > **Obogaćivanje**.

1. Idite na karticu Otkrivanje i na pločici Angažiranje **računa odaberite** Obogati moje **podatke**.**·**

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Pločica o angažmanu na računu.":::
   
1. U koraku **Pregled** odaberite **Dalje** i unesite adrese e-pošte tvrtke ili ustanove za koje će se podaci sustava Office agregirati. Za relevantnu komunikaciju obrađuju se samo podaci s navedenih adresa e-pošte. Najbolja praksa je korištenje grupa e-pošte, na primjer, *tima za prodaju* u SAD-u, kojima se lako upravlja u sustavu Office 365. Broj adresa e-pošte u grupama se razrješava i prikazuje. Ukupan broj adresa e-pošte mora biti najmanje 2 i ne smije biti veći od 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Adrese e-pošte za angažiranje računa.":::

1. Pregledajte izjavu o pristanku, potvrdite **okvir Slažem se**, a zatim **Dalje**.

1. Odaberite skup podataka kupca, a zatim **Dalje**.

1. Mapirajte polje adrese e-pošte kontakta i odaberite **Dalje**.

1. Pregledajte konfiguraciju obogaćivanja, dajte naziv obogaćivanju i odaberite **Spremi obogaćivanje** da biste spremili obogaćivanje.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 pristanak administratora klijenta

Za aktivaciju obogaćivanja Office 365 potreban je pristanak administratora klijenta. E-pošta se Office 365 šalje administratorima klijenta prilikom spremanja obogaćivanja, što od njih traži da pregledaju i pristanu na dopuštanje aplikacijama sustava Dynamics 365 da koriste podatke vaših poduzeća za pružanje Office 365 uvida **za organizaciju**. Administrator klijenta Office 365 također može dati pristanak izravno na svojoj administratorskoj konzoli Office 365 odabirom **uvida za tvrtku ili ustanovu**.

## <a name="running-the-enrichment-for-the-first-time"></a>Prvi put pokretanje obogaćivanja

Kada se obogaćivanje započne prvi put, nakon što Office 365 administrator klijenta da pristanak, počinje preuzimanje Office 365 podataka. Ovaj proces traje neko vrijeme. Prva utrka obogaćivanja trebala bi se dogoditi s odgodom od šest sati. Broj dana koje podaci pokrivaju možete vidjeti na stranici pregleda angažmana računa nakon završetka obogaćivanja. S velikom količinom podataka ponovno pokrenite obogaćivanje nakon nekoliko dana. Osigurava da su podaci potpuni za cijelo vremensko razdoblje, koje traje godinu dana.

Da biste pokrenuli postupak, na stranici Konfiguracija angažmana računa odaberite **Pokreni**. Osim toga, možete dopustiti sustavu automatsko pokretanje obogaćivanja kao dio zakazanog [osvježavanja](system.md#schedule-tab). Prema zadanim postavkama, obogaćivanje se pokreće jednom tjedno.

Ovisno o veličini podataka sustava Office, do dovršetka obogaćivanja može proći nekoliko sati.

Kada pokrenete obogaćivanje, Microsoft će obraditi podatke unutar Office 365 granice usklađenosti kako bi stvorio zbirne uvide koji se zatim dodaju u okruženje Customer Insights. Korisnicima uvida u klijenta ne postaju dostupni podaci na pojedinačnoj razini (na primjer, tijelo bilo koje pozivnice za e-poštu ili kalendar). 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon pokretanja procesa obogaćivanja idite na **Moje obogaćivanje** kako biste pregledali rezultate obogaćivanja. Pronaći ćete ukupan broj obogaćenih kupaca i pregled rezultata obogaćivanja. Uključuje broj obrađenih poruka e-pošte i sastanaka, broj dana za koje su podaci agregirani i još mnogo toga.

Pronaći ćete i grafikon s brojem obogaćenih korisnika tijekom vremena i pregled podataka o obogaćivanju.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Pretpregled rezultata nakon pokretanja postupka obogaćivanja.":::

Svi se podaci zbrajaju do razine računa. Sustav izračunava ocjenu angažmana, koja se kreće od 0 do 100, za svaki račun. Ocjena angažmana pruža složenu mjeru angažmana računa u porukama e-pošte i sastancima u odnosu na druge račune. Sljedeći popis sadrži agregirane podatke koje pruža obogaćivanje angažmana računa:



| Podaci                                                                              | Naziv stupca                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Rezultat angažmana                                                                  |  AngažmanScore                         |
| Broj poruka e-pošte na račun                                                       |  NoOfEmails_ToAccount                    |
| Broj poruka e-pošte s računa                                                     |  NoOfEmails_FromAccount                  | 
| Broj sastanaka koje je pokrenuo račun                                           |  NoOfMeetings_FromAccount                | 
| Broj sastanaka koje je pokrenula vaša tvrtka ili ustanova                                 |  NoOfMeetings_ToAccount                  | 
| Broj osoba iz tvrtke ili ustanove u sastancima s računom                  |  NoOfContactsInvolved_Meetings           | 
| Broj osoba iz tvrtke ili ustanove u razgovorima e-poštom s računom       |  NoOfContactsInvolved_Emails             | 
| Broj osoba s računa na sastancima s tvrtkom ili ustanovom                  |  NoOfAccountContactsInvolved_Meetings    | 
| Broj osoba s računa u razgovorima e-poštom s tvrtkom ili ustanovom       |  NoOfAccountContactsInvolved_Emails      | 
| Datum početka angažmana (prva e-pošta ili sastanak u podacima)                        |  EngagementStartDate                     | 
| Dani od zadnje e-pošte                                                             |  DaysSinceLastEmail                      | 
| Dani od posljednjeg sastanka                                                           |  DaysSinceLastMeeting                    | 
| Prosječno trajanje sastanaka                                                      |  AverageDuration_Of_Meetings             | 
| Prosječno trajanje odgovora e-poštom s računa                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Datum početka zbrajanja                                                            |  AgregacijaStartDate                    | 
| Razina agregacije (godina, mjesec ili tjedan)                                          |  AgregacijaLevel                        | 


Pregledajte obogaćene podatke tako da u odjeljku pretpregleda **odaberete Pogledajte više**. Otvara *entitet Office*. Entitet naveden u **grupi Obogaćivanje** možete pronaći i u **podatkovnim** > **entitetima**. Pronaći *ćete i Office_UserEntity* koja sadrži ID-ove servisa Active Directory za adrese e-pošte odabrane tijekom konfiguracije obogaćivanja 

## <a name="see-enrichment-data-on-the-customer-card"></a>Prikaz podataka o obogaćivanju na kartici klijenta

Angažman računa može se pregledati i na pojedinačnim karticama kupaca. Idite na **Klijenti** i odaberite profil klijenta. Na kartici kupca pronaći ćete ocjenu angažmana računa, ukupan broj poruka e-pošte i ukupan broj sastanaka agregiranih tijekom prošle godine. Pronađite i grafikone koji prikazuju povijest e-pošte i sastanaka.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kartica klijenta s obogaćenim podacima.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Stvaranje segmenata i mjera na temelju obogaćenih podataka

Obogaćeni podaci mogu se koristiti za izradu segmenata i mjera kako je detaljno opisano u nastavku. Na primjer, segment koji sadrži sve korisnike koji imaju vrijednost veću od 60 godina od *zadnje e-pošte* i *dana od posljednjeg sastanka*. Taj segment sadrži ustajale račune koje možete pokušati ponovno aktivirati. 

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
