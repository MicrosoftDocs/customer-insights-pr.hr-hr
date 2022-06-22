---
title: Povezivanje podataka oblika Common Data Model s računom servisa Azure Data Lake
description: Rad s podacima oblika Common Data Model pomoću servisa Azure Data Lake Storage.
ms.date: 05/30/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2ab7ec77252be33f1203959c2a596ddec20425f2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011548"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Povezivanje s podacima u usluzi Azure Data Lake Storage

Unosite podatke u Dynamics 365 Customer Insights korištenje računa Azure Data Lake Storage tvrtke Gen2. Unos podataka može biti pun ili inkrementalan.

## <a name="prerequisites"></a>Preduvjeti

- Unos podataka podržava Azure Data Lake Storage *isključivo Gen2* račune. Ne možete koristiti račune Data Lake Storage Gen1 za unos podataka.

- Račun Azure Data Lake Storage mora imati [omogućen hijerarhijski prostora za naziv](/azure/storage/blobs/data-lake-storage-namespace). Podaci moraju biti pohranjeni u obliku hijerarhijski mape koji definira korijensku mapu i ima podmape za svaki entitet. Podmape mogu imati potpune podatke ili inkrementalne mape podataka.

- Da biste provjerili autentičnost s upraviteljem servisa Azure, provjerite je li konfiguriran na vašem klijentu. Dodatne informacije potražite u članku [Povezivanje Azure Data Lake Storage s gen2 računom pomoću upravitelja](connect-service-principal.md) servisa Azure.

- Podaci Azure Data Lake Storage iz kojih želite povezati i unositi podatke moraju biti u istoj regiji servisa Azure kao i Dynamics 365 Customer Insights okruženje. Veze s mapom Common Data Model iz podatkovnog jezera u drugoj Azure regiji nisu podržane. Da biste saznali regiju okruženja servisa Azure, otvorite **Odjeljak O sustavu** > **·** > **administratora** u odjeljku Customer Insights.

- Podaci pohranjeni u online uslugama mogu se pohraniti na drugoj lokaciji od one na kojoj se podaci obrađuju ili pohranjuju u Dynamics 365 Customer Insights sustavu.Uvozom ili povezivanjem s podacima pohranjenim u mrežnim uslugama slažete se da se podaci mogu prenositi i pohranjivati pomoću programa Dynamics 365 Customer Insights. [Saznajte više u Microsoftovu centru za pouzdanost](https://www.microsoft.com/trust-center).

- Ravnatelj usluge Customer Insights mora biti u jednoj od sljedećih uloga da bi pristupio računu za pohranu. Dodatne informacije potražite u članku [Dodjela dozvola ravnatelju servisa za pristup računu](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account) za pohranu.
  - Čitač podataka bloba pohrane
  - Vlasnik podataka bloba pohrane
  - Suradnik podataka bloba pohrane

- Podaci u vašoj pohrani na jezeru podataka trebali bi slijediti standard uobičajenog podatkovnog modela za pohranu vaših podataka i imati zajednički manifest podatkovnog modela koji predstavlja shemu podatkovnih datoteka (*.csv ili *.parket). U manifestu se moraju navesti pojedinosti o entitetima kao što su stupci entiteta i vrste podataka te mjesto podatkovne datoteke i vrsta datoteke. Dodatne informacije potražite u članku [Manifest](/common-data-model/sdk/manifest) Uobičajeni podatkovni model. Ako manifesta nema, administratorski korisnici s vlasnikom podataka o blobu za pohranu ili pristupom Blob Data storage Blob Data suradnik mogu definirati shemu prilikom unosa podataka.

## <a name="connect-to-azure-data-lake-storage"></a>Povezivanje sa sustavom Azure Data Lake Storage

1. Idite na **Podaci** > **Izvor podataka**.

1. Odaberite **Dodaj izvor podataka**.

1. Odaberite **Azure data lake storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Dijaloški okvir za unos detalja o vezi za Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. **Unesite naziv** izvor podataka i neobavezni **Opis**. Naziv jedinstveno identificira izvor podataka i referenciran je u silaznim procesima i ne može se mijenjati.

1. Odaberite jednu od sljedećih mogućnosti za povezivanje prostora za **pohranu pomoću.** Dodatne informacije potražite u članku [Povezivanje uvida Azure Data Lake Storage korisnika s gen2 računom s upraviteljem](connect-service-principal.md) servisa Azure.

   - **Azure resource**: Unesite **ID** resursa. Ako po želji želite unijeti podatke s računa za pohranu putem privatne veze servisa Azure, odaberite **Omogući privatnu vezu**. Dodatne informacije potražite u odjeljku [Privatne veze](security-overview.md#private-links-tab).
   - **Pretplata** na Azure: Odaberite pretplatu **,** a zatim grupu **Resursa** i **račun** za pohranu. Ako po želji želite unijeti podatke s računa za pohranu putem privatne veze servisa Azure, odaberite **Omogući privatnu vezu**. Dodatne informacije potražite u odjeljku [Privatne veze](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Za stvaranje izvor podataka potrebna vam je jedna od sljedećih uloga u spremniku ili računu za pohranu:
   >
   >  - Pohrana Blob Data Čitatelj dovoljna je za čitanje s računa za pohranu i unos podataka u Customer Insights. 
   >  - Ako želite urediti datoteke manifesta izravno u odjeljku Customer Insights, potreban je suradnik ili vlasnik podataka za pohranu blob podataka.  
  
1. Odaberite naziv spremnika **koji sadrži podatke** i shemu (datoteka model.json ili manifest.json) iz kojeg želite uvesti podatke, a zatim odaberite **Dalje**.
   > [!NOTE]
   > Nijedna datoteka model.json ili manifest.json povezana s drugim izvorom podataka u okruženju neće se prikazati na popisu. Međutim, ista datoteka model.json ili manifest.json može se koristiti za izvore podataka u više okruženja.

1. Da biste stvorili novu shemu, idite na [Stvaranje nove datoteke sheme](#create-a-new-schema-file).

1. Da biste koristili postojeću shemu, idite do mape koja sadrži datoteku model.json ili manifest.cdm.json. Možete pretraživati unutar direktorija da biste pronašli datoteku.

1. Odaberite json datoteku i odaberite **Dalje**. Prikazuje se popis dostupnih entiteta.

   :::image type="content" source="media/review-entities.png" alt-text="Dijaloški okvir popisa entiteta za odabir":::

1. Izaberite entitete koje želite uključiti.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dijaloški okvir s prikazom potrebnog za primarni ključ":::

   > [!TIP]
   > Da biste uredili entitete u JSON-ovom sučelju za uređivanje, odaberite **Pokaži više** > **uređivanje datoteke sheme**. Unesite promjene i odaberite **Spremi**.

1. Za odabrane entitete koji zahtijevaju inkrementalno gutanje, **obavezni** prikazi u odjeljku **Inkrementalno osvježavanje**. Za svaki od tih entiteta pročitajte članak [Konfiguriranje postupnog osvježavanja za izvore podataka servisa Azure Data Lake](incremental-refresh-data-sources.md).

1. Za odabrane entitete u kojima primarni ključ nije definiran, **Obavezni** prikazivaju se u odjeljku **Primarni ključ**. Za svaki od ovih entiteta:
   1. Odaberite **Obavezno**. Prikazat će se **ploča Uređivanje entiteta**.
   1. Odaberite primarni **ključ**. Primarni ključ je atribut jedinstven za entitet. Da bi atribut bio važeći primarni ključ, on ne bi trebao uključivati dvostruke vrijednosti, vrijednosti koje nedostaju ili vrijednosti nula. Atributi vrste podataka nizova, cijelog broja i GUID-a podržani su kao primarni ključevi.
   1. Po želji promijenite uzorak particije.
   1. Odaberite **Zatvori** da biste spremili i zatvorili ploču.

1. Odaberite broj atributa **za** svaki uključeni entitet. Prikazuje se **stranica Upravljanje atributima**.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dijaloški okvir za odabir profiliranja podataka.":::

   1. Stvorite nove atribute, uredite ili izbrišite postojeće atribute. Možete promijeniti naziv, oblik podataka ili dodati semantičku vrstu.
   1. Da biste omogućili analitiku i druge mogućnosti, odaberite **Profiliranje** podataka za cijeli entitet ili za određene atribute. Prema zadanim postavkama nijedan entitet nije omogućen za profiliranje podataka.
   1. Odaberite **Gotovo**.

1. Odaberite **Spremi**. Otvorit **će se stranica Izvori** podataka koja prikazuje novi izvor podataka u **statusu Osvježavanje**.

### <a name="create-a-new-schema-file"></a>Stvaranje nove datoteke sheme

1. Odaberite **Nova datoteka sheme**.

1. Unesite naziv datoteke i odaberite **Spremi**.

1. Odaberite **Novi entitet**. Prikazuje se **ploča Novi entitet**.

1. Unesite naziv entiteta i odaberite mjesto **podatkovnih** datoteka.
   - **Više .csv ili .parketnih datoteka**: pronađite korijensku mapu, odaberite vrstu uzorka i unesite izraz.
   - **Datoteke s jednim .csv ili .parketom**: pronađite datoteku .csv ili .parketa i odaberite je.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Dijaloški okvir za stvaranje novog entiteta s istaknutim mjestom podatkovnih datoteka.":::

1. Odaberite **Spremi**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Dijaloški okvir za definiranje ili automatsko generiranje atributa.":::

1. Odaberite **definirajte atribute** za ručno dodavanje atributa ili odaberite **automatsko generiranje.** Da biste definirali atribute, unesite naziv, odaberite oblik podataka i neobaveznu semantičku vrstu. Za automatski generirane atribute:

   1. Kada se atributi automatski generiraju, odaberite **Pregledaj atribute**. Prikazuje se **stranica Upravljanje atributima**.

   1. Provjerite je li oblik podataka ispravan za svaki atribut.

   1. Da biste omogućili analitiku i druge mogućnosti, odaberite **Profiliranje** podataka za cijeli entitet ili za određene atribute. Prema zadanim postavkama nijedan entitet nije omogućen za profiliranje podataka.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dijaloški okvir za odabir profiliranja podataka.":::

   1. Odaberite **Gotovo**. Prikazuje se **stranica Odabir entiteta**.

1. Nastavite dodavati entitete i atribute, ako je primjenjivo.

1. Kada dodate sve entitete, odaberite **Uključi da biste uključili** entitete u izvor podataka gutanja.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dijaloški okvir s prikazom potrebnog za primarni ključ":::

1. Za odabrane entitete koji zahtijevaju inkrementalno gutanje, **obavezni** prikazi u odjeljku **Inkrementalno osvježavanje**. Za svaki od tih entiteta pročitajte članak [Konfiguriranje postupnog osvježavanja za izvore podataka servisa Azure Data Lake](incremental-refresh-data-sources.md).

1. Za odabrane entitete u kojima primarni ključ nije definiran, **Obavezni** prikazivaju se u odjeljku **Primarni ključ**. Za svaki od ovih entiteta:
   1. Odaberite **Obavezno**. Prikazat će se **ploča Uređivanje entiteta**.
   1. Odaberite primarni **ključ**. Primarni ključ je atribut jedinstven za entitet. Da bi atribut bio važeći primarni ključ, on ne bi trebao uključivati dvostruke vrijednosti, vrijednosti koje nedostaju ili vrijednosti nula. Atributi vrste podataka nizova, cijelog broja i GUID-a podržani su kao primarni ključevi.
   1. Po želji promijenite uzorak particije.
   1. Odaberite **Zatvori** da biste spremili i zatvorili ploču.

1. Odaberite **Spremi**. Otvorit **će se stranica Izvori** podataka koja prikazuje novi izvor podataka u **statusu Osvježavanje**.


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Azure Data Lake Storage Uređivanje izvor podataka

Pomoću mogućnosti Poveži se s računom *za pohranu možete ažurirati*. Dodatne informacije potražite u članku [Povezivanje uvida Azure Data Lake Storage korisnika s gen2 računom s upraviteljem](connect-service-principal.md) servisa Azure. Da biste se povezali sa spremnikom drugačijim od računa za pohranu ili promijenili naziv računa, [stvorite novu vezu izvora podataka](#connect-to-azure-data-lake-storage).

1. Idite na **Podaci** > **Izvor podataka**.

1. Uz izvor podataka koje želite ažurirati odaberite **Uredi**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Dijaloški okvir za uređivanje izvor podataka servisa Azure Data Lake.":::

1. Promijenite bilo koju od sljedećih informacija:

   - **Opis**
   - **Povežite svoj prostor za pohranu pomoću** podataka i informacija o vezi. Ne možete promijeniti podatke za **Spremnik** prilikom ažuriranja veze.
      > [!NOTE]
      > Računu za pohranu ili spremniku mora se dodijeliti jedna od sljedećih uloga:
        > - Čitač podataka bloba pohrane
        > - Vlasnik podataka bloba pohrane
        > - Suradnik podataka bloba pohrane

   - **Omogućite privatnu vezu** ako želite unijeti podatke s računa za pohranu putem privatne veze servisa Azure. Dodatne informacije potražite u odjeljku [Privatne veze](security-overview.md#private-links-tab).

1. Odaberite **Dalje**.
1. Promijenite nešto od sljedećeg:
   - Idite na drugu datoteku model.json ili manifest.json s različitim skupom entiteta iz spremnika.
   - Da biste u unos dodali dodatne entitete, odaberite **Novi entitet**.
   - Da biste uklonili već odabrane entitete ako nema zavisnosti, odaberite entitet i **Izbrišite**.
      > [!IMPORTANT]
      > Ako postoje ovisnosti o postojećoj datoteci model.json ili manifest.json i skupu entiteta, vidjet ćete poruku o pogrešci i ne možete odabrati drugu datoteku model.json ili manifest.json. Uklonite te ovisnosti prije promjene datoteke model.json ili manifest.json ili stvorite novi izvor podataka s datotekom model.json ili manifest.json koju želite koristiti da biste izbjegli uklanjanje ovisnosti.
   - Da biste promijenili mjesto podatkovne datoteke ili primarni ključ, odaberite **Uredi**.
   - Upute za promjenu inkrementalnih podataka o gutanju potražite u članku [Konfiguriranje postupnog osvježavanja za izvore podataka servisa Azure Data Lake](incremental-refresh-data-sources.md)

1. Odaberite **Atributi da biste dodali** ili promijenili atribute ili omogućili profiliranje podataka. Zatim odaberite **Gotovo**.

1. Kliknite **Spremi** da biste primijenili promjene i vratili se na **stranicu Izvori** podataka.
