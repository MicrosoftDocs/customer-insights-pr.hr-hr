---
title: Česta pitanja o probnoj verziji za Dynamics 365 Customer Insights
description: Rješenja za uobičajena pitanja povezana s postavljanjem probne verzije aplikacije Customer Insights i njezinim upravljanjem. Saznajte kako riješiti probleme s platformom specifične za aplikaciju.
author: m-hartmann
ms.author: mhart
ms.date: 09/30/2021
ms.topic: get-started
ms.service: customer-insights
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 2837ae13b4150310193a2d09d59aed66b4a69c69
ms.sourcegitcommit: e6020c178a61beb0ee31a031c11ded914d10d995
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/13/2021
ms.locfileid: "7642854"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Najčešća pitanja u vezi probne verzije sustava Dynamics 365 Customer Insights

## <a name="sign-up"></a>Registracija

### <a name="what-are-the-system-requirements-for-the-trial"></a>Koji su sistemski preduvjeti za probnu verziju?

Ova je aplikacija usluga koja se temelji na oblaku i ne zahtijeva posebni softver, osim ažuriranog web-preglednika, iako vrijede neka ograničenja. Za najbolje iskustvo rada s probnom verzijom izbjegavajte pristupiti web-mjestu probne verzije u anonimnom načinu rada i odaberite lokaciju probne verzije koja vam je najbliža. [Saznajte više o zahtjevima za web-aplikaciju.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Kako se registrirati probnu verziju bez klijenta sustava Microsoft 365?

Možete unijeti adresu e-pošte koja nije poslovna i mi ćemo za vas stvoriti račun i klijenta.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Mogu li se registrirati za više aplikacija sustava Dynamics 365, kao što su Sales, Marketing i Customer Service?

Da, možete. Da biste pregledali sve dostupne probne verzije, [posjetite stranicu središta za probne verzije](https://dynamics.microsoft.com/dynamics-365-free-trial). Možete koristiti isti račun e-pošte da biste se registrirali za različite probne verzije. Međutim, nije moguće imati više aplikacija na istom web-mjestu probne verzije. Svaka će probna verzija biti u različitoj tvrtki ili ustanovi ili na različitom URL-u. Podaci probne verzije neće se dijeliti među aplikacijama.

## <a name="trial-app"></a>Probna verzija aplikacije

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Nisam primio e-poštu s pojedinostima o probnom razdoblju nakon prijave, što da učinim?

Kada se registrirate za probnu verziju, dobit ćete poruku e-pošte s pojedinostima o probnoj verziji. Ako ne vidite poruku e-pošte u svojoj ulaznoj pošti, provjerite mapu neželjene e-pošte. Ili umjesto toga, poduzmite sljedeće korake da biste pristupili aplikaciji:

1. Idite na web-mjesto probne verzije i odaberite **Isprobaj besplatno**.
1. Unesite ID e-pošte koju ste koristili da biste se registrirali za probnu verziju. Bit ćete preusmjereni na probnu verziju aplikacije.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Kako mogu dodati veći broj korisnika probnoj verziji?

Da biste dodali korisnike, idite u [Centar za administratore sustava Microsoft 365](https://admin.microsoft.com) pomoću računa administratora za probnu verziju. Slijedite [Vodič centra za administratore](/microsoft-365/admin/add-users/add-users) da biste dodali korisnike do ograničenja licence probne verzije. Ako korisnik kojeg dodajete već ima račun sustava Microsoft 365, dodijelite mu odgovarajuću sigurnosnu ulogu u tvrtki ili ustanovi probne verzije. Za više informacija pogledajte [Dodjela sigurnosne uloge korisniku](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Koliko korisnika mogu dodati u svoje probno okruženje?

Probnom okruženju možete dodati neograničen broj korisnika.

### <a name="how-do-i-reset-the-trial-environment"></a>Kako ponovno postaviti okruženje probne verzije?

Ne možete ponovno postaviti probno okruženje. Međutim, možete pričekati da probno razdoblje završi i zatim se ponovno registrirati za novu probnu verziju.

## <a name="trial-expiration-and-extension"></a>Istek i produljenje probne verzije

### <a name="how-do-i-extend-the-trial"></a>Kako produljiti probnu verziju?

Probno razdoblje u aplikaciji možete produžiti izravno. Probno razdoblje možete produljiti jednom.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Mogu li pretvoriti probnu verziju u plaćenu licencu?

Općenito preporučujemo da počnete iznova s vlastitim podacima prilikom nadogradnje na plaćenu verziju Customer Insights. 

Izborno, ako koristite samo uvide u ciljne skupine, možete kopirati svoje podatke iz probnog okruženja ako kupite Customer Insights. Morate biti administrator probne verzije Customer Insights i globalni administrator vašeg klijenta za Microsoft 365 ili administrator sustava Dynamics 365 u vašoj tvrtki ili ustanovi za premještanje postavki iz probnog okruženja u plaćeno okruženje. 

Nakon što se prvi put prijavite u svoju plaćenu instancu Customer Insights, od vas će se tražiti da stvorite novo okruženje. U ovom procesu možete odabrati kopiranje konfiguracije iz postojećeg okruženja i premještanje većine postavki. Ako imate gore navedene dozvole, probno okruženje prikazat će se na ovom popisu. Za više informacija pogledajte [Kopiranje konfiguracije okruženja](audience-insights/manage-environments.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Koja su ograničenja i kvote probne verzije?

- Ne možete koristiti vlastiti račun za pohranu za Azure Data Lake kako biste pohranili izlazne podatke tijekom upotrebe probne verzije uvida u ciljne skupine. Međutim, možete unijeti podatke s računa za pohranu Data Lake.
- Možete spremiti do 3 GB podataka u okruženje Dataverse kojemu se automatski dodjeljuju sredstva kada pokrenete probnu verziju aplikacije Customer Insights.

## <a name="customer-insights-specific-questions"></a>Customer Insights – specifična pitanja

### <a name="how-do-i-start-using-the-trial"></a>Kako započeti koristiti probnu verziju?

Nakon što se registrirate za probnu verziju, dospjet ćete na glavni zaslon aplikacije. Glavni zaslon pruža veze za korisničke vodiče i priručnike. Da biste saznali više, posjetite veze u [Dodatnim resursima](trial-signup.md#additional-resources) na stranici za postavljanje probne verzije.

### <a name="what-features-are-available-in-the-trial"></a>Koje su značajke dostupne u probnoj verziji?

Većina značajki mogućnosti aplikacije Customer Insights dostupno je u probnom razdoblju.

Sljedeća značajka nije dostupna: 
- Ne možete stvoriti nova okruženja koja koriste vlastiti račun za pohranu za Azure Data Lake.

### <a name="how-long-does-the-trial-last"></a>Koliko dugo traje probna verzija?

Probno razdoblje aplikacije Customer Insights traje 30 dana. Probno razdoblje možete produžiti jednom nakon 23 dana kada se prijavite u svoje probno okruženje.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Kako ukloniti uzorak podataka iz probne verzije?

Ne možete ukloniti ogledne podatke iz probne verzije.