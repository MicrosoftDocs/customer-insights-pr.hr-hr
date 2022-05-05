---
title: Neka vaš vlastiti sef za ključeve platforme Azure upravlja tajnama
description: Saznajte kako konfigurirati Customer Insights za upotrebu vlastitog sefa za ključeve platforme Azure.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 9eb06a1190fe4e8012ecd3d6742b8b3f5f4d6349
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653468"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Povezivanje vlastitog sefa za ključeve platforme Azure (pretpregled)

Povezivanje namjenskog [trezora](/azure/key-vault/general/basic-concepts) s ključevima servisa Azure s okruženjem Customer Insights pomaže organizacijama da ispune zahtjeve usklađenosti.
Namjenski sef za ključeve može se koristiti za postavljanje i korištenje tajni u granicama usklađenosti tvrtke ili ustanove. Customer Insights može koristiti tajne u trezoru ključeva servisa Azure za [postavljanje veza sa](connections.md) sustavima drugih proizvođača.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Povezivanje trezora ključeva s okruženjem Customer Insights

### <a name="prerequisites"></a>Preduvjeti

Da biste konfigurirali trezor s ključevima u customer insightsu, moraju se ispuniti sljedeći preduvjeti:

- Morate imati aktivnu pretplatu za na Azure.

- Imate administratorsku [ulogu](permissions.md#admin) u korisničkom uvidu. Saznajte više o [korisničkim dozvolama u odjeljku Customer Insights](permissions.md#assign-roles-and-permissions).

- Imate ulogu [suradnika](/azure/role-based-access-control/built-in-roles#contributor) i [administratora pristupa korisnika](/azure/role-based-access-control/built-in-roles#user-access-administrator) u sefu za ključeve ili grupi resursa kojima pripada sef za ključeve. Dodatne informacije potražite u odjeljku [Dodavanje ili uklanjanje dodjele uloga na platformi Azure putem portala Azure](/azure/role-based-access-control/role-assignments-portal). Ako nemate ulogu administratora pristupa za korisnike u sefu za ključeve, morate postaviti dopuštenja za kontrolu pristupa temeljena na ulogama za upravitelja usluge Azure za Dynamics 365 Customer Insights. Slijedite korake kako biste [upotrijebili upravitelja usluge Azure](connect-service-principal.md) za sef za ključeve koji treba povezati.

- Sef za ključeve mora imati **onemogućen** vatrozid sefa za ključeve.

- Trezor za ključeve nalazi se na istoj [lokaciji](https://azure.microsoft.com/global-infrastructure/geographies/#overview) servisa Azure kao i okruženje Customer Insights. Regija okruženja u customer insights navedena je pod **AdminSystemAboutRegion** > **·** > **·** > **·**.

### <a name="link-a-key-vault-to-the-environment"></a>Povezivanje sefa za ključeve s okruženjem

1. Otvorite **Administratorska** > **sigurnost**, a zatim odaberite karticu Trezor **ključeva**.
1. Na pločici **Sef za ključeve** odaberite **Postavljanje**.
1. Odaberite **Pretplata**.
1. Odaberite sef za ključeve s padajućeg popisa **Sef za ključeve**. Ako se prikazuje previše sefova za ključeve, odaberite grupu resursa kako biste ograničili rezultate pretraživanja.
1. Prihvatite izjavu **Privatnost podataka i sukladnost**.
1. Odaberite **Spremi**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Koraci za postavljanje povezanog trezora ključeva u customer insights.":::

Pločica **Sef za ključeve** sada prikazuje naziv povezanog sefa za ključeve, grupu resursa i pretplatu. Spremno je za upotrebu u postavljanju veze.
Detalje o tome koja su dopuštenja za trezor za ključeve dodijeljena uvidima kupaca potražite [u odjeljku Dozvole dodijeljene u trezoru ključeva](#permissions-granted-on-the-key-vault) u nastavku ovog članka.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Upotreba sefa za ključeve u postavljanju veze

Kada [uspostavljate veze](connections.md) sa sustavima trećih strana, tajne iz povezanog sefa za ključeve mogu se koristiti za konfiguriranje veza.

1. Idite na **Admin** > **Veze**.
1. Odaberite **Dodaj vezu**.
1. Za podržane vrste povezivanja dostupan je preklopni gumb **Upotrijebi sef za ključeve** ako ste povezali sef za ključeve.
1. Umjesto ručnog unosa tajne, možete odabrati tajni naziv koji upućuje na tajnu vrijednost u sefu za ključeve.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Okno za povezivanje s SFTP vezom koja koristi tajnu sefa za ključeve.":::

## <a name="supported-connection-types"></a>Podržane vrste veze

Podržane su sljedeće veze za [izvoz](export-destinations.md):

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Dozvole dodijeljene u trezoru ključeva

Sljedeće dozvole dodjeljuju se uvidima korisnika u povezanom trezoru ključeva ako [je omogućeno pravilo pristupa trezoru ključeva](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ili [kontrola pristupa utemeljenoj na ulogama](/azure/key-vault/general/rbac-guide?tabs=azure-cli) na servisu Azure.

### <a name="key-vault-access-policy"></a>Pravila pristupa sefu za ključeve

| Tip        | Dopuštenja          |
| ----------- | -------------------- |
| Tipka         | [Dohvati ključeve](/rest/api/keyvault/get-keys), [Dohvati ključ](/rest/api/keyvault/get-key)                                 |
| Tajno      | [Dohvati tajne](/rest/api/keyvault/get-secrets), [Dohvati tajnu](/rest/api/keyvault/get-secret)                     |
| Certifikat | [Dohvati certifikate](/rest/api/keyvault/get-certificates), [Dohvati certifikat](/rest/api/keyvault/get-certificate) |

Prethodne vrijednosti minimalne su za popis i čitanje tijekom izvođenja.

### <a name="azure-role-based-access-control"></a>Kontrola pristupa na Azure temeljena na ulogama

Korisničke uloge Čitatelj i tajni key vaulta bit će dodane za customer insights. Za pojedinostima o tim ulogama idite na [Ugrađene uloge platforme Azure za rad s podacima sefa za ključeve](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Preporuke

- Koristite zaseban ili namjenski trezor ključeva koji sadrži samo tajne potrebne za Customer Insights. Pročitajte više o tome zašto [se preporučuju zasebni sefovi za ključeve](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Slijedite [najbolje prakse za korištenje sefa za ključeve](/azure/key-vault/general/best-practices#turn-on-logging) za mogućnosti kontrole pristupa, sigurnosne kopije, revizije i oporavka.

## <a name="frequently-asked-questions"></a>Najčešća pitanja

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Mogu li Customer Insights pisati tajne ili prebrisati tajne u trezor za ključeve?

Ne. Uvidima kupaca dodijeljene su samo dozvole za čitanje i popis navedene u [odjeljku odobrene](#permissions-granted-on-the-key-vault) dozvole iz prethodnog članka. Sustav ne može dodavati, brisati ili prepisivati tajne u sefu za ključeve. To je i razlog zašto ne možete unijeti vjerodajnice kada veza koristi sef za ključeve.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Mogu li promijeniti vezu s korištenja tajni sefa za ključeve na zadanu provjeru autentičnosti?

Ne. Ne možete se vratiti na zadanu vezu nakon što ste je konfigurirali s pomoću tajne iz povezanog sefa za ključeve. Stvorite zasebnu vezu i izbrišite staru ako vam više ne treba.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Kako mogu opozvati pristup trezoru ključeva za Customer Insights?

Ovisno o tome je li omogućena opcija [Pravila pristupa sefu za ključeve](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ili [Kontrola pristupa za Azure temeljena na ulogama](/azure/key-vault/general/rbac-guide?tabs=azure-cli), morate ukloniti dozvole za upravitelja usluge`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` pod nazivom `Dynamics 365 AI for Customer Insights`. Sve veze koje koriste sef za ključeve prestat će raditi.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Tajna koja se koristi u vezi uklonjena je iz sefa za ključeve. Što mogu učiniti?

Obavijest se pojavljuje u customer insights kada konfigurirana tajna iz trezora ključeva više nije dostupna. Omogućite [privremeno brisanje](/azure/key-vault/general/soft-delete-overview) na sefu za ključeve radi vraćanja tajni ako su slučajno uklonjene.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Veza ne radi, ali moja tajna je u sefu za ključeve. Što bi mogao biti uzrok?

Obavijest se pojavljuje u customer insights kada ne može pristupiti trezoru ključeva. Uzrok može biti:

- Dozvole za upravitelja usluge Customer Insights uklonjene su. Potrebno ih je ručno obnoviti.

- Vatrozid na sefu za ključeve je omogućen. Vatrozid mora biti onemogućen kako bi trezor za ključeve ponovno bio dostupan uvidima u kupce.
