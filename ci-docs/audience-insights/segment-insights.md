---
title: Uvidi u segmente za postojeće segmente
description: Steknite uvid u postojeće segmente da biste vidjeli razlike i zajedničke karakteristike.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1f90b0d18331584fce306da38bd31faea93ef97e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732303"
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

Nakon dovršetka analize, pronađite detalje o ovom uvidu u **Segmenti** > **Uvidi (pretpregled)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Pojedinosti uvida u preklapanje segmenta.":::

Odaberite uvid da biste vidjeli rezultate analize:

- Broj članova kod kojih se preklapaju segmenti odabrani za analizu.
- Broj članova koji su uključeni u jedan od segmenata, ali ne i u ostale segmente.
- Ako ste tijekom konfiguriranja analize preklapanja odabrali polja, naći ćete ih na odgovarajućim karticama. Pomoću padajućeg izbornika filtra možete odabrati bilo koju razinu atributa koja vas zanima, a tablica na dnu prikazat će odgovarajuće podatke.

## <a name="segment-differentiators"></a>Diferencijatori segmenta

Elementi razlikovanja segmenata pomažu vam otkriti po čemu se neki segment razlikuje od ostalih klijenata ili nekog drugog segmenta. Trebate samo odabrati segment i sustav će prepoznati atribute profila i mjere koje razlikuju odabrani segment.

### <a name="run-a-differentiator-analysis"></a>Pokretanje analize elemenata razlikovanja

1. Idite na **Segmenti** i odaberite karticu **Uvidi (pretpregled)**.

1. Odaberite **Novo** i odaberite opciju **Preklapanje** u oknu **Odabir vrste uvida**.

1. Odaberite segment koji želite analizirati kao **Primarni segment** i odaberite **Dalje**.

1. Odaberite **Svi klijenti** ili **Sekundarni segment** za usporedbu vašeg primarnog segmenta i zatim odaberite **Dalje**.

1. Također, možete odabrati jedno ili više polja koja vas zanimaju da biste analizu usredotočili na određene atribute i zatim odaberite **Dalje**.

1. Navedite naziv za analizu preklapanja, neobvezni zaslonski naziv i opis.

1. Odaberite **Spremi** kako biste započeli analizu. Analiza preklapanja bit će spremna kada se status promijeni s Osvježavanje na Uspješno.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Prikaz i optimiziranje analize elemenata razlikovanja

Nakon dovršetka analize, pronađite detalje o ovom uvidu u **Segmenti** > **Uvidi (pretpregled)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Pojedinosti uvida u elemente razlikovanja segmenta.":::

Odaberite uvid da biste vidjeli rezultate analize. Analiza elemenata razlikovanja uključuje dvije kartice. Na kartici **Atributi** nalaze se atributi profila koji se smatraju elementima razlikovanja. Na kartici **Mjere** nalaze se elementi razlikovanja. Svaka kartica sadrži sljedeće detalje:

- Rangirani popis elemenata razlikovanja, poredan po ocjeni razlike.
- **Ocjena razlike** za svaki element razlikovanja. Ocjena razlike predstavlja stupanj razlike atributa između dva segmenta. Što je veća ocjena razlike, to se više atributi razlikuju između dva segmenta. Odaberite ocjenu kako bi se otvorilo okno **Ocjena razlike** s raspodjelom vrijednosti za taj atribut.

## <a name="manage-segment-insights"></a>Upravljanje uvidima u segmente

Sljedeće opcije s naredbene trake možete koristiti za svoje uvide:

- **Natrag** za vraćanje popisa uvida
- **Osvježi** za ponovno pokretanje analize
- **Izbriši** za uklanjanje ovog uvida


[!INCLUDE[footer-include](../includes/footer-banner.md)]
