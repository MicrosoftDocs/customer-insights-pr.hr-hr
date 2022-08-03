---
title: Izvoz segmenata u LiveRamp (pretpregled)
description: Saznajte kako konfigurirati vezu i izvesti u LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196707"
---
# <a name="export-segments-to-liverampreg-preview"></a>Izvoz segmenata u LiveRamp&reg; (pretpregled)

Aktivirajte svoje podatke u LiveRamp da biste se povezali s više od 500 platformi putem digitalnih i društvenih mreža te televizora. Radite sa svojim podacima na usluzi LiveRamp kako biste ciljali, suzbili i personalizirali oglasne kampanje.

## <a name="prerequisites"></a>Preduvjeti

- Pretplata na LiveRamp za korištenje ovog poveznika. Da biste se pretplatili, izravno [kontaktirajte LiveRamp](https://liveramp.com/contact/). [Saznajte više o usluzi LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Poznata ograničenja

- Izvoz LiveRamp koristi SFTP izvoz. SFTP odredišta iza vatrozida trenutno nisu podržana.
- Ako za provjeru autentičnosti koristite SSH ključ, provjerite jeste li [privatni ključ](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) stvorili kao PEM ili SSH.COM format. Ako koristite Putty, pretvorite svoj privatni ključ izvozom kao Open SSH. Podržani su sljedeći oblici privatnih ključeva:
  - RSA u OpenSSL PEM i ssh.com formatu
  - DSA u OpenSSL PEM i ssh.com formatu
  - ECDSA 256/384/521 u OpenSSL PEM formatu
  - ED25519 i RSA u formatu ključa OpenSSH
- Vrijeme izvoza ovisi o performansama vašeg sustava. Preporučujemo dvije CPU jezgre i 1 Gb memorije kao minimalnu konfiguraciju vašeg poslužitelja.
- Izvoz entiteta s do 100 milijuna profila klijenata može potrajati 90 minuta kada se koristi preporučena minimalna konfiguracija dviju CPU jezgri i 1 Gb memorije.
- Stvarni broj profila (ili podataka) koje možete izvesti na LiveRamp ovisi o vašoj pretplati na LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Postavljanje veze s LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **LiveRamp**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Odaberite želite li provjeriti autentičnost putem SSH-a ili korisničkog imena/lozinke za svoju vezu i navedite potrebne detalje.

1. Odaberite **Provjeri** da biste testirali vezu s uslugom LiveRamp.

1. Nakon uspješne [provjere pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka LiveRamp. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. **U polju Povezivanje podataka** odaberite **E-pošta**, **ime i adresa** ili **Telefon** koji želite poslati na LiveRamp radi rješavanja identiteta.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Poveznik LiveRamp s mapiranjem atributa.":::

1. Preslikajte odgovarajuće atribute iz entiteta *Klijent* za odabrani identifikator ključa.

1. Odaberite **Dodaj atribut** za mapiranje više atributa za slanje u LiveRamp.

   > [!TIP]
   > Ako pošaljete više atributa identifikatora ključa usluzi LiveRamp, vjerojatno ćete dobiti višu stopu podudaranja.

1. Odaberite segmente koje želite izvesti.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
