---
title: Dodavanje koda na svoje web-mjesto
description: Kako dodati isječak koda za bilježenje događaja na svojem web-mjestu.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035085"
---
# <a name="install-the-code-snippet-on-a-website"></a>Instalacija isječka koda na web-mjestu

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovaj članak opisuje kako administrator instalira isječak koda na web-mjesto. Događaje ćete početi vidjeti u svojem radnom prostoru ubrzo nakon dodavanja skripte na svoje web-mjesto. Za više informacija pogledajte [Upravljanje radnim prostorima i okruženjima](manage-environments-workspaces.md). Da biste bilježili događaje u mobilnim aplikacijama, pogledajte [Pregled resursa za programere](developer-resources.md).


### <a name="prerequisites"></a>Preduvjeti

* Morate imati administratorske dozvole za radni prostor za pohranu podataka.
* Da biste slali podatke o aktivnostima, vaše web-mjesto ili projekt moraju biti udomaćeni na mreži. Podatke poslane iz lokalne datoteke poslužitelj neće prihvatiti.


## <a name="add-code-to-your-website"></a>Dodavanje koda na svoje web-mjesto
1.  Idite na **Admin** > **Radni prostor** i zatim odaberite **Vodič za instalaciju**.
1. Odaberite **Kopiraj kod** da biste kopirali isječak koda. Prema zadanim postavkama ključ za unos za vaš radni prostor ugrađen je u isječak koda.
:::image type="content" source="media/copy-code.png" alt-text="Snimka zaslona stranice isječka koda.":::
3. Dodajte kopirani isječak koda na svoje web-mjesto, blizu <head> oznake i prije bilo koje druge skripte ili CSS oznake.
4.  Objavite svoje ažurirano web-mjesto i pričekajte nekoliko minuta kako biste snimili dolazni web-promet.
5.  Da biste vidjeli svoje podatke, odaberite svoj radni prostor iz prebacivača radnog prostora u navigacijskom oknu. Zatim odaberite jedno od izvješća u odjeljku **Otkrij**.

## <a name="configuration-options"></a>Mogućnosti konfiguracije

U isječku koda možete promijeniti sljedeće mogućnosti konfiguracije:

- **ingestionKey**: Ključ za unos koji se koristi za slanje događaja na vaš radni prostor. Možete promijeniti ključ za unos da biste slali događaje u drugi radni prostor. Ključ za unos jedinstven je za svaki radni prostor. 
- **autoCapture**: Određuje jesu li prikazi stranice i interakcije s web-mjestom zabilježeni. Ima dvije mogućnosti:
    - **prikaz**: Postavite na *true* za snimanje prikaza stranice. Prikazi stranice bilježe se kao *Prikaz* [događaja](glossary.md#event), vrsta [osnovnog događaja](glossary.md#base-event).
    - **klik**: Postavite na *true* za bilježenje interakcija posjetitelja na web-mjestu. Interakcije se bilježe kao *Događaji* [radnji](glossary.md#event), vrsta [osnovnog događaja](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
