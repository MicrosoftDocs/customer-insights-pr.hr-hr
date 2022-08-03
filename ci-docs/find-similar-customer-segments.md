---
title: Pronalaženje sličnih korisnika pomoću umjetne inteligencije (pretpregled) (sadrži videozapis)
description: Pronađite slične segmente klijenata koristeći se umjetnom inteligencijom.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170718"
---
# <a name="find-similar-customers-with-ai-preview"></a>Pronađite slične klijente pomoću umjetne inteligencije (pretpregleda)

Pronađite slične klijente svojoj bazi klijenata koristeći umjetnu inteligenciju. Za korištenje ove značajke potreban vam je barem jedan segment stvoren. Proširenje kriterija postojećeg segmenta pomaže u pronalaženju kupaca koji su slični tom segmentu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Pronađite slične kupce* koji koriste automatizirana sredstva za procjenu podataka i predviđanje na temelju tih podataka. Stoga ima mogućnost koristiti se kao metoda profiliranja jer je taj pojam definiran Općom uredbom o zaštiti podataka ("GDPR"). Klijentova upotreba ove značajke za obradu podataka može biti podložna OUZP-u ili drugim zakonima ili propisima. Odgovorni ste osigurati da je da vaše korištenje Dynamics 365 Customer Insights, uključujući predviđanja, u skladu sa svim primjenjivim zakonima i uredbama, uključujući zakone koji se odnose na privatnost, osobne podatke, biometrijske podatke, zaštitu podataka i povjerljivost komunikacija.

## <a name="find-similar-customers"></a>Pronalaženje sličnih klijenata

1. Otvorite **Segmenti** i odaberite segment na kojem želite temeljiti novi segment. To je vaš *izvorni segment*.

1. Odaberite **Pronađi slične klijente**.

1. Pregledajte predloženi naziv za svoj novi segment i promijenite ga ako je potrebno.

1. Po želji dodajte [oznake](work-with-tags-columns.md#manage-tags) novom segmentu.

1. Pregledajte polja koja definiraju vaš novi segment. Ova polja određuju osnovu na kojoj će sustav pokušati pronaći klijente slične vašem izvornom segmentu. Sustav prema zadanim postavkama odabire preporučena polja. Ako je potrebno, dodajte još polja.
  Polja koja mogu značajno smanjiti učinak modela automatski se isključuju:
  
   - Polja sa sljedećim vrstama podataka: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Polja s kardinalnošću (broj elemenata u polju) manjom od 2 ili većom od 30

1. Odaberite želite li u novi segment uključiti **sve kupce** osim izvornog segmenta ili samo kupce u drugom **segmentu**.

1. Sustav prema zadanim postavkama predlaže da se u izlaz uključi samo 20% ciljne publike. Uredite ovaj prag ako je potrebno. Povećanje praga smanjit će preciznost.

1. Uključite kupce u segment izvora tako da potvrdite okvir Uključi članove iz izvornog **segmenta uz kupce sa sličnim atributima**.

1. Odaberite **Pokreni** pri dnu stranice da biste započeli [zadatak](#about-similarity-scores) binarne klasifikacije (metoda Strojno učenje) koji analizira skup podataka.

## <a name="view-the-similar-segment"></a>Prikaz sličnog segmenta

Nakon obrade sličnog segmenta pronaći ćete novi segment naveden na **stranici Segmenti** s vrstom **Proširenje**.

Odaberite **Prikaz** da biste vidjeli raspodjelu rezultata po [rezultatima](#about-similarity-scores) sličnosti i vrijednostima rezultata sličnosti u pretpregledu **članova segmenta**.

:::image type="content" source="media/expanded-segment.png" alt-text="Segment sa sličnim klijentima.":::

## <a name="manage-a-similar-segment"></a>Upravljanje sličnim segmentom

[Radite sa sličnim segmentom i upravljajte njime](segments.md#manage-existing-segments) kao i s drugim segmentima. Na primjer, izvezite segment ili izradite mjeru.

Uredite, osvježite, preimenujte, preuzmite i izbrišite sličan segment. Uređivanje sličnog segmenta ponovno obrađuje vaše podatke. Prethodno stvoreni segment ažurira se osvježenim podacima.

## <a name="about-similarity-scores"></a>O ocjenama sličnosti

Model strojnog učenja binarne klasifikacije dodjeljuje ocjene klijentima u sličnom segmentu. Ocjena se temelji na sličnosti s klijentima u izvornom segmentu.

- Ocjene sličnosti manje od 0,55 su klijenti koje je sustav klasificirao kao *neslične* klijentima u izvornom segmentu
- Ocjene sličnosti između 0,55 i 0,7 klasificiraju se kao *donekle slični*
- Ocjene sličnosti između 0,7 i 0,85 klasificiraju se kao *slični*
- Ocjene sličnosti između 0,85 i 1 klijenti su koje je sustav klasificirao kao *vrlo slične*

Klijenti s ocjenama sličnosti manjim od 0,4 ne uvrštavaju se u izlaz modela. Sustav ih ne smatra dovoljno sličnim izvornom segmentu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
