---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611123"
---
- **Izvedba** modela vježbanja: razredi A, B ili C označavaju izvedbu predviđanje i mogu vam pomoći u donošenju odluke o korištenju rezultata pohranjenih u izlaznom entitetu.

  Ocjene se određuju na temelju sljedećih pravila:
  - **A** kada je model točno predvidio najmanje 50% ukupnih predviđanja i kada je postotak točnih predviđanja za klijente koji su odustali veći od osnovne stope za najmanje 10%.
  - **B** kada je model točno predvidio najmanje 50% ukupnih predviđanja i kada je postotak točnih predviđanja za klijente koji su odustali do 10% veći od osnovne stope.
  - **C** kada je model točno predvidio manje od 50% ukupnih predviđanja ili kada je postotak točnih predviđanja za kupce koji su se bućkali manji od polazne vrijednosti.
  - **Polazna crta** uzima ulaz vremenskog prozora predviđanje za model (na primjer, godinu dana) i stvara različite dijelove vremena dijeleći ga s 2 dok ne dosegne mjesec dana ili manje. Koristi ove dijelove za stvaranje poslovnog pravila za klijente koji nisu kupovali u ovom vremenskom okviru. Smatra se da su ti klijenti odustali. Kao osnovni model odabrano je poslovno pravilo temeljeno na vremenu s najvećom sposobnošću predviđanja tko će vjerojatno bućkati.

- **Vjerojatnost gubitka (broj klijenata)**: Grupe klijenata na temelju njihovog predviđenog rizika da budu izgubljeni. Po želji stvorite [segmente kupaca](../prediction-based-segment.md) s visokim rizikom od bućkanja. Takvi segmenti pomažu vam da shvatite gdje bi trebao biti vaš prag za članstvo u segmentu.

- **Najutjecajniji faktori**: Mnogo je faktora koji se uzimaju u obzir prilikom izrade predviđanja. Svaki od čimbenika ima svoju važnost izračunatu za skupna predviđanja koja model stvara. Pomoću tih čimbenika provjerite predviđanje rezultate. Ili kasnije upotrijebite te podatke za [stvaranje segmenata](../prediction-based-segment.md) koji bi mogli utjecati na rizik za kupce.