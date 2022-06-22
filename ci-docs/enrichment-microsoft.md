---
title: Obogatite profile kupaca Microsoftovim robnim markama i interesima
description: Koristite Microsoftove vlasničke podatke da biste svoje korisničke podatke obogatili afinitetima i Udio prisutnosti.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953756"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Obogatite profile kupaca afinitetima i Udio prisutnosti (pregled)

Koristite Microsoftove vlasničke podatke za obogaćivanje korisničkih podataka afinitetima robne marke, afinitetima interesa i Udio prisutnosti (SoV). Ovi afiniteti i SoV temelje se na podacima ljudi s demografijom sličnim vašim kupcima. Te vam informacije pomažu da bolje razumijete i segmentirate svoje kupce na temelju njihovih afiniteta ili SoV-a prema određenim robnim markama i interesima.

## <a name="how-we-determine-affinities-and-sov"></a>Kako određujemo afinitete i SoV

Microsoftove podatke o internetskom pretraživanju koristimo za pronalaženje afiniteta i SoV-a za robne marke i interese u različitim demografskim segmentima (definiranim prema dobi, spolu ili lokaciji). Volumen internetskog pretraživanja za marku ili interes čini osnovu za određivanje afiniteta ili SoV-a. Međutim, svaka pruža drugačiju perspektivu razumijevanju vaših kupaca.

- Afinitet je komparativan u demografskim segmentima. Te podatke možete koristiti za identifikaciju demografskih segmenata koji imaju najveći afinitet prema određenoj robnoj marki ili interesu u usporedbi s drugim segmentima.

- Udio prisutnosti je komparativna u odabranim robnim markama ili interesima. Te podatke možete koristiti da biste utvrdili koja marka ili interes ima najveći udio glasa za određeni demografski segment u usporedbi s drugim robnim markama ili interesima koje ste odabrali.

## <a name="affinity-level-and-score"></a>Razina i ocjena afiniteta

Na svakom obogaćenom profilu klijenta pružamo dvije povezane vrijednosti: razinu afiniteta i ocjenu afiniteta. Te vam vrijednosti pomažu odrediti koliko je jak afinitet prema demografskom segmentu tog profila, prema marki ili interesu u usporedbi s ostalim demografskim segmentima.

*Razina afiniteta* sastoji se od četiri razine, a *ocjena afiniteta* izračunava se na skali od 100 točaka koja se mapira na razine afiniteta.

|Razina afiniteta |Ocjena afiniteta  |
|---------|---------|
|Vrlo visoko     | 85 – 100       |
|Visoko     | 70 – 84        |
|Srednji     | 35 – 69        |
|Nisko     | 1 – 34        |

Ovisno o granularnosti koju biste željeli za mjerenje afiniteta, možete koristiti razinu ili ocjenu afiniteta. Ocjena afiniteta daje vam precizniju kontrolu.

## <a name="share-of-voice-sov"></a>Udio prisutnosti (SoV)

Izračunavamo SoV na ljestvici od 100 točaka. Ukupni SoV u svim markama ili interesima za svaki obogaćeni profil kupaca dodaje do 100. Za razliku od afiniteta, SoV je u odnosu na marke i interese koje odaberete. Na primjer, Vrijednosti SoV za "Microsoft" mogu se razlikovati ako su odabrane robne marke ("Microsoft", "GitHub") u odnosu na ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Podržane zemlje/regije

Trenutno podržavamo sljedeće mogućnosti zemlje/regije: Australija, Kanada (engleski), Francuska, Njemačka, Ujedinjeno Kraljevstvo ili Sjedinjene Države (engleski).

## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. Idite na **Podaci** > **Obogaćivanje** i odaberite karticu **Pronađi**.

   - Da biste konfigurirali afinitete robne marke i obogaćivanje SoV-a, odaberite **Obogati moje podatke** na pločici **Robne marke**.

   - Da biste konfigurirali afinitete interesa i obogaćivanje SoV-a, odaberite **Obogati moje podatke** na pločici **Interesi**.

   > [!div class="mx-imgBorder"]
   > ![Pločice Robna marka i Interesi.](media/BrandsInterest-tile-Hub.png "pločice Robne marke i Interes")

1. Pregledajte pregled, a zatim odaberite **Dalje**.

1. Da biste promijenili državu ili regiju, pokraj stavke **Država/regija** odaberite **Promijeni**. **U oknu s postavkama** države/regije odaberite podržanu državu/regiju [...](#supported-countriesregions), a zatim **Primijeni**.

   > [!NOTE]
   > Kada odabirete vlastite marke, sustav pruža prijedloge na temelju odabrane države ili regije. Kada odabirete industriju, dobit ćete najrelevantnije marke ili interese na temelju odabrane države ili regije.

1. Odaberite do pet robnih marki ili interesa pomoću jedne ili obje ove mogućnosti:

   - **Djelatnot** : Na padajućem popisu odaberite svoju djelatnost, a zatim odaberite vodeće marke ili interese za tu djelatnost.
   - **Odaberite vlastito**: Unesite marku ili interes koji su relevantni za vašu tvrtku ili ustanovu, a zatim odaberite među odgovarajućim prijedlozima. Ako nismo naveli robnu marku ili interes koji tražite, pošaljite nam povratne informacije putem veze **Predloži**.

1. Odaberite **Dalje** i pregledajte zadane postavke obogaćivanja i po potrebi ih ažurirajte.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Snimka zaslona prozora s preferencama obogaćivanja.":::

1. Odaberite **Dalje**.

1. **Odaberite customer skup podataka** i odaberite profil ili segment koji želite obogatiti podacima tvrtke Microsoft. Subjekt *Kupac* obogaćuje sve vaše profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Odaberite **Dalje**.

1. Mapirajte polja iz jedinstvenog entiteta klijenta u Microsoftove podatke.

   > [!NOTE]
   > Potrebni su barem atributi Datuma rođenja ili spola. Potrebna je država/regija i barem grad (i država/pokrajina) ili poštanski broj. Preporučujemo da se datum rođenja pretvori u dateTime vrstu tijekom gutanja podataka. Alternativno, to može biti niz u [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formatu "yyyy-MM-dd" ili "yyyy-MM-ddTHH: mm: ss".

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja.

1. Navedite naziv za obogaćivanje. Automatski se odabire **naziv** izlaznog entiteta.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stranica za pregled i imenovanje interesa.":::

1. Odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.

1. Odaberite **Pokreni** da biste pokrenuli postupak obogaćivanja ili zatvorili da biste se vratili na **stranicu Obogaćivanje**.

   Kada obogaćujemo profile, obogatit ćemo sve profile kupaca za koje dobivamo podatke za odabrane marke i interese, uključujući profile koji nisu u odabranoj državi ili regiji. Na primjer, ako ste odabrali Njemačku, obogatit ćemo profile koji se nalaze u Sjedinjenim Državama ako imamo dostupne podatke za odabrane brendove i interese u SAD-u.

## <a name="enrichment-results"></a>Rezultati obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Pretpregled rezultata nakon pokretanja postupka obogaćivanja.":::

Rezultati uključuju grafikone **na razini** afiniteta ili **Udio prisutnosti**.

Subjekti stvoreni iz obogaćivanja navedeni su u **grupi Obogaćivanje** u **podatkovnim** > **entitetima**. Obogaćeni podaci za robne marke idu **brandAffinityFromMicrosoft** i **BrandShareOfVoiceFromMicrosoft** entitetima. Podaci za interese nalaze se u **subjektima InterestAffinityFromMicrosoft** i **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Prikaz podataka o obogaćivanju na kartici klijenta

Marka i interes SoV također se mogu vidjeti na pojedinačnim karticama kupaca. Idite na **Klijenti** i odaberite profil klijenta. Na kartici kupca pronaći ćete grafikone za robnu marku ili interes SoV na temelju osoba u demografskom profilu tog kupca.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica klijenta s obogaćenim podacima.":::

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
