---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755535"
---
Nakon unosa podataka započnite postupak objedinjavanja podataka kako biste stvorili jedinstveni korisnički profil. Dodatne informacije potražite u odjeljku [Objedinjavanje podataka](../data-unification.md).

### <a name="select-source-fields"></a>Odabir izvorišnih polja

1. Nakon unosa podataka, mapirajte kontakte iz e-trgovine i podataka o vjernosti u uobičajene vrste podataka. Otvorite Objedinjavanje **podataka** > **·**.

1. Odaberite entitete koji predstavljaju profil klijenta – **Kontakti e-trgovine** i **Odani kupci**.

   ![objedinite izvore podataka o e-trgovini i vjernosti.](../media/unify-ecommerce-loyalty.png)

1. Odaberite **ContactId** kao primarni ključ za **eCommerceContacts** i **LoyaltyID** kao primarni ključ za **loyCustomers**.

1. Odaberite **Dalje**. Preskočite duplicirane zapise i odaberite **Dalje**.

### <a name="match-conditions"></a>Uskladi uvjete

1. Odaberite **e-trgovinaKontacts: e-trgovina** kao primarni entitet i uključite sve zapise.

1. Odaberite **loyCustomers: LoyaltyScheme i uključite sve zapise**.

1. Dodaj pravilo:
   - Odaberite **FullName** i za e-trgovineKontacts i za LoyCustomers.
   - Odaberite **Vrstu (telefon, ime, adresa, ...)** za **Normalizaciju**.
   - Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.
   - Unesite **FullName, E-pošta** za ime.

1. Dodajte drugi uvjet za adresu e-pošte:
   - Odaberite **E-pošta** i za e-trgovinekontakti i za loyCustomers.
   - Ostavite praznim polje Normaliziraj.
   - Postavite **Razina preciznosti**: **Osnovna** i **Vrijednost**: **Visoko**.

   ![objedinite pravilo podudaranja za naziv i e-poštu.](../media/unify-match-rule.png)

1. Odaberite **Gotovo**.

1. Odaberite **Dalje**.

### <a name="unify-fields"></a>Objedinjavanje polja

1. Preimenujte **contactid** za **loyCustomers** entitet u **ContactIdLOYALTY** da biste ga razlikovali od ostalih unesenih ID-ova.

1. Odaberite **Dalje** da biste pregledali, a zatim Odaberite **Stvori profile** kupaca.
