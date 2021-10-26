---
title: Neka vaš vlastiti sef za ključeve platforme Azure upravlja tajnama
description: Saznajte kako konfigurirati Customer Insights za upotrebu vlastitog sefa za ključeve platforme Azure.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: 6f521dfce3e0922238d16beee3be8e1bbcfc63a5
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606048"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Povezivanje vlastitog sefa za ključeve platforme Azure (pretpregled)

Povezivanje namjenskog [sefa za ključeve platforme Azure](/azure/key-vault/general/basic-concepts) s okruženjem za uvide u ciljne skupine pomaže tvrtkama ili ustanovama da ispune zahtjeve usklađenosti.
Namjenski sef za ključeve može se koristiti za postavljanje i korištenje tajni u granicama usklađenosti tvrtke ili ustanove. Uvidi u ciljne skupine mogu koristiti tajne u sefu za ključeve platforme Azure za [uspostavu veza](connections.md) sa sustavima trećih strana.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Povezivanje sefa s ključevima s okruženjem za uvide u ciljne skupine

### <a name="prerequisites"></a>Preduvjeti

Da biste konfigurirali sef za ključeve u uvidima u ciljanu skupinu, moraju biti ispunjeni sljedeći preduvjeti:

- Morate imati aktivnu pretplatu za na Azure.

- Imate ulogu [Administrator](permissions.md#administrator) u uvidima u ciljne skupine. Saznajte više o [korisničkim dozvolama u uvidima u ciljne skupine](permissions.md#assign-roles-and-permissions).

- Imate ulogu [suradnika](/azure/role-based-access-control/built-in-roles#contributor) i [administratora pristupa korisnika](/azure/role-based-access-control/built-in-roles#user-access-administrator) u sefu za ključeve ili grupi resursa kojima pripada sef za ključeve. Dodatne informacije potražite u odjeljku [Dodavanje ili uklanjanje dodjele uloga na platformi Azure putem portala Azure](/azure/role-based-access-control/role-assignments-portal). Ako nemate ulogu administratora pristupa za korisnike u sefu za ključeve, morate postaviti dopuštenja za kontrolu pristupa temeljena na ulogama za upravitelja usluge Azure za Dynamics 365 Customer Insights. Slijedite korake kako biste [upotrijebili upravitelja usluge Azure](connect-service-principal.md) za sef za ključeve koji treba povezati.

- Sef za ključeve mora imati **onemogućen** vatrozid sefa za ključeve.

- Sef za ključeve nalazi se na istoj [lokaciji platforme Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) kao okruženje za uvide u ciljne skupine. Područje okruženja u uvidima u ciljne skupine navedeno je u opciji **Administrator** > **Sustav** > **Pojedinosti** > **Regija**.

### <a name="link-a-key-vault-to-the-environment"></a>Povezivanje sefa za ključeve s okruženjem

1. Idite na **Administrator** > **Sustav**, a zatim odaberite karticu **Sigurnost**.
1. Na pločici **Sef za ključeve** odaberite **Postavljanje**.
1. Odaberite **Pretplata**.
1. Odaberite sef za ključeve s padajućeg popisa **Sef za ključeve**. Ako se prikazuje previše sefova za ključeve, odaberite grupu resursa kako biste ograničili rezultate pretraživanja.
1. Prihvatite izjavu **Privatnost podataka i sukladnost**.
1. Odaberite **Spremi**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Koraci za postavljanje povezanog sefa za ključeve u uvidima u ciljne skupine.":::

Pločica **Sef za ključeve** sada prikazuje naziv povezanog sefa za ključeve, grupu resursa i pretplatu. Spremno je za upotrebu u postavljanju veze.
Za pojedinosti o tome koje su dozvole za sef za ključeve dodijeljene uvidima u ciljne skupine idite na odjeljak [Dozvole odobrene za sef za ključeve uvidima u ciljne skupine](#permissions-granted-on-the-key-vault-to-audience-insights), kasnije u ovom članku.

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Dozvole odobrene za sef za ključeve uvidima u ciljne skupine

Sljedeće dozvole odobravaju se uvidima u ciljne skupine na povezanom sefu za ključeve ako je omogućena opcija [Pravila pristupa sefu za ključeve](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ili [Kontrola pristupa na Azure temeljena na ulogama](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

### <a name="key-vault-access-policy"></a>Pravila pristupa sefu za ključeve

| Tip        | Dopuštenja          |
| ----------- | -------------------- |
| Tipka         | [Dohvati ključeve](/rest/api/keyvault/get-keys), [Dohvati ključ](/rest/api/keyvault/get-key)                                 |
| Tajno      | [Dohvati tajne](/rest/api/keyvault/get-secrets), [Dohvati tajnu](/rest/api/keyvault/get-secret)                     |
| Certifikat | [Dohvati certifikate](/rest/api/keyvault/get-certificates), [Dohvati certifikat](/rest/api/keyvault/get-certificate) |

Prethodne vrijednosti minimalne su za popis i čitanje tijekom izvođenja.

### <a name="azure-role-based-access-control"></a>Kontrola pristupa na Azure temeljena na ulogama

Uloge čitača sefa za ključeve i korisnika tajni sefa za ključeve dodat će se za uvide u ciljne skupine. Za pojedinostima o tim ulogama idite na [Ugrađene uloge platforme Azure za rad s podacima sefa za ključeve](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Preporuke

- Upotrijebite zaseban ili namjenski sef za ključeve koji sadrži samo tajne potrebne za uvide u ciljne skupine. Pročitajte više o tome zašto [se preporučuju zasebni sefovi za ključeve](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Slijedite [najbolje prakse za korištenje sefa za ključeve](/azure/key-vault/general/best-practices#turn-on-logging) za mogućnosti kontrole pristupa, sigurnosne kopije, revizije i oporavka.

## <a name="frequently-asked-questions"></a>Najčešća pitanja

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Mogu li uvidi u ciljne skupine zapisati tajne ili prebrisati tajne u sefu za ključeve?

Ne. Samo dozvole za čitanje i popisivanje navedene u odjeljku [odobrene dozvole](#permissions-granted-on-the-key-vault-to-audience-insights) u ovom članku odobrene su uvidima u ciljne skupine. Sustav ne može dodavati, brisati ili prepisivati tajne u sefu za ključeve. To je i razlog zašto ne možete unijeti vjerodajnice kada veza koristi sef za ključeve.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Mogu li promijeniti vezu s korištenja tajni sefa za ključeve na zadanu provjeru autentičnosti?

Ne. Ne možete se vratiti na zadanu vezu nakon što ste je konfigurirali s pomoću tajne iz povezanog sefa za ključeve. Stvorite zasebnu vezu i izbrišite staru ako vam više ne treba.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Kako mogu opozvati pristup sefu za ključeve za uvide u ciljne skupine?

Ovisno o tome je li omogućena opcija [Pravila pristupa sefu za ključeve](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ili [Kontrola pristupa za Azure temeljena na ulogama](/azure/key-vault/general/rbac-guide?tabs=azure-cli), morate ukloniti dozvole za upravitelja usluge`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` pod nazivom `Dynamics 365 AI for Customer Insights`. Sve veze koje koriste sef za ključeve prestat će raditi.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Tajna koja se koristi u vezi uklonjena je iz sefa za ključeve. Što mogu učiniti?

Obavijest se prikazuje u uvidima u ciljne skupine kada konfigurirana tajna iz sefa za ključeve više nije dostupna. Omogućite [privremeno brisanje](/azure/key-vault/general/soft-delete-overview) na sefu za ključeve radi vraćanja tajni ako su slučajno uklonjene.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Veza ne radi, ali moja tajna je u sefu za ključeve. Što bi mogao biti uzrok?

Obavijest se prikazuje u uvidima u ciljne skupine kada ne može pristupiti sefu za ključeve. Uzrok može biti:

- Uklonjene su dozvole za upravitelja usluge uvida u ciljne skupine. Potrebno ih je ručno obnoviti.

- Vatrozid na sefu za ključeve je omogućen. Vatrozid mora biti onemogućen kako bi sef za ključeve bio dostupan za uvide u ciljne skupine.
