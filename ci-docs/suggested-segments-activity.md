---
title: Predloženi segmenti na temelju aktivnosti (pretpregled)
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
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170580"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Predloženi segmenti na temelju aktivnosti (pretpregled)

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
Ako pružate javnu zdravstvenu skrb, a vaš je cilj smanjiti troškove za pojedine pacijente, mogli biste pokušati smanjiti ponavljajuće posjete pružanjem najbolje moguće skrbi u što manje posjeta. U ovom je slučaju vaš cilj održati učestalost posjeta niskom i minimizirati ponavljajuće troškove za pacijente. Ili možete identificirati segmente pacijenata koji imaju česte posjete i visoke troškove koji se ponavljaju i analizirati te slučajeve kako biste poboljšali liječenje pojedinca.

## <a name="required-data"></a>Obavezni podaci

Prijedlozi se stvaraju na temelju odabranih ulaznih podataka.

- Profili klijenata: svi klijenti ili članovi određenog segmenta.

- Vremensko razdoblje: prošli mjesec, prošla godina ili bilo koji prilagođeni vremenski okvir.

- Vrsta aktivnosti: kupnje, maloprodajne transakcije, mrežne transakcije, slučajevi korisničke podrške, pretplate itd.  

- Entitet u usluzi Customer Insights koji sadrži podatke o aktivnostima: entitet UnifiedActivity ili entitet za određenu aktivnost.

- Dimenzije koje treba uključiti: vrijeme, učestalost ili novčanu dimenziju, ovisno o vašim poslovnim zahtjevima.

## <a name="generate-suggested-segments"></a>Stvaranje predloženih segmenata

1. Otvorite **Segmenti** i odaberite karticu **Prijedlozi (pretpregled).**

1. Odaberite **Pronađi nove prijedloge** i odaberite **Prati ili predvidi ponašanje klijenata**. Odaberite **Start**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Prvi korak čarobnjaka za konfiguraciju za predloženi segment na temelju aktivnosti.":::

1. Navedite potrebne ulazne podatke i odaberite **Dalje**.

   - Odaberite klijente: uključite sve klijente ili određeni segment.
   - Odaberite aktivnost: odaberite vrstu aktivnosti i entitete koji opisuju aktivnost.
   - Postavke: postavite vremensko razdoblje koje treba uzeti u obzir, čimbenike za prijedloge i mapirajte atribute.

1. Pregledajte svoj unos i odaberite **Pokreni** za pokretanje modela i stvaranje prijedloga.

To može potrajati nekoliko minuta, ovisno o broju profila klijenata i odabranim aktivnostima.

Nakon stvaranja prijedloga možete ih filtrirati prema dimenziji ili vrijednosti koja vas najviše zanima.

## <a name="manage-suggested-segments"></a>Upravljanje predloženim segmentima

Otvorite **Segmenti** i odaberite karticu **Prijedlozi (pretpregled).** **U odjeljku Prijedlozi temeljeni na aktivnostima** odaberite predloženi segment za prikaz dostupnih akcija.

- **Pogledajte prijedlog** da se pojedinosti tog segmenta pogledaju kao opseg svake dimenzije u usporedbi s ciljnom skupinom. Također naglašava broj potencijalnih članova u segmentu i odgovarajući postotak ukupnog broja klijenata.
- **Kreirajte segment** da biste spremili predloženi kao segment. Prikazuje se na **kartici Svi segmenti** i može se [osvježiti ili izbrisati](segments.md). Ne možete uređivati pojedinosti segmenta. Međutim, možete promijeniti ulazne kriterije za prijedloge i stvarati različite prijedloge.
- **Uredite prijedloge** za izmjenu konfiguriranih atributa koji će zamijeniti trenutne prijedloge.
- **Osvježite prijedloge** da biste osvježili prijedloge uz zadržavanje konfiguriranih atributa.

[!INCLUDE [footer-include](includes/footer-banner.md)]
