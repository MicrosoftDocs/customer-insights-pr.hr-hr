---
title: Povezivanje podataka oblika Common Data Model s računom servisa Azure Data Lake
description: Rad s podacima oblika Common Data Model pomoću servisa Azure Data Lake Storage.
ms.date: 01/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: eeb6b9d97be5f9c0b9f6cbd6dbc6985559a1cd9d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642267"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Povezivanje s mapom značajke Common Data Model s pomoću računa za Azure Data Lake

U ovom se članku nalaze informacije o unosu Dynamics 365 Customer Insights podataka iz mape Uobičajeni podatkovni model pomoću Azure Data Lake Storage računa gen2.

## <a name="important-considerations"></a>Važne stavke

- Podaci u Azure Data Lake trebaju slijediti standard Common Data Model. Ostali formati trenutno nisu podržani.

- Unos podataka podržava isključivo račune servis za pohranu Azure Data Lake *Gen2*. Ne možete koristiti račune za pohranu servisa Azure Data Lake Gen1 za unos podataka.

- Račun za pohranu servisa Azure Data Lake mora imati [omogućen hijerarhijski prostora za naziv](/azure/storage/blobs/data-lake-storage-namespace).

- Da biste provjerili autentičnost s upraviteljem servisa Azure, provjerite je li konfiguriran na vašem klijentu. Dodatne informacije potražite u članku [Povezivanje Azure Data Lake Storage s gen2 računom pomoću upravitelja servisa Azure](connect-service-principal.md).

- Azure Data Lake s kojim se želite povezati i s kojeg želite unositi podatke mora biti u istoj regiji platforme Azure kao i okruženje Dynamics 365 Customer Insights. Veze s mapom Common Data Model iz podatkovnog jezera u drugoj Azure regiji nisu podržane. Da biste upoznali regiju okruženja servisa Azure, otvorite **AdminSystemAbout** > **·** > **u** odjeljku Customer Insights.

- Podaci pohranjeni u online uslugama mogu se pohraniti na drugoj lokaciji od one na kojoj se podaci obrađuju ili pohranjuju u Dynamics 365 Customer Insights sustavu.Uvozom ili povezivanjem s podacima pohranjenim u mrežnim uslugama slažete se da se podaci mogu prenositi i pohranjivati pomoću programa Dynamics 365 Customer Insights. [Saznajte više u Microsoftovu centru za](https://www.microsoft.com/trust-center) pouzdanost.

## <a name="connect-to-a-common-data-model-folder"></a>Spojite se na mapu Common Data Model

1. Idite na **Podaci** > **Izvor podataka**.

1. Odaberite **Dodaj izvor podataka**.

1. Odaberite **Azure data lake storage**, unesite **Naziv** izvor podataka, a zatim **dalje**.

   - Ako se to od vas zatraži, odaberite jedan od oglednih skupova podataka koji se odnose na vašu industriju, a zatim odaberite **Dalje**. 

1. Možete birati između korištenja mogućnosti koja se temelji na resursima i mogućnosti koja se temelji na pretplati za provjeru autentičnosti. Dodatne informacije potražite u članku [Povezivanje Azure Data Lake Storage s gen2 računom pomoću upravitelja servisa Azure](connect-service-principal.md). Unesite adresu poslužitelja **, odaberite** Prijava **, a zatim Dalje** **.**
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

1. Vidjet ćete popis dostupnih entiteta u odabranoj datoteci model.json ili manifest.json. Pregledajte i odaberite s popisa dostupnih entiteta, a zatim odaberite **Spremi**. Svi odabrani entiteti unijet će se iz novog izvora podataka.
   > [!div class="mx-imgBorder"]
   > ![Dijaloški okvir s popisom entiteta iz datoteke model.json.](media/review-entities.png)

8. Navedite koje podatkovne entitete želite omogućiti profiliranje podataka, a zatim odaberite **Spremi**. Profiliranje podataka omogućuje analitiku i druge mogućnosti. Možete odabrati cijeli entitet koji odabire sve atribute iz entiteta ili odabrati određene atribute po svom izboru. Prema zadanim postavkama nijedan entitet nije omogućen za profiliranje podataka.
   > [!div class="mx-imgBorder"]
   > ![Dijaloški okvir u kojemu se prikazuje profiliranje podataka.](media/dataprofiling-entities.png)

9. Nakon spremanja odabira otvara se stranica **Izvori podataka**. Sada biste trebali vidjeti vezu mape Common Data Model kao izvor podataka.

> [!NOTE]
> Datoteke model.json ili manifest.json mogu se povezati samo s jednim izvorom podataka u istom okruženju. Međutim, ista datoteka model.json ili manifest.json može se koristiti za izvore podataka u više okruženja.

## <a name="edit-a-common-data-model-folder-data-source"></a>Uređivanje izvora podataka mape Common Data Model

Možete ažurirati pristupni ključ za račun pohrane koji sadrži mapu Common Data Model. Možete i promijeniti datoteke model.json ili manifest.json. Da biste se povezali sa spremnikom drugačijim od računa za pohranu ili promijenili naziv računa, [stvorite novu vezu izvora podataka](#connect-to-a-common-data-model-folder).

1. Idite na **Podaci** > **Izvor podataka**.

2. Pored izvora podataka koji želite ažurirati odaberite elipsu.

3. S popisa odaberite mogućnost **Uredi**.

4. Ako želite ažurirajte **Pristupni ključ** i odaberite **Sljedeće**.

   ![Dijaloški okvir za uređivanje i ažuriranje pristupnog ključa za postojeći izvor podataka.](media/edit-access-key.png)

5. Ako želite, možete ažurirati s veze ključa računa na vezu koja se temelji na resursima ili pretplati. Dodatne informacije potražite u članku [Povezivanje Azure Data Lake Storage s gen2 računom pomoću upravitelja servisa Azure](connect-service-principal.md). Ne možete promijeniti podatke za **Spremnik** prilikom ažuriranja veze.
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


[!INCLUDE [footer-include](includes/footer-banner.md)]