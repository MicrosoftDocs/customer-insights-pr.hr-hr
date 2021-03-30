---
title: Eksperimenti Machine Learning Studio (klasični)
description: Koristite modele Machine Learning Studio (klasični) u sustavu Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 71881f7e1f9448fe0a7d6d92b8102b8b42de7c2a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598330"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Korištenje modela na temelju Azure Machine Learning Studio (klasični)

Objedinjeni podaci u sustavu Dynamics 365 Customer Insights izvor su za izgradnju modela strojnog učenja koji mogu stvoriti dodatne poslovne uvide. Customer Insights integrira se s Machine Learning Studio (klasični) kako bi koristio vlastite prilagođene modele. Da biste vidjeli kako su modeli razvijeni u Azure Machine Learning integrirani s Customer Insights, pogledajte [Eksperimenti Azure Machine Learning i](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Preduvjeti

- Pristup značajci Customer Insights
- Aktivna pretplata za Azure Enterprise
- [Objedinjeni profili klijenata](data-unification.md)
- Postavljen [izvoz entiteta u spremište blobova platforme Azure](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Postavljanje Machine Learning Studio Classic

U prvom koraku moramo stvoriti radni prostor i otvoriti Machine Learning Studio (klasični).

1. Otvorite [https://www.portal.azure.com](https://www.portal.azure.com/) i prijavite se.

1. Odaberite **Stvori resurs**.

1. Pretražite **Radni prostor za Strojno učenje Studio** i odaberite **Stvori**.

1. Unesite potrebne pojedinosti za [stvaranje radnog prostora](/azure/machine-learning/studio/create-workspace). Odaberite **Razina cijena plana web-servisa** na temelju količine podataka koje planirate uvesti. Za najbolju izvedbu odaberite **Mjesto** koje vam je geografski najbliže.

1. Nakon stvaranja resursa, prikazuje se nadzorna ploča radnog prostora za Strojno učenje Studio. Odaberite **Pokreni Strojno učenje Studio**.

   ![Korisničko sučelje za Strojno učenje Azure Studio](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Rad sa Strojnim učenjem Azure Studio

Sada možete stvoriti novi eksperiment ili uvesti postojeći predložak eksperimenta iz galerije uzoraka. Postoje uzorci eksperimenata za tri standardna scenarija:

- [Predviđanje odustajanja](#churn-analysis)

- [Trajna vrijednost klijenta](#customer-lifetime-value-prediction)

- [Preporuka proizvoda ili sljedeća najbolja radnja](#productrecommendation-or-next-best-action)

1. Ako stvorite novi eksperiment ili upotrebljavate predložak eksperimenta iz galerije, trebate konfigurirati svojstva za **Uvoz podataka**. Koristite vođeno iskustvo ili izravno navedite pojedinosti za spremište blobova platforme Azure koji sadrži vaše podatke.  

   ![Eksperiment sa Strojnim učenjem Azure Studio](media/azure-machine-learning-studio-experiment.png)

1. Sada možete izraditi prilagođeni kanal za obradu kako biste očistili podatke i pripremili ih za obradu, izdvojili značajke i uvježbali odgovarajući model.

1. Testirajte i optimizirajte performanse modela.

1. Kad budete zadovoljni kvalitetom modela, odaberite **Postavi web-uslugu** > **Prediktivna web-usluga**. Ova opcija uvozi uvježbani model i kanal za razvoj značajki iz eksperimenta uvježbavanja u prediktivnu uslugu. Prediktivna usluga može preuzeti drugi skup ulaznih podataka sa shemom koja se u eksperimentu uvježbavanja služi za predviđanje.

   ![Postavljanje prediktivne web-usluge](media/predictive-webservice-control.png)

1. Nakon uspješnog eksperimenta web-usluge možete je implementirati za automatsko zakazivanje. Da bi web-usluga radila sa značajkom Customer Insights, odaberite **Uvedi web-uslugu** > **Uvedi pregled web-usluge [novo]**. [Saznajte više o uvođenju web-usluge](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Uvođenje prediktivne web-usluge](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Modeli uzoraka iz galerije

Upotrijebit ćemo izmišljeni scenarij hotela Jović za modele u ovom članku. Hotel Jović prikuplja sljedeće podatke:

- CRM podatke koji se sastoje od aktivnosti odsjedanja u hotelu. Skup podataka uključuje podatke o datumima odsjedanja za svakog registriranog klijenta. Sadrži i podatke o rezervaciji, vrstama soba, detalje o potrošnji i sl. Podaci obuhvaćaju četiri godine, od siječnja 2014. do siječnja 2018.
- Korisničke profile gostiju hotela. Ovi profili sadrže informacije o svakom klijentu, uključujući ime, datum rođenja, poštansku adresu, spol i telefonski broj.
- Upotreba usluga koje nudi hotel, kao što su centar za zdravlje i ljepotu, praonica rublja, Wi-Fi mreža ili kurirska služba. Ove se informacije bilježe za svakog registriranog klijenta. Upotreba usluga obično je povezana s odsjedanjem. U nekim slučajevima klijenti mogu koristiti usluge bez odsjedanja u hotelu.

## <a name="churn-analysis"></a>Analiza odustajanja

Analiza odustajanja primjenjuje se na različita područja poslovanja. U ovom ćemo primjeru razmotriti odustajanje od usluga, posebno u kontekstu hotelskih usluga kao što je prethodno opisano. Omogućuje praktičan primjer kanala za sveobuhvatni model koji se može poslužiti kao početna točka za bilo koju vrstu modela odustajanja.

### <a name="definition-of-churn"></a>Definicija odustajanja

Definicija odustajanja može se razlikovati ovisno o scenariju. U ovom bi primjeru gost koji nije posjetio hotel u posljednjih godinu dana trebao bi biti označen kao da je odustao.  

Predložak eksperimenta može se uvesti iz galerije. Najprije trebate uvesti podatke za odjeljke **Aktivnost odsjedanja u hotelu**, **Podaci o klijentu** i **Podaci o upotrebi usluge** iz spremišta blobova platforme Azure.

   ![Uvoz podataka za model odustajanja](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Razvoj značajki

Na temelju definicije odustajanja najprije pronalazimo osnovne značajke koje će utjecati na oznaku. Zatim obrađujemo te osnovne značajke u numeričke značajke koje se mogu upotrebljavati u modelima strojnog učenja. Integracija podataka događa se u Customer Insights tako da se možemo pridružiti ovim tablicama pomoću *ID-ja klijenta*.

   ![Pridruživanje uvezenih podataka](media/join-imported-data.png)

Razvoj značajki za izradu modela za analizu odustajanja nije tako jednostavan. Podaci uključuju funkciju vremena s novim aktivnostima hotela koje se svakodnevno bilježe. Tijekom razvoja značajki nastojimo generirati statičke značajke iz dinamičkih podataka. U ovom slučaju generiramo više značajki iz aktivnosti hotela s kliznim prozorom od jedne godine. Također proširujemo kategorizirane značajke, npr. vrstu sobe ili vrstu rezervacije, u zasebne značajke s pomoću one-hot kodiranja.  

Konačni popis značajki:

| **Broj**  | **Original_Column**          | **Izvedene značajke**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Vrsta sobe                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Vrsta rezervacije                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Kategorija putovanja              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Potrošeno dolara                | TotalDollarSpent                                                                                                                          |
| 5           | Datumi prijave i odjave  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Upotreba usluge                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Odabir modela

Sada moramo odabrati optimalni algoritam koji ćemo koristiti. U ovom se slučaju većina značajki temelji na kategoriziranim značajkama. Modeli koji se temelje na stablu odluke obično dobro funkcioniraju. Ako postoje samo numeričke značajke, neuronske mreže mogu biti bolji odabir. Metoda potpornih vektora (SVM) također je dobar izbor u tim situacijama. No zahtijeva dosta podešavanja da bi se postigle najbolje performanse. Odabiremo **Poboljšano stablo odluke u dvije klase** kao prvi izbor modela, a **SVM u dvije klase** kao drugi model. Strojno učenje Azure Studio omogućuje provođenje A/B testiranja, tako da je korisno započeti s dva modela, a ne s jednim.

Slika u nastavku prikazuje kanal za uvježbavanje i procjenu modela u Strojnom učenju Azure Studio:

![Model odustajanja u Strojnom učenju Azure Studio](media/azure-machine-learning-model.png)

Primjenjujemo i tehniku zvanu **Važnost značajke permutacije**, što je važan aspekt optimizacije modela. Ugrađeni modeli pružaju slab ili nikakav uvid u utjecaj određenih značajki na konačno predviđanje. Kalkulator važnosti značajki koristi prilagođeni algoritam za izračunavanje utjecaja pojedinih značajki na ishod određenog modela. Važnost značajki normirana je između +1 do -1. Negativni utjecaj znači da odgovarajuća značajka ima suprotan utjecaj na ishod i da je treba ukloniti iz modela. Pozitivan utjecaj ukazuje na to da značajka značajno doprinosi predviđanju. Te vrijednosti nisu koeficijenti korelacije jer su različiti mjerni podaci. Dodatne informacije potražite u odjeljku [Važnost značajki permutacije](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Cijeli [eksperiment odustajanja dostupan je u AI galeriji platforme Azure](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Predviđanje trajne vrijednosti klijenta

Izračun trajne vrijednosti klijenta (CLTV) jedan je od ključnih mjernih podataka koje tvrtka može koristiti za procjenu i segmentiranje klijenata. Za hotelsku djelatnost poznavanje klijenata je ključno. Na primjer, razumijevanje čimbenika koji čine dobre klijente ključna je informacija. Upravitelji hotela tako mogu procijeniti na koje se značajke trebaju usredotočiti te ih poboljšati da bi zadovoljili svoje klijente u višem platnom razredu. Te odluke mogu imati izravan utjecaj na prodaju i zaradu.  

### <a name="definition-of-cltv"></a>Definicija CLTV-a

U ovom primjeru CLTV klijenta definiramo kao ukupni iznos u dolarima za koji se očekuje da će klijent potrošiti u sljedećih 365 dana. Za predviđanje ove vrijednosti koristit ćemo podatke od protekle tri godine za sve klijente.

### <a name="featurization"></a>Razvoj značajki

U ovom slučaju razvoj značajki uvelike nalikuje scenariju odustajanja. Međutim, oznake i predviđene vrijednosti razlikuju se od prethodno definiranih.

### <a name="model-selection"></a>Odabir modela

Predviđanje CLTV-a je problem regresije jer je predviđena vrijednost stalna varijabla s pozitivnom vrijednosti. Na temelju svojstava značajki odabiremo **Regresiju poboljšanog stabla odluke** kao jedan algoritam i **Regresiju neuronske mreže** kao drugi algoritam za uvježbavanje modela.

## <a name="product-recommendation-or-next-best-action"></a>Preporuka proizvoda ili sljedeća najbolja radnja

Preporuka proizvoda u scenariju hotela tumači se kao preporuka usluga koje hotel nudi klijentima. Cilj je odabrati odgovarajuće usluge za klijente kako bi se povećala njihova upotreba. To je slično preporukama filmova za korisnike usluga strujanja videozapisa.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definicija preporuke proizvoda ili sljedeće najbolje radnje

Cilj definiramo kao povećavanje iznosa u dolarima za upotrebu usluge ponudom usluga koje najbolje odgovaraju korisnicima hotela u skladu s njihovim interesom.

### <a name="featurization"></a>Razvoj značajki

Slično modelu odustajanja ServiceCustomerID za hotel pridružujemo CustomerID-ju kako bi preporuke odgovarale CustomerID-ju.

![Razvoj značajki modela preporuka](media/azure-machine-learning-model-featurization.png)

Podaci se dobivaju iz tri različita entiteta i iz njih se izvode značajke. Razvoj značajki za problem preporuke razlikuje se u usporedbi sa scenarijima odustajanja ili CLTV-a. Model preporuke treba ulazne podatke u obliku tri skupa značajki.

### <a name="model-selection"></a>Odabir modela

Predviđamo proizvode ili usluge uz pomoć algoritma koji se zove **Uvježbavanje odgovarajućeg preporučitelja** za uvježbavanje modela preporuke.

![Algoritam za preporuke proizvoda](media/azure-machine-learning-model-recommendation-algorithm.png)

Tri ulazna priključka za model **Uvježbavanje odgovarajućeg preporučitelja** preuzimaju podatke o korištenju usluge uvježbavanja, opis klijenta (neobavezno) i opis usluge. Postoje tri različita načina bodovanja modela. Jedan je za procjenu modela u kojem se ocjena normalizirane umanjene kumulativne dobiti (NDCG) izračunava za rangiranje ocijenjenih stavki. U ovom eksperimentu imamo NDCG ocjenu od 0,97. Ostale su dvije mogućnosti ocjenjivanje modela u cijelom katalogu usluga koje se preporučuju ili ocjenjivanje samo za stavke koje korisnici još nisu koristili.

Dodatnim proučavanjem raspodjele preporuka u cijelom katalogu usluga uočavamo da su telefonski pozivi, Wi-Fi mreža i kurirska služba vrhunske usluge koje se mogu preporučiti. To je u skladu s onim što smo ustanovili iz raspodjele podataka o upotrebi usluga:

![Izlaz modela preporuke](media/azure-machine-learning-model-output.png)

Cijelom [eksperimentu preporuke proizvoda može se pristupiti u AI galeriji platforme Azure.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integrirani prilagođeni modeli

Da biste koristili ta predviđanja u značajci Customer Insights trebate **izvesti** predviđanja zajedno s ID-jevima klijenata. [Izvezite ih na isto mjesto spremišta blobova platforme Azure](/azure/storage/common/storage-import-export-data-from-blobs) u koji izvozite izvorne podatke. Može se zakazati redovito pokretanje prediktivne web-usluge i ažuriranje ocjena.

Podaci generirani prema prilagođenom modelu mogu se koristiti za dodatno obogaćivanje podataka o klijentima. Za dodatne informacije pogledajte [Prilagođeni modeli strojnog učenja](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]