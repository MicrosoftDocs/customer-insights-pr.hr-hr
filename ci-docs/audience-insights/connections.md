---
title: Veze s ostalim uslugama iz Customer Insights.
description: Podijelite podatke s drugim uslugama.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3689c7016454ed44e22b4d4ff5a338836a8fe288
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605940"
---
# <a name="connections-preview-overview"></a>Pregled (pretpregled) veza

Veze su ključ za omogućavanje dijeljenja podataka s i iz Customer Insights. Svaka veza uspostavlja dijeljenje podataka s određenom uslugom. Veze su temelj za [konfiguriranje obogaćivanja treće strane](enrichment-hub.md) i [konfiguriranje izvoza](export-destinations.md). Ista veza može se koristiti više puta. Na primjer, jedna veza s Dynamics 365 Marketing funkcionira za više izvoza, a jedna veza Leadspace može se koristiti za nekoliko obogaćivanja.

Idite na **Admin** > **Veze** za stvaranje i pregled veza.

Kartica **Veze** prikazuje sve aktivne veze. Popis prikazuje redak za svaku vezu. 

Dobijte brzi pregled, opis i saznajte što možete učiniti sa svakom mogućnosti proširenja na kartici **Otkrij**.

### <a name="exports"></a>Izvozi

Samo administratori mogu konfigurirati nove veze, ali suradnicima mogu odobriti pristup korištenju postojećih veza. Administratori kontroliraju kamo podaci mogu ići, suradnici definiraju korisne podatke i frekvenciju u skladu sa svojim potrebama. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Obogaćivanja

Samo administratori mogu konfigurirati nove veze, ali stvorene veze uvijek su dostupne i administratorima i suradnicima. Administratori upravljaju vjerodajnicama i daju pristanak za prijenos podataka. Tada veze za obogaćivanja mogu koristiti i administratori i suradnici.

## <a name="add-a-new-connection"></a>Dodavanje nove veze

Da biste dodali veze, morate imati [administratorske dozvole](permissions.md). Ako se povežete s ostalim Microsoftovim uslugama, pretpostavljamo da su obje usluge u istoj tvrtki ili ustanovi.

1. Idite na **Admin** > **Veze (pretpregled)**.

1. Idite na karticu **Veze**.

1. Odaberite **Nova veza** da biste stvorili novu vezu. Na padajućem izborniku odaberite vrstu veze koju želite stvoriti.

1. U oknu **Postavi vezu** okno navedite potrebne pojedinosti. 
   1. **Zaslonski naziv** i vrsta veze opisuju vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj te veze.
   1. Točna polja ovise o tome na koju se uslugu povezujete. O pojedinostima određene vrste veze možete saznati u članku o ciljnoj usluzi.
   1. Ako [koristite vlastiti sef za ključeve](use-azure-key-vault.md) za pohranu tajni, aktivirajte **Upotrijebi sef za ključeve** i odaberite tajnu s popisa.

1. Da biste stvorili vezu, odaberite **Spremi**.

Možete odabrati i **Postavljanje** na pločici na kartici **Otkrivanje**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Omogućavanje korištenja veze za izvoze suradnicima

Kada postavljate ili uređujete vezu za izvoz, odabirete koji korisnici smiju koristiti tu određenu vezu za definiranje [izvoza](export-destinations.md). Prema zadanim postavkama veza je dostupna korisnicima s ulogom administratora. Ovu postavku možete promijeniti pod **Odaberi tko može koristiti ovu vezu** i dopustite korisnicima s ulogom suradnika da koriste ovu vezu.

- Suradnici neće moći pregledati ili urediti vezu. Vidjet će samo zaslonski naziv i njegovu vrstu prilikom stvaranja izvoza.
- Dijeljenjem veze dopuštate suradnicima korištenje veze. Suradnici će vidjeti dijeljene veze kada postave izvoze. Oni mogu upravljati svakim izvozom koji koristi ovu specifičnu vezu.
- Ovu postavku možete promijeniti zadržavajući izvoze koje su suradnici već definirali.

## <a name="edit-a-connection"></a>Uređivanje veze

1. Idite na **Admin** > **Veze (pretpregled)**.

1. Idite na karticu **Veze**.

1. Odaberite okomitu elipsu za vezu koju želite urediti.

1. Odaberite **Uredi**.

1. Promijenite vrijednosti koje želite ažurirati i odaberite **Spremi**.

## <a name="remove-a-connection"></a>Uklanjanje veze

Ako se veza koju uklanjate koristi za obogaćivanje ili izvoze, najprije ih morate odvojiti ili ukloniti. Dijaloški okvir za uklanjanje vodit će vas do relevantnih obogaćivanja ili izvoza. 

Odvojena obogaćivanja i izvozi postaju neaktivni. Ponovno ih aktivirate tako da im dodate drugu vezu na stranici [Obogaćivanja](enrichment-hub.md) ili [Izvozi](export-destinations.md).

1. Idite na **Admin** > **Veze (pretpregled)**.

1. Idite na karticu **Veze**.

1. Odaberite okomitu elipsu za vezu koju želite ukloniti.

1. Na padajućem popisu odaberite **Ukloni**. Pojavljuje se dijaloški okvir za potvrdu.

   1. Ako postoje obogaćivanja ili izvozi koji koriste ovu vezu, odaberite gumb da biste vidjeli što koristi vezu.
      - **Izvozi:** Možete odabrati da uklonite ili prekinete izvoze kako biste mogli ukloniti vezu. Da bi prekinuli izvoz, administratori mogu koristiti radnju **Prekini vezu**. Ova je radnja dostupna za pojedinačne i višestruko odabrane izvoze. Prekidanjem veze zadržavate konfiguraciju izvoza, ali ona se neće pokrenuti dok joj se ne doda druga veza.
      - **Obogaćivanja:** Možete odabrati da uklonite ili deaktivirate obogaćivanja kako biste mogli ukloniti vezu. 
   1. Kada veza više nema ovisnosti, vratite se na **Admin** > **Veze** i ponovno pokušajte ukloniti vezu.

1. Da biste potvrdili brisanje, odaberite **Ukloni**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Uspostavljanje veza s tajnama kojima upravlja vaš vlastiti sef za ključeve

Za neke veze potrebne su tajne poput API ključeva ili lozinki. Neke veze podržavaju tajne pohranjene u sefu za ključeve. Saznajte više o podržanim vezama i načinu postavljanja na [vlastiti sef za ključeve za uvide u ciljne skupine](use-azure-key-vault.md).
