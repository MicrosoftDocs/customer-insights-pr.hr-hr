---
title: Početna stranica u uvidima u ciljnu skupinu
description: Počnite istraživati aplikaciju na početnoj stranici.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405324"
---
# <a name="create-a-new-environment"></a>Stvorite novo okruženje

## <a name="create-a-trial-environment"></a>Stvaranje novog okruženja

Možete se prijaviti za probno razdoblje na [stranici za prijavu za probnu razdoblje](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Probna razdoblja ističu nakon 30 dana.

1. Odaberite mogućnost **Prijavi se za besplatno probno razdoblje** i odaberite **Prijavi se odmah**.

1. Navedite svoju poslovnu ili školsku adresu e-pošte, recite nam više o sebi i odaberite **Dalje**.

1. Navedite **Naziv** za svoje novo okruženje. 

1. Odaberite vrstu probne verzije.

1. Odaberite **Regiju** za svoje okruženje.

1. Neobvezno, za administratore tvrtke ili ustanove sustava Dynamics 365: Odaberite **Napredne postavke** i navedite URL-adresu svoje tvrtke ili ustanove za uporabu značajki predviđanja poput gubitka klijenta.

1. Kliknite **Stvori**. 

Nakon stvaranja okruženja vidjet ćete **Pokazno** okruženje koje vam omogućuje istraživanje aplikacije s fiktivnim podacima. Možete promijeniti uzorke podataka kako bi pristajali vašoj djelatnosti. Odaberite ikonu **Postavke** u zaglavlju i zatim **Postavke probne verzije**. Uz to možete promijeniti vizualnu temu. 

[Prijeđite na okruženje](#change-between-environments) koje ste stvorili tijekom postupka registracije kako biste radili s vlastitim podacima.

## <a name="create-a-new-production-or-sandbox-environment"></a>Stvorite novo okruženje za proizvodnju ili testiranje

U svom okruženju odaberite ikonu **Postavke** u zaglavlju i zatim **Novo okruženje**.

Slijedite korake kao da [stvarate okruženje probne verzije](#create-a-trial-environment). Pri odabiru mogućnosti **Napredne postavke** dobivate dodatnu mogućnost za pohranu podataka u vlastitom rješenju Azure Data Lake. Navedite naziv i ključ računa kako biste uspostavili vezu s vašim rješenjem Azure Data Lake. Podaci se prema zadanim postavkama pohranjuju u rješenju Data Lake kojim upravlja aplikacija Customer Insights.

> [!IMPORTANT]
> Pohranjivanjem podataka u svoju aplikaciju Azure Data Lake Storage slažete se s prijenosom podataka na odgovarajuću geografsku lokaciju za taj račun za pohranu Azure, a one se može razlikovati od lokacije za pohranu podataka u aplikaciji Dynamics 365 Customer Insights. [Saznajte više u Microsoftom centru za pouzdanost.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Istraživanje početne stranice

Možete [pristupiti okruženju Customer Insights](https://home.ci.ai.dynamics.com/) na sljedećem URL-u: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Početna** stranica prikazuje pregled vaše baze klijenata i osnovne mjerne podatke za praćenje stanja vašeg poslovanja.

> [!div class="mx-imgBorder"] 
> ![Uvidi na početnoj stranici](media/home-page-insights.png "Uvidi na početnoj stranici")

u odjeljku **Najnoviji segmenti** prikazuju se grupe klijenata na temelju demografskih, bihevioralnih ili transakcijskih atributa koje ste definirali. [Stvaranje segmenata](segments.md) pomaže vam da bolje ciljate svoje poslovne aktivnosti.

**Najnoviji mjerni podaci** prikazuju pločice s [mjerilima](measures.md). Mjerila su ključni pokazatelji uspješnosti (KPI) koje ste definirali. Na primjer, prosječna vjerojatnost gubitka klijenata ili prosječna internetska potrošnja po klijentu.

Odjeljak **Najnovija obogaćenja** navodi rezultate nedavno završenih ciklusa obogaćivanja. Obogaćenja dodaju informacije o vašoj bazi klijenata. Na primjer, razumijevanjem interesa i robnih marki za koje imaju sklonosti. Ove se informacije mogu otključati pomoću mogućnosti [obogaćenja](enrichment-microsoft-graph.md) nakon završetka faza [mapiranje](map-entities.md), [podudaranje](match-entities.md) i [spajanje](merge-entities.md).

## <a name="change-between-environments"></a>Prebacivanje između okruženja

Kada postavite i konfigurirate [izvore podataka](data-sources.md), htjet ćete se prebaciti iz demo okruženja u živo okruženje. Korištenje radnog okruženja omogućuje vam rad s vlastitim podacima o klijentima. Odaberite kontrolu **Okruženje** u gornjem desnom kutu stranice kako biste se prebacili između okruženja.

> [!div class="mx-imgBorder"] 
> ![Prebaci okruženje](media/home-page-environment-switcher.png "Prebaci okruženje")

Administratori mogu kreirati i upravljati s [više okruženja](manage-environments.md). Održavanje više okruženja može biti korisno ako, primjerice, vaša tvrtka ili ustanova djeluje na međunarodnoj razini pa trebate razdvajati podatke i uvide na različite načine.

## <a name="next-step"></a>Sljedeći korak

Da biste vidjeli svoje uvide na početnoj stranici, najprije morate [dodati izvore podataka](data-sources.md) i [ujediniti](data-unification.md) svoje podatke kako biste izgradili korisničke profile.
