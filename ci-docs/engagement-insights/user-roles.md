---
title: Uloge i dozvole
description: Pregled dostupnih uloga i dozvola za članove radnog prostora.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645528"
---
# <a name="roles-and-permissions"></a>Uloge i dozvole

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Radni prostor mjesto je za pohranu i upravljanje događajima i izvješćima. Dodatne informacije potražite u odjeljku [Stvaranje radnog prostora i dodavanje članova](create-workspace.md). 

Radni prostor može uključivati sljedeće uloge i dozvole:

- Uloge *Član* su korisnici koji mogu pristupiti radnom prostoru. Možete svojem radnom prostoru dodijeliti članove i definirati njihove uloge i dozvole. 
- Uloge *Administrator* upravljaju radnim prostorima i okruženjima te konfiguriraju uvide u angažman za ostale korisnike. 
- Uloge *Suradnik* usmjerene su na analitičare koji ne moraju konfigurirati uvide u angažman, nego žele stvoriti vlastita izvješća, kanale ili segmente.

## <a name="permissions"></a>Dopuštenja
  
Sljedeća tablica identificira dozvole za svaku ulogu. 

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
