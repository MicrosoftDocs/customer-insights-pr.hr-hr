---
title: Predloženi segmenti koje pokreće strojno učenje
description: Neka vam strojno učenje pomogne da pronađete nove i zanimljive segmente na temelju atributa klijenata.
ms.date: 02/01/2021
ms.reviewer: jimsonc
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 54655d57f4f0f723b497fe47891fd397ccb9dbf4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268217"
---
# <a name="suggested-segments-preview"></a>Predloženi segmenti (pretpregled)

Otkrijte zanimljive segmente svojih klijenata uz pomoć modela umjetne inteligencije. Ova značajka koju pokreće strojno učenje predlaže segmente na temelju mjera ili atributa klijenata. Može vam pomoći poboljšati KPI-je ili bolje razumjeti utjecaj atributa u kontekstu drugih atributa. 

> [!NOTE]
> Značajka za predložene segmente koristi automatizirana sredstva za procjenu podataka i predviđanje na temelju tih podataka, te stoga ima mogućnost da se koristi kao metoda profiliranja, jer je taj pojam definiran Općom uredbom o zaštiti podataka ("OUZP"). Vaša upotreba ove značajke za obradu podataka može podlijegati GDPR-u ili drugim zakonima ili propisima. Odgovorni ste osigurati da je da vaše korištenje servisa Dynamics 365 Customer Insights, uključujući ovu značajku, u skladu sa svim primjenjivim zakonima i uredbama, uključujući zakone koji se odnose na privatnost, osobne podatke, biometrijske podatke, zaštitu podataka i povjerljivost komunikacija.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Stranica predloženih segmenata u servisu Customer Insights koja prikazuje pojedinosti prijedloga u bočnom oknu.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Predloženi segmenti za poboljšanje vaših KPI-ja

Kao korisnik uvida u ciljnu skupinu, vjerojatno imate niz [stvorenih mjera](measures.md) koje pomažu u praćenju vaših ključnih pokazatelja uspješnosti (KPI-ji). Važno je razumjeti kako određeni atributi utječu na ovaj KPI za stvaranje segmenata i vođenje visoko ciljane kampanje.   
Na primjer, pratite mjeru koja se zove *Ukupnotrošenjepoklijentu*. Kao tvrtka želite vidjeti da ovaj broj raste. Odabir mjere kao primarnog atributa omogućuje vam odabir atributa čiji utjecaj želite procijeniti. Recimo *razina članstva*, *razdoblje članstva* i *zanimanje*. Customer Insights tada može predložiti segment koji vam govori koji su najveći utjecaji te mjere. Na primjer, *Računovođe* koje su *Zlatni* članovi i koje posluju s vama *najmanje pet godina* su najveći utjecatelji na *Ukupnotrošenjepoklijentu*. Za svaki prijedlog dobit ćete procijenjenu veličinu segmenta. Te podatke možete koristiti za izradu kampanja za ciljanu publiku.

## <a name="understand-what-influences-a-customer-attribute"></a>Objašnjenje što utječe na atribut klijenta

Možete odabrati atribut klijenta umjesto mjere kao primarnog atributa. Na temelju vašeg odabira utjecaja na atribute, model umjetne inteligencije stvara niz prijedloga koji pokazuju kako odabrani atributi utječu na primarni atribut.   
Na primjer, odabrali ste *Član programa Rewards (Da/Ne)* kao primarni atribut. *Stalno mjesto*, *Zanimanje* i *Broj potvrda o prijavi problema službi za podršku* postavljeni su kao drugi utjecajni atributi. Model umjetne inteligencije mogao bi predložiti segmente koji ukazuju na to da su uglavnom IT profesionalci sa stalnim mjestom duljim od dvije godine članovi programa Rewards. Drugi prijedlog mogao bi istaknuti da su računovođe sa stalnim mjestom duljim od jedne godine i s manje od tri potvrde o prijavi problema službi za podršku članovi programa Rewards. 

## <a name="artificial-intelligence-usage"></a>Upotreba umjetne inteligencije

Algoritam stabla odluke predlaže zanimljive segmente koristeći primarni atribut i utjecajne atribute. Prijedlozi se temelje na pravilima ili obrascima koje je prikupio algoritam umjetne inteligencije. Kao prijedlozi su prikazani samo segmenti koji se značajno razlikuju od prosječne populacije. Usporedba s prosječnom populacijom temelji se na odabranoj mjeri ili primarnom atributu.

### <a name="responsible-ai"></a>Odgovorna umjetna inteligencija

Predloženi segmenti omogućuju vam odabir atributa za stvaranje novih segmenata i obradu podataka koje odaberete. Pri odabiru atributa, uključujući osjetljive atribute poput rase, seksualne orijentacije ili spola, morate osigurati da možete i trebate obrađivati te podatke. Odgovorni ste za poštivanje svih zakona primjenjivih na vašu tvrtku ili ustanovu i pridržavanje načela i pravila privatnosti vaše tvrtke ili ustanove.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Različiti rezultati za primarne atribute s kategorijskim i numeričkim vrijednostima

Prijedlozi segmenata će se razlikovati ovisno o tome jeste li odabrali numerički ili kategorijski atribut kao primarni atribut. Vrijednosti u kategorijskom atributu sadrže dvije ili više kategorija ili vrsta. Numerički atribut sadrži kvantitativne podatke i s njima je povezan osjećaj mjerenja.

S numeričkim atributom kao što je *godišnji prihod* ili *razdoblje članstva* kao primarnim atributom, sustav predlaže segmente koji imaju veću ili manju prosječnu vrijednost numeričkog atributa u usporedbi sa svim klijentima.

Kategorijski atribut kao što je *zadovoljstvo klijenata* kao primarni atribut rezultira predloženim segmentima koji imaju veći ili manji postotak klijenata koji pripadaju određenoj kategoriji u usporedbi s postotkom svih klijenata koji pripadaju istoj kategoriji. Na primjer, *zadovoljstvo klijenata* je odabrano kao primarni atribut i sastoji se od tri kategorije (*Nisko*, *Srednje* i *Visoko*). Za svaku će se kategoriju predložiti segmenti koji imaju znatno veći ili manji postotak klijenata koji pripadaju toj kategoriji u usporedbi s udjelom svih klijenata u istoj kategoriji. Ako 22 % svih klijenata ima *Visoko* zadovoljstvo, tada će se samo segmenti koji imaju znatno veći ili manji udio klijenata s *Visokim* zadovoljstvom u odnosu na 22 % predložiti za tu kategoriju. Slično tome, predložit će se segmenti za svaku od ostalih kategorija (*Nisko* i *Srednje*) ako su statistički značajni.

> [!NOTE]
> Trenutno podržavamo samo primarne kategorijske atribute koji imaju do 10 kategorija. Ako želite vidjeti prijedloge segmenata koji se temelje na primarnom atributu s više od 10 kategorija, preporučujemo da neke kategorije grupirate kako biste smanjili broj kategorija na 10 ili manje. Ovo se ograničenje odnosi samo na primarne atribute. Za utjecajne kategorijske atribute trenutno podržavamo najviše 100 kategorija.

## <a name="generate-suggested-segments"></a>Stvaranje predloženih segmenata

1. Idite na **Segmenti**.

1. Odaberite karticu **Prijedlozi (pretpregled)**.

1. Odaberite **Dohvaćanje novih prijedloga** za početak vođenog iskustva.

1. Odaberite mjeru ili atribut klijenta kao primarni atribut pa odaberite **Sljedeće**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Odabir primarnog atributa za prijedloge o predloženim segmentima.":::

1. Odaberite utjecajne atribute pa odaberite **Spremi**.
   
   > [!TIP]
   > Odabir više utjecajnih atributa poboljšava šanse za procjenu načina na koji oni utječu na primarni atribut. Nemojte uključiti atribute koji nemaju utjecaja na primarni atribut. Na primjer, ako su svi vaši klijenti iz određene države, nemojte uključiti atribut *država* jer neće utjecati na rezultat.

1. Ovisno o broju profila klijenata i odabranim atributima, obrada odabranih atributa može potrajati nekoliko minuta. 

## <a name="view-details-of-a-suggested-segment"></a>Prikaz pojedinosti o predloženom segmentu

Nakon što model umjetne inteligencije generira prijedloge, pronaći ćete ih na popisu u odjeljku **Segmenti** > **Prijedlozi (pretpregled)**.
 
Odaberite predloženi segment da biste pregledali pojedinosti tog prijedloga, uključujući usporedbu prosječne vrijednosti i broja članova segmenta. Također možete pregledati vrijednosti ili pravila atributa koje je model umjetne inteligencije naučio za prijedlog odabranog segmenta.

## <a name="save-a-suggestion-as-a-segment"></a>Spremanje prijedloga kao segmenta

1. Idite u odjeljak **Segmenti** > **Prijedlozi (pretpregled)**.

1. Odaberite segment koji želite spremiti. 

1. U bočnom oknu odaberite **Spremi kao segment**. 

1. Nakon spremanja segmenta, prikazat će se na popisu segmenata na kartici **Svi segmenti**. Tada se može [osvježiti, urediti ili izbrisati kao i bilo koji drugi segment](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Osvježavanje ili uređivanje skupa prijedloga

1. Idite u odjeljak **Segmenti** > **Prijedlozi (pretpregled)**.

1. Odaberite **Osvježavanje prijedloga** za osvježavanje prijedloga uz zadržavanje konfiguriranih atributa. Ili odaberite **Uređivanje atributa** za izmjenu konfiguriranih atributa. Sustav će ponovno pokrenuti model umjetne inteligencije, generirati prijedloge segmenata na temelju najnovijih podataka i zamijeniti trenutne prijedloge.

## <a name="limitations"></a>Ograničenja

1. Nepodudaranje procijenjene veličine segmenta: ako odaberete primarni atribut koji sadrži prazne vrijednosti, to može utjecati na procijenjenu veličinu segmenta u prijedlozima segmenta. Prilikom spremanja takvog segmenta stvarna veličina segmenta može se razlikovati od izvorne procjene.
 
2. Primarni atributi Booleove vrste ne rade: Trenutno kao primarni atribut podržavamo samo string podatke i numeričke vrste podataka.

3. Predloženi segmenti nisu dovoljno različiti: Imajte na umu da odabrani atributi i raspodjela vrijednosti tih atributa utječu na rezultate. Možete promijeniti utjecajne atribute ili čak primarni atribut da biste dobili drugačije rezultate.



[!INCLUDE[footer-include](../includes/footer-banner.md)]