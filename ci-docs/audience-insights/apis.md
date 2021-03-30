---
title: Rad s API-jima
description: Koristite API-je i shvatite ograničenja.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710451"
---
# <a name="work-with-customer-insights-apis"></a>Rad s API-jima Customer Insights

Dynamics 365 Customer Insights pruža API-je za izradu vlastitih aplikacija na temelju vaših podataka u Customer Insights.

> [!IMPORTANT]
> Pojedinosti o tim API-jima navedeni su [u Referenci za API-je za Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Oni uključuju dodatne informacije o operacijama, parametrima i odgovorima.

Ovaj članak vodi vas do pristupa API-jiima za Customer Insights, izrade registracije Azure aplikacije i pomoći vam da započnete s dostupnim klijentskim bibliotekama.

## <a name="get-started-trying-the-customer-insights-apis"></a>Početak s isprobavanjem API-ja za Customer Insights

1. [Prijavite se](https://home.ci.ai.dynamics.com) u Customer Insights. Ako još nemate pretplatu, [prijavite se za probnu verziju Customer Insights](https://aka.ms/tryci).

1. Da biste omogućili API-je u svom okruženju Customer Insights, idite na **Administrator** > **Dozvole**. Za to će vam trebati administratorske dozvole.

1. Idite na karticu **API-ji** pa odaberite gumb **Omogući**.    
   Omogućavanjem API-ja stvara se primarni i sekundarni ključ pretplate za vašu instancu koji se koristi u zahtjevima API-ja. Ključeve možete ponovno generirati odabirom **Ponovno generiraj primarni** ili **Ponovno generiraj sekundarni** na **Administrator** > **Dozvole** > **API-ji**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Omogućavanje API-jeva za Customer Insights":::

1. Odaberite **Istražite naše API-je** da [isprobate API-je](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Odaberite operaciju API-ja pa odaberite **Isprobaj**.

1. U bočnom oknu vrijednost u padajućem izborniku **Ovlaštenje** postavite na **implicitno**. Zaglavlje `Authorization` dobiva s dodanim tokenom nositelja. Vaš ključ pretplate automatski će se popuniti.
  
1. Po želji dodajte sve potrebne parametre upita.

1. Pomaknite se do dna bočnog okna pa odaberite **Pošalji**.

HTTP odgovor uskoro će se pojaviti u nastavku.


   :::image type="content" source="media/try-apis.gif" alt-text="Animirani gif koji pokazuje kako odabrati testiranje API-ja.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Stvaranje nove registracije aplikacije na Azure portalu

Ovi vam koraci pomažu u početku korištenja API-ja Customer Insights u Azure aplikaciji pomoću delegiranih dozvola. Svakako prvo dovršite [odjeljak Početak](#get-started-trying-the-customer-insights-apis).

1. Prijavite se na [Azure portal](https://portal.azure.com) s računom koji može pristupiti podacima Customer Insights.

1. S lijeve strane odaberite **Registracije aplikacija**.

1. Odaberite **Nova registracija**, navedite naziv aplikacije pa odaberite vrstu računa.
   Ako želite, dodajte URL preusmjeravanja. http://localhost dovoljan je za razvoj aplikacije na vašem lokalnom računalu.

1. Na novoj registraciji aplikacije idite na **Dozvole API-ja**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Animirani gif za postavljanje dozvole API-ja u registraciji aplikacije.":::

1. Odaberite **Dodaj dozvolu** pa odaberite **Customer Insights** u bočnom oknu.

1. Za **Vrsta dozvole** odaberite **Delegirane dozvole** pa odaberite dozvolu **user_impersonation**.

1. Odaberite **Dodaj dozvole**. Ako trebate pristupiti API-ju bez prijave korisnika, pregledajte odjeljak [Dozvole aplikacija s poslužitelja na poslužitelj](#server-to-server-application-permissions).

1. Odaberite **Daj pristanak administratora za...** da biste dovršili registraciju aplikacije.

Možete koristiti ID aplikacije/klijenta za registraciju ove aplikacije u Microsoftovoj biblioteci za provjeru autentičnosti (MSAL) da biste dobili token nositelja koji će se s vašim zahtjevom poslati API-ju.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Animirani gif za davanje pristanka administratora.":::

Za više informacija o MSAL-u pogledajte [Pregled Microsoftove biblioteke za provjeru autentičnosti (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Za više informacija o registraciji aplikacija na platformi Azure pogledajte [Novo iskustvo registracije aplikacija Azure portala](/azure/active-directory/develop/app-registration-portal-training-guide).

Za informacije o korištenju API-ja naših klijentskih biblioteke pogledajte [Klijentske biblioteke Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Dozvole aplikacije s poslužitelja na poslužitelj

U [odjeljku za registraciju aplikacije](#create-a-new-app-registration-in-the-azure-portal) opisuje se kako registrirati aplikaciju koja zahtijeva da se korisnik prijavi radi provjere autentičnosti. Saznajte kako stvoriti registraciju aplikacije koja ne treba interakciju korisnika i može se pokrenuti na poslužitelju.

1. Na registraciji svoje aplikacije na Azure portalu idite na **Dozvole API-ja**.

1. Odaberite **Dodaj dozvolu** pa odaberite **Customer Insights** u bočnom oknu.

1. Za **Vrsta dozvole** odaberite **Dozvole aplikacija** pa odaberite dozvolu **CustomerInsights.Api.All**.

1. Odaberite **Dodaj dozvole**.

1. Da biste dali pristanak administratora na ovu dozvolu aplikaciju, morate dodati upravitelja servisa.

   1. Instalirajte Azure Active Directory (AD) PowerShell modul: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Povežite se na svoj račun za AD: `Connect-AzureAD -TenantId <your tenant id>`. Svoj ID klijenta možete pronaći na **Pregled** > **Azure Active Directory**.
   1. Pokrenite sljedeću naredbu za dodavanje Azure AD upravitelja servisa: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Parametar AppId odnosi se na aplikaciju Customer Insights API-ja.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Ogledni upravitelj servisa":::

1. Vratite se na **Dozvole API-ja** za registraciju svoje aplikacije.

1. Odaberite **Daj pristanak administratora za...** da biste dovršili registraciju aplikacije.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Animirani gif za davanje pristanka administratora.":::

1. Da zaključimo, moramo dodati naziv registracije aplikacije kao korisnika u Customer Insights.    
   Otvorite Customer Insights, idite na **Administrator** > **Dozvole** pa odaberite **Dodaj korisnika**.

1. Potražite naziv registracije svoje aplikacije, odaberite ga iz rezultata pretraživanja pa odaberite **Spremi**.

## <a name="customer-insights-client-libraries"></a>Klijentske biblioteke Customer Insights

Ovaj vam odjeljak pomaže u početku korištenja klijentskih knjižnica dostupnih za API-je Customer Insights. Svi izvorni kodovi biblioteke i ogledne aplikacije mogu se naći na [stranici servisa GitHub za Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Naučite kako započeti s korištenjem klijentskih biblioteka za C# s NuGet.org. Za više informacija o paketu NuGet pogledajte [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Trenutačno ovaj paket cilja okvire netstandard2.0 i netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Dodavanje klijentske biblioteke za C# projektu u C#

1. U Visual Studio otvorite **Upravitelj paketa NuGet** za svoj projekt.

1. Potražite **Microsoft.Dynamics.CustomerInsights.Api**.

1. Odaberite **Instaliraj** za dodavanje paketa u projekt.
   Alternativno, pokrenite ovu naredbu u **Konzoli upravitelja paketa NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Dodavanje NuGet paketa Visual Studio projektu":::

#### <a name="use-the-c-client-library"></a>Korištenje klijentske biblioteke za C#

1. Koristite [Microsoftovu biblioteku za provjeru autentičnosti (MSAL)](/azure/active-directory/develop/msal-overview) da biste dobili `AccessToken` koristeći svoju postojeću [Registraciju Azure aplikacije](#create-a-new-app-registration-in-the-azure-portal).

1. Nakon uspješne autentifikacije i stjecanja tokena, izgradite novi ili upotrijebite postojeći `HttpClient` s dodatnim **DefaultRequestHeaders "Authorization"** postavljenim na **Nositelj <access token>** i **Ocp-Apim-Subscription-Key** postavljenim na [**ključ pretplate** iz svog okruženja Customer Insights](#get-started-trying-the-customer-insights-apis).    
   Po potrebi resetirajte zaglavlje **Authorization**. Primjerice, kada token istekne.

1. Proslijedite ovaj `HttpClient` u izgradnju klijenta `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Ogledni httpclient":::

1. Uputite pozive s klijentom na „metode produženja“,, primjerice `GetAllInstancesAsync`. Ako se preferira pristup temeljnom `Microsoft.Rest.HttpOperationResponse`, upotrijebite "metode poruka http", primjerice `GetAllInstancesWithHttpMessagesAsync`.

1. Odgovor će vjerojatno biti vrste `object` jer metoda može vratiti više vrsta (primjerice `IList<InstanceInfo>` i `ApiErrorResult`). Da biste provjerili vrstu povrata, možete sigurno pretvoriti objekte u vrste odgovora navedene na [stranica s pojedinostima API-ja](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) za tu operaciju.    
   Ako su potrebne dodatne informacije o zahtjevu, upotrijebite **http metode poruka** za pristup neobrađenom objektu odgovora.

### <a name="nodejs-package"></a>Paket NodeJS

Upotrijebite klijentske biblioteke NodeJS dostupne putem NPM-a: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Paket Python

Upotrijebite klijentske biblioteke Python dostupne putem PyPi-ja: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
