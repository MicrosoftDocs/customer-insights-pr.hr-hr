---
title: Izvoz dijagnostičkih zapisnika (pretpregled)
description: Saznajte kako poslati zapisnike na Microsoft Azure Monitor.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: hr-HR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245916"
---
# <a name="export-diagnostic-logs-preview"></a>Izvoz dijagnostičkih zapisnika (pretpregled)

Prosljeđivanje zapisnika iz korisničkih uvida pomoću servisa Azure Monitor. Zapisnici resursa servisa Azure Monitor omogućuju vam praćenje i slanje zapisnika u [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) ili njihovo strujanje u [Azure Središta događaja](https://azure.microsoft.com/services/event-hubs/).

Customer Insights šalje sljedeće zapisnike događaja:

- **Događaji nadzora**
  - **APIEvent** - omogućuje praćenje promjena putem korisničkog Dynamics 365 Customer Insights sučelja.
- **Operativni događaji**
  - **WorkflowEvent** - omogućuje vam postavljanje [izvora](data-sources.md) podataka, objedinjavanje [,](data-unification.md)[obogaćivanje](enrichment-hub.md) i [izvoz](export-destinations.md) podataka u druge sustave. Ti se koraci mogu izvršiti pojedinačno (na primjer, pokrenuti jedan izvoz). Oni također mogu pokrenuti orkestrirano (na primjer, osvježavanje podataka iz izvora podataka koji pokreću proces ujedinjenja, koji će povući obogaćivanja i izvesti podatke u drugi sustav). Dodatne informacije potražite u shemi za otkrivanje tijeka [rada](#workflow-event-schema).
  - **APIEvent** - šalje sve API pozive instance klijenata u Dynamics 365 Customer Insights. Dodatne informacije potražite u [APIEvent shemi](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Postavljanje dijagnostičkih postavki

### <a name="prerequisites"></a>Preduvjeti

- Aktivna [pretplata na](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) Azure.
- [Administratorske](permissions.md#admin) dozvole u customer insights.
- [suradnik uloga](/azure/role-based-access-control/role-assignments-portal) administratora i administratora korisničkog pristupa na odredišnom resursu na servisu Azure. Resurs može biti Azure Data Lake Storage račun, središte događaja servisa Azure ili radni prostor azure Log Analytics. Ta je dozvola potrebna tijekom konfiguriranja dijagnostičkih postavki u customer insightsu, ali se može promijeniti nakon uspješnog postavljanja.
- [Ispunjeni su odredišni preduvjeti](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) za Azure Storage, Azure Event Hub ili Azure Log Analytics.
- Barem **Čitatelj** ulogu u grupi resursa kojoj resurs pripada.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Postavljanje dijagnostike pomoću servisa Azure Monitor

1. U odjeljku Customer Insights otvorite **Administratorski** > **sustav** i odaberite karticu **Dijagnostika**.

1. Odaberite **Dodaj odredište**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Dijagnostička veza.":::

1. Navedite naziv u **polju Naziv odredišta** dijagnostike.

1. Odaberite vrstu **resursa (račun za pohranu, središte događaja ili Analitika** zapisnika).

1. Odaberite pretplatu **,** grupu **resursa** i **resurs** za odredišni resurs. Informacije [o dozvolama i zapisivanju potražite u odjeljku Konfiguracija odredišnog resursa](#configuration-on-the-destination-resource).

1. [Pregledajte privatnost i usklađenost](connections.md#data-privacy-and-compliance) podataka i odaberite **Slažem se**.

1. Odaberite **Poveži se sa sustavom** da biste se povezali s odredišnim resursom. Zapisnici se počinju pojavljivati na odredištu nakon 15 minuta, ako se API koristi i generira događaje.

## <a name="configuration-on-the-destination-resource"></a>Konfiguracija odredišnog resursa

Na temelju vašeg izbora vrste resursa automatski se događaju sljedeće promjene:

### <a name="storage-account"></a>Račun za pohranu

Voditelj usluge Customer Insights dobiva **dozvolu za suradnik** računa za pohranu na odabranom resursu i stvara dva spremnika u odabranom prostoru naziva:

- `insight-logs-audit` koji sadržavaju **događaje revizije**
- `insight-logs-operational` koji sadrže operativne **događaje**

### <a name="event-hub"></a>Središte događaja

Upravitelj servisa Customer Insights dobiva **dozvolu vlasnika** podataka za Azure Središta događaja za resurs i stvara dva Središta događaja u odabranom prostoru naziva:

- `insight-logs-audit` koji sadržavaju **događaje revizije**
- `insight-logs-operational` koji sadrže operativne **događaje**

### <a name="log-analytics"></a>Log Analytics

Direktor usluge Customer Insights dobiva **dopuštenje za suradnik** log analyticsa za resurs. Zapisnici su dostupni u odjeljku **Upravljanje zapisnicima tablica** > **zapisnika** > **na** odabranom radnom prostoru Log Analyticsa. Proširite **rješenje za upravljanje zapisnicima** i pronađite tablice `CIEventsAudit` i `CIEventsOperational`.

- `CIEventsAudit` koji sadržavaju **događaje revizije**
- `CIEventsOperational` koji sadrže operativne **događaje**

**U prozoru Upiti proširite** rješenje nadzora **i** pronađite primjere upita koje pruža traženje `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Uklanjanje odredišta dijagnostike

1. Otvorite **Administratorski** > **sustav** i odaberite karticu **Dijagnostika**.

1. Na popisu odaberite odredište dijagnostike.

   > [!TIP]
   > Uklanjanje odredišta zaustavlja prosljeđivanje zapisnika, ali ne briše resurs na pretplati na Azure. Da biste izbrisali resurs u servisu Azure, odaberite vezu u stupcu **Akcije da biste otvorili** portal servisa Azure za odabrani resurs i tamo ga izbrisali. Zatim izbrišite odredište dijagnostike.

1. U stupcu **Akcije** odaberite ikonu **Izbriši**.

1. Potvrdite brisanje da biste uklonili odredište i zaustavili prosljeđivanje zapisnika.

## <a name="log-categories-and-event-schemas"></a>Evidentiraj kategorije i sheme događaja

Trenutno [su podržani događaji](apis.md) IPI-ja i događaji tijeka rada te se primjenjuju sljedeće kategorije i sheme.
Shema zapisnika slijedi uobičajenu shemu [Azure](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema) Monitora.

### <a name="categories"></a>Kategorije

Customer Insights nudi dvije kategorije:

- **Događaji** nadzora: [događaji](#api-event-schema) API-ja za praćenje promjena konfiguracije na usluzi. `POST|PUT|DELETE|PATCH` operacije ulaze u ovu kategoriju.
- **Operativni događaji**: [događaji](#api-event-schema) API-ja ili [događaji tijeka](#workflow-event-schema) rada generirani tijekom korištenja usluge.  Na primjer, `GET` zahtjevi ili događaji izvršenja tijeka rada.

## <a name="event-schemas"></a>Sheme događaja

Događaji API-ja i događaji tijeka rada imaju zajedničku strukturu, ali s nekoliko razlika. Dodatne informacije potražite u odjeljku [Shema događaja](#api-event-schema) API-ja ili [shema događaja tijeka](#workflow-event-schema) rada.

### <a name="api-event-schema"></a>Shema događaja API-ja

| Polje             | DataType  | Obavezno/neobavezno | Opis       | Primjer        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Podaci vremenske oznake | Obvezno          | Vremenska oznaka događaja (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Obvezno          | ResourceId instance koja je emitirala događaj         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Obvezno          | Naziv operacije predstavljene ovim događajem.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Obvezno          | Kategorija zapisnika događaja. Ili `Operational` ili `Audit`. Svi POST/PUT/PATCH/DELETE HTTP Zahtjevi su označeni sa `Audit`, sve ostalo s`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Obvezno          | Stanje događaja. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Neobavezno          | Stanje rezultata događaja. Ako operacija odgovara REST API pozivu, to je HTTP kod stanja.        | `200`             |
| `durationMs`      | Dugi      | Neobavezno          | Trajanje operacije u milisekundama.     | `133`     |
| `callerIpAddress` | String    | Neobavezno          | IP adresa pozivatelja, ako operacija odgovara API pozivu koji dolazi s javno dostupne IP adrese.                                                 | `144.318.99.233`         |
| `identity`        | String    | Neobavezno          | JSON objekt koji opisuje identitet korisnika ili aplikacije koja je izvršila operaciju.       | Pogledajte [odjeljak Identitet](#identity-schema).     |  
| `properties`      | String    | Neobavezno          | JSON objekt s više svojstava u određenu kategoriju događaja.      | Pogledajte [odjeljak Svojstva](#api-properties-schema).    |
| `level`           | String    | Obvezno          | Razina ozbiljnosti događaja.    | `Informational`, `Warning`, `Error` ili `Critical`.           |
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
| `Authorization.UserRole`      | Dodijeljena uloga korisniku ili aplikaciji. Dodatne informacije potražite u korisničkim [dozvolama](permissions.md).                                     |
| `Authorization.RequiredRoles` | Potrebne uloge za izvođenje operacije. `Admin` uloga je dopuštena za obavljanje svih operacija.                                                    |
| `Claims`                      | Potraživanja korisnika ili aplikacije JSON web token (JWT). Svojstva zahtjeva razlikuju se ovisno o organizaciji i konfiguraciji Azure Active Directory. |

#### <a name="api-properties-schema"></a>Shema svojstava API-ja

[Događaji API-ja](apis.md) imaju sljedeća svojstva.

| Polje                        | Opis                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Uvijek `ApiEvent`, označavajući događaj zapisnika kao API događaj.                                                                 |
| `properties.userAgent`       | Agent preglednika koji šalje zahtjev ili `unknown`.                                                                        |
| `properties.method`          | HTTP metoda:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Relativni put zahtjeva.                                                                                          |
| `properties.origin`          | URI koji pokazuje odakle dolazi dohvat ili `unknown`.                                                                  |
| `properties.operationStatus` | `Success` za HTTP kod stanja < 400 <br> `ClientError` za HTTP kod stanja < 500 <br> `Error` za HTTP status >= 500 |
| `properties.tenantId`        | ID organizacije                                                                                                        |
| `properties.tenantName`      | Naziv te tvrtke ili ustanove.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId pozivatelja.                                                                         |
| `properties.instanceId`      | Uvidi kupaca`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Shema događaja tijeka rada

Tijek rada sadrži više koraka. [Unos izvora](data-sources.md) podataka, [objedinjavanje](data-unification.md), [obogaćivanje](enrichment-hub.md) i [izvoz](export-destinations.md) podataka. Svi ti koraci mogu se izvoditi pojedinačno ili orkestrirano sljedećim procesima.

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
| AttributeMeasures | [Segmenti i mjere](segments.md)      |
| EntityMeasures    | [Segmenti i mjere](segments.md)      |
| Mjerila          | [Segmenti i mjere](segments.md)      |
| Segmentacija      | [Segmenti i mjere](segments.md)      |
| Obogaćivanje        | [Obogaćivanje](enrichment-hub.md)                                          |
| Intelligence      | [Predviđanja](predictions-overview.md)                                          |
| AiBuilder         | [Predviđanja](predictions-overview.md)                                          |
| Uvidi          | [Predviđanja](predictions-overview.md)                                          |
| Export            | [Izvozi](export-destinations.md)                                          |
| ModelManagement   | [Predviđanja](custom-models.md)                                           |
| Odnos      | [Objedinjavanje podataka](relationships.md)                                           |

#### <a name="field-description"></a>Opis polja

| Polje           | DataType  | Obavezno/neobavezno | Opis                                                                                                                                                   | Primjer                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Podaci vremenske oznake | Obvezno          | Vremenska oznaka događaja (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Obvezno          | ResourceId instance koja je emitirala događaj.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Obvezno          | Naziv operacije predstavljene ovim događajem. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Za referencu pogledajte [Vrste](#operation-types) operacija. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Obvezno          | Kategorija zapisnika događaja. Uvijek `Operational` za događaje tijeka rada                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Obvezno          | Stanje događaja. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Dugi      | Neobavezno          | Trajanje operacije u milisekundama.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Neobavezno          | JSON objekt s više svojstava u određenu kategoriju događaja.                                                                                        | Pogledajte svojstva tijeka rada [pododjeljka](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Obvezno          | Razina ozbiljnosti događaja.                                                                                                                                  | `Informational`, `Warning` ili `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Shema svojstava tijeka rada

Događaji tijeka rada imaju sljedeća svojstva.

| Polje              | Workflow | Zadatak | Opis            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Jest      | Jest  | Uvijek `WorkflowEvent` označite događaj kao događaj tijeka rada.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Jest      | Jest  | Identifikator pokretanja tijeka rada. Svi događaji toka posla i zadataka unutar izvršavanja toka posla imaju isti `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Jest      | Jest  | Identifikator operacije potražite u članku [Vrste](#operation-types) operacija.                                                                                                                                                                               |
| `properties.tasksCount`                      | Jest      | No   | Samo tijek rada. Broj zadataka koje tijek rada pokreće.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Jest      | No   | Nije obavezno. Samo događaji tijeka rada. ObjectId Azure Active Directory [korisnika](/azure/marketplace/find-tenant-object-id#find-user-object-id) koji je pokrenuo tijek rada, pogledajte i `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Jest      | No   | `full` ili `incremental` osvježiti.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Jest      | No   | `OnDemand` ili `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Jest      | No   | `Running` ili `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Jest      | Jest  | UTC vremenska oznaka`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Jest      | Jest  | UTC vremenska oznaka`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Jest      | Jest  | UTC vremenska oznaka`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Jest      | Jest  | Uvidi kupaca`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Jest  | - Za OperationType = `Export` identifikator je guid konfiguracije izvoza. <br> - Za OperationType = `Enrichment`, to je guid obogaćivanja <br> - Za OperationType `Measures` i `Segmentation` identifikator je naziv entiteta. |
| `properties.friendlyName`                    | No       | Jest  | Korisničko ime izvoza ili obrađenog entiteta.                                                                                                                                                                                           |
| `properties.error`                           | No       | Jest  | Nije obavezno. Poruka o pogrešci s više detalja.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Jest  | Nije obavezno. Samo za OperationType `Export`. Identificira vrstu izvoza. Dodatne informacije potražite [u pregledu izvoznih odredišta](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Jest  | Nije obavezno. Samo za OperationType `Export`. Sadrži popis konfiguriranih entiteta u izvozu.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Jest  | Nije obavezno. Samo za OperationType `Export`. Detaljna poruka za izvoz.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Jest  | Nije obavezno. Samo za OperationType `Segmentation`. Označava ukupan broj članova koje segment ima.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
