---
title: Pregled (pretpregled) veza
description: Veze s ostalim uslugama iz Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245502"
---
# <a name="connections-preview-overview"></a>Pregled (pretpregled) veza

Veze su ključ za omogućavanje dijeljenja podataka s i iz Customer Insights. Svaka veza uspostavlja dijeljenje podataka s određenom uslugom. Koristite veze za konfiguriranje [obogaćivanja](enrichment-hub.md) drugih proizvođača i [konfiguriranje izvoza](export-destinations.md). Ista veza može se koristiti više puta. Na primjer, jedna veza s Dynamics 365 Marketing funkcionira za više izvoza, a jedna veza Leadspace može se koristiti za nekoliko obogaćivanja.

## <a name="export-connections"></a>Izvoz veza

Samo administratori mogu konfigurirati nove veze, ali mogu [odobriti pristup suradnicima](#allow-contributors-to-use-a-connection-for-exports) za korištenje postojećih veza. Administratori kontroliraju kamo podaci mogu ići, suradnici definiraju korisne podatke i frekvenciju u skladu sa svojim potrebama.

## <a name="enrichment-connections"></a>Veze s obogaćivanjem

Samo administratori mogu konfigurirati nove veze, ali stvorene veze uvijek su dostupne i administratorima i suradnicima. Administratori upravljaju vjerodajnicama i daju pristanak za prijenos podataka. Tada veze za obogaćivanja mogu koristiti i administratori i suradnici.

## <a name="add-a-new-connection"></a>Dodavanje nove veze

### <a name="prerequisites"></a>Preduvjeti

- [Dozvole administratora](permissions.md)
- Ostali Microsoftovi servisi, ako ih ima, nalaze se u istoj organizaciji

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu** i odaberite vrstu veze koju želite stvoriti. Ili idite na karticu **Otkrivanje** i odaberite **Postavi** na pločici veze.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Unesite potrebne detalje. Točna polja ovise o usluzi s kojom se povezujete. Pojedinosti o određenoj vrsti veze potražite u članku o ciljnoj usluzi.

1. Ako [koristite vlastiti sef za ključeve](use-azure-key-vault.md) za pohranu tajni, aktivirajte **Upotrijebi sef za ključeve** i odaberite tajnu s popisa.

1. Pregledajte privatnost i usklađenost podataka i odaberite **Slažem se**.

1. Odaberite **Spremi** da biste stvorili vezu.

### <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights prijenos podataka trećim stranama ili drugim Microsoftovim proizvodima, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenijeti takve podatke prema vašim uputima, ali vi ste odgovorni za to da treća strana ispunjava sve obveze zaštite privatnosti ili sigurnosti koje možda imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights može ukloniti vezu u bilo kojem trenutku kako bi prekinuo korištenje funkcije.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Omogućavanje korištenja veze za izvoze suradnicima

Prilikom postavljanja ili uređivanja izvozne veze odaberite koji korisnici smiju koristiti ovu vezu za definiranje [izvoza](export-destinations.md). Prema zadanim postavkama, veza je dostupna korisnicima s administratorskom ulogom. Promijenite postavku Odaberi **tko može koristiti ovu vezu** da biste korisnicima s suradnik ulogom omogućili korištenje ove veze.

- Suradnici neće moći pregledati ili urediti vezu. Oni će vidjeti samo zaslonsko ime i njezinu vrstu prilikom stvaranja izvoza.
- Dijeljenjem veze dopuštate suradnicima korištenje veze. Suradnici će vidjeti dijeljene veze kada postave izvoze. Oni mogu upravljati svakim izvozom koji koristi ovu specifičnu vezu.
- Ovu postavku možete promijeniti zadržavajući izvoze koje su suradnici već definirali.

## <a name="manage-existing-connections"></a>Upravljanje postojećim vezama

1. Idite na **Admin** > **Veze**.

1. Odaberite karticu **Obogaćenje** ili **Izvoz** da biste vidjeli popis veza za obogaćivanje ili izvoz, vrstu veze, prilikom stvaranja i tko ima pristup. Popis veza možete sortirati po bilo kojem stupcu.

1. Odaberite vezu da biste vidjeli dostupne akcije.

   - **Uredite** vezu.
   - [**Uklonite**](#remove-a-connection) vezu.

### <a name="remove-a-connection"></a>Uklanjanje veze

Ako se veza koju uklanjate koristi obogaćivanjem ili izvozom, najprije je odvojite ili uklonite. Dijaloški okvir uklanjanje vodi vas do odgovarajućih obogaćivanja ili izvoza.

> [!TIP]
> Deaktivirana obogaćivanja i odvojeni izvoz postaju neaktivni. Ponovno ih aktivirate tako da im dodate drugu vezu na stranici [Obogaćivanja](enrichment-hub.md) ili [Izvozi](export-destinations.md).

1. Idite na **Admin** > **Veze**.

1. Odaberite karticu **Obogaćivanje** ili **Izvoz**.

1. Odaberite vezu koju želite ukloniti.

1. Na padajućem popisu odaberite **Ukloni**. Pojavljuje se dijaloški okvir za potvrdu.

   1. Ako postoje obogaćivanja ili izvozi koji koriste ovu vezu, odaberite gumb da biste vidjeli što koristi vezu.
      - **Izvoz:** Odaberite ukloni **izvoz** ili **Odvoji vezu**. Odvajanjem veze zadržava se konfiguracija izvoza, ali ona se neće izvoditi dok joj se ne doda druga veza.
      - **Obogaćivanja:** Odaberite **brisanje** ili **deaktiviranje** obogaćenja.
   1. Kada veza više nema ovisnosti, vratite se na **Admin** > **Veze** i ponovno pokušajte ukloniti vezu.

1. Da biste potvrdili brisanje, odaberite **Ukloni**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Uspostavljanje veza s tajnama kojima upravlja vaš vlastiti sef za ključeve

Za neke veze potrebne su tajne poput API ključeva ili lozinki. Neke veze podržavaju tajne pohranjene u sefu za ključeve. Saznajte više o podržanim vezama i kako postaviti u vlastitom trezoru [ključeva za uvide u kupce](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
