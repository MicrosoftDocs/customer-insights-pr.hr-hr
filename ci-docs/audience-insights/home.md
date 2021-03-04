---
title: Početna stranica u uvidima u ciljnu skupinu
description: Počnite istraživati aplikaciju na početnoj stranici.
ms.date: 01/07/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7cc767f5d80b213a4c1bb5b2e8062bd44c15279b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477032"
---
# <a name="create-a-new-environment"></a>Stvorite novo okruženje

## <a name="create-a-trial-environment"></a>Stvaranje novog okruženja

Možete se prijaviti za probno razdoblje na [stranici za prijavu za probnu razdoblje](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Probna razdoblja ističu nakon 30 dana.

1. Odaberite mogućnost **Prijavi se za besplatno probno razdoblje** i odaberite **Prijavi se odmah**.

1. Navedite svoju poslovnu ili školsku adresu e-pošte, recite nam više o sebi i odaberite **Dalje**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dijaloški okvir za prijavu za probnu verziju instance":::

1. Navedite **Naziv** za svoje novo okruženje. 

1. Odaberite vrstu probne verzije.

1. Odaberite **Regiju** za svoje okruženje.

1. Neobvezno, za administratore tvrtke ili ustanove sustava Dynamics 365: Odaberite **Napredne postavke** i navedite URL-adresu svoje tvrtke ili ustanove za uporabu značajki predviđanja poput gubitka klijenta.

1. Kliknite **Stvori**. 

Nakon stvaranja okruženja vidjet ćete **Pokazno** okruženje koje vam omogućuje istraživanje aplikacije s fiktivnim podacima. Možete promijeniti uzorke podataka kako bi pristajali vašoj djelatnosti. Odaberite ikonu **Postavke** u zaglavlju i zatim **Postavke probne verzije**. Uz to možete promijeniti vizualnu temu. 

[Prijeđite na okruženje](#switch-environments) koje ste stvorili tijekom postupka registracije kako biste radili s vlastitim podacima.

## <a name="create-a-new-production-or-sandbox-environment"></a>Stvorite novo okruženje za proizvodnju ili testiranje

U svojem okruženju odaberite birač **Okruženja** u zaglavlju aplikacije i odaberite **Novo**.

Slijedite korake kao da [stvarate okruženje probne verzije](#create-a-trial-environment). Podaci se prema zadanim postavkama pohranjuju u rješenju Data Lake kojim upravlja aplikacija Customer Insights. Pri odabiru mogućnosti **Napredne postavke** dobivate dodatnu mogućnost za pohranu podataka u vlastitom rješenju Azure Data Lake. Navedite naziv i ključ računa kako biste uspostavili vezu s vašim rješenjem Azure Data Lake. 

> [!IMPORTANT]
> Pohranjivanjem podataka u svoju aplikaciju Azure Data Lake Storage slažete se s prijenosom podataka na odgovarajuću geografsku lokaciju za taj račun za pohranu Azure, a one se može razlikovati od lokacije za pohranu podataka u aplikaciji Dynamics 365 Customer Insights. [Saznajte više u Microsoftom centru za pouzdanost.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Istraživanje početne stranice

Možete [pristupiti uvidima u ciljnu skupinu iz Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) na sljedećem URL-u: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Početna** stranica prikazuje pregled segmenata, mjera i podataka o obogaćivanju (ako su konfigurirani) nakon dovršavanja faza [mapiranja](map-entities.md), [podudaranja](match-entities.md) i [spajanja](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Uvidi na početnoj stranici](media/home-page-insights.png "Uvidi na početnoj stranici")

u odjeljku **Najnoviji segmenti** prikazuju se grupe klijenata na temelju demografskih, bihevioralnih ili transakcijskih atributa koje ste definirali. [Stvaranje segmenata](segments.md) pomaže vam da grupirate svoju bazu klijenata i bolje usmjerite svoje poslovne aktivnosti.

**Najnovije mjere** pokazuje pločice s [ključnim pokazateljima uspješnosti (KPI)](measures.md) koje ste definirali. Na primjer, prosječna vjerojatnost gubitka klijenata ili prosječna mrežna potrošnja po klijentu.

Odjeljak **Najnovija obogaćenja** navodi rezultate nedavno završenih ciklusa obogaćivanja. [Obogaćivanja](enrichment-hub.md) dodaju informacije o vašoj bazi klijenata. Na primjer, razumijevanjem interesa i robnih marki za koje imaju sklonosti.

## <a name="switch-environments"></a>Prebacivanje okruženja

Odaberite kontrolu **Okruženje** u gornjem desnom kutu stranice kako biste se prebacili između okruženja.

> [!div class="mx-imgBorder"] 
> ![Prebaci okruženje](media/home-page-environment-switcher.png "Prebaci okruženje")

Administratori mogu kreirati i upravljati s [više okruženja](manage-environments.md). Održavanje više okruženja može biti korisno ako, primjerice, vaša tvrtka ili ustanova djeluje na međunarodnoj razini pa trebate razdvajati podatke i uvide na različite načine.

## <a name="next-step"></a>Sljedeći korak

Da biste vidjeli svoje uvide na početnoj stranici, najprije morate [dodati izvore podataka](data-sources.md) i [ujediniti](data-unification.md) svoje podatke kako biste izgradili korisničke profile.


[!INCLUDE[footer-include](../includes/footer-banner.md)]