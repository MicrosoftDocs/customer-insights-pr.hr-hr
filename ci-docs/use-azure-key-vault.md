---
title: Povezivanje vlastitog sefa za ključeve platforme Azure (pretpregled)
description: Saznajte kako konfigurirati Customer Insights za korištenje vlastitog trezora ključeva servisa Azure za upravljanje tajnama.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246146"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Povezivanje vlastitog sefa za ključeve platforme Azure (pretpregled)

Povezivanje namjenskog [trezora](/azure/key-vault/general/basic-concepts) ključeva servisa Azure s okruženjem Customer Insights pomaže organizacijama da ispune zahtjeve usklađenosti.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Povezivanje trezora ključeva s okruženjem Customer Insights

Postavite namjenski trezor ključeva za pozornicu i koristite tajne u granici usklađenosti tvrtke ili ustanove.

### <a name="prerequisites"></a>Preduvjeti

- Aktivna pretplata na Azure.

- Administratorska [uloga](permissions.md#admin) dodijeljena [u](permissions.md#add-users) uvidima kupaca.

- [suradnik](/azure/role-based-access-control/built-in-roles#contributor) i [uloga administratora](/azure/role-based-access-control/built-in-roles#user-access-administrator) korisničkog pristupa u trezoru ključeva ili grupi resursa kojoj pripada trezor ključeva. Dodatne informacije potražite u odjeljku [Dodavanje ili uklanjanje dodjele uloga na platformi Azure putem portala Azure](/azure/role-based-access-control/role-assignments-portal). Ako u trezoru za ključeve nemate ulogu administratora korisničkog pristupa, postavite dozvole kontrole pristupa utemeljene na ulogama za upravitelj servisa Azure za Dynamics 365 Customer Insights zasebno. Slijedite korake kako biste [upotrijebili upravitelja usluge Azure](connect-service-principal.md) za sef za ključeve koji treba povezati.

- Trezor ključeva mora imati onemogućen vatrozid **key vaulta**.

- Trezor za ključeve nalazi se na istoj [lokaciji](https://azure.microsoft.com/global-infrastructure/geographies/#overview) servisa Azure kao i okruženje Customer Insights. U odjeljku Uvidi u korisnike otvorite **Administratorski** > **sustav** i karticu **O** programu da biste pogledali regiju okruženja.

### <a name="recommendations"></a>Preporuke

- [Koristite zaseban ili namjenski trezor ključeva](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) koji sadrži samo tajne potrebne za Customer Insights.

- Slijedite [najbolje prakse za korištenje sefa za ključeve](/azure/key-vault/general/best-practices#turn-on-logging) za mogućnosti kontrole pristupa, sigurnosne kopije, revizije i oporavka.

### <a name="link-a-key-vault-to-the-environment"></a>Povezivanje sefa za ključeve s okruženjem

1. Otvorite **Sigurnost administratora** > **·**, a zatim odaberite karticu Trezor **ključeva**.
1. Na pločici **Sef za ključeve** odaberite **Postavljanje**.
1. Odaberite **Pretplata**.
1. Odaberite sef za ključeve s padajućeg popisa **Sef za ključeve**. Ako je dostupno previše trezora ključeva, odaberite grupu resursa da biste ograničili rezultate pretraživanja.
1. Pregledajte [Zaštita privatnosti podataka i usklađenost](connections.md#data-privacy-and-compliance) i odaberite **Slažem se**.
1. Odaberite **Spremi**.

Pločica **Key Vault** prikazuje povezani naziv trezora ključeva, pretplatu i grupu resursa. Spremno je za upotrebu u postavljanju veze.
Pojedinosti o tome koja se dopuštenja za trezor za ključeve dodjeljuju uvidima u kupce potražite u odjeljku [Dozvole dodijeljene u trezoru ključeva](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Upotreba sefa za ključeve u postavljanju veze

Prilikom [postavljanja veza](connections.md) s [podržanim sustavima trećih strana](#supported-connection-types) koristite tajne iz povezanog trezora za ključeve da biste konfigurirali veze.

1. Idite na **Admin** > **Veze**.
1. Odaberite **Dodaj vezu**.
1. Za podržane vrste povezivanja dostupan je preklopni gumb **Upotrijebi sef za ključeve** ako ste povezali sef za ključeve.
1. Umjesto da ručno unesete tajnu, odaberite tajni naziv koji ukazuje na tajnu vrijednost u trezoru ključeva.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Okno za povezivanje s SFTP vezom koja koristi tajnu sefa za ključeve.":::

1. Odaberite **Spremi** da biste stvorili vezu.

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
| Tipka         | [Dohvati ključeve](/rest/api/keyvault/keys/get-keys/get-keys), [Dohvati ključ](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Tajno      | [Dohvati tajne](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Dohvati tajnu](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Certifikat | [Dohvati certifikate](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Dohvati certifikat](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Prethodne vrijednosti minimalne su za popis i čitanje tijekom izvođenja.

### <a name="azure-role-based-access-control"></a>Kontrola pristupa na Azure temeljena na ulogama

Uloge [korisnika Čitatelj i tajni key vaulta bit će dodane](/azure/key-vault/general/rbac-guide?tabs=azure-cli) za customer insights.

## <a name="frequently-asked-questions"></a>Najčešća pitanja

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Mogu li Customer Insights pisati tajne ili prebrisati tajne u trezor za ključeve?

Ne. Uvidima korisnika dodjeljuju se samo dozvole za čitanje i popis navedene [u](#permissions-granted-on-the-key-vault) dodijeljenim dozvolama. Sustav ne može dodavati, brisati ili prepisivati tajne u sefu za ključeve. To je i razlog zašto ne možete unijeti vjerodajnice kada veza koristi sef za ključeve.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Mogu li promijeniti vezu s korištenja tajni sefa za ključeve na zadanu provjeru autentičnosti?

Ne. Ne možete se vratiti na zadanu vezu nakon što ste je konfigurirali s pomoću tajne iz povezanog sefa za ključeve. Stvorite zasebnu vezu i izbrišite staru ako vam više ne treba.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Kako mogu opozvati pristup trezoru ključeva za Customer Insights?

Ako je omogućeno pravilo pristupa trezoru [ključeva](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ili [kontrola](/azure/key-vault/general/rbac-guide?tabs=azure-cli) pristupa utemeljena na ulogama servisa Azure, uklonite dozvole za upravitelja `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` servisa pod nazivom `Dynamics 365 AI for Customer Insights`. Sve veze koje koriste sef za ključeve prestat će raditi.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Tajna koja se koristi u vezi uklonjena je iz sefa za ključeve. Što mogu učiniti?

Obavijest se pojavljuje u customer insights kada konfigurirana tajna iz trezora ključeva više nije dostupna. Omogućite [privremeno brisanje](/azure/key-vault/general/soft-delete-overview) na sefu za ključeve radi vraćanja tajni ako su slučajno uklonjene.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Veza ne radi, ali moja tajna je u sefu za ključeve. Što bi mogao biti uzrok?

Obavijest se pojavljuje u customer insights kada ne može pristupiti trezoru ključeva. Uzrok može biti:

- Dozvole za upravitelja usluge Customer Insights uklonjene su. Potrebno ih je ručno obnoviti.

- Vatrozid na sefu za ključeve je omogućen. Vatrozid mora biti onemogućen kako bi trezor za ključeve ponovno bio dostupan uvidima u kupce.
