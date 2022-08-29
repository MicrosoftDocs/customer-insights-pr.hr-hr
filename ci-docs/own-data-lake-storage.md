---
title: Koristite vlastiti Azure Data Lake Storage Gen2 račun
author: mukeshpo
description: Informirajte se o preduvjetima za korištenje vlastitog Azure Data Lake Storage računa za pohranu podataka Customer Insights.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304372"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Koristite vlastiti Azure Data Lake Storage Gen2 račun

Dynamics 365 Customer Insights daje vam mogućnost pohrane svih podataka u [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction). Spremanjem podataka u data lake pohranu slažete se da će se podaci prenositi i pohranjivati na odgovarajuće zemljopisno mjesto za taj račun za pohranu na servisu Azure. Dodatne informacije potražite u članku [Microsoftov centar za pouzdanost](https://www.microsoft.com/trust-center).

Administratori u customer insights mogu [stvoriti okruženja](create-environment.md) i [odrediti mogućnost](create-environment.md#step-2-configure-data-storage) pohrane podataka u tom procesu.

## <a name="prerequisites"></a>Preduvjeti

- Azure Data Lake Storage računi moraju biti u istoj regiji servisa Azure koju ste odabrali prilikom stvaranja okruženja Customer Insights. Da biste upoznali regiju okruženja, idite na **Admin** > **System** > **About** in Customer Insights.
- Račun za pohranu na servisu Data Lake mora biti Gen2. Računi za pohranu servisa Azure Data Lake Gen1 nisu podržani.
- Račun za pohranu na servisu Data Lake mora imati [omogućen](/azure/storage/blobs/data-lake-storage-namespace) hijerarhijski prostora naziva.
- Imenovani `customerinsights` spremnik mora postojati na računu za pohranu. Stvorite ga prije nego što koristite vlastitu pohranu na jezeru podataka u customer insights.
- Administratoru koji postavlja okruženje Customer Insights potrebna je uloga Pohrane blobo podataka suradnik ili Vlasnika podataka o blobu pohrani na računu za pohranu ili spremniku`customerinsights`. Dodatne informacije o dodjeli dozvole na računu za pohranu potražite u članku [Stvaranje računa](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) za pohranu.

## <a name="connect-customer-insights-with-your-storage-account"></a>Povezivanje uvida kupaca s računom za pohranu

Kada stvorite novo okruženje, provjerite postoji li račun za pohranu na servisu Data Lake i jesu li ispunjeni svi preduvjeti.

1. U koraku pohrane **podataka** tijekom stvaranja okruženja postavite **Spremi izlazne podatke** na **Azure Data Lake Storage Gen2**.
1. Odaberite način povezivanja prostora za **pohranu**. Možete birati između mogućnosti utemeljene na resursima i mogućnosti utemeljene na pretplati za provjeru autentičnosti. Dodatne informacije potražite u članku [Povezivanje s računom Azure Data Lake Storage pomoću programa Azure Service Principal](connect-service-principal.md).
   - Za **pretplatu** na Azure odaberite pretplatu **,** grupu **resursa** i **račun** pohrane koji sadrži `customerinsights` spremnik.
   - Za **ključ** računa navedite **naziv** računa i **ključ** računa za račun data lake pohrane. Korištenje ove metode provjere autentičnosti podrazumijeva da ćete biti obaviješteni ako vaša tvrtka ili ustanova rotira ključeve. Prilikom zakretanja konfiguraciju [okruženja morate](manage-environments.md#edit-an-existing-environment) ažurirati novim ključem.
1. Odaberite želite li koristiti Azure Private Link za povezivanje s računom za pohranu i [stvaranje veze s privatnom vezom](security-overview.md#set-up-an-azure-private-link).

Kada se dovrši sistemski procesi poput gutanja podataka, sustav stvara odgovarajuće mape na računu za pohranu. Podatkovne datoteke i datoteke model.json stvaraju se i dodaju u mape na temelju naziva procesa.

Ako stvorite više okruženja za Customer Insights i odlučite spremiti izlazne entitete iz tih okruženja na svoj račun za pohranu, Customer Insights stvara zasebne mape za svako okruženje s `ci_environmentID` u spremniku.
