---
title: Izvoz podataka u SFTP domaćine (pretpregled) (sadrži videozapis)
description: Saznajte kako konfigurirati vezu i izvesti na SFTP lokaciju.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207220"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Izvoz podataka u SFTP domaćine (pretpregled)

Koristite svoje podatke o klijentima u aplikacijama trećih strana tako što ćete ih izvesti na lokaciju sigurnog protokola prijenosa datoteka (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Preduvjeti

- Dostupnost glavnog računala SFTP-a i odgovarajućih vjerodajnica.

## <a name="known-limitations"></a>Poznata ograničenja

- SFTP odredišta iza vatrozida trenutno nisu podržana.
- Vrijeme izvoza ovisi o performansama vašeg sustava. Preporučujemo dvije CPU jezgre i 1 Gb memorije kao minimalnu konfiguraciju vašeg poslužitelja.
- Do 100 milijuna korisničkih profila, što može potrajati 90 minuta kada se koristi preporučena minimalna konfiguracija dviju CPU jezgri i 1 Gb memorije.
- Ako za provjeru autentičnosti koristite SSH ključ, provjerite jeste li [privatni ključ](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) stvorili kao PEM ili SSH.COM format. Ako koristite Putty, pretvorite svoj privatni ključ izvozom kao Open SSH. Podržani su sljedeći oblici privatnih ključeva:
  - RSA u OpenSSL PEM i ssh.com formatu
  - DSA u OpenSSL PEM i ssh.com formatu
  - ECDSA 256/384/521 u OpenSSL PEM formatu
  - ED25519 i RSA u formatu ključa OpenSSH

## <a name="set-up-connection-to-sftp"></a>Postavljanje veze sa SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Admin** > **Veze**.

1. Odaberite **Dodaj vezu**, a zatim **SFTP**.

1. Dodijelite vezi prepoznatljivi naziv u polju **Zaslonski naziv**. Naziv i vrsta veze opisuju tu vezu. Preporučujemo odabir naziva koji objašnjava svrhu i cilj veze.

1. Odaberite tko može se može koristiti vezom. Prema zadanim postavkama to su samo administratori. Za više informacija pogledajte [Omogućavanje korištenja veze za izvoze suradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Odaberite želite li provjeriti autentičnost putem SSH-a ili korisničkog imena/lozinke za svoju vezu i navedite potrebne detalje. Ako za provjeru autentičnosti koristite SSH ključ, provjerite jeste li [privatni ključ](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) stvorili kao PEM ili SSH.COM format. Ako koristite Putty, pretvorite svoj privatni ključ izvozom kao Open SSH. Podržani su sljedeći oblici privatnih ključeva:
   - RSA u OpenSSL PEM i ssh.com formatu
   - DSA u OpenSSL PEM i ssh.com formatu
   - ECDSA 256/384/521 u OpenSSL PEM formatu
   - ED25519 i RSA u formatu ključa OpenSSH

1. Odaberite **Provjeri** da biste testirali vezu.

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Spremi** da biste završili vezu.

## <a name="configure-an-export"></a>Konfiguracija izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odjeljka SFTP. Ako nijedna veza nije dostupna, obratite se administratoru.

1. Unesite naziv izvoza.

1. Odaberite želite li izvesti svoje podatke **Komprimirane** ili **Nekomprimirane** i **graničnik polja** za izvezene datoteke.

1. Odaberite entitete, na primjer segmente, koje želite izvesti.

   > [!NOTE]
   > Svaki odabrani entitet bit će podijeljen u najviše pet izlaznih datoteka prilikom izvoza.

1. Odaberite **Spremi**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Izvoz entiteta koji sadrže veliku količinu podataka može dovesti do više CSV datoteka u istoj mapi za svaki izvoz. Podjela izvoza događa se iz razloga performansi kako bi se smanjilo vrijeme potrebno za dovršetak izvoza.

[!INCLUDE [footer-include](includes/footer-banner.md)]
