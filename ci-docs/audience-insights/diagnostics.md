---
title: Nadzor Dynamics 365 Customer Insights pomoću nadzora servisa Azure
description: Saznajte kako poslati zapisnike na Microsoft Azure monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: d962c359d70a068fcf939b61e340f86de088b419
ms.sourcegitcommit: 0c3c473e0220de9ee3c1f1ee1825de0b3b3663c3
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920864"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Prijava prosljeđivanja Dynamics 365 Customer Insights pomoću Azure monitora (pretpregled)

Dynamics 365 Customer Insights omogućuje izravnu integraciju s Azure Monitorom. Zapisi resursa za nadzor platforme Azure omogućuju vam praćenje i slanje zapisnika u [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) ili njihovo strujanje na [Azure Središta događaja](https://azure.microsoft.com/services/event-hubs/).

Customer Insights šalje sljedeće zapisnike događaja:

- **Događaji nadzora**
  - **APIEvent** - omogućuje praćenje promjena putem Dynamics 365 Customer Insights UI-ja.
- **Operativni događaji**
  - **WorkflowEvent** - Tijek rada omogućuje postavljanje [izvora podataka,](data-sources.md)[ujedinjenje i](data-unification.md)[obogaćivanje](enrichment-hub.md) te konačno izvoz podataka u druge [sustave](export-destinations.md). Svi ti koraci mogu se provesti pojedinačno (npr. potaknuti jedan izvoz) ili orkestrirati (npr. osvježavanje podataka iz izvora podataka koji pokreću postupak ujedinjenja koji će povući dodatna obogaćivanja i nakon što se učine izvoz podataka u drugi sustav). Dodatne informacije potražite u [shemi workflowEvent](#workflow-event-schema).
  - **APIEvent** - svi API pozivi klijentima instanca na Dynamics 365 Customer Insights. Više detalja potražite u [APIEvent shemi](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Postavljanje dijagnostičkih postavki

### <a name="prerequisites"></a>Preduvjeti

Da biste konfigurirali dijagnostiku u uvidima u klijenta, moraju biti zadovoljeni sljedeći preduvjeti:

- Imate aktivnu pretplatu na [Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Imate [administratorske](permissions.md#administrator) dozvole u uvidima u klijenta.
- Na **·** **odredišnom** resursu na servisu Azure imate ulogu administratora suradnik i korisničkog pristupa. Resurs može biti račun za pohranu servisa Azure, središte događaja platforme Azure ili radni prostor analitike zapisnika platforme Azure. Dodatne informacije potražite [u članku Dodavanje i uklanjanje dodjela uloga servisa Azure pomoću portala Azure](/azure/role-based-access-control/role-assignments-portal).
- [Ispunjeni su odredišni](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) preduvjeti za Azure Storage, Azure Event Hub ili Azure Log Analytics.
- Imate barem **Čitatelj ulogu** u grupi resursa kojoj resurs pripada.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Postavljanje dijagnostike pomoću Azure monitora

1. U odjeljku Uvidi u klijente odaberite **Dijagnostika sustava** > **da biste vidjeli** dijagnostička odredišta konfigurirana za ovu instancu.

1. Odaberite **Dodaj odredište**.

   > [!div class="mx-imgBorder"]
   > ![Dijagnostička veza](media/diagnostics-pane.png "Dijagnostička veza")

1. Navedite naziv u **odredišnom polju Naziv** dijagnostike.

1. Odaberite **klijent** pretplate na Azure s odredišnim resursom i odaberite **prijava**.

1. Odaberite **vrstu resursa** (račun za pohranu, središte događaja ili analitika zapisnika).

1. Odaberite **Pretplatu** za odredišni resurs.

1. Odaberite **grupu Resurs** za odredišni resurs.

1. Izaberite **resurs**.

1. Potvrdite **izjavu o privatnosti i usklađenosti** podataka.

1. Odaberite **Poveži se sa** sustavom da biste se povezali s odredišnim resursom. Zapisnici se počinju pojavljivati na odredištu nakon 15 minuta, ako se API koristi i generira događaje.

### <a name="remove-a-destination"></a>Uklanjanje odredišta

1. Idite na **Dijagnostiku sustava** > **·**.

1. Odaberite odredište dijagnostike na popisu.

1. U **stupcu Akcije** odaberite **ikonu** Izbriši.

1. Potvrdite brisanje da biste zaustavili prosljeđivanje zapisnika. Resurs na pretplati na Azure neće se izbrisati. Možete odabrati vezu u **stupcu Akcije** da biste otvorili portal Azure za odabrani resurs i tamo ga izbrisali.

## <a name="log-categories-and-event-schemas"></a>Kategorije zapisnika i sheme događaja

Trenutno [su podržani API događaji](apis.md) i događaji tijeka rada i primjenjuju se sljedeće kategorije i sheme.
Shema zapisnika slijedi [zajedničku shemu Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorije

Customer Insights nudi dvije kategorije:

- **Revizijski događaji** : [API događaji](#api-event-schema) za praćenje promjena konfiguracije na usluzi. `POST|PUT|DELETE|PATCH` operacije ulaze u ovu kategoriju.
- **Operativni događaji** : [API događaji](#api-event-schema) ili događaji [tijeka rada](#workflow-event-schema) generirani tijekom korištenja usluge.  Na primjer, `GET` zahtjevi ili događaji izvršavanja tijeka rada.

## <a name="configuration-on-the-destination-resource"></a>Konfiguracija na odredišnom resursu

Na temelju vašeg izbora vrste resursa automatski će se primijeniti sljedeći koraci:

### <a name="storage-account"></a>Račun za pohranu

Direktor servisa Customer Insights dobiva **dozvolu za suradnik računa za** pohranu na odabranom resursu i stvara dva spremnika pod odabranim prostorom naziva:

- `insight-logs-audit` sadrži **revizijske događaje**
- `insight-logs-operational` koji sadrže **operativne događaje**

### <a name="event-hub"></a>Središte događaja

Voditelj servisa Customer Insights dobiva **dozvolu vlasnika podataka platforme Azure Središta događaja** za resurs i stvorit će dva Središta događaja u odabranom prostoru naziva:

- `insight-logs-audit` sadrži **revizijske događaje**
- `insight-logs-operational` koji sadrže **operativne događaje**

### <a name="log-analytics"></a>Analitika zapisnika

Direktor servisa Customer Insights dobiva **dozvolu za suradnik Log Analytics** za resurs. Zapisnici će biti dostupni u **odjeljku** > **Upravljanje zapisnikom tablica** > **zapisnika** zapisnika u odabranom radnom prostoru analitike zapisnika. Proširite **rješenje Upravljanje zapisnikom i** pronađite `CIEventsAudit` tablice i `CIEventsOperational`.

- `CIEventsAudit` sadrži **revizijske događaje**
- `CIEventsOperational` koji sadrže **operativne događaje**

U **prozoru Upiti** **proširite rješenje Nadzor** i pronađite primjere upita koje nudi traženje `CIEvents` sustava.

## <a name="event-schemas"></a>Sheme događaja

API događaji i događaji tijeka rada imaju zajedničku strukturu i detalje gdje se razlikuju, pogledajte [shemu DOGAĐAJA API-ja](#api-event-schema) ili [shemu događaja tijeka rada](#workflow-event-schema).

### <a name="api-event-schema"></a>Shema API događaja

| Polje             | Vrsta podataka  | Obavezno/neobavezno | Opis       | Primjer        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Podaci vremenske oznake | Obvezno          | Vremenska oznaka događaja (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Obvezno          | ID resursa instance koja je emitirala događaj         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Obvezno          | Naziv operacije koju predstavlja ovaj događaj.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Obvezno          | Kategorija zapisnika događaja. Ili `Operational``Audit`. Svi POST/PUT/PATCH/DELETE HTTP zahtjevi označeni su sa `Audit`, sve ostalo sa sustavom`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Obvezno          | Stanje događaja. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Neobavezno          | Stanje rezultata događaja. Ako operacija odgovara REST API pozivu, to je HTTP kod stanja.        | `200`             |
| `durationMs`      | Dugi      | Neobavezno          | Trajanje operacije u milisekundama.     | `133`     |
| `callerIpAddress` | String    | Neobavezno          | IP adresa pozivatelja, ako operacija odgovara API pozivu koji dolazi s javno dostupne IP adrese.                                                 | `144.318.99.233`         |
| `identity`        | String    | Neobavezno          | JSON objekt koji opisuje identitet korisnika ili aplikacije koja je obavila operaciju.       | Pogledajte [odjeljak](#identity-schema) Identitet.     |  |
| `properties`      | String    | Neobavezno          | JSON objekt s više svojstava u određenoj kategoriji događaja.      | Pogledajte [odjeljak](#api-properties-schema) Svojstva.    |
| `level`           | String    | Obvezno          | Razina ozbiljnosti događaja.    | `Informational`, `Warning` ili `Error``Critical`.           |
| `uri`             | String    | Neobavezno          | Apsolutni zahtjev URI.    |               |

#### <a name="identity-schema"></a>Shema identiteta

`identity` JSON objekt ima sljedeću strukturu

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Polje                         | Opis                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Dodijeljena uloga korisniku ili aplikaciji. Dodatne informacije potražite u [odjeljku Korisničke dozvole](permissions.md).                                     |
| `Authorization.RequiredRoles` | Potrebne uloge za operaciju. `Admin` uloga je dopuštena za obavljanje svih operacija.                                                    |
| `Claims`                      | Potraživanja korisnika ili aplikacije JSON web token (JWT). Svojstva zahtjeva razlikuju se ovisno o tvrtki ili ustanovi i Azure Active Directory konfiguraciji. |

#### <a name="api-properties-schema"></a>Shema svojstava API-ja

[API događaji](apis.md) imaju sljedeća svojstva.

| Polje                        | Opis                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Uvijek `ApiEvent` označite događaj zapisnika kao API događaj.                                                                 |
| `properties.userAgent`       | Agent preglednika šalje zahtjev ili `unknown`.                                                                        |
| `properties.method`          | HTTP metoda:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Relativni put zahtjeva.                                                                                          |
| `properties.origin`          | URI pokazuje odakle dolazi dohvat ili `unknown`.                                                                  |
| `properties.operationStatus` | `Success` za HTTP kod stanja < 400 <br> `ClientError` za HTTP kod stanja < 500 <br> `Error` za HTTP status >= 500 |
| `properties.tenantId`        | ID organizacije                                                                                                        |
| `properties.tenantName`      | Naziv organizacije.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId pozivatelja.                                                                         |
| `properties.instanceId`      | Uvidi u kupce`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Shema događaja tijeka rada

Tijek rada sadrži više koraka. [Uvezite izvore podataka](data-sources.md), [ujedinite](data-unification.md), [obogatite i](enrichment-hub.md)[izvezite](export-destinations.md) podatke. Svi ti koraci mogu se izvoditi pojedinačno ili orkestrirano sljedećim procesima. 

#### <a name="operation-types"></a>Vrste operacija

| OperationType     | Grupiraj                                     |
| ----------------- | ----------------------------------------- |
| Unos         | [Izvori podataka](data-sources.md)           |
| Usporedba podataka   | [Izvori podataka](data-sources.md)           |
| Mapa               | [Objedinjavanje podataka](data-unification.md)   |
| Usklađivanje             | [Objedinjavanje podataka](data-unification.md)   |
| Spoji             | [Objedinjavanje podataka](data-unification.md)   |
| ProfileStore      | [Profili klijenata](customer-profiles.md) |
| Traži            | [Profili klijenata](customer-profiles.md) |
| Aktivnost          | [Aktivnosti](activities.md)                  |
| AtributMeasures | [Segmenti i mjere](segments.md)      |
| EntityMeasures    | [Segmenti i mjere](segments.md)      |
| Mjerila          | [Segmenti i mjere](segments.md)      |
| Segmentacija      | [Segmenti i mjere](segments.md)      |
| Obogaćivanje        | [Obogaćivanje](enrichment-hub.md)                                          |
| Intelligence      | [Predviđanja](predictions-overview.md)                                          |
| AiBuilder         | [Predviđanja](predictions-overview.md)                                          |
| Uvidi          | [Predviđanja](predictions-overview.md)                                          |
| Export            | [Izvozi](export-destinations.md)                                          |
| ModelUpravljanje   | [Predviđanja](custom-models.md)                                           |
| Odnos      | [Objedinjavanje podataka](relationships.md)                                           |

#### <a name="field-description"></a>Opis polja

| Polje           | Vrsta podataka  | Obavezno/neobavezno | Opis                                                                                                                                                   | Primjer                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Podaci vremenske oznake | Obvezno          | Vremenska oznaka događaja (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Obvezno          | ID resursa instance koja je emitirala događaj.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Obvezno          | Naziv operacije koju predstavlja ovaj događaj. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Referencu [potražite u odjeljku Vrste](#operation-types) operacija. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Obvezno          | Kategorija zapisnika događaja. Uvijek `Operational` za događaje tijeka rada                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Obvezno          | Stanje događaja. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Dugi      | Neobavezno          | Trajanje operacije u milisekundama.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Neobavezno          | JSON objekt s više svojstava u određenoj kategoriji događaja.                                                                                        | Pogledajte [svojstva tijeka rada pododsječka](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Obvezno          | Razina ozbiljnosti događaja.                                                                                                                                  | `Informational`, `Warning` ili `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Shema svojstava tijeka rada

Događaji tijeka rada imaju sljedeća svojstva.

| Polje              | Workflow | Zadatak | Opis            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Jest      | Jest  | Uvijek `WorkflowEvent` označite događaj kao događaj tijeka rada.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Jest      | Jest  | Identifikator izvođenja tijeka rada. Svi događaji toka posla i zadataka unutar izvršavanja toka posla imaju isti `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Jest      | Jest  | Identifikator operacije potražite u odjeljku [Vrste operacija]. (vrste #operation)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Jest      | No   | Samo tijek rada. Broj zadataka koje pokreće tijek rada.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Jest      | No   | Nije obavezno. Samo događaji tijeka rada. Azure Active Directory [ID objekta korisnika](/azure/marketplace/find-tenant-object-id#find-user-object-id) koji je pokrenuo tijek rada potražite u odjeljku `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Jest      | No   | `full` ili `incremental` osvježiti.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Jest      | No   | `OnDemand` ili `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Jest      | No   | `Running` ili `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Jest      | Jest  | UTC vremenska oznaka`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Jest      | Jest  | UTC vremenska oznaka`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Jest      | Jest  | UTC vremenska oznaka`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Jest      | Jest  | Uvidi u kupce`instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Jest  | - Za OperationType = `Export`, identifikator je guid konfiguracije izvoza. <br> - Za OperationType = `Enrichment`, to je guid obogaćivanja <br> - Za OperationType `Measures` i, identifikator je naziv `Segmentation` entiteta. |
| `properties.friendlyName`                    | No       | Jest  | Korisnički naziv izvoza ili entiteta koji se obrađuje.                                                                                                                                                                                           |
| `properties.error`                           | No       | Jest  | Nije obavezno. Poruka o pogrešci s više detalja.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Jest  | Nije obavezno. Samo za `Export` OperationType. Identificira vrstu izvoza. Dodatne informacije potražite u [pregledu odredišta izvoza](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Jest  | Nije obavezno. Samo za `Export` OperationType. Sadrži popis konfiguriranih entiteta u izvozu.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Jest  | Nije obavezno. Samo za `Export` OperationType. Detaljna poruka za izvoz.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Jest  | Nije obavezno. Samo za `Segmentation` OperationType. Označava ukupan broj članova koje segment ima.                                                                                                                                                    |
