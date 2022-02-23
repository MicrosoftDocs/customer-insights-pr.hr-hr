---
title: Pronalaženje sličnih korisnika pomoću AI-ja (sadrži videozapis)
description: Pronađite slične segmente klijenata koristeći se umjetnom inteligencijom.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: de337ae989558c81fff25a6ff7cca01890ed306b
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934831"
---
# <a name="similar-customers-preview"></a>Slični klijenti (pretpregled)

Ova značajka omogućuje vam pronaći klijente u svojoj bazi klijenata koristeći se umjetnom inteligencijom. Za upotrebu ove značajke morate imati stvoren barem jedan segment. Proširenje kriterija postojećeg segmenta pomaže u pronalaženju klijenata koji su slični tom segmentu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Nalaženje sličnih klijenata* koristi se automatiziranim sredstvima za procjenu podataka i daje predviđanja na temelju tih podataka, pa se stoga može koristiti kao metoda profiliranja, jer je taj pojam definiran Općom uredbom o zaštiti podataka („GDPR”). Klijentova upotreba ove značajke za obradu podataka može biti podložna OUZP-u ili drugim zakonima ili propisima. Odgovorni ste osigurati da je da vaše korištenje Dynamics 365 Customer Insights, uključujući predviđanja, u skladu sa svim primjenjivim zakonima i uredbama, uključujući zakone koji se odnose na privatnost, osobne podatke, biometrijske podatke, zaštitu podataka i povjerljivost komunikacija.

## <a name="finding-similar-customers"></a>Nalaženje sličnih klijenata

1. U uvidima u ciljnu skupinu idite na **Segmenti** i odaberite segment na kojem želite temeljiti svoj novi segment. To je vaš *izvorni segment*.

1. Na akcijskoj traci odaberite **Nalaženje sličnih klijenata**.

1. Pregledajte predloženi naziv za svoj novi segment i promijenite ga ako je potrebno.

1. Pregledajte polja koja definiraju vaš novi segment. Ova polja određuju osnovu na kojoj će sustav pokušati pronaći klijente slične vašem izvornom segmentu. Sustav će prema zadanim postavkama odabrati preporučena polja.
  Polja koja mogu značajno smanjiti učinak modela automatski se isključuju:
  
   - Polja sa sljedećim vrstama podataka: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Polja s kardinalnošću (broj elemenata u polju) manjom od 2 ili većom od 30

1. Odaberite želite li da u novom segmentu budu uključeni **Svi klijenti** ili samo klijenti za **Specifični postojeći segment**.

1. Isključite klijente iz svog izvornog segmenta odabirom potvrdnog okvira **Isključi sve iz izvornog segmenta**.

1. Sustav prema zadanim postavkama predlaže da se u izlaz uključi samo 20% ciljne publike. Uredite ovaj prag ako je potrebno. Povećanje praga smanjit će preciznost.

1. Odaberite **Pokreni** pri dnu stranice kako biste pokrenuli zadatak binarne klasifikacije (metoda strojnog učenja) koji analizira skup podataka.

## <a name="view-the-similar-segment"></a>Prikaz sličnog segmenta

Nakon obrade sličnog segmenta, novi ćete segment pronaći na stranici **Segmenti**.

> [!div class="mx-imgBorder"]
> ![Segment sa sličnim klijentima.](media/expanded-segment.png "Segment sa sličnim klijentima")

Odaberite **Prikaz** na akcijskoj traci kako bi se otvorile pojedinosti segmenta. Ovaj prikaz sadrži informacije o raspodjeli rezultata po različitim [ocjenama sličnosti](#about-similarity-scores). Vrijednosti ocjena sličnosti također ćete pronaći u **Pretpregled članova segmenta**.

## <a name="use-the-output-of-a-similar-segment"></a>Upotrijebite izlaz sličnog segmenta

Možete [raditi s izlazom sličnog segmenta](segments.md) kao kod drugih segmenata. Na primjer, izvezite segment ili izradite mjeru.

## <a name="refresh-and-edit-a-similar-segment"></a>Osvježavanje i uređivanje sličnog segmenta

Da biste osvježili sličan segment, odaberite ga na stranici **Segmenti** i odaberite **Osvježi** u akcijskoj traci.

Uređivanjem sličnog segmenta vaši će se podaci ponovno obraditi. Prethodno stvoreni segment ažurira se osvježenim podacima.    
Da biste uredili sličan segment, odaberite ga na stranici **Segmenti** i odaberite **Uredi** u akcijskoj traci. Primijenite promjene i odaberite **Pokreni** da biste započeli obradu.

## <a name="delete-a-similar-segment"></a>Brisanje sličnog segmenta

Odaberite segment na stranici **Segmenti** i odaberite **Izbriši** u akcijskoj traci. Zatim potvrdite brisanje.

## <a name="about-similarity-scores"></a>O ocjenama sličnosti

Model strojnog učenja binarne klasifikacije dodjeljuje ocjene klijentima u sličnom segmentu. Ocjena se temelji na sličnosti s klijentima u izvornom segmentu.

- Ocjene sličnosti manje od 0,55 su klijenti koje je sustav klasificirao kao *neslične* klijentima u izvornom segmentu
- Ocjene sličnosti između 0,55 i 0,7 klasificiraju se kao *donekle slični*
- Ocjene sličnosti između 0,7 i 0,85 klasificiraju se kao *slični*
- Ocjene sličnosti između 0,85 i 1 klijenti su koje je sustav klasificirao kao *vrlo slične*

Klijenti s ocjenama sličnosti manjim od 0,4 ne uvrštavaju se u izlaz modela. Sustav ih ne smatra dovoljno sličnim izvornom segmentu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]