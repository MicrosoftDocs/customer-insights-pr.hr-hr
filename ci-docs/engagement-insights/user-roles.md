---
title: Uloge i dozvole
description: Pregled dostupnih uloga i dozvola za članove radnog prostora.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036684"
---
# <a name="roles-and-permissions"></a>Uloge i dozvole

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Radni prostor način je za pohranu i upravljanje događajima i izvješćima. Član je korisnik koji može pristupiti radnom prostoru. Možete svojem radnom prostoru dodijeliti članove i definirati njihove uloge i dozvole. Uloge administratora upravljaju radnim prostorima i okruženjima te konfiguriraju uvide u angažman za ostale korisnike. Uloge suradnika namijenjene su analitičarima koji ne trebaju konfigurirati uvide u angažman, već žele stvarati vlastita izvješća, kanale ili segmente.

## <a name="permissions"></a>Dopuštenja
  
Sljedeći grafikon identificira dozvole za svaku ulogu. 

| Dozvola | Administrator okruženja | Administrator radnog prostora | Suradnik za okruženje | Suradnik za radni prostor | 
|--|--|--|--|--|
| Stvaranje okruženja (autor automatski postaje administrator okruženja) | X* | X* | X* | X* |  
| Konfiguriranje okruženja (članovi okruženja, brisanje okruženja) | X |  |  |  |  
| Stvaranje radnih prostora | X |  |  |  |  
| Konfiguriranje radnih prostora (članovi radnog prostora, brisanje radnog prostora) | X | X |  |  |  
| Konfiguriranje događaja i pročišćeni događaji | X | X | |  |  
| Pregledavanje događaja radnog prostora i pročišćenih događaja | X | X | |  |  
| Prikaz resursa radnog prostora (izvješća, segmenti i mjerni podaci)| X | X | X | X |  
| Stvaranje prilagođenih izvješća i kanala | X | X | X | X |  
| Stvaranje osnovnih mjernih podataka i dimenzija| X | X |  |  |  
| Stvaranje segmenata| X | X | X | X |  

*Može stvoriti samo probna okruženja u pretpregledu. 

## <a name="add-members"></a>Dodajte članove

Možete dodati i ukloniti članove iz radnih prostora i okruženja. Za više informacija pogledajte [Okruženja i radni prostori](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
