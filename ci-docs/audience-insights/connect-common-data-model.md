---
title: Povezivanje podataka oblika Common Data Model s računom servisa Azure Data Lake
description: Rad s podacima oblika Common Data Model pomoću servisa Azure Data Lake Storage.
ms.date: 01/25/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8a871d65bd79d3246984e23fb52210c8dc7259b8
ms.sourcegitcommit: 7a99f3490e6582c2bc2b38019ed1898348b0eaba
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 01/25/2022
ms.locfileid: "8027043"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Povezivanje s mapom značajke Common Data Model s pomoću računa za Azure Data Lake

Ovaj članak pruža informacije o unosu podataka iz mape Common Data Model pomoću vašeg računa servisa Azure Data Lake Storage Gen2.

## <a name="important-considerations"></a>Važne stavke

- Podaci u Azure Data Lake trebaju slijediti standard Common Data Model. Ostali formati trenutno nisu podržani.

- Unos podataka podržava isključivo račune servis za pohranu Azure Data Lake *Gen2*. Ne možete koristiti račune za pohranu servisa Azure Data Lake Gen1 za unos podataka.

- Račun za pohranu na Azure Data Lakeu mora imati [omogućen hijerarhijski prostor naziva](/azure/storage/blobs/data-lake-storage-namespace).

- Da biste provjerili autentičnost s upraviteljem servisa Azure, provjerite je li konfiguriran na vašem klijentu. Za više informacija pogledajte [Povezivanje uvida ciljne skupine s računom servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure](connect-service-principal.md).

- Azure Data Lake s kojim se želite povezati i s kojeg želite unositi podatke mora biti u istoj regiji platforme Azure kao i okruženje Dynamics 365 Customer Insights. Veze s mapom Common Data Model iz podatkovnog jezera u drugoj Azure regiji nisu podržane. Da biste znali koja je Azure regija okruženja, idite na **Administrator** > **Sustav** > **O sustavu** u uvidima ciljne skupine.

- Podaci pohranjeni u mrežnim servisima mogu se pohraniti na lokaciji različitoj od mjesta obrade ili pohranjivanja podataka u sustavu Dynamics 365 Customer Insights.Uvozom ili povezivanjem s podacima pohranjenima u mrežnim servisima suglasni ste da se podaci mogu prenositi i pohranjivati sa sustavom Dynamics 365 Customer Insights. [Saznajte više u Microsoftovu centru za pouzdanost](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Spojite se na mapu Common Data Model

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

1. Odaberite **Dodaj izvor podataka**.

1. Odaberite Spremište **podatkovnog jezera Azure, unesite** naziv **izvor podataka, a zatim dalje** **.**

   - Ako se to od vas zatraži, odaberite jedan od oglednih skupova podataka koji se odnose na vašu industriju, a zatim odaberite **Dalje**. 

1. Možete birati između korištenja mogućnosti koja se temelji na resursima i mogućnosti koja se temelji na pretplati za provjeru autentičnosti. Za više informacija pogledajte [Povezivanje uvida ciljne skupine s računom servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure](connect-service-principal.md). Unesite adresu **poslužitelja**, odaberite **Prijava**, a zatim **Dalje**.
   > [!div class="mx-imgBorder"]
   > ![Dijaloški okvir za unos novih pojedinosti o vezi za Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Potrebna vam je jedna od sljedećih uloga u gore navedenom spremniku ili računu za pohranu da biste se mogli povezati i stvoriti izvor podataka:
   >  - Čitač podataka bloba pohrane
   >  - Vlasnik podataka bloba pohrane
   >  - Suradnik podataka bloba pohrane

1. U dijaloškom okviru **Odaberi mapu Common Data Model** odaberite datoteku model.json ili manifest.json iz koje želite uvesti podatke pa odaberite **Dalje**.
   > [!NOTE]
   > Nijedna datoteka model.json ili manifest.json povezana s drugim izvorom podataka u okruženju neće se prikazati na popisu.

1. Popis dostupnih entiteta vidjet ćete u odabranoj datoteci model.json ili manifest.json. Pregledajte i odaberite s popisa dostupnih entiteta, a zatim odaberite **Spremi**. Svi odabrani entiteti unijet će se iz novog izvora podataka.
   > [!div class="mx-imgBorder"]
   > ![Dijaloški okvir s popisom entiteta iz datoteke model.json.](media/review-entities.png)

8. Navedite entitete podataka koje želite omogućiti profiliranje podataka, a zatim odaberite **Spremi**. Profiliranje podataka omogućuje analitiku i druge mogućnosti. Možete odabrati cijeli entitet koji odabire sve atribute iz entiteta ili odabrati određene atribute po svom izboru. Prema zadanim postavkama nijedan entitet nije omogućen za profiliranje podataka.
   > [!div class="mx-imgBorder"]
   > ![Dijaloški okvir u kojemu se prikazuje profiliranje podataka.](media/dataprofiling-entities.png)

9. Nakon spremanja odabira otvara se stranica **Izvori podataka**. Sada biste trebali vidjeti vezu mape Common Data Model kao izvor podataka.

> [!NOTE]
> Datoteke model.json ili manifest.json mogu se povezati samo s jednim izvorom podataka u istom okruženju. Međutim, ista datoteka model.json ili manifest.json može se koristiti za izvore podataka u više okruženja.

## <a name="edit-a-common-data-model-folder-data-source"></a>Uređivanje izvora podataka mape Common Data Model

Možete ažurirati pristupni ključ za račun pohrane koji sadrži mapu Common Data Model. Možete i promijeniti datoteke model.json ili manifest.json. Da biste se povezali sa spremnikom drugačijim od računa za pohranu ili promijenili naziv računa, [stvorite novu vezu izvora podataka](#connect-to-a-common-data-model-folder).

1. U uvidima u ciljnu skupinu idite na **Podaci** > **Izvori podataka**.

2. Pored izvora podataka koji želite ažurirati odaberite elipsu.

3. S popisa odaberite mogućnost **Uredi**.

4. Ako želite ažurirajte **Pristupni ključ** i odaberite **Sljedeće**.

   ![Dijaloški okvir za uređivanje i ažuriranje pristupnog ključa za postojeći izvor podataka.](media/edit-access-key.png)

5. Ako želite, možete ažurirati s veze ključa računa na vezu koja se temelji na resursima ili pretplati. Za više informacija pogledajte [Povezivanje uvida ciljne skupine s računom servisa Azure Data Lake Storage Gen2 s upraviteljem servisa Azure](connect-service-principal.md). Ne možete promijeniti podatke za **Spremnik** prilikom ažuriranja veze.
   > [!div class="mx-imgBorder"]

   > ![Dijaloški okvir za unos pojedinosti o vezi za Azure Data Lake na postojeći račun za pohranu.](media/enter-existing-storage-details.png)

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
