---
title: Povezivanje podataka oblika Common Data Model s računom servisa Azure Data Lake
description: Rad s podacima oblika Common Data Model pomoću servisa Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267851"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Povezivanje s mapom značajke Common Data Model s pomoću računa za Azure Data Lake

Ovaj članak pruža informacije o unosu podataka iz mape Common Data Model pomoću vašeg računa servisa Azure Data Lake Storage Gen2.

## <a name="important-considerations"></a>Važne stavke

- Podaci u Azure Data Lake trebaju slijediti standard Common Data Model. Ostali formati trenutno nisu podržani.

- Unos podataka podržava isključivo račune servis za pohranu Azure Data Lake *Gen2*. Ne možete koristiti račune za pohranu servisa Azure Data Lake Gen1 za unos podataka.

- Da biste provjerili autentičnost s upraviteljem servisa Azure, provjerite je li konfiguriran na vašem klijentu. Za više informacija pogledajte [Povezivanje uvida ciljne skupine s računom servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure](connect-service-principal.md).

- Azure Data Lake s kojim se želite povezati i s kojeg želite unositi podatke mora biti u istoj regiji platforme Azure kao i okruženje Dynamics 365 Customer Insights. Veze s mapom Common Data Model iz podatkovnog jezera u drugoj Azure regiji nisu podržane. Da biste znali koja je Azure regija okruženja, idite na **Administrator** > **Sustav** > **O sustavu** u uvidima ciljne skupine.

- Podaci pohranjeni na mrežnim servisima mogu se pohraniti na lokaciji koje se razlikuje od lokacije na kojoj se obrađuju ili pohranjuju u značajci Dynamics 365 Customer Insights. Uvozom ili povezivanjem s podacima pohranjenima u internetskim servisima slažete se da se podaci mogu prenijeti i pohraniti sa sustavom Dynamics 365 Customer Insights. [Saznajte više u programu Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Spojite se na mapu Common Data Model

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

1. Odaberite **Dodaj izvor podataka**.

1. Odaberie **Poveži se s mapom Common Data Model**, unesite **Naziv** za izvor podataka pa odaberite **Dalje**. Imenujte smjernice: 
   - Započnite slovom.
   - Koristite samo slova i brojeve. Nisu dopušteni posebni znakovi i razmaci.
   - Koristite između 3 i 64 znaka.

1. Možete birati između korištenja mogućnosti koja se temelji na resursima i mogućnosti koja se temelji na pretplati za provjeru autentičnosti. Za više informacija pogledajte [Povezivanje uvida ciljne skupine s računom servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure](connect-service-principal.md). Unesite podatke za **Spremnik** pa odaberite **Dalje**.
   > [!div class="mx-imgBorder"]
   > ![Dijaloški okvir za unos novih pojedinosti o vezi za Azure Data Lake](media/enter-new-storage-details.png)
   > [!NOTE]
   > Potrebna vam je jedna od sljedećih uloga u gore navedenom spremniku ili računu za pohranu da biste se mogli povezati i stvoriti izvor podataka:
   >  - Čitač podataka bloba pohrane
   >  - Vlasnik podataka bloba pohrane
   >  - Suradnik podataka bloba pohrane

1. U dijaloškom okviru **Odaberi mapu Common Data Model** odaberite datoteku model.json ili manifest.json iz koje želite uvesti podatke pa odaberite **Dalje**.
   > [!NOTE]
   > Nijedna datoteka model.json ili manifest.json povezana s drugim izvorom podataka u okruženju neće se prikazati na popisu.

1. Dobit ćete popis dostupnih entiteta u odabranoj datoteci model.json ili manifest.json. Možete pregledati i odabrati neki s popisa dostupnih entiteta i odabrati **Spremi**. Svi odabrani entiteti unijet će se iz novog izvora podataka.
   > [!div class="mx-imgBorder"]
   > ![Dijaloški okvir s popisom entiteta iz datoteke model.json](media/review-entities.png)

8. Navedite za koje entitete podataka želite omogućiti profiliranje podataka pa odaberite **Spremi**. Profiliranje podataka omogućuje analitiku i druge mogućnosti. Možete odabrati cijeli entitet koji odabire sve atribute iz entiteta ili odabrati određene atribute po svom izboru. Prema zadanim postavkama nijedan entitet nije omogućen za profiliranje podataka.
   > [!div class="mx-imgBorder"]
   > ![Dijaloški okvir u kojem se prikazuje profiliranje podataka](media/dataprofiling-entities.png)

9. Nakon spremanja odabira otvara se stranica **Izvori podataka**. Sada biste trebali vidjeti vezu mape Common Data Model kao izvor podataka.

> [!NOTE]
> Datoteke model.json ili manifest.json mogu se povezati samo s jednim izvorom podataka u istom okruženju. Međutim, ista datoteka model.json ili manifest.json može se koristiti za izvore podataka u više okruženja.

## <a name="edit-a-common-data-model-folder-data-source"></a>Uređivanje izvora podataka mape Common Data Model

Možete ažurirati pristupni ključ za račun pohrane koji sadrži mapu Common Data Model. Možete i promijeniti datoteke model.json ili manifest.json. Da biste se povezali sa spremnikom drugačijim od računa za pohranu ili promijenili naziv računa, [stvorite novu vezu izvora podataka](#connect-to-a-common-data-model-folder).

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Pored izvora podataka koji želite ažurirati odaberite elipsu.

3. S popisa odaberite mogućnost **Uredi**.

4. Ako želite ažurirajte **Pristupni ključ** i odaberite **Sljedeće**.

   ![Dijaloški okvir za uređivanje i ažuriranje pristupnog ključa za postojeći izvor podataka](media/edit-access-key.png)

5. Ako želite, možete ažurirati s veze ključa računa na vezu koja se temelji na resursima ili pretplati. Za više informacija pogledajte [Povezivanje uvida ciljne skupine s računom servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure](connect-service-principal.md). Ne možete promijeniti podatke za **Spremnik** prilikom ažuriranja veze.
   > [!div class="mx-imgBorder"]

   > ![Dijaloški okvir za unos pojedinosti o vezi za Azure Data Lake na postojeći račun za pohranu](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Potrebna vam je jedna od sljedećih uloga u gore navedenom spremniku ili računu za pohranu da biste se mogli povezati i stvoriti izvor podataka:
   >  - Čitač podataka bloba pohrane
   >  - Vlasnik podataka bloba pohrane
   >  - Suradnik podataka bloba pohrane


6. Neobavezno odaberite drugu datoteku model.json ili manifest.json s različitim skupom entiteta iz spremnika.

7. Po želji možete odabrati dodatne entitete za unos. Također, možete ukloniti sve već odabrane entitete ako nema ovisnosti.

   > [!IMPORTANT]
   > Ako postoje ovisnosti o postojećoj datoteci model.json ili manifest.json i skupu entiteta, vidjet ćete poruku o pogrešci i ne možete odabrati drugu datoteku model.json ili manifest.json. Uklonite te ovisnosti prije promjene datoteke model.json ili manifest.json ili stvorite novi izvor podataka s datotekom model.json ili manifest.json koju želite koristiti da biste izbjegli uklanjanje ovisnosti.

8. Po želji možete odabrati dodatne atribute ili entitete kako biste omogućili profiliranje podataka ili onemogućili već odabrane.   


[!INCLUDE[footer-include](../includes/footer-banner.md)]