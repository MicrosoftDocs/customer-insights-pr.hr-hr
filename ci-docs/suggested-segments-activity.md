---
title: Predloženi segmenti na temelju aktivnosti.
description: Neka vam strojno učenje pomogne da pronađete nove i zanimljive segmente na temelju aktivnosti klijenata.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: 85c3cef3a8d531b31b64a7e5decbdc122c4383fc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642331"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Predloženi segmenti na temelju podataka o aktivnostima (pretpregled)

Otkrijte zanimljive segmente svojih klijenata na temelju podataka o aktivnostima klijenata koji se unose u Customer Insights. Primjeri podataka o aktivnostima su transakcije, trajanje poziva za podršku, kupnje ili povrati. Da bi se segmenti predložili, podaci o aktivnostima analiziraju se u odnosu na vrijeme, učestalost i novčanu vrijednost (ili trajanje). Umjesto toga možete stvoriti [predložene segmente za poboljšanje mjere ili bolje razumijevanje utjecaja na atribut](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Kartica predloženih segmenata koja prikazuje prijedloge segmenata za segmente na temelju aktivnosti i atributa.":::

## <a name="categorize-customers-by-activity"></a>Kategorizacija klijenata prema aktivnosti

S [podacima o aktivnostima](activities.md) dostupnim u usluzi Customer Insights možemo stvoriti prijedloge koji predstavljaju grupe klijenata:

- najaktivniji klijenti 
- klijenti koji su obavili najviše kupnji 
- klijenti koji su stvorili najviše prihoda 
- klijenti koji u posljednje vrijeme nisu aktivni 
- klijenti koji često komuniciraju s vašom tvrtkom  

Ako imate maloprodajnu trgovinu, mogli biste saznati koji klijenti donose najveći prihod i nagraditi ih kuponom. Ili možete identificirati povremene klijente i ponuditi im da se pridruže programu nagrađivanja kako bi češće posjećivali vašu tvrtku.
Ako se bavite zdravstvenom djelatnošću koja pruža javnu zdravstvenu zaštitu i vaš je cilj smanjiti troškove za pojedine pacijente. Način da se to učini mogao bi biti smanjenje ponavljajućih posjeta pružanjem najbolje moguće skrbi u što manje posjeta. U ovom je slučaju vaš cilj održati učestalost posjeta niskom i minimizirati ponavljajuće troškove za pacijente. Ili možete identificirati segmente pacijenata koji imaju česte posjete i visoke troškove koji se ponavljaju i analizirati te slučajeve kako biste poboljšali liječenje pojedinca. 

## <a name="required-data"></a>Obavezni podaci

Prijedlozi se stvaraju na temelju odabranih ulaznih podataka. 

- Profili klijenata: svi klijenti ili članovi određenog segmenta. 

- Vremensko razdoblje: prošli mjesec, prošla godina ili bilo koji prilagođeni vremenski okvir.

- Vrsta aktivnosti: kupnje, maloprodajne transakcije, mrežne transakcije, slučajevi korisničke podrške, pretplate itd.  

- Entitet u usluzi Customer Insights koji sadrži podatke o aktivnostima: entitet UnifiedActivity ili entitet za određenu aktivnost. 

- Dimenzije koje treba uključiti: vrijeme, učestalost ili novčanu dimenziju, ovisno o vašim poslovnim zahtjevima.

## <a name="generate-suggested-segments"></a>Stvaranje predloženih segmenata

1. Idite na **Segmenti**.

1. Odaberite karticu **Prijedlozi (pretpregled)**.

1. Odaberite **Pronađi nove prijedloge** i odaberite **Prati ili predvidi ponašanje klijenata**. Odaberite **Pokreni** za pokretanje vođenog iskustva.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Prvi korak čarobnjaka za konfiguraciju za predloženi segment na temelju aktivnosti.":::

1. Navedite potrebne ulazne podatke i odaberite **Sljedeće** za nastavak.

   - Odaberite klijente: uključite sve klijente ili određeni segment.
   - Odaberite aktivnost: odaberite vrstu aktivnosti i entitete koji opisuju aktivnost.
   - Postavke: postavite vremensko razdoblje koje treba uzeti u obzir, čimbenike za prijedloge i mapirajte atribute.

1. Pregledajte svoj unos i odaberite **Pokreni** za pokretanje modela i stvaranje prijedloga.

1. To može potrajati nekoliko minuta, ovisno o broju profila klijenata i odabranim aktivnostima. 

Nakon stvaranja prijedloga možete ih filtrirati prema dimenziji ili vrijednosti koja vas najviše zanima. 

## <a name="view-details-of-a-suggested-segment"></a>Prikaz pojedinosti o predloženom segmentu

Kada se stvore prijedlozi, pronaći ćete ih na popisu **Segmenti** > **Prijedlozi (pretpregled)** u odjeljku **Prijedlozi na temelju aktivnosti**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Prošireno bočno okno s detaljnim podacima predloženog segmenta.":::

Odaberite **Prikaži prijedlog** na predloženom segmentu za pregled pojedinosti tog segmenta. Bočno okno pruža pojedinosti poput opsega svake dimenzije u usporedbi s ciljnom skupinom. Također naglašava broj potencijalnih članova u segmentu i odgovarajući postotak ukupnog broja klijenata. Ako želite zadržati prijedlog kao segment, odaberite **Stvori segment**.    

## <a name="save-a-suggestion-as-a-segment"></a>Spremanje prijedloga kao segmenta

1. Idite u odjeljak **Segmenti** > **Prijedlozi (pretpregled)**.

1. Odaberite segment koji želite spremiti. 

1. U bočnom oknu odaberite **Stvori segment**. 

1. Nakon spremanja segmenta, prikazat će se na popisu segmenata na kartici **Svi segmenti**. Sad se može [osvježiti ili izbrisati kao i bilo koji drugi segment](segments.md). Ne možete uređivati pojedinosti segmenta. Međutim, možete promijeniti ulazne kriterije za prijedloge i stvarati različite prijedloge.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Osvježavanje ili uređivanje skupa prijedloga

1. Idite na **Segmenti** > **Prijedlozi (pretpregled)** i potražite segment u odjeljku **Prijedlozi na temelju aktivnosti**.

1. Odaberite **Osvježavanje prijedloga** za osvježavanje prijedloga uz zadržavanje konfiguriranih atributa. Ili odaberite **Uredi prijedloge** za izmjenu konfiguriranih atributa. Sustav će ponoviti postupak, stvoriti prijedloge segmenata na temelju najnovijih podataka i zamijeniti trenutne prijedloge.

[!INCLUDE [footer-include](includes/footer-banner.md)]
