---
title: Uvidi u segmente (pretpregled)
description: Steknite uvid u postojeće segmente da biste vidjeli razlike i zajedničke karakteristike.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170994"
---
# <a name="segment-insights-preview"></a>Uvidi u segmente (pretpregled)

Otkrijte dodatne informacije i uvide o svojim postojećim segmentima. Otkrijte što razlikuje dva segmenta ili što imaju zajedničko.

## <a name="segment-overlap"></a>Preklapanje segmenata

Analiza preklapanja segmenata pokazuje tko su i koliko ima klijenata zajedničkih za dva ili više segmenta. Na primjer, kako se neki segment čestih klijenata preklapa sa segmentom koji sadrži klijente koji su zadovoljni vašom uslugom ili proizvodom.
Također, možete analizirati kako se preklapanje mijenja za određene atribute.

### <a name="run-an-overlap-analysis"></a>Pokretanje analize preklapanja

1. Idite na **Segmenti** i odaberite karticu **Uvidi (pretpregled)**.

1. Odaberite **Novo** i odaberite opciju **Preklapanje** u oknu **Odabir vrste uvida**.

1. Odaberite segmente koji vas zanimaju i odaberite **Dalje**.

1. Također, možete odabrati jedno ili više polja koja vas zanimaju kako biste analizirali preklapanja za svaku moguću vrijednost polja i zatim odabrati **Dalje**.

1. Navedite naziv za analizu preklapanja, neobvezni zaslonski naziv i opis.

1. Odaberite **Spremi** kako biste započeli analizu. Analiza preklapanja bit će spremna kada se status promijeni s Osvježavanje na Uspješno.

### <a name="view-and-optimize-an-overlap-analysis"></a>Prikaz i optimiziranje analize preklapanja

1. Nakon dovršetka analize, pronađite detalje o ovom uvidu u **Segmenti** > **Uvidi (pretpregled)**.

   :::image type="content" source="media/segment-overlap.png" alt-text="Pojedinosti uvida u preklapanje segmenta.":::

1. Odaberite uvid da biste vidjeli rezultate analize:

   - Broj članova kod kojih se preklapaju segmenti odabrani za analizu.
   - Broj članova koji su uključeni u jedan od segmenata, ali ne i u ostale segmente.
   - Ako ste tijekom konfiguriranja analize preklapanja odabrali polja, naći ćete ih na odgovarajućim karticama. Pomoću padajućeg izbornika filtra možete odabrati bilo koju razinu atributa koja vas zanima, a tablica na dnu prikazat će odgovarajuće podatke.

## <a name="segment-differentiators"></a>Diferencijatori segmenta

Elementi razlikovanja segmenata pomažu vam otkriti po čemu se neki segment razlikuje od ostalih klijenata ili nekog drugog segmenta. Odaberite segment i sustav identificira atribute profila i mjere koje razlikuju odabrani segment.

### <a name="run-a-differentiator-analysis"></a>Pokretanje analize elemenata razlikovanja

1. Idite na **Segmenti** i odaberite karticu **Uvidi (pretpregled)**.

1. Odaberite **Novo** i odaberite **mogućnost Diferencijatori** u **oknu Odabir vrste uvida**.

1. Odaberite segment koji želite analizirati kao **Primarni segment** i odaberite **Dalje**.

1. Odaberite **Svi klijenti** ili **Sekundarni segment** za usporedbu vašeg primarnog segmenta i zatim odaberite **Dalje**.

1. Također, možete odabrati jedno ili više polja koja vas zanimaju da biste analizu usredotočili na određene atribute i zatim odaberite **Dalje**.

1. Navedite naziv za analizu diferencijatora, neobaveznu zaslonsko ime i opis.

1. Odaberite **Spremi** kako biste započeli analizu. Analiza diferencijatora spremna je kada se status promijeni iz Osvježavanje u Uspješno.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Prikaz i optimiziranje analize elemenata razlikovanja

1. Nakon završetka analize idite na **Segments** > **Insights (pregled)**.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Pojedinosti uvida u elemente razlikovanja segmenta.":::

1. Odaberite uvid da biste vidjeli rezultate analize. Analiza elemenata razlikovanja uključuje dvije kartice. Na kartici **Atributi** nalaze se atributi profila koji se smatraju elementima razlikovanja. Na kartici **Mjere** nalaze se elementi razlikovanja. Svaka kartica sadrži sljedeće detalje:

   - Rangirani popis elemenata razlikovanja, poredan po ocjeni razlike.
   - **Ocjena razlike** za svaki element razlikovanja. Ocjena razlike predstavlja stupanj razlike atributa između dva segmenta. Što je veća ocjena razlike, to se više atributi razlikuju između dva segmenta. Odaberite ocjenu kako bi se otvorilo okno **Ocjena razlike** s raspodjelom vrijednosti za taj atribut.

## <a name="manage-segment-insights"></a>Upravljanje uvidima u segmente

Idite na **Segments** > **Insights (pregled)** da biste vidjeli uvide u segmente i upravljali njima. Odaberite uvid u segmente da biste vidjeli dostupne akcije.

- **Prikaz** analize uvida
- **Uređivanje** uvida radi promjene njegovih svojstava
- **Osvježite** uvid da biste ponovno pokrenuli analizu
- **Preimenujte** uvid
- **Brisanje** uvida

[!INCLUDE [footer-include](includes/footer-banner.md)]
