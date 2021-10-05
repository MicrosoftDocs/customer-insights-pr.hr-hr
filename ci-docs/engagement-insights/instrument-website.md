---
title: Dodavanje koda na svoje web-mjesto
description: Kako dodati isječak koda za bilježenje događaja Dynamics 365 Customer Insights na svojem web-mjestu.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558784"
---
# <a name="install-the-web-sdk-on-a-website"></a>Instaliranje web-SDK-a na web-mjestu

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovaj članak opisuje kako administrator instalira paket alata za razvoj web-softvera (SDK) na web-mjesto. Događaji će se ppčeti prikazivati u radnom prostoru ubrzo nakon instrumentacije web-stranice. Za više informacija pogledajte [Upravljanje radnim prostorima i okruženjima](manage-environments-workspaces.md). Da biste bilježili događaje u mobilnim aplikacijama, pogledajte [Pregled resursa za programere](developer-resources.md).


### <a name="prerequisites"></a>Preduvjeti

* Morate imati administratorske dozvole za radni prostor za pohranu podataka.
* Da biste slali podatke o aktivnostima, vaše web-mjesto ili projekt moraju biti udomaćeni na mreži. Podatke poslane iz lokalne datoteke poslužitelj neće prihvatiti.


## <a name="add-web-sdk-to-your-website"></a>Dodavanje web-SDK-a na svoje web-mjesto

Idite na **Admin** > **Radni prostor** i zatim odaberite **Vodič za instalaciju**. Postoje dvije mogućnosti instaliranje web-SDK-a: Prvi je korištenje veze za preuzimanje, a drugi je instaliranje paketa upravitelja paketa čvorova (NPM).

### <a name="option-1-using-the-download-link"></a>1. opcija: Upotreba veze za preuzimanje

1. Odaberite **Kopiraj kod** da biste kopirali isječak koda. Prema zadanim postavkama ključ za unos za vaš radni prostor ugrađen je u isječak koda.
  :::image type="content" source="media/copy-code.png" alt-text="Snimka zaslona stranice isječka koda.":::

1. Dodajte kopirani kôd na svoju web-lokaciju, blizu <head> oznake i prije bilo koje druge skripte ili CSS oznake.
1. Objavite svoje ažurirano web-mjesto i pričekajte nekoliko minuta kako biste snimili dolazni web-promet.
1. Da biste vidjeli svoje podatke, odaberite svoj radni prostor iz prebacivača radnog prostora u navigacijskom oknu. Zatim odaberite jedno od izvješća u odjeljku **Otkrij**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>2. opcija: Upotreba NPM paketa (preporučuje se za web-aplikacije na tememlju programskog jezika JavaScript)

1. Otvorite našu [NPM web-stranicu](https://www.npmjs.com/package/engagementinsights-web) i slijedite upute za instaliranje i postavljanje NPM paketa za web-SDK.
1. Objavite svoje ažurirano web-mjesto i pričekajte nekoliko minuta kako biste snimili dolazni web-promet.
1. Da biste vidjeli svoje podatke, odaberite svoj radni prostor iz prebacivača radnog prostora u navigacijskom oknu. Zatim odaberite jedno od izvješća u odjeljku **Otkrij**.

## <a name="configuration-options"></a>Mogućnosti konfiguracije

U isječku koda možete promijeniti sljedeće mogućnosti konfiguracije:

- **ingestionKey**: Ključ za unos koji se koristi za slanje događaja na vaš radni prostor. Možete promijeniti ključ za unos da biste slali događaje u drugi radni prostor. Ključ za unos jedinstven je za svaki radni prostor.
- **autoCapture**: Određuje jesu li prikazi stranice i interakcije s web-mjestom zabilježeni. Ima dvije mogućnosti:
    - **prikaz**: Postavite na *true* za snimanje prikaza stranice. Prikazi stranice bilježe se kao *Prikaz* [događaja](glossary.md#event), vrsta [osnovnog događaja](glossary.md#base-event).
    - **klik**: Postavite na *true* za bilježenje interakcija posjetitelja na web-mjestu. Interakcije se bilježe kao *Događaji* [radnji](glossary.md#event), vrsta [osnovnog događaja](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
