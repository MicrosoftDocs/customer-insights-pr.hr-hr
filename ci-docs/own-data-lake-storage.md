---
title: Koristite vlastiti Azure Data Lake Storage Gen2 račun
author: mukeshpo
description: Informirajte se o preduvjetima za korištenje vlastitog Azure Data Lake Storage računa za pohranu podataka Customer Insights.
ms.author: mukeshpo
ms.date: 05/30/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 9fcd7645e34bf310ac3a1b98a0dd9a60598b19dc
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833942"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Koristite vlastiti Azure Data Lake Storage Gen2 račun

Dynamics 365 Customer Insights daje vam mogućnost pohrane svih podataka u [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Spremanjem podataka u data lake pohranu slažete se da će se podaci prenositi i pohranjivati na odgovarajuće zemljopisno mjesto za taj račun za pohranu na servisu Azure. Dodatne informacije potražite u članku [Microsoftov centar za pouzdanost](https://www.microsoft.com/trust-center).

Administratori u customer insights mogu [stvoriti okruženja](create-environment.md) i [odrediti mogućnost](create-environment.md#step-2-configure-data-storage) pohrane podataka u tom procesu.

## <a name="prerequisites-to-use-your-storage-account"></a>Preduvjeti za korištenje računa za pohranu

- Azure Data Lake Storage računi moraju biti u istoj regiji servisa Azure koju ste odabrali prilikom stvaranja okruženja Customer Insights. Regiju okruženja Customer Insights možete provjeriti u odjeljku **O sustavu administratora** > **·** > **.**
- Data Lake Storage mora biti Gen2 i imati [omogućen](/azure/storage/blobs/create-data-lake-storage-account) hijerarhijski prostor za naziv. Računi za pohranu u gen1 nisu podržani.
- Imenovani `customerinsights` spremnik mora postojati na računu za pohranu. Morate ga stvoriti prije nego što koristite vlastitu pohranu na jezeru podataka u Customer Insights. Administratoru koji postavlja okruženje Customer Insights potrebna je uloga Pohrane blobo podataka suradnik ili Vlasnika podataka o blobu pohrani na računu za pohranu ili spremniku`customerinsights`. Dodatne informacije o dodjeli dozvole na računu za pohranu potražite u članku [Stvaranje računa](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) za pohranu.

## <a name="connect-customer-insights-with-your-storage-account"></a>Povezivanje uvida kupaca s računom za pohranu

Kada stvorite novo okruženje, provjerite postoji li račun za pohranu na servisu Data Lake i jesu li ispunjeni svi preduvjeti.

1. U koraku pohrane **podataka** tijekom stvaranja okruženja postavite **Spremi izlazne podatke** na **Azure Data Lake Storage Gen2**.
1. Odaberite način povezivanja prostora za **pohranu**. Možete birati između mogućnosti utemeljene na resursima i mogućnosti utemeljene na pretplati za provjeru autentičnosti. Dodatne informacije potražite u članku [Povezivanje s računom Azure Data Lake Storage pomoću programa Azure Service Principal](connect-service-principal.md).
   - Za **pretplatu** na Azure odaberite pretplatu **,** grupu **resursa** i **račun** pohrane koji sadrži `customerinsights` spremnik.
   - Za **ključ** računa navedite **naziv** računa i **ključ** računa za račun data lake pohrane. Korištenje ove metode provjere autentičnosti podrazumijeva da ćete biti obaviješteni ako vaša tvrtka ili ustanova rotira ključeve. Prilikom zakretanja konfiguraciju [okruženja morate](manage-environments.md#edit-an-existing-environment) ažurirati novim ključem.

Kada se dovrši sistemski procesi poput gutanja podataka, sustav stvara odgovarajuće mape na računu za pohranu. Podatkovne datoteke i datoteke *model.json* stvaraju se i dodaju u mape na temelju naziva procesa.

Ako stvorite više okruženja za Customer Insights i odlučite spremiti izlazne entitete iz tih okruženja na svoj račun za pohranu, Customer Insights stvara zasebne mape za svako okruženje s `ci_environmentID` u spremniku.
