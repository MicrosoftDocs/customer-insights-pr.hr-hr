---
title: Pregled (pretpregled) veza
description: Veze s ostalim uslugama iz Customer Insights.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 4a0bc5dd4100b462a26660a0c51fda1fe92b6bb9
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195165"
---
# <a name="connections-preview-overview"></a>Pregled (pretpregled) veza

Veze su ključ za omogućavanje dijeljenja podataka s i iz Customer Insights. Svaka veza uspostavlja dijeljenje podataka s određenom uslugom. Veze su temelj za [konfiguriranje obogaćivanja treće strane](enrichment-hub.md) i [konfiguriranje izvoza](export-destinations.md). Ista veza može se koristiti više puta. Na primjer, jedna veza s Dynamics 365 Marketing funkcionira za više izvoza, a jedna veza Leadspace može se koristiti za nekoliko obogaćivanja.

Idite na **Admin** > **Veze** za stvaranje i pregled veza.

Kartica **Veze** prikazuje sve aktivne veze. Popis prikazuje redak za svaku vezu.

Dobijte brzi pregled, opis i saznajte što možete učiniti sa svakom mogućnosti proširenja na kartici **Otkrij**.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights prijenos podataka trećim stranama ili drugim Microsoftovim proizvodima, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenijeti takve podatke prema vašim uputima, ali vi ste odgovorni za to da treća strana ispunjava sve obveze zaštite privatnosti ili sigurnosti koje možda imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights može ukloniti vezu u bilo kojem trenutku kako bi prekinuo korištenje funkcije.

## <a name="exports"></a>Izvozi

Samo administratori mogu konfigurirati nove veze, ali suradnicima mogu odobriti pristup korištenju postojećih veza. Administratori kontroliraju kamo podaci mogu ići, suradnici definiraju korisne podatke i frekvenciju u skladu sa svojim potrebama. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](#allow-contributors-to-use-a-connection-for-exports).

## <a name="enrichments"></a>Obogaćivanja

Samo administratori mogu konfigurirati nove veze, ali stvorene veze uvijek su dostupne i administratorima i suradnicima. Administratori upravljaju vjerodajnicama i daju pristanak za prijenos podataka. Tada veze za obogaćivanja mogu koristiti i administratori i suradnici.

## <a name="add-a-new-connection"></a>Dodavanje nove veze

Da biste dodali veze, morate imati [administratorske dozvole](permissions.md). Ako se povežete s ostalim Microsoftovim uslugama, pretpostavljamo da su obje usluge u istoj tvrtki ili ustanovi.

1. Idite na **Admin** > **Veze (pretpregled)**.

1. Odaberite **Nova veza** da biste stvorili novu vezu. Na padajućem izborniku odaberite vrstu veze koju želite stvoriti.

1. U oknu **Postavi vezu** okno navedite potrebne pojedinosti.
   1. **Zaslonski naziv** i vrsta veze opisuju vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj te veze.
   1. Točna polja ovise o usluzi s kojom se povezujete. O pojedinostima određene vrste veze možete saznati u članku o ciljnoj usluzi.
   1. Ako [koristite vlastiti sef za ključeve](use-azure-key-vault.md) za pohranu tajni, aktivirajte **Upotrijebi sef za ključeve** i odaberite tajnu s popisa.

1. Da biste stvorili vezu, odaberite **Spremi**.

Možete odabrati i **Postavljanje** na pločici na kartici **Otkrivanje**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Omogućavanje korištenja veze za izvoze suradnicima

Kada postavljate ili uređujete vezu za izvoz, odabirete koji korisnici smiju koristiti tu određenu vezu za definiranje [izvoza](export-destinations.md). Prema zadanim postavkama veza je dostupna korisnicima s ulogom administratora. Ovu postavku možete promijeniti pod **Odaberi tko može koristiti ovu vezu** i dopustite korisnicima s ulogom suradnika da koriste ovu vezu.

- Suradnici neće moći pregledati ili urediti vezu. Oni će vidjeti samo zaslonsko ime i njezinu vrstu prilikom stvaranja izvoza.
- Dijeljenjem veze dopuštate suradnicima korištenje veze. Suradnici će vidjeti dijeljene veze kada postave izvoze. Oni mogu upravljati svakim izvozom koji koristi ovu specifičnu vezu.
- Ovu postavku možete promijeniti zadržavajući izvoze koje su suradnici već definirali.

## <a name="edit-a-connection"></a>Uređivanje veze

1. Idite na **Admin** > **Veze (pretpregled)**.

1. Idite na karticu **Veze**.

1. Odaberite okomitu trotočje (&vellip;) za vezu koju želite urediti.

1. Odaberite **Uredi**.

1. Promijenite vrijednosti koje želite ažurirati i odaberite **Spremi**.

## <a name="remove-a-connection"></a>Uklanjanje veze

Ako se veza koju uklanjate koristi obogaćivanjem ili izvozom, najprije je morate odvojiti ili ukloniti. Dijaloški okvir za uklanjanje vodit će vas do relevantnih obogaćivanja ili izvoza.

Odvojena obogaćivanja i izvozi postaju neaktivni. Ponovno ih aktivirate tako da im dodate drugu vezu na stranici [Obogaćivanja](enrichment-hub.md) ili [Izvozi](export-destinations.md).

1. Idite na **Admin** > **Veze (pretpregled)**.

1. Idite na karticu **Veze**.

1. Odaberite okomitu trotočje (&vellip;) za vezu koju želite ukloniti.

1. Na padajućem popisu odaberite **Ukloni**. Pojavljuje se dijaloški okvir za potvrdu.

   1. Ako postoje obogaćivanja ili izvozi koji koriste ovu vezu, odaberite gumb da biste vidjeli što koristi vezu.
      - **Izvozi:** Možete odabrati da uklonite ili prekinete izvoze kako biste mogli ukloniti vezu. Da bi prekinuli izvoz, administratori mogu koristiti radnju **Prekini vezu**. Ova je radnja dostupna za pojedinačne i višestruko odabrane izvoze. Prekidanjem veze zadržavate konfiguraciju izvoza, ali ona se neće pokrenuti dok joj se ne doda druga veza.
      - **Obogaćivanja:** Možete odabrati da uklonite ili deaktivirate obogaćivanja kako biste mogli ukloniti vezu.
   1. Kada veza više nema ovisnosti, vratite se na **Admin** > **Veze** i ponovno pokušajte ukloniti vezu.

1. Da biste potvrdili brisanje, odaberite **Ukloni**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Uspostavljanje veza s tajnama kojima upravlja vaš vlastiti sef za ključeve

Za neke veze potrebne su tajne poput API ključeva ili lozinki. Neke veze podržavaju tajne pohranjene u sefu za ključeve. Saznajte više o podržanim vezama i kako postaviti u vlastitom trezoru [ključeva za uvide u kupce](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
