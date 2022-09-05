---
title: Rad s API-jima Customer Insights
description: Koristite API-je i shvatite ograničenja.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387331"
---
# <a name="work-with-customer-insights-apis"></a>Rad s API-jima Customer Insights

Dynamics 365 Customer Insights pruža API-je za izradu vlastitih aplikacija na temelju vaših podataka u značajci Customer Insights.

> [!IMPORTANT]
> Pojedinosti o tim API-jima navedeni su u [Referenci za API-je za Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Oni uključuju dodatne informacije o operacijama, parametrima i odgovorima.

Isprobajte API-jevi customer insights, izradite registraciju aplikacije azure i započnite s bibliotekama klijenata.

## <a name="get-started-trying-the-customer-insights-apis"></a>Početak s isprobavanjem API-ja za Customer Insights

Omogućite API-jeve uvida kupaca i isprobajte ih. Administrator customer insightsa mora omogućiti pristup API-ju uvidima u kupce. Nakon što je pristup omogućen, svaki korisnik može koristiti API s ključem pretplate.

1. [Prijavite se](https://home.ci.ai.dynamics.com) u Customer Insights. Ako još nemate pretplatu, [prijavite se za probnu verziju Customer Insights](https://aka.ms/tryci).

1. Otvorite **Sigurnost administratora** > **i** odaberite karticu **API-ji**.

1. Ako API pristup okolišu nije postavljen, odaberite **Omogući**.

   Omogućavanjem API-ja stvara se primarni i sekundarni ključ pretplate za vašu instancu koji se koristi u zahtjevima API-ja. Da biste regenerirali tipke, na kartici API-ji odaberite **Sekundarni regeneratiraj primarni** ili **Regeneriraj sekundarni** **·**.

1. Odaberite [**Istraži naše API-je**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) da biste isprobali API-je.

1. Potražite i odaberite operaciju API-ja, a zatim odaberite **Isprobaj**.

   :::image type="content" source="media/try-api.png" alt-text="Kako testirati API-je.":::

1. U bočnom oknu vrijednost na padajućem izborniku **Autorizacija** postavite na **implicitna**. Zaglavlje `Authorization` dodaje se tokenom nositelja. Ključ pretplate automatski se popunjava.
  
1. Po želji dodajte sve potrebne parametre upita.

1. Pomaknite se do dna bočnog okna pa odaberite **Pošalji**.

   HTTP odgovor prikazuje se pri dnu okna.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Stvaranje nove registracije aplikacije na Azure portalu

Stvorite novu [registraciju](/graph/auth-register-app-v2) aplikacije da biste koristili API-je customer insights u aplikaciji servisa Azure pomoću ovlaštenih dozvola.

1. [Dovršite odjeljak](#get-started-trying-the-customer-insights-apis) Prvi koraci.

1. Prijavite se na [Azure portal](https://portal.azure.com) s računom koji može pristupiti podacima Customer Insights.

1. Potražite, a zatim odaberite **Registracije** aplikacija.

1. Odaberite **Nova registracija**, navedite naziv aplikacije pa odaberite vrstu računa.

   Ako želite, dodajte URL preusmjeravanja. http://localhost dovoljan je za razvoj aplikacije na vašem lokalnom računalu.

1. Odaberite **Registriraj se**.

1. Na novoj registraciji aplikacije idite na **Dozvole API-ja**.

1. Odaberite **Dodaj dozvolu**, a zatim u bočnom oknu odaberite **Dynamics 365 AI za customer insights** .

1. Za opciju **Vrsta dozvole** odaberite **Delegirane dozvole**, a zatim odaberite dozvolu **user_impersonation**.

1. Odaberite **Dodaj dozvole**.

1. Odaberite **Daj pristanak administratora za...** da biste dovršili registraciju aplikacije.

1. Da biste pristupili API-ju bez prijave korisnika, idite na [dozvole aplikacije od poslužitelja do poslužitelja](#server-to-server-application-permissions).

ID aplikacije/klijenta možete koristiti za registraciju ove aplikacije u Microsoftovoj [biblioteci autentifikacije (MSAL)](/azure/active-directory/develop/msal-overview) da biste dobili token nositelja koji će poslati sa svojim zahtjevom API-ju.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Za informacije o korištenju API-ja u našim klijentskim bibliotekama pogledajte [Klijentske bliblioteke značajke Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Dozvole aplikacije s poslužitelja na poslužitelj

Izradite registraciju aplikacije koja ne treba interakciju s korisnikom i koja se može pokrenuti na poslužitelju.

1. Na registraciji svoje aplikacije na Azure portalu idite na **Dozvole API-ja**.

1. Odaberite **Dodaj dozvolu**.

1. Odaberite karticu **API-ji koje koristi moja tvrtka ili ustanova** pa s popisa odaberite **Dynamics 365 AI za Customer Insights**.

1. Za opciju **Vrsta dozvole** odaberite **Dozvole aplikacije**, a zatim odaberite dozvolu **CustomerInsights.Api.All**.

1. Odaberite **Dodaj dozvole**.

1. Vratite se na **Dozvole API-ja** za registraciju svoje aplikacije.

1. Odaberite **Daj pristanak administratora za...** da biste dovršili registraciju aplikacije.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Dodajte naziv registracije aplikacije kao korisnika u Customer Insights.

   1. Otvorite Customer Insights, idite na **Sigurnost administratora** > **i** odaberite **Dodaj korisnike**.

   1. Potražite naziv registracije svoje aplikacije, odaberite ga iz rezultata pretraživanja pa odaberite **Spremi**.

## <a name="sample-queries"></a>Ogledni upiti

Kratki popis OData oglednih upita za rad s API-jevima potražite [u primjerima](odata-examples.md) upita OData.

## <a name="customer-insights-client-libraries"></a>Klijentske biblioteke Customer Insights

Počnite koristiti klijentske biblioteke dostupne za API-je uvide u klijente. Svi izvorni kodovi biblioteke i ogledne aplikacije mogu se naći na [stranici servisa GitHub za Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

NuGet Trenutno paket cilja okvire netstandard2.0 i netcoreapp2.0 i netcoreapp2.0. Dodatne informacije o paketu potražite u NuGet članku [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Dodavanje klijentske biblioteke za C# projektu u C#

1. U Visual Studio otvorite **Upravitelj paketa NuGet** za svoj projekt.

1. Potražite **Microsoft.Dynamics.CustomerInsights.Api**.

1. Odaberite **Instaliraj** za dodavanje paketa u projekt.

   Alternativno, pokrenite ovu naredbu u **Konzoli upravitelja paketa NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Korištenje klijentske biblioteke za C#

1. Koristite [Microsoftovu biblioteku za provjeru autentičnosti (MSAL)](/azure/active-directory/develop/msal-overview) da biste dobili `AccessToken` koristeći svoju postojeću [Registraciju Azure aplikacije](#create-a-new-app-registration-in-the-azure-portal).

1. Nakon uspješne provjere autentičnosti i stjecanja tokena, izradite novi ili upotrijebite postojeći `HttpClient` s DefaultRequestHeaders "Autorization"**postavljenim** na **Bearer "pristupni token"** i **Ocp-Apim-Subscription-Key** postavljenim na [**pretplatnički ključ** iz okruženja](#get-started-trying-the-customer-insights-apis) Customer Insights.   

   Po potrebi resetirajte zaglavlje **Authorization**. Primjerice, kada token istekne.

1. Proslijedite ovaj `HttpClient` u izgradnju klijenta `CustomerInsights`.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Uputite pozive s klijentom na „metode produženja“,, primjerice `GetAllInstancesAsync`. Ako je pristup podlozi `Microsoft.Rest.HttpOperationResponse` preferiran, koristite "http metode poruka", na primjer, `GetAllInstancesWithHttpMessagesAsync`.

1. Odgovor je vjerojatno `object` tip jer metoda može vratiti više vrsta (na primjer, `IList<InstanceInfo>` i `ApiErrorResult`). Da biste provjerili vrstu povrata, za tu operaciju koristite objekte u vrstama odgovora navedenim na [stranici](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) s detaljima API-ja.

   Ako su potrebne dodatne informacije o zahtjevu, upotrijebite **http metode poruka** za pristup neobrađenom objektu odgovora.

### <a name="nodejs-package"></a>Paket NodeJS

Upotrijebite klijentske biblioteke NodeJS dostupne putem NPM-a: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Paket Python

Upotrijebite klijentske biblioteke Python dostupne putem PyPi-ja: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
