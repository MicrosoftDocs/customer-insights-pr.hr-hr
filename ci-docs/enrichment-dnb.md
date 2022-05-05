---
title: Obogaćivanje profila tvrtke Dun & Bradstreet
description: Opće informacije o obogaćivanju treće strane Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: hr-HR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653774"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Obogaćivanje profila tvrtke Dun & Bradstreet (pregled)

Dun & Bradstreet pruža komercijalne podatke, analitiku i uvide za tvrtke. Klijentima pruža objedinjene korisničke profile kako bi tvrtke obogatile svoje podatke. Obogaćivanja uključuju atribute kao što su DUNS broj, veličina tvrtke, lokacija, industrija i još mnogo toga.

## <a name="prerequisites"></a>Preduvjeti

Da biste konfigurirali obogaćivanje Dun & Bradstreeta, moraju se ispuniti sljedeći preduvjeti:

- Imate aktivnu [licencu Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- Imati [objedinjene korisničke profile](customer-profiles.md) za tvrtke.
- Vezu Dun & Bradstreet [konfigurira](connections.md) administrator. Možete ga stvoriti ako imate [administratorske](permissions.md#admin) dozvole i vjerodajnice tvrtke Dun & Bradstreet Connect. 

## <a name="setting-up-your-dun--bradstreet-project"></a>Postavljanje projekta Dun & Bradstreet

Kao licencirani korisnik Dun & Bradstreeta, možete postaviti projekt u [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). 


1. Prijavite se na [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Da biste dohvatili vjerodajnice, [vratite lozinku](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Preuzmite [našu csv datoteku](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) predloška koja će se koristiti za mapiranje polja publika uvida u odgovarajuća polja Dun & Bradstreet. 

1. Prenesite datoteku u koraku **prijenosa podataka** iskustva stvaranja projekta Dun & Bradstreet. 

1. Odaberite vodoravne točke ispod relevantnog **izvora** u novostvorenom projektu Dun & Bradstreet da biste vidjeli dostupne opcije.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Snimka zaslona točaka u projektu Dun & Bradstreet.":::

1. Odaberite **Dohvati detalje o** S3. Te podatke pohranite na sigurno mjesto. Trebat će vam za [postavljanje veze za obogaćivanje](#configure-a-connection-for-dun--bradstreet) u publika uvidima. 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Snimka zaslona odabira s3 informacija u projektu Dun & Bradstreet.":::



## <a name="configure-the-enrichment"></a>Konfiguracija za obogaćivanje

1. U uvidima u ciljnu skupinu idite u odjeljak **Podaci** > **Obogaćivanje**.

1. Odaberite **Obogati moje podatke** na pločici Dun & Bradstreet i odaberite **Započni.**

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Snimka zaslona pločice Dun & Bradstreet.":::

1. Odaberite [vezu](connections.md) s padajućeg popisa. Ako nijedna veza nije dostupna, obratite se administratoru. Ako ste administrator, možete stvoriti vezu. Odaberite **Dodaj vezu**, a zatim **Dun & Bradstreet**. 

1. Odaberite **Poveži se s Dun & Bradstreetom** da biste potvrdili vezu.

1. Odaberite **Dalje** i odaberite **customer skup podataka** želite obogatiti podacima tvrtke Dun & Bradstreet. Možete odabrati **entitet Kupac** da biste obogatili sve svoje profile kupaca ili odabrali entitet segmenta da biste obogatili samo jedinstvene profile kupaca sadržane u tom segmentu.

1. Odaberite **Dalje** i definirajte koja se polja iz vaših jedinstvenih profila koriste za traženje odgovarajućih podataka tvrtke tvrtke Dun & Bradstreet. Potrebna **su POLJA DUNS broj** ili **Naziv tvrtke** i **Država**. Polje zemlje podržava [dva ili tri slova kodova](https://www.iso.org/iso-3166-country-codes.html) zemlje, naziv države na engleskom jeziku, naziv zemlje na materinskom jeziku i prefiks telefona. Neke uobičajene varijante zemalja uključuju:

   * SAD: Sjedinjene Američke Države, Sjedinjene Američke Države, SAD, Amerika.
   * CA: Kanada.
   * GB: Ujedinjeno Kraljevstvo, Velika Britanija, Velika Britanija, GB, Ujedinjeno Kraljevstvo Velike Britanije i Sjeverne Irske, Ujedinjeno Kraljevstvo Velike Britanije.
   * AU: Australija, Zajednica Australije.
   * FR: Francuska, Francuska Republika.
   * DE: Njemačka, Njemačka, Deutschland, Allemagne, Savezna Republika Njemačka, Republika Njemačka.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Okno za mapiranje polja Dun & Bradstreet.":::

1. Odaberite **Sljedeće** da biste dovršili mapiranje polja.

1. Navedite naziv za obogaćivanje i odaberite **Spremi obogaćivanje** nakon pregledavanja svojih odabira.


## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfiguriranje veze za Dun & Bradstreet 

Morate biti administrator da biste konfigurirali veze. Odaberite **Dodaj vezu** prilikom konfiguriranja obogaćivanja *ili* Idite na **AdminConnections** > **·**, a zatim odaberite **Postavi** na pločici Dun & Bradstreet.

1. Odaberite **Početak rada**. 

1. Unesite naziv za vezu u dijaloški okvir **Zaslonski naziv**.

1. Navedite valjane vjerodajnice Dun & Bradstreet i detalje projekta *Dun & Bradstreet Regija, Put mape Drop i Naziv* mape Drop. Ove [informacije](#setting-up-your-dun--bradstreet-project) dobivate iz projekta Dun & Bradstreet.

1. Pregledajte i dajte svoj pristanak za **Privatnost podataka i usklađenost** odabirom opcije **Slažem se**.

1. Odaberi **Potvrdi** za provjeru valjanosti konfiguracije.

1. Nakon dovršetka provjere valjanosti odaberite **Spremi**.
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Stranica konfiguracije veze Dun & Bradstreet.":::

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon osvježavanja obogaćivanja, možete pregledati novoobogaćene podatke tvrtke pod [Moja obogaćivanja](enrichment-hub.md). Možete pronaći vrijeme posljednjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti odabirom **Prikaz obogaćenih podataka**.

## <a name="next-steps"></a>Sljedeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i sukladnost

Kada omogućite Dynamics 365 Customer Insights prijenos podataka u Dun & Bradstreet, dopuštate prijenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osjetljive podatke kao što su osobni podaci. Microsoft će prenijeti takve podatke prema vašim uputama, ali vi ste odgovorni za to da Dun & Bradstreet ispunjava sve obveze privatnosti ili sigurnosti koje možda imate. Dodatne informacije potražite u odjeljku [Microsoftova izjava o zaštiti privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš administrator usluge Dynamics 365 Customer Insights može ovo obogaćivanje ukloniti u bilo kojem trenutku kako bi se ta funkcija prestala upotrebljavati.


[!INCLUDE[footer-include](includes/footer-banner.md)]
