---
title: Predloženi segmenti na temelju mjera (pregled)
description: Neka vam strojno učenje pomogne da pronađete nove i zanimljive segmente na temelju atributa klijenata.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170948"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Predloženi segmenti na temelju mjera (pregled)

Otkrijte zanimljive segmente svojih klijenata uz pomoć modela umjetne inteligencije. Ova značajka koju pokreće strojno učenje predlaže segmente na temelju mjera ili atributa klijenata. To može pomoći poboljšati vaše ključne pokazatelje uspješnosti (KPI-jeve) ili bolje razumjeti utjecaj atributa u kontekstu drugih atributa.

> [!NOTE]
> Značajka predloženih segmenata koristi automatizirana sredstva za procjenu podataka i izradu predviđanja na temelju tih podataka. Stoga ima mogućnost koristiti se kao metoda profiliranja jer je taj pojam definiran Općom uredbom o zaštiti podataka ("GDPR"). Vaša upotreba ove značajke za obradu podataka može podlijegati GDPR-u ili drugim zakonima ili propisima. Odgovorni ste osigurati da je da vaše korištenje servisa Dynamics 365 Customer Insights, uključujući ovu značajku, u skladu sa svim primjenjivim zakonima i uredbama, uključujući zakone koji se odnose na privatnost, osobne podatke, biometrijske podatke, zaštitu podataka i povjerljivost komunikacija.

:::image type="content" source="media/suggested-segments.png" alt-text="Stranica predloženih segmenata koja prikazuje pojedinosti prijedloga u bočnom oknu.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Predloženi segmenti za poboljšanje vaših KPI-ja

Ako koristite [mjere stvorene](measures.md) za praćenje KPI-ja, stvorite segmente da biste vidjeli utjecaje na KPI. Te podatke možete koristiti za pokretanje visoko ciljane kampanje.

Na primjer, pratite mjeru koja se zove *Ukupnotrošenjepoklijentu*. Kao tvrtka želite vidjeti da ovaj broj raste. Odabirom mjere kao primarnog atributa odaberite atribute koje želite procijeniti za utjecaj. Recimo *razina članstva*, *razdoblje članstva* i *zanimanje*. Customer Insights tada može predložiti segment koji vam govori koji su najveći utjecaji te mjere. Na primjer, *Računovođe* koje su *Zlatni* članovi i koje posluju s vama *najmanje pet godina* su najveći utjecatelji na *Ukupnotrošenjepoklijentu*. Za svaki prijedlog dobit ćete procijenjenu veličinu segmenta. Te podatke možete koristiti za izradu kampanja za ciljanu publiku.

## <a name="understand-what-influences-a-customer-attribute"></a>Objašnjenje što utječe na atribut klijenta

Možete odabrati atribut klijenta umjesto mjere kao primarnog atributa. Na temelju vašeg odabira utjecaja na atribute, model umjetne inteligencije stvara niz prijedloga koji pokazuju kako odabrani atributi utječu na primarni atribut.

Na primjer, odabrali ste *Član programa Rewards (Da/Ne)* kao primarni atribut. *Stalno mjesto*, *Zanimanje* i *Broj potvrda o prijavi problema službi za podršku* postavljeni su kao drugi utjecajni atributi. Model umjetne inteligencije mogao bi predložiti segmente koji ukazuju na to da su uglavnom IT profesionalci sa stalnim mjestom duljim od dvije godine članovi programa Rewards. Drugi prijedlog mogao bi istaknuti da su računovođe sa stalnim mjestom duljim od jedne godine i s manje od tri potvrde o prijavi problema službi za podršku članovi programa Rewards.

## <a name="artificial-intelligence-usage"></a>Upotreba umjetne inteligencije

Algoritam stabla odluke predlaže zanimljive segmente koristeći primarni atribut i utjecajne atribute. Prijedlozi se temelje na pravilima ili obrascima koje je prikupio algoritam umjetne inteligencije. Kao prijedlozi su prikazani samo segmenti koji se značajno razlikuju od prosječne populacije. Usporedba s prosječnom populacijom temelji se na odabranoj mjeri ili primarnom atributu.

### <a name="responsible-ai"></a>Odgovorna umjetna inteligencija

Pomoću predloženih segmenata odabirete atribute za kreiranje novih segmenata i obradu odabranih podataka. Pri odabiru atributa, uključujući osjetljive atribute poput rase, seksualne orijentacije ili spola, morate osigurati da možete i trebate obrađivati te podatke. Odgovorni ste za poštivanje svih zakona primjenjivih na vašu tvrtku ili ustanovu i pridržavanje načela i pravila privatnosti vaše tvrtke ili ustanove.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Različiti rezultati za primarne atribute s kategorijskim i numeričkim vrijednostima

Prijedlozi segmenata će se razlikovati ovisno o tome jeste li odabrali numerički ili kategorijski atribut kao primarni atribut. Vrijednosti u kategorijskom atributu sadrže dvije ili više kategorija ili vrsta. Numerički atribut sadrži kvantitativne podatke i s njima je povezan osjećaj mjerenja.

S numeričkim atributom kao što je *godišnji prihod* ili *razdoblje članstva* kao primarnim atributom, sustav predlaže segmente koji imaju veću ili manju prosječnu vrijednost numeričkog atributa u usporedbi sa svim klijentima.

Kategorijski atribut kao što je *zadovoljstvo klijenata* kao primarni atribut rezultira predloženim segmentima koji imaju veći ili manji postotak klijenata koji pripadaju određenoj kategoriji u usporedbi s postotkom svih klijenata koji pripadaju istoj kategoriji. Na primjer, *zadovoljstvo klijenata* je odabrano kao primarni atribut i sastoji se od tri kategorije (*Nisko*, *Srednje* i *Visoko*). Za svaku kategoriju predložit će se segmenti koji imaju veći ili niži postotak kupaca koji pripadaju toj kategoriji u usporedbi s udjelom svih kupaca u istoj kategoriji. Ako 22 % svih klijenata ima *Visoko* zadovoljstvo, onda će samo segmenti koji imaju veći ili manji udio klijenata sa zadovoljstvom *Visoko* u usporedbi s 22 % biti predloženi za tu kategoriju. Slično tome, predložit će se segmenti za svaku od ostalih kategorija (*Nisko* i *Srednje*) ako su statistički značajni.

> [!NOTE]
> Trenutno podržavamo samo primarne kategorijske atribute koji imaju do 10 kategorija. Ako želite vidjeti prijedloge segmenata na temelju primarnog atributa s više od 10 kategorija, preporučujemo grupiranje nekih kategorija kako biste smanjili broj kategorija na 10 ili manje. Ovo se ograničenje odnosi samo na primarne atribute. Za utjecajne kategorijske atribute trenutno podržavamo najviše 100 kategorija.

## <a name="generate-suggested-segments"></a>Stvaranje predloženih segmenata

1. Otvorite **Segmenti** i odaberite karticu **Prijedlozi (pretpregled).**

1. Odaberite **Traži nove prijedloge**, a zatim **Poboljšaj mjeru/mjerni podatak**. Odaberite **Start**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Odabir mjere poboljšanja na predloženim segmentima.":::

1. Odaberite atribut ili mjeru klijenta kao primarni atribut i odaberite **Dalje**.

1. Odaberite atribute koji utječu i odaberite **Pokreni**.

   > [!TIP]
   > Odabir više utjecajnih atributa poboljšava šanse za procjenu načina na koji oni utječu na primarni atribut. Nemojte uključivati atribute koji nemaju utjecaja na primarni atribut. Na primjer, ako su svi vaši klijenti iz određene države, nemojte uključiti atribut *država* jer neće utjecati na rezultat.

Ovisno o broju profila klijenata i odabranim atributima, obrada odabranih atributa može potrajati nekoliko minuta.

## <a name="manage-suggested-segments"></a>Upravljanje predloženim segmentima

Otvorite **Segmenti** i odaberite karticu **Prijedlozi (pretpregled).** **U odjeljku Prijedlozi segmenata temeljenih na atributima** odaberite predloženi segment za prikaz dostupnih akcija.

- **Pogledajte** predložene detalje segmenta te vrijednosti ili pravila atributa koje je AI model naučio.
- **Spremite kao segment** prijedlog kao segment. Prikazuje se na **kartici Svi segmenti** i može se [osvježiti, urediti ili izbrisati](segments.md).
- **Uredite atribute** i izmijenite konfigurirane atribute koji će zamijeniti trenutne prijedloge.
- **Osvježite prijedloge** da biste osvježili prijedloge uz zadržavanje konfiguriranih atributa.

## <a name="limitations"></a>Ograničenja

1. Nepodudaranje procijenjene veličine segmenta: ako odaberete primarni atribut koji sadrži prazne vrijednosti, to može utjecati na procijenjenu veličinu segmenta u prijedlozima segmenta. Prilikom spremanja takvog segmenta stvarna veličina segmenta može se razlikovati od izvorne procjene.

2. Primarni atributi Booleove vrste ne rade: Trenutno kao primarni atribut podržavamo samo string podatke i numeričke vrste podataka.

3. Predloženi segmenti nisu dovoljno različiti: Imajte na umu da odabrani atributi i raspodjela vrijednosti tih atributa utječu na rezultate. Možete promijeniti utjecajne atribute ili čak primarni atribut da biste dobili drugačije rezultate.

[!INCLUDE [footer-include](includes/footer-banner.md)]